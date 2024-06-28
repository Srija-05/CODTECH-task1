# CODTECH-task1
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
