## Priority Table

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

A very common point of confusion! Looking at the priority table, it might seem like unary operators (Priority 1) should always beat exponentiation (Priority 2). However, there is a specific rule in Python regarding how the unary operator interacts with the exponentiation operator when it's on the left side.
