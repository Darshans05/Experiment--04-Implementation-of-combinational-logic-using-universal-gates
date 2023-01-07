# Experiment--04-Implementation-of-combinational-logic-using-universal-gates
Implementation of combinational logic using universal-gates
 
## AIM:
To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate
F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate
## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime


## Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

## Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

## Logic Diagram

Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

## Logic Diagram
## Procedure
## Program:
/*
Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.
Developed by: DARSHAN S 
RegisterNumber: 22008842 
*/
using NAND:

module combo1(a,b,c,d,f);
input a,b,c,d;
output f;
wire p,q,r;
assign p=(~c & b & a);

assign q=(~d & c & ~a);

assign r=(c & ~b & a);

assign f=(~(~p & ~q & ~r));

endmodule

using NOR:

module combo2(a,b,c,d,f);
input a,b,c,d;

output f;

wire p,q,r;

assign p=( c & ~b & a);

assign q=( d & ~c & a);

assign r=( c & ~b & a);

assign f=((( p | q | r)));

endmodule

## RTL realization
USING NAND GATE
![image](https://user-images.githubusercontent.com/115534676/211152926-56920e7e-09a6-4807-b94f-d9413aa91b17.png)
Timing Diagram
![image](https://user-images.githubusercontent.com/115534676/211152950-f97dca77-ec52-478d-833d-f8457728a757.png)
TRUTH TABLE
![image](https://user-images.githubusercontent.com/115534676/211152994-b8cd34b2-c57e-41ea-9d22-892d2a057222.png)
## Output:
## RTL
USING NOR GATE:
![image](https://user-images.githubusercontent.com/115534676/211153021-887de72c-68a1-48af-bf5a-a78d439b41c9.png)
![image](https://user-images.githubusercontent.com/115534676/211153028-527de06d-b3cc-4afd-91c5-8392c38ac856.png)
## Timing Diagram
![image](https://user-images.githubusercontent.com/115534676/211153043-08d73760-0b2d-4bb4-a86b-3757c9a4e74d.png)
## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
