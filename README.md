AIM:

To implement SR flipflop using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED:

Quartus prime

THEORY

SR flipflop

An SR Flip-Flop (Set–Reset Flip-Flop) is the simplest bistable multivibrator used in sequential digital circuits. It is a memory element that can store one bit of binary information. The flip-flop has two inputs, labeled S (Set) and R (Reset), and two complementary outputs, Q and Q′.

The SR Flip-Flop can be implemented using either cross-coupled NOR gates (active-high version) or cross-coupled NAND gates (active-low version). In both implementations, the output is fed back into the input of the opposite gate, causing a stable locking state. This feedback property gives the circuit its memory characteristic.

Operation

The behavior of the SR flip-flop is determined by the combination of the S and R inputs:

Set Condition (S = 1, R = 0):
The flip-flop sets its output, making Q = 1 and Q′ = 0.

Reset Condition (S = 0, R = 1):
The flip-flop resets its output, making Q = 0 and Q′ = 1.

Hold Condition (S = 0, R = 0):
The flip-flop maintains its previous state. There is no change in the output, showing its memory property.

Invalid Condition (S = 1, R = 1):
In the NOR-gate version, this drives both outputs to 0, which violates the rule that Q and Q′ must be complements. Therefore, this input combination is considered undefined or invalid, and must be avoided.

PROCEDURE

1.Connect the IC 7402 (NOR gates) to the digital trainer kit.

2.Give 5V supply to Vcc and GND pins of the IC.

3.Connect two NOR gates in a cross-coupled fashion to form an SR Flip-Flop.

4.Connect input switches to S and R.

5.Connect outputs Q and Q’ to LEDs.

6.Apply input combinations (S, R) one by one.

7.Note the LED outputs for each input condition.

8.Compare with the theoretical truth table.

PROGRAM

~~~
module sr_ff (
    input  wire clk, rst, S, R,
    output reg  Q
);
    always @(posedge clk) begin
        if (rst)
            Q <= 1'b0;         // Reset
        else begin
            case ({S,R})
                2'b00: Q <= Q;     // No change
                2'b01: Q <= 1'b0;  // Reset
                2'b10: Q <= 1'b1;  // Set
                2'b11: Q <= 1'bx;  // Invalid
            endcase
        end
    end
endmodule
~~~
Developed By: V JAYACHANDRA

Register number:25017587*/

RTL LOGIC FOR FLIPFLOPS

TIMING DIGRAMS FOR FLIP FLOPS

RESULTS: 

Thus the SR flipflop using verilog and validating their functionality using their functional tables is implemented and verified


