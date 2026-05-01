## Sign and Unsigned Bits

**Part 1: Conceptual Check**

1. Which bit is traditionally used as the "sign bit" in signed integers?
   - A) The Least Significant Bit (LSB) on the right.
   - B) The Most Significant Bit (MSB) on the left.
   - C) The middle bit.

**Answer:**\
B (The MSB): In signed notation, the leftmost bit tells you if the number is negative ($`1`$) or positive ($`0`$).

2. If an 8-bit number is "unsigned," what is the total range of values it can represent?
   - A) $`-128`$ to $`127`$
   - B) $`0`$ to $`127`$
   - C) $`0`$ to $`255`$

**Answer:**\
C ($`0`$ to $`255`$): Since you don't need a sign bit, you can use all 8 bits for magnitude ($`2^8 - 1`$).

3. What is the primary advantage of using Two's Complement for signed numbers?
   - A) It makes the numbers look prettier.
   - B) It allows the hardware to use the same addition logic for both positive and negative numbers.
   - C) It doubles the amount of memory available.

**Answer:**\
B: Two's Complement simplifies CPU design because $`A - B`$ is treated the same as $`A + (-B)`$.
<hr>

**Part 2: The "Translation" Challenge**

For these questions, assume we are working with an 8-bit system.

4. Convert the binary string `10000001` to decimal:
   - As an Unsigned Integer: _________
   - As a Signed Integer (Two's Complement): _________

**Answer:**\
`10000001`

- **Unsigned:** $`128 + 1 =`$ **129**.
- **Signed:** Since the MSB is $`1`$, it's negative. In Two's Complement, this represents **-127**.

5. You have the binary string `11111111`:
   - As an Unsigned Integer: _________
   - As a Signed Integer (Two's Complement): _________

**Answer:**\
`11111111`

- **Unsigned: 255** (the maximum value).
- **Signed: -1.** (A shortcut: all $`1`$s in Two's Complement is always $`-1`$).
<hr>

**Part 3: Overflow & Logic**

6. If you have a 4-bit unsigned system, what happens if you add `1111` (15) and `0001` (1)?
   - A) It becomes `10000` (16).
   - B) It wraps around to `0000` (0).
   - C) The computer explodes.

**Answer:**\
**B (Wraparound):** In a fixed 4-bit system, the $`5^{th}`$ bit is discarded, leading to an "overflow" where the value resets to zero.
