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
### Step 1:
Module Declaration. module is a keywords defined in Verilog .

### Step 2:
Input-Output Delecaration.

8 to 3 Encoder has eight inputs and three outputs. 3 to 8 Decoder has three inputs and eight outputs.

### Step 3:
In the verilog program of encoder we use or gates . In the verilog program of decoder we use only and gates.

### Step 4:
Ending module. endmodule is a keywords defined in Verilog.

### PROGRAM 
/*
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: NAVEENKUMAR V
RegisterNumber:  212221230068
*/
### ENCODER:
~~~
module encoder(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
input d0,d1,d2,d3,d4,d5,d6,d7;
output a,b,c;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule
~~~
### Decoders:
~~~
module decoder(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
input a,b,c;
output d0,d1,d2,d3,d4,d5,d6,d7;
assign d0=(~a & ~b & ~c);
assign d1=(~a & ~b & c);
assign d2=(~a & b & ~c);
assign d3=(~a &b & c);
assign d4=(a & ~b & ~c);
assign d5=(a & ~b & c);
assign d6=(a & b & ~c);
assign d7=(a & b &c);
endmodule
~~~





### RTL LOGIC  
### Encoders:
![image](https://user-images.githubusercontent.com/94165322/204084525-4dd84135-5788-4ffd-9f25-865c1b292b42.png)
### Decoders:
![image](https://user-images.githubusercontent.com/94165322/204084535-80c7e316-38ef-46c9-aa5e-f02c86ca8beb.png)








### TIMING DIGRAMS  
### Encoders:
![image](https://user-images.githubusercontent.com/94165322/204084548-d5e63868-852c-4e46-860f-25c102ed96f1.png)
### Decoders:
![image](https://user-images.githubusercontent.com/94165322/204084560-bf701bd2-2b6e-4807-97b2-945f60410c4b.png)





### TRUTH TABLE 
### Encoders:
![image](https://user-images.githubusercontent.com/94165322/204084573-2ce9edba-8828-4ec1-afbd-dcf915609084.png)
### Decoders:
![image](https://user-images.githubusercontent.com/94165322/204084579-f54e07a5-e6e5-43f4-90d0-e2585d1b1230.png)






### RESULTS 
Implementation of 8 to 3 Encoder and 3 to 8 Decoder is done using verilog and its outputs is validated.
