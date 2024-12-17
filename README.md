# SR-FLIPFLOP-USING-CASE

**AIM:**

To implement  SR flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/0f710028-ad52-4d3e-9276-8714cf023a25)

 
This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/dabfc4f4-87e3-4cbc-9472-f89ee1b5ed30)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/dd90d16c-aec5-4290-a586-e2346b1e9eb5)

 
By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/473efad6-d70b-4ca7-aeb7-898bbfca319f)

 
The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)

**Procedure**

Step1: Define the specifications and initialize the design.
Step2: Declare the name of the entity and architecture by using VHDL source code.
Step3: Write the source code in VERILOG.
Step4: Check the syntax and debug the errors if found, obtain the synthesis report.
Step5: Verify the output by simulating the source code.
Step6: Write all possible combinations of input using the test bench.
Step7: Obtain the place and route report.

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

```
module srflipflops(s, r, clk, rst, q, qbar);
 input s;
 input r;
 input clk;
 input rst;
 output q;
 output qbar;
		  reg q,qbar;	
		  always @ (posedge(clk) or posedge(rst)) begin
		  if(rst==1'b1) begin
        q= 1'b0;qbar= 1'b1;
		  end
		  else if(s==1'b0 && r==1'b0)
		   begin
		  q=q; qbar=qbar;
		  end
                else if(s==1'b0 && r==1'b1)
                 begin
        q= 1'b0; qbar= 1'b1;
        end
                else if(s==1'b1 && r==1'b0)
                 begin
        q= 1'b1; qbar= 1'b0;
        end
        else
        begin
        q=1'bx;qbar=1'bx;
        end
        end
endmodule

```

Developed by: NANDA KISHOR SP 
RegisterNumber: 24011485
*/

**RTL LOGIC FOR FLIPFLOPS**

![Screenshot (100)](https://github.com/user-attachments/assets/702d1f87-297d-44c3-a71f-5d16ae3f6745)


**TIMING DIGRAMS FOR FLIP FLOPS**

![Screenshot (101)](https://github.com/user-attachments/assets/07d2f5e5-0219-4dcd-8161-a1d112f8717b)


**RESULTS**

The SR flip-flop was implemented successfully using Verilog, and its functionality was validated through simulation. The output matches the expected functional table of the SR flip-flop.
