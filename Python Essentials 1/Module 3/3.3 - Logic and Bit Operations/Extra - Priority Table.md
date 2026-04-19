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

<ins>Unary and Exponentiation</ins>

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

<ins>Negative Binaries</ins>

To understand why `-18 | 5` equals `-17`, we have to look at how computers represent negative numbers using Two's Complement and how the Bitwise OR (|) operator interacts with the "sign bit."
