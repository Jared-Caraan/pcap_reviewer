## Priority Table

| Priority | Operator |   |   |
| -------- | -------- | - | - |
| 1  | `~`, `+`, `-`                                                       | unary  | unary operator       |
| 2  | `**`                                                                |        | exponentiation       |
| 3  | `*`, `/`, `//`, `%`                                                 |        | mult, divs, modulo   |
| 4  | `+`, `-`                                                            | binary | add/subtract         |
| 5  | `<<`, `>>`                                                          |        | bitwise shifts       |
| 6  | `<`, `<=`, `>`, `>=`                                                |        | relational operators |
| 7  | `==`, `!=`                                                          |        | equality operators   |
| 8  | `&`                                                                 |        | bitwise AND          |
| 9  |  `\|`                                                               |        | bitwise OR           |
| 10 | `=`, `+=`, `-=`, `*=`, `/=`, `%=`, `&=`, `^=`, `\|=`, `>>=`, `<<=`  |        | assignment operators |

### Examples

**Mixed Arithmetic and Bitwise**
```python
x = 10
x += ~2 ** 3 << 1 | 5
```

**Breakdown of logic:**

1. **Exponentiation (`**`):** `2 ** 3 = 8`
2. **Unary (`~`):** `~8 = -9`
3. **Bitwise Shift (`<<`):** `-9 << 1 = -18`
4. **Bitwise OR (`|`):** `-18 | 5` (In binary: `...101110 | ...000101`)
5. **Assignment (`+=`):** Add the result to the initial `x`.
6. **Answer**: `-7`

**Notes:**

<details>
<summary>Unary and Exponentiation</summary>
<br>
A very common point of confusion! Looking at the priority table, it might seem like **unary operators** (Priority 1) should always beat **exponentiation** (Priority 2). However, there is a specific rule in Python regarding how the unary operator interacts with the exponentiation operator when it's on the left side.

In the expression `~2 ** 3`:

1. **The Rule:** Python’s power operator `**` binds more tightly than unary operators on its `left`.
2. **The Logic:** Even though unary is technically "higher" in the general list, the language spec treats `-x ** y` as `-(x ** y)` and `~x ** y` as `~(x ** y)`.
3. **The Result:** First, it calculates `2 ** 3 = 8`.
   - Then, it applies the bitwise NOT: `~8`.
   - If the code were `(~2) ** 3`, the result would be very different ($`-3^3 = -27`$).

**Why does this happen?**

This behavior mimics standard mathematical notation. In math, if you write $`-2^3`$, you almost always mean $`-(2^3) = -8`$, rather than $`(-2)^3`$. Python follows this convention to keep its math intuitive for scientists and engineers.

<ins>Bit Shifting "Unlike" Terms</ins>

1. **Left Shift: Negative << Positive = Negative**

   In Python, the left shift (`<<`) is mathematically equivalent to:

   $`result = x \times 2^n`$

   Since you are multiplying a negative number by a positive power of 2, the result stays negative.

   - **Example:** `-5 << 2`
   - **Calculation:** $`-5 \times 2^2 = -5 \times 4 = -20`$.

2. **Right Shift: Negative >> Positive = Negative**

   Python uses **arithmetic right shifts** for signed integers. This means it "fills" the new empty slots on the left with the sign bit (1 for negative numbers).

   Rule: A negative number shifted right stays negative (it eventually becomes -1 if you shift it enough).

   Example: `-10 >> 1` results in `-5`.

