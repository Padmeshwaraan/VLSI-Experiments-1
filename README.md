EXP.NO: 1 

DATE: 13/02/2024

SIMULATION AND IMPLEMENTATION OF LOGIC GATES AND 4 BIT ADDER & SUBTRACTOR 

AIM: To simulate and synthesis Logic Gates, Adders and Subtractor using VIVADO 


APPARATUS REQUIRED: VIVADO 2023.2 


PROCEDURE: 


STEP:1 Start the Vivado, Select and Name the New project. 


STEP:2 Select the device family, device, package and speed. 


STEP:3 Select new source in the New Project and select Verilog Module as the Source type. 


STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it. 


STEP:5 Select the Behavioural Simulation in the Source Window and click the check syntax. 


STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.
 


LOGIC-GATES: 

![image](https://github.com/Karthikeyan8296/VLSI-EXP-1/assets/165583967/fe825cf3-cf22-45f2-8953-c605426076da)

                            

PROGRAM: 

module logic_gates(a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate);

input a,b;

output andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate;

and(andgate,a,b);

or(orgate,a,b);

xor(xorgate,a,b);

nand(nandgate,a,b);

nor(norgate,a,b);

xnor(xnorgate,a,b);

not(notgate,a);

endmodule

OUTPUT:       

![image](https://github.com/Karthikeyan8296/VLSI-EXP-1/assets/165583967/e3bb8a12-f37c-42ac-925f-143296448b83)

 



HALF ADDER: 

![image](https://github.com/Karthikeyan8296/VLSI-EXP-1/assets/165583967/dfb9ede6-56e4-4a12-ba58-aafe034023e7)



 



PROGRAM: 

module ha(a,b,sum,carry);

input a,b;

output sum,carry;

assign sum=a^b;

assign carry=a&b;

endmodule






OUTPUT:

![image](https://github.com/Karthikeyan8296/VLSI-EXP-1/assets/165583967/0a21eb1c-1806-4c63-9cb1-5ce8f55a5c23)


 
HALFSUBTRACTOR: 

![image](https://github.com/Karthikeyan8296/VLSI-EXP-1/assets/165583967/dd10a7e4-a9b3-4322-b681-2477af439761)



 


PROGRAM: 
module hs(a,b,diff,borrow);

input a,b; 

output diff,borrow;

assign diff=a^b; 

assign borrow=~a&b;

endmodule


OUTPUT:

![image](https://github.com/Karthikeyan8296/VLSI-EXP-1/assets/165583967/4d9d5900-1f2f-411d-9107-040496bbb93c)

 




FULLADDER: 

![image](https://github.com/Karthikeyan8296/VLSI-EXP-1/assets/165583967/69627c10-cd9b-4dbe-96bb-e788158a0286)


 


PROGRAM: 

module fa(a,b,c,sum,carry);

input a,b,c; 

output sum,carry;

assign sum=a^b^c; 

assign carry=(a&b)|(a&c)|(b&c);

endmodule



OUTPUT:

![image](https://github.com/Karthikeyan8296/VLSI-EXP-1/assets/165583967/0253e8f4-68f4-41cb-aa0a-e0816101ad99)


 




FULLSUBTRACTOR: 

![image](https://github.com/Karthikeyan8296/VLSI-EXP-1/assets/165583967/e199046a-1577-4844-9f9e-9f2b67d26382)




 






PROGRAM: 

module fs(a,b,c,diff,borrow);

input a,b,c;

output diff,borrow;

assign diff=a^b^c; 

assign borrow=(~a&c)|(~a&b)|(b&c); 

endmodule


OUTPUT:

![image](https://github.com/Karthikeyan8296/VLSI-EXP-1/assets/165583967/4377c1ba-9c64-476b-8873-5802eeb492bd)


 8-BIT-RIPPLE-CARRY-ADDER: 
 
 ![image](https://github.com/Karthikeyan8296/VLSI-EXP-1/assets/165583967/7a15fa9f-b3f6-4e67-b577-1df899110d05)


 

PROGRAM: 

module ripplemod(a, b, cin, sum, cout);

input [07:0] a;

input [07:0] b;

input cin;

output [7:0]sum;

output cout;

wire[6:0] c;

fulladd a1(a[0],b[0],cin,sum[0],c[0]);

fulladd a2(a[1],b[1],c[0],sum[1],c[1]);

fulladd a3(a[2],b[2],c[1],sum[2],c[2]);

fulladd a4(a[3],b[3],c[2],sum[3],c[3]);

fulladd a5(a[4],b[4],c[3],sum[4],c[4]);

fulladd a6(a[5],b[5],c[4],sum[5],c[5]);

fulladd a7(a[6],b[6],c[5],sum[6],c[6]);

fulladd a8(a[7],b[7],c[6],sum[7],cout);

endmodule

module fulladd(a, b, cin, sum, cout);

input a;

input b;

input cin;

output sum;

output cout;

assign sum=(a^b^cin);

assign cout=((a&b)|(b&cin)|(a&cin));

endmodule
















OUTPUT: 

 ![image](https://github.com/Karthikeyan8296/VLSI-EXP-1/assets/165583967/0268a8d3-2f03-4ce2-b33c-25c5bb932aeb)













RESULT:
        Thus, the logic gates and 4 Bit of Adder and Subtractor are Implemented 
and simulated successfully.

