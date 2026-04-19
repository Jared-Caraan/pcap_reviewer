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
