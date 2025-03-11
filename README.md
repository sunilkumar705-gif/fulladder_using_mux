 Full Adder Using MUX
A full adder can be designed using multiplexers instead of logic gates. The concept behind using multiplexers is that the Sum and Carry outputs can be represented as a function of inputs, and a multiplexer can be used to select the correct output based on these inputs.

The Sum (S) and Carry (Cout) equations for a full adder are:
𝑆=𝐴⊕𝐵⊕𝐶𝑖𝑛
Cout=AB+BCin+ACin
Here, a multiplexer (MUX) is used to implement these logic equations.

2. Understanding the Verilog Code (fulladder_using_mux.v)
The module fulladder_using_mux defines a full adder using a multiplexer-based approach.
Inputs: a, b, cin
Outputs: sum, cout
Working Principle:
The mux1 module is used as a 4:1 multiplexer, which selects different sum and carry outputs based on the input conditions.
Key Code Sections:
assign cinb = ~cin;
This inverts the carry-in bit to be used in multiplexer selection.
mux1 v(sum, c0, c1, c2, c3, a, b);
Implements the Sum function using a MUX.
mux1 n(cout, l'0, c1, l'1, a, b);
Implements the Carry-out function using a MUX.

3.Testbench (tb.v) - Explanation
A testbench is used to verify the correctness of the fulladder_using_mux.v module.
Testbench (tb.v) Components:
Declares inputs (a, b, cin) as reg
Declares outputs (sum, cout) as wire
Instantiates the full adder module
Uses initial begin ... end to apply different input combinations in a sequence.
