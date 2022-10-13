# Experiment--03-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure
#### Step 1:
   Module Declaration. module is a keywords defined in Verilog .

#### Step 2:
   Input-Output Delecaration. Half Subtractor has two inputs. Full Subtractor has three inputs.

#### Step 3:
   Use wire declaration and assign statements to define the functionality of logic circuits.

#### Step 4:
   Ending module. endmodule is a keywords defined in Verilog.


## Program:
```
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: RAJESHKANNAN.M
RegisterNumber:  212221230081
``` 
#### Half Subtractor
```
module halfsub(A,B,diff,barrow);
input A,B;
output diff,barrow;
wire x;
xor(diff,A,B);
not(x,A);
and(barrow,x,B);
endmodule
```

#### Full Subtractor
```
module fullsub(A,B,C,diff,barrow);
input A,B,C;
output diff,barrow;
assign diff = A ^ B ^ C;
assign barrow = ~A & (B^C) | B & C;
endmodule
```
## Output:

## Truthtable :

#### Half Subtractor
![TT1](https://user-images.githubusercontent.com/93901857/195669312-2f7d4e31-c6f2-48df-866c-2df34062f6c6.jpg)

#### Full Subtractor
![TT2](https://user-images.githubusercontent.com/93901857/195669319-bdd17d7e-73e0-41d0-bc82-f232b13f218c.jpg)

##  RTL realization

#### Half Subtractor
![rtl1](https://user-images.githubusercontent.com/93901857/195669194-955fef5a-ca93-4c76-8067-5df6b359eecb.jpg)

#### Full Subtractor
![rtl2](https://user-images.githubusercontent.com/93901857/195669274-7cc27e72-7f8c-46cb-969b-de74e07ce29f.jpg)

## Timing diagram 

#### Half Subtractor
![t1](https://user-images.githubusercontent.com/93901857/195669285-43de67f2-0ad8-49f0-abb5-90293913c9b6.jpg)

#### Full Subtractor
![t2](https://user-images.githubusercontent.com/93901857/195669305-6d3855cd-8c69-4b5d-bc33-3c2bfb33d038.jpg)


## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
