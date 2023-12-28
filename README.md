## Developed by: Farhana H
## Reference number:212223230057
# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: To implement 4 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 
## UP COUNTER 
The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.
The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.
The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.
Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.
Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.
The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:
Four-bit “Up” Counter
![image](https://user-images.githubusercontent.com/36288975/169644758-b2f4339d-9532-40c5-af40-8f4f8c942e2c.png)

## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://user-images.githubusercontent.com/36288975/169644844-1a14e123-7228-4ed8-81a9-eb937dff4ac8.png)


4-bit Count Down Counter
### Procedure
```
1.Create a new project in Quartus2 software .
2.Name the project as uc for upcounter and dc for down counter.
3.Create a new verilog hdl file in the project file.
4.Name the module declare as dc and uc for down counter and upcounter.
5.Within the module declare input and output variable
6.Create a loop using if-else with condition parameter as reset.
7.End the loop. 8.End the mo
```
### PROGRAM
Program for flipflops  and verify its truth table in quartus using Verilog programming.
## UP COUNTER
```
module upcounter(clk,q1,q2,q3);
input clk;
output reg q1,q2,q3;
always@(posedge clk)
begin
q3 = (q1&q2)^q3;
q2 = q1^q2;
q1 = 1^q1;
end
endmodule
```
## DOWN COUNTER
```
module downcounter(clk,q1,q2,q3);
input clk;
output reg q1,q2,q3;
always@(posedge clk)
begin
q3 = ((~q1)&(~q2))^q3;
q2 = (~q1)^q2;
q1 = 1^q1;
end
endmodule
```
## TRUTH TABLE
## UP COUNTER
![image](https://github.com/syedfayaz3105/Exp-7-Synchornous-counters-/assets/147144126/2816df81-6cea-4201-917c-214cac5c5e2f)

## DOWN COUNTER
![image](https://github.com/syedfayaz3105/Exp-7-Synchornous-counters-/assets/147144126/2560ff4e-d445-468f-aa3d-56b113542352)

## CIRCUIT DIAGRAM
## UP COUNTER
![image](https://github.com/syedfayaz3105/Exp-7-Synchornous-counters-/assets/147144126/4a9659e7-2a78-44ba-9490-d53c697e7bee)

## DOWN COUNTER
![image](https://github.com/syedfayaz3105/Exp-7-Synchornous-counters-/assets/147144126/86b37d71-2ca0-4d69-884d-5eadc67ba41a)

## OUTPUT
## UP COUNTER
![image](https://github.com/syedfayaz3105/Exp-7-Synchornous-counters-/assets/147144126/8caba7de-2c95-4847-8ce8-f5bada38092d)

## DOWN COUNTER
![image](https://github.com/syedfayaz3105/Exp-7-Synchornous-counters-/assets/147144126/b5516fcb-4903-4358-a06d-e5f23db3bd99)

### RESULTS 
Thus the up counter and down counter circuit and truth table are formed by the Quartus System
