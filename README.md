# Experiment-08--Encoders-and-decoders

AIM: To implement 8 to 3 Encoder and 3to8 Decoder using verilog and validate its outputs
HARDWARE REQUIRED: – PC, Cyclone II , USB flasher
SOFTWARE REQUIRED: Quartus prime
THEORY
Encoders
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

Encoders – An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.
As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.


![171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a](https://user-images.githubusercontent.com/121932143/214296047-cfe68c3d-546a-4cfd-99ed-9d04236b9369.png)

Figure -01 3 to 8 Encoder
Implementation –

X = D4 + D5 + D6 + D7 Y = D2 +D3 + D6 + D7 Z = D1 + D3 + D5 + D7 Hence, the encoder can be realised with OR gates as foll0ws!
[171543740-68403b82-aa93-4c98-9343-f32b14885a2e](https://user-images.githubusercontent.com/121932143/214296110-a22619b8-2775-4365-9470-14e2ebde3ff5.png)
ws:




Figure -02 3 to 8 Encoder implenentation
Decoders
A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder. Implementation – D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ Similarly,

D1 = X’ Y’ Z D2 = X’ Y Z’ D3 = X’ Y Z D4 = X Y’ Z’ D5 = X Y’ Z D6 = X Y Z’ D7 = X Y Z
![171543978-ee2d0671-2846-40a1-8705-507fd6287a49](https://user-images.githubusercontent.com/121932143/214296273-861bbfa0-d65a-4069-8de4-32d32e0f26d9.png)






Figure -03 8 to 3 Decoder
![171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035](https://user-images.githubusercontent.com/121932143/214296330-1e9c3a42-8da3-4c80-b75d-1b1881958751.png)




Figure -04 8 to 3 Decoder implementation
Procedure
Step 1: Create module encoder and decoder.
Step 2: Get inputs and outputs for encoders and decoders.
Step 3: Perform "or" operation for encoder and "and" logic for decoders.
Step 4: Perform RTL LOGIC and get waveform.
Step-5: End the module.
PROGRAM
Program for Endocers and Decoders and verify its truth table in quartus using Verilog programming.

Developed by: Ronick Aakshath P

RegisterNumber: 22007303

ENCODER
module EX8(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
output a,b,c;
input d0,d1,d2,d3,d4,d5,d6,d7;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule
DECODER
module EX8(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
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
endmodule
RTL LOGIC
For ENCODER


![encoder](https://user-images.githubusercontent.com/121932143/214296451-b098d01a-c5f4-49ca-a80b-d25f778f6296.png)





For DECODER



![decoder](https://user-images.githubusercontent.com/121932143/214296498-1e714ef7-4011-4bd7-882a-affc34b8b4a3.png)




TIMING DIGRAMS
For ENCODER



![encodert](https://user-images.githubusercontent.com/121932143/214296731-d2a5c06c-8205-427d-af37-9edf552ce325.png)



For DECODER


![decodert](https://user-images.githubusercontent.com/121932143/214296751-a4d3f501-243e-49f1-8094-a44b7034e958.png)




TRUTH TABLE
For ENCODER



![encodertt](https://user-images.githubusercontent.com/121932143/214296778-f1396a14-80d4-47ab-8b00-3e0167454d28.png)


For DECODER



![decodertt](https://user-images.githubusercontent.com/121932143/214296808-f013e7ed-db1d-4312-b75c-f24040aec544.png)




RESULTS
Thus the program to implement encoder and decoder using verilog is verified.
