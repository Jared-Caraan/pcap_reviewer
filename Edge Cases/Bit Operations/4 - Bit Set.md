## Bit Set

To **set** a bit (forcing a specific bit to become `1` regardless of its current state), we use the **Bitwise OR** operator (`|`) combined with a **Left Shift** (`<<`).The OR operator is perfect for this because of its logic: $`1 \text{ OR anything} = 1`$.
<hr>

### The Set Formula

To set the $`n^{th}`$ bit of a number:

```python
def set_bit(number, index):
    # Create a mask with a 1 at the target position
    mask = 1 << index
    
    # Use OR to force that bit to 1
    return number | mask
```

**How it Works (Step-by-Step)**

Imagine you have the number **8** (`1000` in binary) and you want to set the **bit at index 0** to make it **9**.

1. **Shift:** `1 << 0` creates the mask `0001`.
2. OR (`|`): We compare the original number and the mask.
   - `1000` (Original: 8)
   - `0001` (Mask)
   - `----`
   - `1001` (Result: 9)
