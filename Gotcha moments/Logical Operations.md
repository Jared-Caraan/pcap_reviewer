1. **The Core Logic: Short-Circuiting**

    Python doesn't just return `True` or `False`. It returns the actual value that determined the outcome of the expression.
  
    | Operator | Rule | Practical Result |
    | -------- | ---- | ---------------- |
    | `and` | Returns the **first falsy** value it finds. | If all are truthy, it returns the **last** value. |
    | `or` | Returns the **first truthy** value it finds. | If all are falsy, it returns the **last** value. |
<hr>

2. **What is "Falsy"?**

    To predict the result, you just need to know what Python considers "False." Everything else is "Truthy."
    
    - **Falsy:** `0`, `None`, `False`, `""` (empty string), `[]` (empty list), `{}` (empty dict).
    - **Truthy:** `15`, `22`, `"Hello"`, `[1, 2]`, and any other non-empty object.
<hr>

3. **Order of Operations (Precedence)**

    When you mix them together, Python follows a specific hierarchy, much like PEMDAS in mathematics:
    
      1. `not` (Highest priority)
      2. `and`
      3. `or` (Lowest priority)

  > [!TIP]
  > Always use **parentheses** `()` when mixing `and` and `or`. It prevents logic errors and makes your code much easier for others (and future you) to read.
<hr>

4. **Comparison Table**

   | Expression | Step-by-Step | Result |
   | ---------- | ------------ | ------ |
   | `15 and 22`     | `15` is truthy $\rightarrow$ move to `22`    | `22`   |
   | `or`            | Returns the **first truthy** value it finds. | `15`   |
   | `0 and 5`       | `0` is falsy $\rightarrow$ stop immediately  | `0`    |
   | `0 or None`     | `0` is falsy $\rightarrow$ move to `None`    | `None` |
   | `5 or 0 and 10` | Evaluates `(0 and 10)` first, then `5 or 0`  | `5`    |
