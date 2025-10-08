# FULL_ADDER_SUBTRACTOR

Implementation-of-Full-Adder-and-Full-subtractor-circuit

**AIM:**

To design a Full Adder and Full Subtractor circuit and verify its truth table in Quartus using Verilog programming.

**Equipments Required:**

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime

**Full Adder and Full Subtractor**

**Full Adder**

Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.

Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin 

Carry = AB + ACin + BCin

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/0f30ba51-5ffb-4198-845f-18e054f675e7)

**Figure -1 FULL ADDER**

**Full Subtractor**

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/02b24f51-ab51-4304-9ad6-7b81ffc1ead5)

Diff = A ⊕ B ⊕ Bin 

Borrow out = A'Bin + A'B + BBin

**Truthtable**

**Procedure**

Write the detailed procedure here

**Program:**

module full_adder (
    input A, B, Cin,
    output SUM, Cout
);
    wire s1, c1, c2;

    // First stage (half adder)
    xor (s1, A, B);
    and (c1, A, B);

    // Second stage (add s1 and Cin)
    xor (SUM, s1, Cin);
    and (c2, s1, Cin);

    // Final carry
    or  (Cout, c1, c2);
endmodule

module full_subtractor (
    input A, B, Bin,
    output DIFF, Bout
);
    wire d1, b1, b2;

    // First stage (half subtractor)
    xor (d1, A, B);
    and (b1, ~A, B);

    // Second stage (subtract Bin)
    xor (DIFF, d1, Bin);
    and (b2, ~d1, Bin);

    // Final borrow
    or  (Bout, b1, b2);
endmodule

**RTL Schematic**
<img width="953" height="268" alt="image" src="https://github.com/user-attachments/assets/ef11b355-4c52-4fe4-bf02-c5d98ac2a1a6" />

**Output Timing Waveform**
<img width="1041" height="428" alt="image" src="https://github.com/user-attachments/assets/a7b99730-018a-4a3a-81b2-04b27afa994e" />

**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



