# 🔐 Password Authentication on RISC-V Processor

A Verilog-based custom RISC-V processor with **hardware-level password authentication**, preventing unauthorized instruction execution until a correct password is entered.

---

## 👥 Team Members

- Vaishnavi Kadolkar (02FE22BEC115)  
- Shraman Kanthi (02FE22BEC092)  
- Swati Patil (02FE22BEC112)  
- Darshan Modekar (02FE22BEC119)

**Mentor:** Prof. Sushant S. Jadhav  
**Institution:** KLE Technological University  
**Department:** Electronics and Communication Engineering  
**Semester:** VI, 2024–2025

---

## 🎯 Objectives

- Embed a 4-bit password authentication mechanism into the RISC-V pipeline.
- Block instruction execution unless authentication succeeds.
- Simulate and verify secure execution through RISC-V assembly programs.
- Demonstrate processor-level access control in Verilog HDL.

---

## 💡 Problem Statement

Traditional authentication systems rely on software, which can be bypassed or tampered with.  
This project proposes a **hardware-integrated password check**, where instruction execution is restricted until the correct 4-bit password is entered, making security more robust in embedded processors.

---

## 🔧 Architecture Overview

The processor is built using Verilog and includes:

- **Password Authentication Module**  
- **RISC-V Core Modules** (PC, ALU, Control Unit, Register File, etc.)  
- **Instruction Memory** (Loaded via `.hex` file)

<img src="images/architecture_diagram.png" width="600" alt="Architecture Diagram" />

---

## 🔑 Password Authentication Logic

- A 4-bit user input is compared to a hardcoded password (e.g., `4'b1011`).
- If matched, the `auth_success` signal enables instruction fetch.
- If mismatched, processor receives NOP (no operation), halting execution.

---

## 📂 Core Modules

| Module            | Function                                        |
|-------------------|-------------------------------------------------|
| `processor.v`      | Top-level design, integrates all modules        |
| `password_auth.v`  | Compares user input with predefined password    |
| `alu.v`            | Executes arithmetic/logical operations          |
| `register_file.v`  | 32 general-purpose registers                    |
| `instruction_memory.v` | Loads instructions from hex file            |
| `control_unit.v`   | Generates control signals based on opcode       |
| `data_memory.v`    | Handles `lw` and `sw` memory access             |

---

## 🧪 Simulation and Testing

- **Tool Used:** ModelSim / Vivado / GTKWave  
- **Test Cases:**  
  - Successful authentication → full instruction execution  
  - Failed authentication → instruction fetch blocked

### ✅ Success Case Waveform  
<img src="images/waveform_success.png" width="500"/>

### ❌ Failure Case Waveform  
<img src="images/waveform_failure.png" width="500"/>

---

## ⚙️ Ports Summary

| Port        | Description                    |
|-------------|--------------------------------|
| `clk`       | System clock                   |
| `reset`     | System reset                   |
| `user_input`| 4-bit binary input for password|
| `auth_success` | Signal enabling instruction flow |

---

## 🛠️ Implementation

- Code written in **Verilog HDL**  
- Simulation performed using `.hex` files as instruction memory  
- Modular architecture ensures reusability and scalability

---

## ✅ Advantages

- Hardware-level access control  
- Low latency and tamper-resistant  
- Customizable and scalable design  
- Useful for **IoT**, **medical**, **industrial**, and **SoC** systems

---

## 🚀 Applications

- Secure embedded systems  
- IoT authentication modules  
- Custom chip design for secure environments  
- Educational tools in computer architecture

---

## 📌 Future Scope

- Integrate dynamic password memory  
- Expand to pipelined/multicycle architecture  
- Interface with external devices (UART, switches)  
- Include timeout/lockout mechanism for failed attempts

---

## 🧾 License

This project is released under the [MIT License](LICENSE).

