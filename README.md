EXP-4

DATE:

             SIMULATION AND IMPLEMENTATION OF SEQUENTIAL LOGIC CIRCUITS

**AIM:**
To simulate and synthesis JK-Flipflop, SR-Flipflop, T-Flipflop, D-Flipflop And counters using Vivado 2023.2

**APPARATUS REQUIRED:**

vivado 2023

# PROCEDURE:

STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation and then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.


LOGIC DIAGRAM

 SR FLIPFLOP:

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/77fb7f38-5649-4778-a987-8468df9ea3c3)

 VERILOG CODE:
module SR(clk,s,r,rst,q );

input s,r,clk,rst;

output reg q;

always@(posedge clk)

begin

if(rst==1)

q=1'b0;

else

begin

case({s,r})

2'b00: q=q;

2'b01:q=1'b0;

2'b10:q=1'b1;

2'b11:q=1'bx;

endcase

end

end

Endmodule

 Output:

![331878583-16a32bed-775f-417f-91ca-ca2c0f1da109](https://github.com/jaggu654/VLSI-LAB-EXP-4/assets/167850134/57ff5f80-ac37-4da3-9bed-15ffb83bee45)

 JK FLIPFLOP:

![331878578-f6fa9fa4-b660-4279-b978-24525b5d83ce](https://github.com/jaggu654/VLSI-LAB-EXP-4/assets/167850134/9726c4a9-dd37-46af-b71a-09fa2f2aa897)

 VERILOG CODE:

module jk(j,k,clk,rst,Q);

input j,k,clk,rst;

output reg Q;

always @(posedge clk)

begin

if(rst==1)Q=0;

else

begin

case({j,k})

2'b00:Q=Q;

2'b01:Q=0;

2'b10:Q=1;

2'b11:Q=~Q;

endcase

end

end

Endmodule

 Output:

![331878557-6d707bda-b2d0-49e7-833f-3ab3f1832452](https://github.com/jaggu654/VLSI-LAB-EXP-4/assets/167850134/5a541104-51b7-4386-a04f-ab0b6d5e5839)

 T FLIPFLOP:


![331878569-255aaef9-0684-4a13-aa81-adfdc5c60d68](https://github.com/jaggu654/VLSI-LAB-EXP-4/assets/167850134/84a5c3a2-c5a7-4b5b-937c-287a34eaea9e)

 VERILOG CODE:

module tff(t,clk,rst,Q);

input t,clk,rst;

output reg Q;

always @(posedge clk)

begin

if(rst==1)

Q=1'b0;

else if(t==0)

Q=Q;

else

Q=~Q;

end

Endmodule

 Output:

![331878533-3e17bf86-5eea-4ec0-9557-d51b5d9ef2d5](https://github.com/jaggu654/VLSI-LAB-EXP-4/assets/167850134/afd7a7b7-0b97-460d-8249-2b41e7c0bb8a)

 D FLIPFLOP:

![331878525-91eb1f6d-fffc-4075-b5e0-c2bb7a6a0305](https://github.com/jaggu654/VLSI-LAB-EXP-4/assets/167850134/eeabd2e3-53e4-42dd-8dd9-6266d425d3b0)

 VERILOG CODE:

module dff(d,clk,rst,Q);

input d,clk,rst;

output reg Q;

always @(posedge clk)

begin

if(rst==1)

Q=1'b0;

else

Q=d;

end

Endmodule

![331878501-a2b8c99e-966e-4173-a878-9d2cca30b631](https://github.com/jaggu654/VLSI-LAB-EXP-4/assets/167850134/aa5a003d-948d-4885-87bb-d89b7bc5283f)

 Output:


 COUNTER:

![331878490-3e30f700-9182-47be-b2de-d26c8a87c6e3](https://github.com/jaggu654/VLSI-LAB-EXP-4/assets/167850134/1d99156a-eeb1-4f9f-82a3-31850d5b5fd4)

4bit UPDOWN COUNTER


![331878471-06f349b3-3fb1-4257-ab73-eb048f1970bb](https://github.com/jaggu654/VLSI-LAB-EXP-4/assets/167850134/ed26be1e-b96e-44aa-aaf2-18b0b07a9781)

 VERILOG CODE:

module updown(clk,rst,updown,out);

input clk,rst,updown;

output reg[3:0]out;

always@(posedge clk)

begin

if(rst==1)

out=4'b0000;

else if(updown==1);

out=out-1;

end

endmodule

Output:
![331878445-5480fedc-52d2-486b-998b-8c8daab4b900](https://github.com/jaggu654/VLSI-LAB-EXP-4/assets/167850134/213a1623-7f4b-4a4c-916d-82cf750a048c)


 MOD 10 COUNER:
 
![331878424-e7e98869-0f96-45c8-a8d8-58f891c4010e](https://github.com/jaggu654/VLSI-LAB-EXP-4/assets/167850134/37bfb159-dd4b-4c3e-889f-abc86bb193cd)


VERILOG CODE:

module mod(clk,rst,out);

input clk,rst;

output reg[3:0]out;

always @(posedge clk)

begin

if(rst==1 | out==4'b1001)

out=4'b0000;

else

out=out+1;

end

endmodule

 Output:

![331878388-197ecc0f-4449-4e01-b9f4-bfe02974ece7](https://github.com/jaggu654/VLSI-LAB-EXP-4/assets/167850134/32a7cc49-5390-47b6-ad63-a087f4ca9f76)


RIPPLE CARRY COUNTER:

![331878376-236c62ed-8c17-43e8-863f-82938eaf836e](https://github.com/jaggu654/VLSI-LAB-EXP-4/assets/167850134/4c023082-4beb-4159-ad81-515cab2d9c63)

VERILOG CODE

module ripple_carry_counter(q, clk, reset);

output [3:0] q;

input clk, reset;

T_FF tff0(q[0], clk, reset);

T_FF tff1(q[1], q[0], reset);

T_FF tff2(q[2], q[1], reset);

T_FF tff3(q[3], q[2], reset);

endmodule

module T_FF(q, clk, reset);

output q;

input clk, reset;

wire d;

D_FF dff0(q, d, clk, reset);

not n1(d, q);

endmodule

module D_FF(q, d, clk, reset);

output q;

input d, clk, reset;

reg q;

always @(posedge reset or negedge clk)

if (reset)

q = 1'b0;

else

q = d;

endmodule

Output:

![331878354-7fe8e184-42af-4f11-9dae-5d14350cce6d](https://github.com/jaggu654/VLSI-LAB-EXP-4/assets/167850134/707fe3ef-b967-499b-8a0e-ee00960a8985)

 RESULT:

Thus simulate and synthesis JK-Flipflop, SR-Flipflop, T-Flipflop, D-Flipflop And counters was succesfully executed and verified.
