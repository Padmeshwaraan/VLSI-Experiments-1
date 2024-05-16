                                                                 
 EXP.NO- 1 

DATE- 
                    SIMULATION AND IMPLEMENTATION OF LOGIC GATES AND 
                                           4 BIT ADDER & SUBTRACTOR 

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

![image](https://github.com/Padmeshwaraan/VLSI-Experiments-1/assets/160568747/598eb676-fc4f-4543-a08b-60624c2c1419)
                            
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


![image](https://github.com/Padmeshwaraan/VLSI-Experiments-1/assets/160568747/0bf7de7a-e772-4f1b-a1ac-76278dc145a5)

HALF ADDER: 


![image](https://github.com/Padmeshwaraan/VLSI-Experiments-1/assets/160568747/1efa0cef-9db7-441b-aad9-4accd714defe)

PROGRAM: 

module ha(a,b,sum,carry);

input a,b;

output sum,carry;

assign sum=a^b;

assign carry=a&b;

endmodule

OUTPUT:


![image](https://github.com/Padmeshwaraan/VLSI-Experiments-1/assets/160568747/7c204f4f-e3dd-4060-bdff-93e019fd3ba2)

HALFSUBTRACTOR:


![image](https://github.com/Padmeshwaraan/VLSI-Experiments-1/assets/160568747/c21b7c8d-c134-4467-b903-6ccf3c576cf6)

PROGRAM: 

module hs(a,b,diff,borrow);

input a,b; 

output diff,borrow;

assign diff=a^b; 

assign borrow=~a&b;

endmodule

OUTPUT:


![image](https://github.com/Padmeshwaraan/VLSI-Experiments-1/assets/160568747/3937e7e8-af45-468d-b05c-05c37d9d68d8)

FULLADDER: 


![image](https://github.com/Padmeshwaraan/VLSI-Experiments-1/assets/160568747/8020948e-1de8-4d83-8531-52532675485c)

PROGRAM: 

module fa(a,b,c,sum,carry);

input a,b,c; 

output sum,carry;

assign sum=a^b^c; 

assign carry=(a&b)|(a&c)|(b&c);

endmodule

OUTPUT:


![image](https://github.com/Padmeshwaraan/VLSI-Experiments-1/assets/160568747/9a51b020-a484-4b9b-b016-f93b67b9b303)

FULLSUBTRACTOR: 


![image](https://github.com/Padmeshwaraan/VLSI-Experiments-1/assets/160568747/c1a5ac2a-235a-47b6-9e5a-5d0487fdb3e0)

PROGRAM: 

module fs(a,b,c,diff,borrow);

input a,b,c;

output diff,borrow;

assign diff=a^b^c; 

assign borrow=(~a&c)|(~a&b)|(b&c); 

endmodule

OUTPUT:


![image](https://github.com/Padmeshwaraan/VLSI-Experiments-1/assets/160568747/5fda3116-d45e-4562-8083-edac1099f3ce)

 8-BIT-RIPPLE-CARRY-ADDER: 
 
 
 ![image](https://github.com/Padmeshwaraan/VLSI-Experiments-1/assets/160568747/b90d6719-3f52-437b-a37d-be4a12f989b5)

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


![image](https://github.com/Padmeshwaraan/VLSI-Experiments-1/assets/160568747/58adbe5a-8aa9-4862-94f3-3af09e0aef9b)

RESULT:

        Thus, the logic gates and 4 Bit of Adder and Subtractor are Implemented 
and simulated successfully.

 


