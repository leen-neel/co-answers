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

# Question 2:

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

   $$
   \begin{array}{c}
   \phantom{0}11000111 \\
   + \phantom{0}00100001 \\
   \hline
   11101000 \\
   \end{array}
   $$

4. **Interpret the result:**

   - The result is \(11101000\_{2}\).
   - Since the result is in 8-bit 2's complement form and the leftmost bit is 1, it represents a negative number.
   - To find the magnitude, take the 2's complement:

     - Flip the bits: \(00010111\_{2}\)
     - Add 1: \(00010111*{2} + 1*{2} = 00011000\_{2}\)

   - \(00011000*{2}\) is \(24*{10}\).

   So, \(11101000*{2}\) in decimal is \(-24*{10}\).

Therefore, \(-57 - (-33) = -24\).

# Question 3:

Sure, let's represent the decimal number 45 in Hexadecimal, Gray code, and BCD (Binary-Coded Decimal).

1. **Hexadecimal Representation:**

To convert 45 to hexadecimal:

First, divide 45 by 16:

\[
45 \div 16 = 2 \text{ remainder } 13
\]

So, \( 45*{10} = 2D*{16} \).

2. **Gray Code Representation:**

Gray code is a binary numeral system where two successive values differ in only one bit.

First, convert 45 to binary:

\[
45*{10} = 101101*{2}
\]

To find the Gray code:

- The most significant bit (MSB) remains the same: \( 1 \)
- Each subsequent bit is found by XOR-ing the current bit with the previous bit in the binary representation.

\[
\begin{align*}
\text{Binary} & : 1 \quad 0 \quad 1 \quad 1 \quad 0 \quad 1 \\
\text{Gray} & : 1 \quad (1 \oplus 0) \quad (0 \oplus 1) \quad (1 \oplus 1) \quad (1 \oplus 0) \quad (0 \oplus 1) \\
& : 1 \quad 1 \quad 1 \quad 0 \quad 1 \quad 1 \\
\end{align*}
\]

So, the Gray code for 45 is:

\[
45*{10} = 111011*{\text{Gray}}
\]

3. **BCD (Binary-Coded Decimal) Representation:**

BCD represents each digit of a decimal number by its 4-bit binary equivalent.

The decimal number 45 has digits 4 and 5.

- 4 in binary: \( 0100 \)
- 5 in binary: \( 0101 \)

So, the BCD representation of 45 is:

\[
45*{10} = 0100 \ 0101*{\text{BCD}}
\]

In summary:

- **Hexadecimal:** \( 2D\_{16} \)
- **Gray Code:** \( 111011\_{\text{Gray}} \)
- **BCD:** \( 0100 \ 0101\_{\text{BCD}} \)

# Question 4:

Refer to the 1st page of the `co.docx` file.

# Question 5:

## Part A:

The two universal gates are the NAND gate and the NOR gate.

## Part B:

### Duality Principle:

The duality principle in Boolean algebra states that every algebraic expression remains valid if we interchange AND (\(\cdot\)) and OR (\(+\)) operators and replace all 0s with 1s and all 1s with 0s. In simpler terms, the dual of a Boolean expression is formed by swapping AND and OR operators and complementing the constants.

### Example of Duality Principle:

Given the Boolean identity:

\[ A + 0 = A \]

The dual of this identity is:

\[ A \cdot 1 = A \]

Both expressions are valid Boolean identities, demonstrating the duality principle.

### Finding Complements Using Duals:

#### For Function \( F1 = x'yz' + x'y'z \):

1. **Original Function:**

\[ F1 = x'yz' + x'y'z \]

2. **Dual Function:**

To find the dual, interchange AND and OR:

\[ \text{Dual}(F1) = (x' + y + z') \cdot (x' + y' + z) \]

3. **Complementing Each Literal:**

Complement each literal in the dual function:

\[ \text{Complement of Dual}(F1) = (x'' \cdot y' \cdot z'') + (x'' \cdot y'' \cdot z') \]

Since \( x'' = x \), \( y'' = y \), and \( z'' = z \):

