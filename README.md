# Experiment-08- Encoders-and-decoders 
### AIM: To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## Encoders
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders –
An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![image](https://user-images.githubusercontent.com/36288975/171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a.png)
## Figure -01 3 to 8 Encoder 


Implementation –

X = D4 + D5 + D6 + D7
Y = D2 +D3 + D6 + D7
Z = D1 + D3 + D5 + D7 
Hence, the encoder can be realised with OR gates as follows:


![image](https://user-images.githubusercontent.com/36288975/171543740-68403b82-aa93-4c98-9343-f32b14885a2e.png)
## Figure -02 3 to 8 Encoder implenentation 

 ### Decoders 
A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder.
Implementation –
D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ 
Similarly,

D1 = X’ Y’ Z
D2 = X’ Y Z’
D3 = X’ Y Z
D4 = X Y’ Z’
D5 = X Y’ Z
D6 = X Y Z’
D7 = X Y Z 


![image](https://user-images.githubusercontent.com/36288975/171543978-ee2d0671-2846-40a1-8705-507fd6287a49.png)
## Figure -03 8 to 3 Decoder 



![image](https://user-images.githubusercontent.com/36288975/171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035.png)
## Figure -04 8 to 3 Decoder implementation 

### Procedure
Step-1: Create module encoder and decoder.
Step-2: Get inputs and outputs for encoders and decoders.
Step-3: Perform or operation for encoderand logic for decoders.
Step-4: Perform RTL LOGIC and get waveform.
Step-5: End the module.


### PROGRAM 
/*
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.

ENCODER

module EX7(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
input d0,d1,d2,d3,d4,d5,d6,d7;
output a,b,c;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
end module

DECODER

module EX7(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
input a,b,c;
output d0,d1,d2,d3,d4,d5,d6,d7;
assign d0 = (~a&~b&~c);
assign d1 = (~a&~b&c);
assign d2 = (~a&b&~c);
assign d3 = (~a&b&c);
assign d4 = (a&~b&~c);
assign d5 = (a&~b&c);
assign d6 = (a&b&~c);
assign d7 = (a&b&c);
end module 


Developed by: Harini.E
RegisterNumber:  212222050017
*/


### RTL LOGIC 

ENCODER
![RTL encoder](https://github.com/vasanthkumarch/Experiment-08-Encoders-and-decoders-/assets/128949246/9b79ec3c-a08e-494b-8988-b3becca31c69)

DECODER
![RTL decoder](https://github.com/vasanthkumarch/Experiment-08-Encoders-and-decoders-/assets/128949246/8491a229-a632-41cb-8f7a-372280e1db2b)



### TIMING DIGRAMS  

ENCODER
![Timing encoder](https://github.com/vasanthkumarch/Experiment-08-Encoders-and-decoders-/assets/128949246/edb895ed-1188-486e-80c0-837d9eb53728)

DECODER
![Timing decoder](https://github.com/vasanthkumarch/Experiment-08-Encoders-and-decoders-/assets/128949246/d4f88593-21a5-4da2-badf-4706e19e7a6a)



### TRUTH TABLE 

ENCODER
![TT encoder](https://github.com/vasanthkumarch/Experiment-08-Encoders-and-decoders-/assets/128949246/9ea738ab-0515-46a3-bf9d-00a954d47bd3)

DECODER
![TT decoder](https://github.com/vasanthkumarch/Experiment-08-Encoders-and-decoders-/assets/128949246/ba60b769-97ac-4a26-a1ed-32b294638577)


### RESULTS 

Thus the program to design encoder and decoder is completed.


