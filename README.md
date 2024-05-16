
SIMULATION AND IMPLEMENTATION OF SEQUENTIAL LOGIC CIRCUITS

AIM: 
 To simulate and synthesis SR, JK, T, D - FLIPFLOP, COUNTER DESIGN using Xilinx ISE.

APPARATUS REQUIRED:

Xilinx 14.7
Spartan6 FPGA

LOGIC DIAGRAM

SR FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/77fb7f38-5649-4778-a987-8468df9ea3c3)

VERILOG CODE 
````````````````````````````````````````````````````````````
module sr_ff(clk,q,rst,s,r);
input s,r,clk,rst;
 output reg q;
always@(posedge clk)
begin if(rst==1)
q=1'b0;
else begin case({s,r}) 
2'b00:q=q; 
2'b01:q=1'b0; 
2'b10:q=1'b1; 
2'b11:q=1'bx; 
endcase end end 
endmodule  
````````````````````````````````````````````````````````````````````````````````
OUTPUT 
![image](https://github.com/YEMANTHKUMAR/VLSI-LAB-EXP-4/assets/160569469/57ff5b92-f4db-4ccb-9cf1-199ac51c2148)


JK FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/1510e030-4ddc-42b1-88ce-d00f6f0dc7e6)
VERILOG CODE
```````````````````````````````````````````````````
module jk_ff(clk,q,rst,j,k);
input j,k,clk,rst; 
output reg q; 
always@(posedge clk) 
begin if(rst==1) 
q=1'b0;
else begin 
case({j,k}) 
2'b00:q=q; 
2'b01:q=1'b0; 
2'b10:q=1'b1; 2'b11:q=~q; endcase end end endmodule
````````````````````````````````````````````````````````````````````
OUTPUT
![image](https://github.com/YEMANTHKUMAR/VLSI-LAB-EXP-4/assets/160569469/d6a220e6-748f-450b-b084-a246186b8f6e)

T FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/7a020379-efb1-4104-85ee-439d660baa08)
VERILOG CODE 
````````````````````````````````````````````````
module t_ff(clk,q,rst,t);
input t,clk,rst; 
output reg q; 
always@(posedge clk)
begin if(rst==1) 
q=1'b0;
else if(t==0)
q=q;
else q=~q; 
end 
endmodule 	
``````````````````````````````````````````````````````````````````````````````

OUTPUT
![image](https://github.com/YEMANTHKUMAR/VLSI-LAB-EXP-4/assets/160569469/d963170e-8f48-4872-8775-25ea97c710eb)


D FLIPFLOP
![image](https://github.com/YEMANTHKUMAR/VLSI-LAB-EXP-4/assets/160569469/552c8ab9-b530-42cb-9360-155489f12fd9)


VERILOG CODE 
```````````````````````````````````````````` 
module d_ff(clk,q,rst,d); 
input d,clk,rst; 
output reg q; 
always@(posedge clk) 
begin if(rst==1) 
q=1'b0;
else 
q=d; 
end endmodule 
 ```````````````````````````````````````````````````````````````````
OUTPUT      
![image](https://github.com/YEMANTHKUMAR/VLSI-LAB-EXP-4/assets/160569469/3112b257-15ab-4753-b96a-1391099edd29)


COUNTER

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/a1fc5f68-aafb-49a1-93d2-779529f525fa)

VERILOG CODE
````````````````````````````````````````````````````
module mod_10(clk,rst,out);
 input clk,rst;
output reg[3:0]out;
 always@(posedge clk)
begin
if(rst==1|out==9)
out=4'b0;
 else
out=out+1;
 end 
endmodule 
```````````````````````````````````````````````````````````````````````````````
OUTPUT
![image](https://github.com/YEMANTHKUMAR/VLSI-LAB-EXP-4/assets/160569469/08dcf46c-94a0-4213-8c5f-0983a5da90d5)


PROCEDURE:

STEP:1  Start  the Xilinx navigator, Select and Name the New project.
STEP:2  Select the device family, device, package and speed.       
STEP:3  Select new source in the New Project and select Verilog Module as the Source type.                       
STEP:4  Type the File Name and Click Next and then finish button. Type the code and save it.
STEP:5  Select the Behavioral Simulation in the Source Window and click the check syntax.                       
STEP:6  Click the simulation to simulate the program and  give the inputs and verify the outputs as per the truth table.               
STEP:7  Select the Implementation in the Sources Window and select the required file in the Processes Window.
STEP:8  Select Check Syntax from the Synthesize  XST Process. Double Click in the  FloorplanArea/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. 
STEP:9  In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu.
STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here.
STEP:11  On the board, by giving required input, the LEDs starts to glow light, indicating the output.

RESULT

 Thus The Simulate And Synthesis SR, Jk, T, D - Flipflop, Counter Design Using Xilinx Ise Are Verified Successfully 

