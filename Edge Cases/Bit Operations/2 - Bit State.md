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

| Index     | Binary Value | Operation       | Result |
| --------- | ------------ | --------------- | ------ |
| **Bit 0** | `0001`       | `13 & (1 << 0)` | `1`    |
| **Bit 1** | `0010`       | `13 & (1 << 1)` | `0`    |
| **Bit 2** | `0100`       | `13 & (1 << 2)` | `4`    |
| **Bit 3** | `1000`       | `13 & (1 << 3)` | `8`    |
<hr>

### Alternative: Using `bin()` or Bit Length

If you prefer working with strings (though it's slower and less "Pythonic" for logic), you can convert the number to a binary string:

```python
number = 13
binary_string = bin(number) # Result: '0b1101'

# Check if the 2nd bit from the right is '1'
# Note: String indexing is left-to-right, binary is right-to-left!
is_set = binary_string[-3] == '1'
```

**Modern Python (3.10+)**

If you are working with large integers and want to know how many bits are required to represent the number, you can use:

- `int.bit_count()`: Returns the number of ones (set bits).
- `int.bit_length()`: Returns the number of bits required to represent the integer in binary, excluding the sign and leading zeros.
