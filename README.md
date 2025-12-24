# RTL Simulation Projects

This repository contains a collection of digital logical circuits and simulations implemented in Verilog. It serves as a workspace for exploring fundamental digital design concepts, ranging from basic logic gates to state machines and signal generators.

## 📂 File Structure

```text
E:\PROJECTS\RTL_SIMULATION
├── D_flipflop/                 # D Flip-Flop Implementation
│   ├── dff.v                   # D Flip-Flop source code
│   └── dff_tb.v                # Testbench for D Flip-Flop
│
├── Ring Oscillator/            # 3-Stage Ring Oscillator
│   ├── ring_oscillator.v       # Oscillator source with parameterized delay
│   └── tb_ring_oscillator.v    # Testbench for simulation
│
├── Sequence_Detector_0110/     # "0110" Sequence Detector
│   ├── Mealy Machine without overlaping/
│   │   ├── detector_mealy.v
│   │   └── tb_detectmealy.v
│   └── Moore Machine without overlaping/
│       ├── detect.v
│       └── tb_detector.v
│
├── full_adder/                 # Full Adder Circuit
│   ├── full_adder.v            # Full Adder source code
│   └── full_adder_tb.v         # Testbench
│
└── wave_generator/             # Waveform Generation
    ├── generator.v             # Verilog signal generator
    ├── wave.py                 # Python script for wave generation/plotting
    └── csv2mem.py              # Utility to convert CSV data to memory files
```

## 📝 Project Details

### 1. D Flip-Flop (`D_flipflop`)
A fundamental memory element in digital circuits. This project implements a D Flip-Flop triggered by a clock edge, capturing the value of the input 'D' at the specific moment.

### 2. Ring Oscillator (`Ring Oscillator`)
Implementation of a **three-stage NOT gate ring oscillator**.
- **Features**: Includes a parameterized delay for each stage to control oscillation frequency.
- **Use Case**: Commonly used for on-chip clock generation, delay measurement, and as true random number generator sources.
- *See `Ring Oscillator/readme.md` for more details on simulation results and advantages/disadvantages.*

### 3. Sequence Detector 0110 (`Sequence_Detector_0110`)
A Finite State Machine (FSM) designed to detect the non-overlapping binary sequence **"0110"**.
- **Mealy Machine**: The output is determined by the current state and the current input.
- **Moore Machine**: The output is determined solely by the current state.

### 4. Full Adder (`full_adder`)
A combinational logic circuit that performs addition of three bits:
- Inputs: `A`, `B`, `Cin` (Carry In)
- Outputs: `Sum`, `Cout` (Carry Out)

### 5. Wave Generator (`wave_generator`)
A hybrid project exploring signal generation and processing.
- **Python (`wave.py`)**: specific script using `numpy` and `matplotlib` to generate and visualize composite sine waves (e.g., 10Hz + 50Hz).
- **Verilog**: Modules to handle signal generation or processing within the hardware simulation environment.

## 🚀 Usage
To run these simulations, you will need a Verilog simulator such as **Icarus Verilog**.

```bash
# Example: Running the Ring Oscillator simulation
cd "Ring Oscillator"
iverilog -o ring_osc tb_ring_oscillator.v ring_oscillator.v
vvp ring_osc
```
