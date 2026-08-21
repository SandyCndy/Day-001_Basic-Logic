
# Day 1 — Basic Digital Logic

## Objective

Learn the fundamentals of combinational RTL
and understand how logic gates are represented
as synthesizable hardware.

## Modules

- AND
- OR
- XOR
- NOT
- NAND
- NOR
- XNOR

```RTL
module day1(//andgate
input a,
input b,
output c
);
assign c = a & b;
endmodule 

module orgate(//orgate
input a,
input b,
output c
);
assign c = a | b;
endmodule 

module day1(//xor
input a,
input b,
output c
);
assign c = a ^ b;
endmodule 

module day1(//not
input a,
output c
);
assign c = ~a;
endmodule
 
module day1(//nand
input a,
input b,
output c
);
assign c = ~(a & b);
endmodule 

module day1(//nor
input a,
input b,
output c
);
assign c = ~(a | b);
endmodule 

module day1( //xnor
input a,
input b,
output c
);
assign c = ~(a ^ b);
endmodule 

```

## Verification
<img width="1919" height="880" alt="Screenshot 2026-08-21 151548" src="https://github.com/user-attachments/assets/a9b72995-79bd-4b41-a0d2-00dc814d5319" />
``` TB
module day1tb;
reg a;
reg b;
wire c;
day1 dut(//andgate
.a(a),
.b(b),
.c(c)
);
initial begin // stimulus
 #10;
 a = 1'b0; b = 1'b0;
 #10;
 a = 1'b0; b = 1'b1;
 #10;
 a = 1'b1; b = 1'b0;
 #10;
 a = 1'b1; b = 1'b1; 
 //endsimulation
 #20;
 $finish;
 end 
 // monitoring
 initial begin 
 $dumpfile("day1.vcd");
 $dumpvars(0,day1tb);
 $monitor("a=%b b=%b y=%b", a,b,c);
 end 
 endmodule

```
Tested all possible input combinations.

## FPGA

Implemented AND gate on Altera Cyclone II.

## What I Learned
i know you will laugh why go so basic because i have altera cycolne II board EP2C8 and i dont have accessories to perform other things
I performed this also for learning about the quartus and understand how it works. I'll be consistent from today

## Problems Faced

problem faced during fpga implementation as this is my first time on quartus and this board

## Future Use

These basic combinational blocks will later form:

- ALU
- control logic
- instruction decoder
- address decoder
- CPU datapath
- RISC-V processor

## Status

Day 1 — completed
