# VLSI-EXPT-5
# SIMULATION AND IMPLEMENTATION OF FINITE STATE MACHINE
## AIM :
        To simulate and synthesis finite state machine using Xilinx ISE.
## APPARATUS REQUIRED : VIVADO 2023.2
## PROCEDURE :
STEP:1 Start the Xilinx navigator, Select and Name the New project.<br>
STEP:2 Select the device family, device, package and speed.<br>
STEP:3 Select new source in the New Project and select Verilog Module as the Source type.<br>
STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it.<br>
STEP:5 Select the Behavioral Simulation in the Source Window and click the check syntax.<br>
STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.<br>
STEP:7 Select the Implementation in the Sources Window and select the required file in the Processes Window.<br>
STEP:8 Select Check Syntax from the Synthesize XST Process. Double Click in the Floorplan Area/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained.<br>
STEP:9 In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu.<br>
STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here.<br>
STEP:11 On the board, by giving required input, the LEDs starts to glow light, indicating the output.<br>
STEP:12 Load the Bit file into the SPARTAN 6 FPGA<br>
## LOGIC DIAGRAM :
![image](https://github.com/JAYASHREEER/VLSI-EXPT-5/assets/166278992/7d3bbae4-9964-4d07-888a-b64aa9b3cdd4)
## PROGRAM :
module fsm(clk,rst,x,z);<br> input clk,rst,x;<br> output z;<br> reg [2:1] ps,ns;<br> parameter s0=2'b00,s1=2'b01,s2=2'b10,s3=2'b11;<br> always@(x,posedge clk)<br> case(ps)<br>
s0:if(x) ns=s1;<br> else ns=s0;<br>
s1:if(x) ns=s1; <br>else ns=s2;<br>
s2:if(x) ns=s3;<br> else ns=s0;<br>
s3:if(x)<br>ns=s1;<br> else ns=s0;<br> endcase always@(posedge clk)<br>
if(rst)<br>
ps<=s0; <br>else ps=ns;<br> assign z=(ps==s3);<br> endmodule
## OUTPUT :
![image](https://github.com/JAYASHREEER/VLSI-EXPT-5/assets/166278992/910b5ecb-2695-448b-a647-2c888c0c13b6)

## RESULT :
      The simulate and synthesis of finite state machine using VIVADO is successfully verified.





