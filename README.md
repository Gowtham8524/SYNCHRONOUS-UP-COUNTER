### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**

1.Type the program in Quartus software.

2.Compile and run the program.

3.Generate the RTL schematic and save the logic diagram.

4.Create nodes for inputs and outputs to generate the timing diagram.

5.For different input combinations generate the timing diagram.

**PROGRAM**
```
 module EXP11(clk,rstn,out);
input clk,rstn;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(!rstn)
     out<=0;
   else 
     out <= out+1;
end
endmodule
```


Developed by:Gowtham S
RegisterNumber:212224100018


**RTL LOGIC UP COUNTER**
![445444939-9f672a0d-fdc0-46d5-98d0-6e8cc6971f0c](https://github.com/user-attachments/assets/cc68f158-c9ff-419c-ba92-8a13ba8eb779)



**TIMING DIAGRAM FOR IP COUNTER**
![445444776-3fd6c8ab-a5dd-4bd7-bd00-72c0d73bc6c1](https://github.com/user-attachments/assets/d4161728-8970-4671-93f9-539535008160)



**TRUTH TABLE**

![446397530-7efc8a50-8790-40e6-936e-e8e900fe28a8](https://github.com/user-attachments/assets/6f90aa57-e730-43b8-b229-03e2459d48f0)


**RESULTS**

The result is sucessfully verified
