## Bit Negate

In bitwise terms, "negating" a bit usually means **toggling** it—flipping a `1` to a `0` or a `0` to a `1`. To do this with shifts, we use the **Bitwise XOR** operator (`^`).

The XOR operator (Exclusive OR) returns `1` only if the two bits are different. Therefore, if you XOR a bit with `1`, it always flips its state.
<hr>

### The Toggle (Negate) Formula

To toggle the $`n^{th}`$ bit of a number:

```python
def toggle_bit(number, index):
    # Create a mask with a 1 at the target position
    mask = 1 << index
    
    # Use XOR to flip the bit at that position
    return number ^ mask
```

**How it Works (Step-by-Step)**

Let's use the number **10** (`1010` in binary) and toggle the bit at **index 1**.

1. **Shift:** `1 << 1` gives us the mask `0010`.
2. **XOR (`^`):**
   - `1010` (Original 10)
   - `0010` (Mask)
   - `----`
   - `1000` (Result: 8)
   - _Notice the second bit flipped from 1 to 0._

If we ran the same operation again on the result (**8**):

- `1000` (Current 8)
- `0010` (Mask)
- `----`
- `1010` (Result: 10)
The bit flipped back from 0 to 1.
