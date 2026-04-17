## Bit Reset

To **reset** a bit (also known as "clearing" a bit), you want to force a specific bit to `0` while leaving all other bits exactly as they were.

To do this with shifts, we use a combination of three operators: **Left Shift** (`<<`), **Bitwise NOT** (`~`), and **Bitwise AND** (`&`).
<hr>

### The Reset Formula

To reset the $`n^{th}`$ bit of a number, use this logic:

```python
def reset_bit(number, index):
    # 1. Create the mask (e.g., 00001000)
    mask = 1 << index
    
    # 2. Invert the mask (e.g., 11110111)
    inverted_mask = ~mask
    
    # 3. AND it with the number
    return number & inverted_mask
```

**Why This Works (Step-by-Step)**

Let's say you have the number **15** (`1111`) and you want to reset the **bit at index 1** (the second bit from the right).

1. **Shift:** `1 << 1` gives us `0010`.

2. **Invert (`~`):** The NOT operator flips every bit. `~0010` becomes `1101`. (Note: In Python, this involves a sign bit, but logically it acts as a mask of all 1s with a 0 at your target spot).

3. **AND (`&`):** We compare our original number with this "inverted mask":

    - `1111` (Original 15)
    - `1101` (Inverted Mask)
    - `----`
    - `1101` (Result: 13)

The `0` in your mask acts like a "hole" that forces the corresponding bit in your number to become `0`, while the `1`s in the mask act like "pass-throughs" that keep the other bits the same.
