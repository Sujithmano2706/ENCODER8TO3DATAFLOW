
**AIM:**

To implement  Encoder 8 To 3 in Dataflow Modelling using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:** Quartus prime

**THEORY**

**Encoder 8 To 3**

The 8 to 3 line Encoder is also known as Octal to Binary Encoder. In 8 to 3 line encoder, there is a total of eight inputs, i.e., D0, D1, D2, D3, D4, D5, D6, and D7 and three outputs, i.e., A0, A1, and A2. In 8-input lines, one input-line is set to true at a time to get the respective binary code in the output side. Below are the block diagram and the truth table of the 8 to 3 line encoder.

![image](https://github.com/naavaneetha/ENCODER8TO3DATAFLOW/assets/154305477/0bc242c1-eb9e-4c47-afe5-30428470efc3)

Figure 01  Block Diagram of Encoder 8 * 3

**Truth Table**

![image](https://github.com/naavaneetha/ENCODER8TO3DATAFLOW/assets/154305477/35496b14-ae6e-4cd1-9abd-d6736b576575)

The logical expression of the term A0, A1, and A2 are as follows:

A0 = D1 + D3 + D5 + D7

A1 = D2 + D3 + D6 + D7

A2 = D4 + D5 + D6 + D7

Logical circuit of the above expressions is given below:

![image](https://github.com/naavaneetha/ENCODER8TO3DATAFLOW/assets/154305477/95acaee6-c873-4c75-89eb-ef09fb158053)

Figure 02  Encoder 8 * 3

**Procedure**

/* Specify the behavior

Decide which encoder you want:

Simple encoder (one-hot only): assumes exactly one input is 1. Output is binary index of that 1.

Priority encoder: if many inputs are 1, a defined priority chooses which index appears (e.g., D7 highest → D0 lowest).

Prepare the functional (truth) table for the one-hot case (below).

Derive boolean expressions (dataflow style)

For one-hot mapping D0→000, D1→001, ... D7→111, the MSB/bit expressions are:

Y[2] = D7 | D6 | D5 | D4

Y[1] = D7 | D6 | D3 | D2

Y[0] = D7 | D5 | D3 | D1

For priority encoder, create signals that indicate the highest asserted input (e.g. d7p = D[7]; d6p = D[6] & ~D[7]; ...) and then form Y from those.

Write Verilog modules

Implement the dataflow encoder using assign statements (I provided templates earlier).

Implement a priority encoder (dataflow) if you need well-defined multi-assert behavior.

Write a self-checking testbench

The testbench should:

Iterate all 8 one-hot vectors and check the output equals expected binary code.

Optionally test all 256 input combinations to detect ambiguous behavior and to verify priority behavior if using the priority encoder.

Print pass/fail per vector, and a final summary.

Simulate

Use Icarus Verilog (iverilog + vvp) or ModelSim/Questa.

Run waveform viewer (gtkwave) if you want to inspect signals interactively.

Check results

If any vector fails, inspect the waveform or printed mismatches and correct logic.

For multi-assert cases, verify the behavior matches your specification (undefined or priority).

Synthesize (optional)

Run synthesis in your target tool (Vivado, Quartus, etc.) if targeting FPGA/ASIC. Check resource usage and timing.

Document final functional table and limitations

Note that the simple dataflow encoder only guarantees correctness for true one-hot inputs; multi-assert inputs produce the OR of logic terms (not a defined index).*/

**PROGRAM**
```
/* Program for Encoder 8 To 3 in Dataflow Modelling and verify its truth table in quartus using Verilog programming. 

Developed by: SUJITH MANO M
RegisterNumber: 25018328
*/
```
```
8to3 ENCODER


module enc(a,b,c,y0,y1,y2,y3,y4,y5,y6,y7);
input y0,y1,y2,y3,y4,y5,y6,y7;
output a,b,c;
assign a= ( y4 | y5 | y6 | y7);
assign b= ( y2 | y3 | y6 | y7);
assign c= ( y1 | y3 | y5 | y7);
endmodule
```

**RTL LOGIC FOR Encoder 8 To 3 in Dataflow Modelling**

<img width="1122" height="800" alt="image" src="https://github.com/user-attachments/assets/ac43540e-8903-466f-9ab5-d5c3d7b4398e" />


**TIMING DIGRAMS FOR Encoder 8 To 3 in Dataflow Modelling**

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/30de7f9d-fccc-4fc4-b3f3-8e637daf533e" />


**RESULTS**

Thus the Encoder 8 To 3 in Dataflow Modelling using verilog and validating their functionality using their functional tables





