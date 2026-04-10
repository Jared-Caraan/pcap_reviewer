## Bit State

Checking the state of a specific bit in Python is a classic bitwise operation. Since Python integers have arbitrary precision, you can think of them as an infinite string of binary digits.

To check if a specific bit is "on" (1) or "off" (0), you use the Bitwise AND operator (`&`) combined with a Left Shift (`<<`).

### The Standard Method

The most common way to check the $`n^{th}`$ bit (starting from 0 for the rightmost bit) is:

```python
def check_bit(number, index):
    # Shift 1 to the left by 'index' positions, then AND it with 'number'
    mask = 1 << index
    return (number & mask) != 0
```

**How it Works**
1. **Shift:** `1 << index` creates a "mask" where only the bit at the target position is 1.
2. **AND:** The `&` operator compares the bits of your number and the mask. If both have a 1 at that position, the result is non-zero.
3. **Evaluate:** If the result is greater than 0, the bit is set (1). If the result is 0, the bit is unset (0).
<hr>

### Quick Examples

Let’s look at the number **13**, which is `1101` in binary.
