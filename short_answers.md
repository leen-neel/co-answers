# Question 1:

10000

# Question 2:

| A   | B   | A XNOR B |
| --- | --- | -------- |
| 0   | 0   | 1        |
| 0   | 1   | 0        |
| 1   | 0   | 0        |
| 1   | 1   | 1        |

# Question 3:

0111

# Question 9:

Refer to [this](https://byjus.com/gate/de-morgans-theorems-notes/)

# Question 10:

A multiplexer (MUX) is a digital circuit that selects one of several input signals and forwards it to a single output.

# Question 11:

An active-high decoder is a digital circuit that decodes a binary input into one of several active-high output lines, where the selected output line is asserted high (logic level 1) based on the input combination.

# Question 13:

100111

# Question 15:

Refer to [this](https://www.geeksforgeeks.org/difference-between-flip-flop-and-latch/)

# Question 16:

A counter is a digital circuit or device used to count events or occurrences of signals over time. Its functionality includes:

1. **Counting:** Incrementing or decrementing a digital value in response to input pulses or clock signals.
2. **Storing:** Holding the current count value until it is updated by the next input pulse.
3. **Outputting:** Providing the count value as an output, often in binary form, for further processing or display.

Counters are essential in various applications such as frequency measurement, digital clocks, timers, and address generation in memory circuits.

# Question 20:

141

# Question 24:

Synchronous counters: Use a common clock signal to synchronize all flip-flops, ensuring simultaneous state changes. Asynchronous counters: Each flip-flop triggers based on the output of the previous flip-flop, allowing for variable timing and potentially uneven propagation delays.

# Question 25:

An accumulator (AC) is a register in a CPU that stores the result of arithmetic and logic operations. Its functionality includes:

1. **Storage:** Holding the interim results of arithmetic computations.
2. **Arithmetic Operations:** Performing addition, subtraction, and other arithmetic operations using data from memory or registers.
3. **Data Transfer:** Facilitating data movement between memory, registers, and input/output devices, crucial in arithmetic calculations and data processing in a computer system.

# Question 26:

A combinational circuit is a digital circuit where the output is solely determined by the current inputs, without any regard to previous input states. These circuits do not have memory elements, such as flip-flops or latches. Examples include:

1. **Logic Gates:** Circuits built from AND, OR, NOT gates, etc., where the output depends only on the current input values.

2. **Multiplexers (MUX):** A MUX selects one of several input lines based on control inputs, with the output determined by the combination of inputs.

3. **Demultiplexers (DEMUX):** A DEMUX routes a single input to one of several output lines based on control inputs, operating similarly to a MUX in terms of input-output relationship.

# Question 27:

1. **Half Adder:** Adds two binary digits and generates a sum and a carry, but cannot handle a carry input from a previous addition.
2. **Full Adder:** Adds three binary digits (two operands and a carry-in) to produce a sum and a carry-out, allowing for cascading multiple additions.

# Question 29:

3221

# Question 30:

1001100

# Question 31:

1000 0100 0001

# Question 35:

8

# Question 39:

To perform an arithmetic shift right on the binary value \(10011101\) (assuming it's an 8-bit register value):

Arithmetic shift right (ASR) preserves the sign bit (the leftmost bit) while shifting the other bits to the right. Here's how it works:

1. **Original Binary Value:** \(10011101\)

2. **Arithmetic Shift Right:**

   - Shift all bits one position to the right.
   - The sign bit (leftmost bit, which is \(1\) in this case) is preserved.

3. **Result After Arithmetic Shift Right:**
   - \(11001110\)

Therefore, after performing an arithmetic shift right on \(10011101\), the register value becomes \(11001110\) in binary.
