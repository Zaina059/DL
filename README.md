# CPU VHDL Project – ModelSim Waveform Setup

This project contains the VHDL implementation of a simple CPU, including the Program Counter (PC), Instruction Register (IR), ALU, Control Unit, Register File, ROM, RAM, and CPU Top module.  
This README explains how to add the required internal signals to the ModelSim waveform demonstration.

## ⚙️ 1. Compile All VHDL Files
Open ModelSim → Compile → Compile All.


---

## ▶️ 2. Load the Testbench

Run the testbench using:
vsim work.cpu_tb


---

## 📡 3. Add Signals to the Waveform

In the *Sim/Objects* panel, expand:
cpu_tb → DUT


Then add the following signals:

### **Program Counter**
- `PC_inst/pc_out`
- `PC_inst/pc_addr`

### **Instruction Register (IR)**
- `IR_inst/instr`
- `IR_inst/opcode`
- `IR_inst/Rs`
- `IR_inst/Rt`
- `IR_inst/Rd`
- `IR_inst/shamt`

### **Register File**
- `RF_inst/rs_data`
- `RF_inst/rt_data`
- `RF_inst/write_data`
- `RF_inst/RegWrite`

### **ALU**
- `ALU_inst/A`
- `ALU_inst/B`
- `ALU_inst/Result`
- `ALU_inst/SR_out`

### **Control Unit**
- `CU_inst/ALUSrc`
- `CU_inst/SRwrite`

### **Memory**
- `RAM_inst/dout`
- `ROM_inst/instr`

---

## 🏃 4. Run the Simulation

After adding all signals, run:
run -all


You will now see:
- PC updates  
- Instruction fetch  
- Decoding  
- Register read/write  
- ALU operations  
- Control signals  
- RAM/ROM data transfers  

---




