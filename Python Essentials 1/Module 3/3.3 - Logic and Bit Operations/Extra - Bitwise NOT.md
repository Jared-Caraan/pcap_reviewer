### Bitwise NOT (`~`)

```python
x = 4
c = ~x
```

Bitwise operations can definitely feel like a "brain teaser" until you look at the binary digits (bits) behind the numbers. In the code you shared, $`x = 4`$. In binary, the number 4 is represented as `100`.
<hr>

### Variable c = ~x (The Bitwise NOT)

This one is "tricky" for a good reason. The `~` operator is the bitwise complement (NOT). It flips every `0` to a `1` and every `1` to a `0`.

1. **Binary Flip:** Python integers are signed, meaning they use **Two’s Complement** representation. For a positive 4, the bits are inverted.
2. **The Rule of Thumb:** For any integer $n$, the bitwise NOT result is always $-(n + 1)$.
3. **The Math:** $$~(4) = -(4 + 1) = -5$$

That is why the output is **-5**.
