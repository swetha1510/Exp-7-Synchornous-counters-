# Exp-6-Synchornous-counters - up counter and down counter 
### AIM:
To implement 4 bit up and down counters and validate  functionality.

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
### 1.Using if statement construct a 4bit UP counter.

### 2.Repeat the same for 4bit DOWN counter.

###3.Find RTL and Timing diagram for the both the counters.

###4.End the program.

### PROGRAM 
```
Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by: SWETHA P
RegisterNumber: 22008542

###UP counter

module uc(input CLK,input reset,output[0:3]counter);
reg[0:3]counter_up;
always@(posedge CLK or posedge reset)
begin
if(reset)
counter_up <=4'd0;
else
counter_up <=counter_up+4'd1;
end
assign counter = counter_up;
endmodule

###DOWN counter
module dc(input CLK,input reset,output[0:3]counter);
reg[0:3]counter_down;
always@(posedge CLK or posedge reset)
begin
if(reset)
counter_down <=4'd0;
else
counter_down <=counter_down-4'd1;
end
assign counter = counter_down;
endmodule
```

### RTL LOGIC
###UP counter
![UCRTL](https://user-images.githubusercontent.com/120623583/214594304-943d06d7-2ef1-44f0-be2f-ede15c4f0b12.png)

###DOWN counter
![DCRTL](https://user-images.githubusercontent.com/120623583/214595042-65c2968f-0511-4a06-b7b1-33114491439a.png)


### TIMING DIGRAMS FOR COUNTER 

###UP counter
![UCSIM](https://user-images.githubusercontent.com/120623583/214595278-db05bde9-8d41-4c3c-a83a-a6a15572051a.png)

###DOWN counter
![DCSIM](https://user-images.githubusercontent.com/120623583/214595369-fcaaabd2-057c-45d6-9075-308bfeb4b484.png)


### TRUTH TABLE 
###UP counter

![uctruth](https://user-images.githubusercontent.com/120623583/214599020-f8bcc15c-a67d-4c3b-846c-a9a1b000f186.png)

###DOWN counter

![dctruth](https://user-images.githubusercontent.com/120623583/214599224-d8a59405-d540-4c84-a8c6-4b39043220c4.png)

### RESULTS 
 Thus the UP counter and DOWN counter are designed and truthtable are verified using quartus software.
