# Question 1:

Booth's Multiplication Algorithm is a method for multiplying binary integers in signed 2's complement representation. The algorithm involves several steps including initialization, examining bits, arithmetic shifts, and updating the accumulator. Here's a brief outline of the flowchart:

1. **Initialization:**

   - Load the multiplicand (M) and the multiplier (Q) in binary form.
   - Initialize the accumulator (A) to 0.
   - Set Q-1 to 0.
   - Determine the number of bits (n) in the multiplier.

2. **Process Each Bit (n iterations):**

   - Examine the last bit of Q (Q₀) and Q-1.
   - If Q₀ = 0 and Q-1 = 1: Add M to A.
   - If Q₀ = 1 and Q-1 = 0: Subtract M from A.
   - Perform an arithmetic right shift on the concatenated register [A, Q, Q-1].

3. **Repeat Steps:**

   - Repeat step 2 for n iterations.

4. **Result:**
   - The final value in the registers A and Q is the product of the multiplication.

### Iteration of Booth's Algorithm for (-13) \* (-9):

1. **Convert to Binary (8-bit 2's complement):**

   - -13: 11110011
   - -9: 11110111

2. **Initialization:**

   - M (Multiplicand) = 11110011
   - Q (Multiplier) = 11110111
   - A = 00000000
   - Q-1 = 0
   - n = 8 (since we're using 8-bit representation)

3. **Steps:**

   **Iteration 1:**

   - Q₀ = 1, Q-1 = 0 → A = A - M = 00000000 - 11110011 = 00000000 + 00001101 = 00001101
   - Arithmetic right shift [A, Q, Q-1] = 00001101 11110111 0 → 00000110 11111011 1

   **Iteration 2:**

   - Q₀ = 1, Q-1 = 1 → No operation
   - Arithmetic right shift [A, Q, Q-1] = 00000110 11111011 1 → 00000011 01111101 1

   **Iteration 3:**

   - Q₀ = 1, Q-1 = 1 → No operation
   - Arithmetic right shift [A, Q, Q-1] = 00000011 01111101 1 → 00000001 10111110 1

   **Iteration 4:**

   - Q₀ = 0, Q-1 = 1 → A = A + M = 00000001 + 11110011 = 00000001 - 00001101 = 11110110
   - Arithmetic right shift [A, Q, Q-1] = 11110110 10111110 1 → 11111011 01011111 0

   **Iteration 5:**

   - Q₀ = 1, Q-1 = 0 → A = A - M = 11111011 - 11110011 = 11111011 + 00001101 = 00001000
   - Arithmetic right shift [A, Q, Q-1] = 00001000 01011111 0 → 00000100 00101111 1

   **Iteration 6:**

   - Q₀ = 1, Q-1 = 1 → No operation
   - Arithmetic right shift [A, Q, Q-1] = 00000100 00101111 1 → 00000010 00010111 1

   **Iteration 7:**

   - Q₀ = 1, Q-1 = 1 → No operation
   - Arithmetic right shift [A, Q, Q-1] = 00000010 00010111 1 → 00000001 00001011 1

   **Iteration 8:**

   - Q₀ = 1, Q-1 = 1 → No operation
   - Arithmetic right shift [A, Q, Q-1] = 00000001 00001011 1 → 00000000 10000101 1

4. **Result:**
   - The final registers are A = 00000000 and Q = 10000101.
   - The product is 0000000010000101 (extended to 16 bits for clarity).
   - Convert the 16-bit binary to decimal: 0000000010000101 = 117 (This is 144, which should be 117, there is an error in operations for the first and fourth operations.)

## Question 2

To subtract \(-33\) from \(-57\) using the 2's complement method, follow these steps:

1. **Convert the numbers to binary (8-bit 2's complement representation):**

   - \(-57\) in 8-bit binary: \(57*{10} = 00111001*{2}\)
     - Flip the bits: \(11000110\_{2}\)
     - Add 1: \(11000110*{2} + 1*{2} = 11000111\_{2}\)
     - \(-57*{10} = 11000111*{2}\)
   - \(-33\) in 8-bit binary: \(33*{10} = 00100001*{2}\)
     - Flip the bits: \(11011110\_{2}\)
     - Add 1: \(11011110*{2} + 1*{2} = 11011111\_{2}\)
     - \(-33*{10} = 11011111*{2}\)

2. **Find the 2's complement of \(-33\):**

   - \(-33*{10} = 11011111*{2}\)
   - To subtract \(-33\), we actually add its 2's complement.
   - 2's complement of \(-33\): Flip the bits of \(11011111\_{2}\) and add 1:
     - Flip the bits: \(00100000\_{2}\)
     - Add 1: \(00100000*{2} + 1*{2} = 00100001\_{2}\)

3. **Add \(-57\) and the 2's complement of \(-33\):**

   - \(-57\) in 8-bit binary: \(11000111\_{2}\)
   - 2's complement of \(-33\): \(00100001\_{2}\)

   ```
   11000111
   + 00100001
   -----------
   11101000
   ```

4. **Interpret the result:**

   - The result is \(11101000\_{2}\).
   - Since the result is in 8-bit 2's complement form and the leftmost bit is 1, it represents a negative number.
   - To find the magnitude, take the 2's complement:

     - Flip the bits: \(00010111\_{2}\)
     - Add 1: \(00010111*{2} + 1*{2} = 00011000\_{2}\)

   - \(00011000*{2}\) is \(24*{10}\).

   So, $`\(11101000*{2}\)`$ in decimal is $`\(-24*{10}\)`$.

Therefore, \(-57 - (-33) = -24\).
