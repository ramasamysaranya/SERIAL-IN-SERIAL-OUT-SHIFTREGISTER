# SERIAL-IN-SERIAL-OUT-SHIFTREGISTER

**AIM:**

To implement  SISO Shift Register using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**SISO shift Register**

A Serial-In Serial-Out shift register is a sequential logic circuit that allows data to be shifted in and out one bit at a time in a serial manner. It consists of a cascade of flip-flops connected in series, forming a chain. The input data is applied to the first flip-flop in the chain, and as the clock pulses, the data propagates through the flip-flops, ultimately appearing at the output.

The logic circuit provided below demonstrates a serial-in serial-out (SISO) shift register. It comprises four D flip-flops that are interconnected in a sequential manner. These flip-flops operate synchronously with one another, as they all receive the same clock signal.

![image](https://github.com/naavaneetha/SERIAL-IN-SERIAL-OUT-SHIFTREGISTER/assets/154305477/e81c4072-37f9-46c6-8145-566764b74c3a)

Figure 01 4 Bit SISO Register

The synchronous nature of the flip-flops ensures that the shifting of data occurs in a coordinated manner. When the clock signal rises, the input data is sampled and stored in the first flip-flop. On subsequent clock pulses, the stored data propagates through the flip-flops, moving from one flip-flop to the next.
Each D flip-flop in the circuit has a Data (D) input, a Clock (CLK) input, and an output (Q). The D input represents the data to be loaded into the flip-flop, while the CLK input is connected to the common clock signal. The output (Q) of each flip-flop is connected to the D input of the next flip-flop, forming a cascade.

**Procedure**
## PROCEDURE

1. Open Quartus II and create a new project using File → New Project Wizard.

2. Enter the project name and select the required FPGA device.

3. Create a new Verilog HDL file using File → New → Verilog HDL File.

4. Write the Verilog program for the SISO (Serial-In Serial-Out) shift register and save the file with a `.v` extension.

5. Set the Verilog module as the Top-Level Entity of the project.

6. Compile the design using Processing → Start Compilation and check for errors or warnings.

7. Open Tools → University Program → Simulation Waveform Editor to create the input waveform.

8. Add the required input and output signals such as clock (clk), serial input (si), clear/reset, and serial output (so).

9. Apply suitable values to the serial input and clock signals and save the waveform file.

10. Perform functional simulation and observe the shifting of the input data through the register.

11. Verify that the serial data appears at the serial output after the required clock cycles.

12. Confirm that the simulated output matches the expected SISO shift-register operation.


**PROGRAM**

Program for flipflops and verify its truth table in quartus using Verilog programming.

Developed by: Saranya R  RegisterNumber: 212225040384
```
module exp5(clk,clear,si,so);
input clk,si,clear;
output so;
reg so;
reg [3:0] tmp;
always @(posedge clk )
begin
if (clear)
tmp <= 4'b0000;
else
tmp <= tmp << 1;
tmp[0] <= si;
so = tmp[3];
end
endmodule
```


**RTL LOGIC FOR SISO Shift Register**
<img width="1396" height="1127" alt="DE exp 5" src="https://github.com/user-attachments/assets/0b19e9f1-8282-4d3d-947b-8b3b1562eea7" />

**TIMING DIGRAMS FOR SISO Shift Register**
<img width="1595" height="986" alt="DE exp5 img2" src="https://github.com/user-attachments/assets/ba3e23f5-434f-4af6-a2ed-2ef7146438c4" />

**RESULTS**

The 4-bit Serial-In Serial-Out (SISO) Shift Register was successfully designed and implemented using Verilog HDL in Quartus Prime. The functional behavior of the circuit was validated through simulation waveforms, confirming that data shifts sequentially through the flip-flops on every positive edge of the clock signal.
