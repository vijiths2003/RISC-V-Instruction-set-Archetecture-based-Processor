# RISC-V Instruction Set Architecture-Based Processor

This repository contains the implementation of a RISC-V processor, designed and verified based on the RISC-V Instruction Set Architecture (ISA). The project aims to provide an efficient and modular design for a processor capable of executing basic RISC-V instructions, making it suitable for educational and research purposes.

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Design Architecture](#design-architecture)
- [Directory Structure](#directory-structure)
- [Simulation and Testing](#simulation-and-testing)
- [Tools Used](#tools-used)
- [How to Run](#how-to-run)
- [Future Work](#future-work)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

The project involves the design and verification of a RISC-V processor capable of executing a subset of the RISC-V instruction set. The implementation adheres to the modular design principles, ensuring scalability and flexibility for further extensions or enhancements.

This processor has been developed with hardware description languages (HDLs) to ensure compatibility with modern simulation and synthesis tools.

---

## Features

- Implements a subset of the RISC-V Instruction Set Architecture (ISA).
- Modular design, including individual modules for the ALU, Control Unit, and Register File.
- Support for:
  - Arithmetic and Logical Instructions
  - Memory Access Instructions
  - Control Flow Instructions (Branch/Jump)
- Testbench for functional verification.

---

## Design Architecture

### Core Components:
1. **Instruction Fetch Unit (IFU):** Fetches instructions from memory.
2. **Instruction Decode Unit (IDU):** Decodes the fetched instruction into control signals.
3. **Execution Unit (EXU):** Handles arithmetic and logical operations.
4. **Memory Access Unit (MAU):** Reads and writes to memory.
5. **Write-Back Unit (WBU):** Writes results back to the register file.

### Data Path:
The processor implements a pipelined data path for efficient execution of instructions.

---

## Directory Structure

```
├── Processor
│   ├── ALU.v                        # Arithmetic Logic Unit
│   ├── CONTROL.v                    # Control Unit
│   ├── DATAPATH.v                   # Processor Datapath
│   ├── INST_MEM.v                   # Memory Module
│   ├── REG_FILE.v                   # Register File
│   └── IFU.v                        # Instruction fetch unit
│   └── PROCESSOR.v                  # Main Code
│   └── Processor_tb.v               # Testbench code
│   └── output_wave.vcd              # Output file
└── README.md            # Project Overview
```

---

## Simulation and Testing

The functionality of the processor is validated using testbenches written for individual modules as well as the overall processor. The simulation covers:

- Instruction execution for all supported types (Arithmetic, Logical, Memory, Branch).
- Corner cases to ensure stability and correctness.

---

## Tools Used

- **HDL:** Verilog/SystemVerilog
- **Simulation:** Icarus Verilog (iverilog) and GTKWave
- **Version Control:** Git and GitHub

---

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/vijiths2003/RISC-V-Instruction-set-Archetecture-based-Processor.git
   ```
2. Navigate to the project directory:
   ```bash
   cd RISC-V-Instruction-set-Archetecture-based-Processor
   ```
3. Compile the Verilog files using Icarus Verilog (iverilog):
   ```bash
   iverilog -o processor_sim processor_tb.v
   ```
   This command compiles all the source files and the processor testbench into a simulation executable called `processor_sim`.

4. Run the simulation:
   ```bash
   vvp processor_sim
   ```
   This command executes the compiled simulation and generates a `.vcd` file for waveform analysis.

5. View the waveforms using GTKWave:
   ```bash
   gtkwave output_wave.vcd
   ```
 Use GTKWave to analyze signal behavior and verify the functionality of the processor.

---

## Future Work

- Extend support to additional RISC-V instruction types, including floating-point and vector instructions.
- Optimize pipelining to improve execution speed.
- Develop an assembler for generating machine code for the processor.

---

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-name`).
3. Commit your changes (`git commit -m 'Add feature'`).
4. Push to the branch (`git push origin feature-name`).
5. Open a pull request.

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.
