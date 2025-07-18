# verilog

module and_gate (
    input a,       // 1-bit input a
    input b,       // 1-bit input b
    output y       // 1-bit output y
);

assign y = a & b;  // bitwise AND operation

endmodule


module tb_and_gate;

reg a, b;          // Testbench inputs (reg)
wire y;            // Output (wire)

and_gate uut (
    .a(a),
    .b(b),
    .y(y)
);

initial begin
    $display("a b | y");
    $monitor("%b %b | %b", a, b, y);

    a = 0; b = 0; #10;
    a = 0; b = 1; #10;
    a = 1; b = 0; #10;
    a = 1; b = 1; #10;

    $finish;
end

endmodule
