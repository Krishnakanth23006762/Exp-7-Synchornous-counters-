## Name: B KRISHNAKANTH
## Register number: 212223230109
# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: To implement 3 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## UP COUNTER 
The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 7 and vice versa based upon the direction of counting (up/down). 

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

 
 

Three-bit “Up” Counter
![image](https://github.com/Krishnakanth23006762/Exp-7-Synchornous-counters-/assets/138849446/a6b2dfb5-ee45-4aaf-b4d9-0752a17858dc)




## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 3-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://github.com/Krishnakanth23006762/Exp-7-Synchornous-counters-/assets/138849446/3cf1ad63-5ff9-4b24-8de8-4554b7a2a3a5)


3-bit Count Down Counter
### Procedure

1.Create a new project in Quartus2 software

2.Name the project as uc for upcounter and dc for down counter.

3.Create a new verilog hdl file in the project file. 

4.Name the module declare as dc and uc for down counter and upcounter. 

5.Within the module declare input and output variables.

6.Create a loop using if-else with condition parameter as reset. 

7.End the loop. 8.End the module



### PROGRAM 

## UP COUNTER:
```
module uc(clk, A);
input clk;
output reg [2:0]A;
always @(posedge clk)
begin
A[2]=(((A[0])&(A[1]))^A[2]);
A[1]=(A[0])^A[1];
A[0]=A[0]^1;
end
endmodule
```
## DOWN COUNTER:
```
module dc(clk,A);
input clk;
output reg [2:0]A;
always @(posedge clk)
begin
A[2]=(((~A[0])&(~A[1]))^A[2]);
A[1]=(~A[0])^A[1];
A[0]=1^A[0];
end
endmodule
```

### RTL LOGIC UP COUNTER AND DOWN COUNTER  

## UP COUNTER:
![image](https://github.com/Krishnakanth23006762/Exp-7-Synchornous-counters-/assets/138849446/d841c3a7-637b-4e14-a512-c5183153aa8d)

## DOWN COUNTER:
![image](https://github.com/Krishnakanth23006762/Exp-7-Synchornous-counters-/assets/138849446/7f025ccb-8851-4dc4-994b-c04e20f309bc)


### TIMING DIGRAMS FOR COUNTER  

## UP COUNTER:
![image](https://github.com/Krishnakanth23006762/Exp-7-Synchornous-counters-/assets/138849446/d07902ab-29ca-4c7e-9402-19c0834242eb)

## DOWN COUNTER:
![image](https://github.com/Krishnakanth23006762/Exp-7-Synchornous-counters-/assets/138849446/520fc6a3-e386-4c04-956a-7a5b4470e9c9)

### TRUTH TABLE 

## UP COUNTER:
![image](https://github.com/Krishnakanth23006762/Exp-7-Synchornous-counters-/assets/138849446/fac6c1ab-f65a-4e4f-8b58-036cbe49523a)

## DOWN COUNTER:
![image](https://github.com/Krishnakanth23006762/Exp-7-Synchornous-counters-/assets/138849446/834f142d-ce71-4c47-ba0f-d9039b5deae4)

### RESULTS 
Thus synchornous counters up counter and down counter circuit are studied and the truth table for different logic gates are verified.
