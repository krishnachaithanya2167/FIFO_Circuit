# FIFO Circuit

## Overview

This project implements a **First-In-First-Out (FIFO) memory** using Verilog. FIFO memory is a type of buffer that outputs data in the same order it was input, ensuring first-in-first-out data processing. It's commonly used in digital systems to manage data flow between components operating at different speeds or with different data timing requirements.

## Features

- **Synchronous Design**: Both write and read operations are synchronized with the clock signal.
- **8-bit Data Width**: Each data word is 8 bits wide.
- **Depth of 16**: The FIFO can store up to 16 data words.
- **Status Indicators**:
  - **Full**: Indicates when the FIFO is full and cannot accept new data.
  - **Empty**: Indicates when the FIFO is empty and no data is available for reading.

## Repository Structure

```
📦 FIFO_Circuit
 ┣ 📂 work
 ┃ ┣ 📜 FIFO Circuit.cr.mti
 ┃ ┣ 📜 FIFO Circuit.mpf
 ┣ 📜 FIFO block diagram.png
 ┣ 📜 FIFO.png
 ┣ 📜 Waveform.png
 ┣ 📜 fifo_sync.v
 ┣ 📜 tb_fifo_sync.v
 ┣ 📜 vsim.wlf
 ┗ 📜 README.md
```

- **`fifo_sync.v`**: Verilog module defining the synchronous FIFO behavior.
- **`tb_fifo_sync.v`**: Testbench for simulating and verifying the FIFO module.
- **`FIFO block diagram.png`**: Visual representation of the FIFO architecture.
- **`FIFO.png`**: Additional diagram related to the FIFO design.
- **`Waveform.png`**: Simulation waveform showcasing the FIFO's operation.
- **`work/`**: Directory containing ModelSim project files.
- **`vsim.wlf`**: ModelSim waveform file.

## How It Works

The FIFO operates using two pointers:
- **Write Pointer**: Indicates where the next data word will be written.
- **Read Pointer**: Indicates where the next data word will be read from.

**Full Condition**: Occurs when the write pointer is one position behind the read pointer in a circular manner, indicating no more space to write new data.

**Empty Condition**: Occurs when both write and read pointers are at the same position, indicating no data is available for reading.

## How to Run the Simulation

1. **Requirements**:
   - **ModelSim**: A simulation tool for verifying HDL designs.

2. **Steps**:
   - Open ModelSim and create a new project.
   - Add the `fifo_sync.v` and `tb_fifo_sync.v` files to the project.
   - Compile both files to ensure there are no syntax errors.
   - Run the simulation using the testbench (`tb_fifo_sync.v`).
   - Observe the waveform to verify correct FIFO behavior. You can refer to `Waveform.png` for expected results.

## Simulation Results

The provided `Waveform.png` illustrates the FIFO's operation, including write and read cycles, and the status indicators for full and empty conditions.

## Future Improvements

- **Parameterization**: Modify the design to allow configurable data width and depth.
- **Asynchronous Design**: Implement asynchronous FIFO to handle different clock domains for write and read operations.
- **Error Handling**: Add overflow and underflow detection mechanisms to handle erroneous conditions gracefully.

## References

- [Synchronous_FIFO by sahu2201](https://github.com/sahu2201/Synchronous_FIFO): A similar FIFO implementation in Verilog.
- [16-stage-FIFO by snmarathe](https://github.com/snmarathe/16-stage-FIFO): Verilog code for a 16-stage FIFO memory.

---

Feel free to contribute to this project by forking the repository and submitting pull requests. For any questions or suggestions, please open an issue in the repository.

