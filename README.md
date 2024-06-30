# CODTECH-task1
LOGIC GATES :
module gates(
    input a,
    input b,
    output y1,y2,y3,y4,y5,y6,y7
    );
    assign y1=a&b;
    assign y2=a|b;
    assign y3=a^b;
    assign y4=~(a&b);
    assign y5=~(a|b);
    assign y6=a~^b;
    assign y7=~a;
endmodule
![image](https://github.com/Srija-05/CODTECH-task1/assets/173922039/7c1b4891-3ac8-46d0-85d8-abda47467586)
HALF AND FULL ADDER :
module adder(
    input a,
    input b,
    input c,
    output sh,
    output sf,
    output cf
    );
    wire t1,t2,t3;
    xor (sh,a,b);
    xor (sf,a,b,c);
    and (t1,a,b);
    and (t2,c,b);
    and (t3,a,c);
    or (cf,t1,t2,t3);
endmodule
![hafa](https://github.com/Srija-05/CODTECH-task1/assets/173922039/abfeb2a2-7f8a-4fd5-8890-92d63e5a0453)
MUX 2:1 :
module mux2(
    input a,
    input b,
    input s,
    output reg o
    );
    always@(*)
    begin
    case(s)
    1'b0 : o = a;
    1'b1 : o = b;
    default : o = a;
    endcase
    end
endmodule
![image](https://github.com/Srija-05/CODTECH-task1/assets/173922039/9a827692-a298-41f8-92f8-adf76be82b54)
MUX 4:1 :
module mux4(
    input [1:0] a,
    input [1:0] b,
    input [1:0] c,
    input [1:0] d,
    input [1:0] s,
    output reg [1:0] o
    );
    always@(*)
    begin
    case(s)
    2'b00 : o = a;
    2'b01 : o = b;
    2'b10 : o = c;
    2'b11 : o = d;
    default : o = a;
    endcase
    end
endmodule
![image](https://github.com/Srija-05/CODTECH-task1/assets/173922039/e3f1cf65-ac85-4218-a1d6-e3275b7d29e8)
MUX 8:1 :
module mux8(
input [7:0] in,
input [2:0] sel,
output out);
    assign out = in[sel];
endmodule
TESTBENCH : 
module mux8_tb();
reg [7:0]a; reg [2:0]s; wire o;
mux8 m(.in(a),.sel(s),.out(o));
initial
begin
$dumpfile("mux8.vcd");
$dumpvars(0,mux8_tb);
$monitor($time," a: %o s: %o out: %b",a,s,o);
#10 a=8'h52; s=3'b011;
#5 s=3'b101;
#5 s=3'b111;
#5 $finish;
end
endmodule
OUTPUT :           0 a: xxx s: x out: x
                  10 a: 122 s: 3 out: 0
                  15 a: 122 s: 5 out: 0
                  20 a: 122 s: 7 out: 0
MUX 16:1 :
module mux16(
    input [15:0] in,
    input [3:0] sel,
    output out
    );
    assign out = in[sel];
endmodule
TESTBENCH : 
module mux16_tb();
reg [15:0]a;reg [3:0]s;wire o;
mux16 m(.in(a),.sel(s),.out(o));
initial
begin
$dumpfile("mux16.vcd");
$dumpvars(0,mux16_tb);
$monitor($time," a: %h s: %h o: %b",a,s,o);
#10 a=16'hd6b8; s=4'h5;
#5 s=4'h8;
#5 s=4'hf;
#5 $finish;
end
endmodule
OUTPUT :           0 a: xxxx s: x o: x
                  10 a: d6b8 s: 5 o: 1
                  15 a: d6b8 s: 8 o: 0
                  20 a: d6b8 s: f o: 1