3. **How Python Sees "Negative" Bits**

   Python handles integers as having an infinite number of sign bits (Two's Complement).
   - Positive numbers are preceded by infinite `0`s.
   - Negative numbers are preceded by infinite `1`s.

**Summary of "Unlike" Bitwise Logic**

| Operation              | Input A  | Input B  | Result Sign                                                                         |
| ---------------------- | -------- | -------- | ----------------------------------------------------------------------------------- |
| **Left Shift (`<<`)**  | Negative | Positive | **Negative**                                                                        |
| **Right Shift (`>>`)** | Negative | Positive | **Negative**                                                                        |
| **Bitwise AND (`&`)**  | Negative | Positive | **Positive** (The infinite `0`s in the positive number mask out the infinite `1`s). |
| **Bitwise OR (`\|`)**  | Negative | Positive | **Negative** (The infinite `1`s in the negative number "win").                      |

</details>

<details>
<summary>Negative Binaries using OR</summary>
<br>
To understand why `-18 | 5` equals `-17`, we have to look at how computers represent negative numbers using Two's Complement and how the Bitwise OR (|) operator interacts with the "sign bit."

1. Representing the Numbers in Binary

   In Python, negative numbers are treated as if they have an infinite string of `1`s to the left (the sign bits).

   - **Positive 5:** In binary, this is `00000101`.
   - **Negative 18:** To get `-18`, we start with `18` (`00010010`), flip the bits, and add `1`.
      - `18` is ...`00010010`
      - `-18` becomes `...11101110` (Notice the infinite leading 1s).

2. **Applying the Bitwise OR (`|`)**
   
   The OR operator compares each bit and returns `1` if **at least one** of the bits is `1`.

   ```
     -18:  ... 1 1 1 0 1 1 1 0  (Infinite 1s to the left)
   |   5:  ... 0 0 0 0 0 1 0 1  (Infinite 0s to the left)
   ---------------------------
   Result: ... 1 1 1 0 1 1 1 1
   ```

3. **Converting the Result Back**

   Now we look at our result: `...11101111`. Because it has leading `1`s, we know it is a negative number. To find out which one:
   1. **Flip the bits:** `...00010000`
   2. **Add 1:** `...00010001`
   3. The result of the conversion is **17**.

   Since the original result had leading `1`s, the final value is **-17**.
   
</details>

<details>
<summary>Negative Binaries using AND</summary>
<br>
When you use the **Bitwise AND** (`&`) operator, the logic changes completely. Instead of "filling in" bits like the OR operator does, the AND operator is very "picky"—it only returns `1` if **both** bits are `1`.

This makes it a "masking" operator. Because a positive number like `5` has infinite `0`s to its left, it effectively "kills" all the infinite `1`s of the negative number.

1. **The Binary Alignment**

   Let's line them up again using Two's Complement:
   - **-18:** `...11111111101110` (The "infinite 1s" represent the negative sign).
   - **5:** `...00000000000101` (The "infinite 0s" represent the positive sign).

   ```
     -18:  ... 1 1 1 1 1 1 1 0 1 1 1 0
   &   5:  ... 0 0 0 0 0 0 0 0 0 1 0 1
   -----------------------------------
   Result: ... 0 0 0 0 0 0 0 0 0 1 0 0
   ```

2. **Evaluating the Result**

   Look at the result: `...00000100`.
   
   1. The leading bits are all `0`s, which means the result is **positive**.
   2. The binary `100` is equal to **4** in decimal.

   So, **-18 & 5 = 4**.
   
</details>
<hr>

**Relational and Logical Priority**

```python
result = 5 + 3 * 2 > 10 == True != 0
```

**Breakdown of logic:**

1. Multiplication (`*`): `3 * 2 = 6`
2. Addition (`+`): `5 + 6 = 11`
3. Relational (`>`): `11 > 10` is `True`.
4. Equality (`==`, `!=`): Note how Python handles "chained comparisons" (e.g., `A == B != C`).
5. **Answer**: `False`

**Notes:**

<details>
<summary>Comparison Chaining</summary>
<br>
   
In Python, comparisons like `A > B == C != D` are "chained." Python evaluates them as a series of pairs joined by an implicit `and`.

The expression is actually evaluated as:

$`(11 > 10) \text{ and } (10 == \text{True}) \text{ and } (\text{True} != 0)`$

**Evaluate the Pairs**

1. `11 > 10`: This is `True`.
2. `10 == True`: In Python, `True` has a numeric value of `1`. Since `10 == 1`, this is `False`.
3. `True != 0`: Since `True` is `1`, and `1 != 0`, this is `True`.

**The Final Result**

Now we combine them with the implicit `and`:

$`\text{True and False and True} = \mathbf{False}`$
<hr>

Many students expect it to be `True` because they assume the code evaluates left-to-right like this: `((11 > 10) == True) != 0`. If Python worked that way, it would be:

1. `(11 > 10)` $`\rightarrow`$ `True`
2. `(True == True)` $`\rightarrow`$ `True`
3. `(True != 0)` $`\rightarrow`$ `True`

But because of **Comparison Chaining**, the `10 == True` part fails, making the whole chain `False`.
</details>

<details>
<summary>Comparison Chaining Occurrence</summary>
<br>

In Python, comparison chaining occurs when you have **two or more comparison operators** following each other in a single expression.

While it feels like the expression is being evaluated from left to right, Python is actually transforming the expression behind the scenes using an implicit `and`.

1. Which operators can be chained?

   It is strictly for **Relational** and **Equality** operators (Priorities 6 and 7 in the priority table), as well as the **Membership** and **Identity** operators.

   The complete list of operators that support chaining is:
   - **Relational:** `<`, `<=`, `>`, `>=`
   - **Equality:** `==`, `!=`
   - **Membership:** `in`, `not in`
   - **Identity:** `is`, `is not`

2. How the Transformation Works

   If you write `a < b == c`, Python treats it as:

   $`(a < b) \text{ and } (b == c)`$

   The key benefit here is that the middle expression (`b`) is **only evaluated once**. This is important if `b` is a function call or a complex calculation; it prevents the code from running that function twice.

3. What CANNOT be chained?

   You cannot chain **Arithmetic**, **Bitwise**, or **Assignment** operators in this same logical "and" fashion.
   - **Arithmetic:** `5 + 3 + 2` is just a sequence of additions ($`8 + 2 = 10`$). It doesn't become `(5 + 3) and (3 + 2)`.
   - **Bitwise:** `x & y | z` follows strict priority order (AND before OR) rather than chaining pairs.
   - **Assignments:** While you can do `x = y = z = 0` (setting all three to zero), this is called **multiple assignment**, which works differently than comparison chaining. It assigns the value on the far right to all variables on the left.

A "Tricky" Example

Consider this expression:

```python
1 < 2 < 3 > 2
```

Python breaks this down as:

$`(1 < 2) \text{ and } (2 < 3) \text{ and } (3 > 2)`$

Since **True and True and True** results in **True**, the whole thing is True.

If even one of those links were false—for example, if you changed it to `1 < 2 < 3 > 5`—the whole result would immediately become **False**.
</details>