\[ \text{Complement of Dual}(F1) = (x \cdot y' \cdot z) + (x \cdot y \cdot z') \]

Thus, the complement of \( F1 \) is:

\[ F1' = (x \cdot y' \cdot z) + (x \cdot y \cdot z') \]

#### For Function \( F2 = x(y'z' + yz) \):

1. **Original Function:**

\[ F2 = x(y'z' + yz) \]

2. **Dual Function:**

To find the dual, interchange AND and OR:

\[ \text{Dual}(F2) = x + (y' + z') \cdot (y + z) \]

3. **Complementing Each Literal:**

Complement each literal in the dual function:

\[ \text{Complement of Dual}(F2) = x' \cdot (y'' \cdot z'') + (y' \cdot z') \]

Since \( x'' = x \), \( y'' = y \), and \( z'' = z \):

\[ \text{Complement of Dual}(F2) = x' \cdot (y \cdot z) + (y' \cdot z') \]

Thus, the complement of \( F2 \) is:

\[ F2' = x' \cdot (y \cdot z) + (y' \cdot z') \]

### Summary:

- **Function \( F1 = x'yz' + x'y'z \):**

\[ F1' = (x \cdot y' \cdot z) + (x \cdot y \cdot z') \]

- **Function \( F2 = x(y'z' + yz) \):**

\[ F2' = x' \cdot (y \cdot z) + (y' \cdot z') \]

# Question 6:

To derive the Boolean expression from the given truth table, we need to identify the rows where the output \(Y\) is 1 and then write the corresponding minterms. Finally, we combine these minterms to form the Boolean expression.

### Given Truth Table:

| A   | B   | C   | Y   |
| --- | --- | --- | --- |
| 0   | 0   | 0   | 0   |
| 0   | 0   | 1   | 1   |
| 0   | 1   | 0   | 1   |
| 0   | 1   | 1   | 0   |
| 1   | 0   | 0   | 1   |
| 1   | 0   | 1   | 0   |
| 1   | 1   | 0   | 0   |
| 1   | 1   | 1   | 1   |

### Steps to Derive the Boolean Expression:

1. **Identify the rows where \(Y = 1\)**:

   - \(A = 0, B = 0, C = 1\)
   - \(A = 0, B = 1, C = 0\)
   - \(A = 1, B = 0, C = 0\)
   - \(A = 1, B = 1, C = 1\)

2. **Write the corresponding minterms**:

   - For \(A = 0, B = 0, C = 1\): \(\overline{A} \cdot \overline{B} \cdot C\)
   - For \(A = 0, B = 1, C = 0\): \(\overline{A} \cdot B \cdot \overline{C}\)
   - For \(A = 1, B = 0, C = 0\): \(A \cdot \overline{B} \cdot \overline{C}\)
   - For \(A = 1, B = 1, C = 1\): \(A \cdot B \cdot C\)

3. **Combine the minterms to form the Boolean expression**:

   $$Y = \overline{A} \cdot \overline{B} \cdot C + \overline{A} \cdot B \cdot \overline{C} + A \cdot \overline{B} \cdot \overline{C} + A \cdot B \cdot C$$

# Question 7:

Draw diagrams for this question.

# Question 8:

Skipped.

# Question 9:

Draw logic diagram.

# Question 10:

## Flip-Flop:

A flip-flop is a fundamental component in digital electronics used for storing binary data. It is a type of bistable multivibrator, meaning it has two stable states (0 or 1), which it can hold indefinitely until directed to change by an external clock or control signal. Flip-flops are used to store state information in sequential logic circuits, such as in memory elements, registers, and counters.

## Race Condition:

A race condition occurs in digital circuits or systems when the outcome of the circuit depends on the timing or sequence of events. Specifically, it arises when the correct functioning of the circuit or system depends not only on the logical order of operations but also on the precise timing of those operations. In other words, the circuit's behavior becomes unpredictable or erroneous because different parts of the circuit are attempting to change simultaneously or in an undefined sequence.
