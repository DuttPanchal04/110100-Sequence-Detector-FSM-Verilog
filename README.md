# 110100 Sequence Detector FSM in Verilog

## Project Overview
This project implements a finite state machine in Verilog to detect the binary sequence `110100` in a serial input stream. The sequence detector is designed to recognize this specific 6-bit pattern and output a signal (e.g., `out`) when the pattern is matched.

## Features
- **Input**: A serial bit stream, usually represented by a single-bit input `in`.
- **Output**: A signal `out` that is asserted (set to `1`) when the sequence `110100` is detected in the input stream.
- **FSM Design**: The FSM is constructed using the principles of state transitions. Each state represents a portion of the detected sequence, and transitions occur based on the incoming bit.
- **Clocking**: The FSM operates synchronously with a clock signal, updating the state on every rising edge of the clock.
- **Reset**: The FSM includes an asynchronous reset to initialize the system to its default state.

## State Machine Description
The FSM is designed to have 6 states, one for each position in the sequence `110100`. Below is a description of the states:

1. **State 0 (Initial State)**: The machine starts here, waiting for the first bit of the sequence, `1`.
2. **State 1**: The first `1` in the sequence is detected. The machine waits for the second `1`.
3. **State 2**: The second `1` is detected. The machine transitions to waiting for `0`.
4. **State 3**: The first `0` is detected after two `1`s. The machine waits for the next `1`.
5. **State 4**: The next `1` in the sequence is detected. The machine waits for the last `0`.
6. **State 5**: The final `0` in the sequence is detected, indicating the full sequence `110100` has been matched. The FSM outputs a `out` signal and returns to the initial state to detect the next occurrence of the sequence.

The FSM operates as follows:
- The state transitions based on the incoming bit.
- If the bit sequence `110100` is successfully detected, the output `out` is asserted high (`1`).
- Once the sequence is detected, the FSM returns to the initial state, ready to detect the next occurrence.

## Inputs and Outputs

### Inputs
- **clk**: Clock signal used to synchronize the FSM.
- **rst**: Asynchronous reset signal to initialize the FSM to the initial state.
- **in**: Serial input bit that is used to match the `110100` sequence.

### Outputs
- **detected**: A signal that is high (`1`) when the sequence `110100` is detected in the input stream.

## Output Waveform

![110100 Sequence Detector FSM in Verilog](https://github.com/user-attachments/assets/92a92b96-00e9-4be5-a501-349af7001a86)

## Design Flow
1. **Reset and Initialization**: The FSM begins at State 0 when the reset signal is asserted.
2. **Input Processing**: On every rising edge of the clock, the FSM reads the `in` input and determines the next state based on the current state and the input value.
3. **State Transition**: The FSM transitions through its states according to the sequence `110100`. When the full sequence is detected, the `out` signal is asserted high (`1`), and the FSM returns to State 0 to start detecting the next occurrence.
4. **Output Assertion**: When the sequence `110100` is matched, the `out` signal is asserted for one clock cycle.

## State Diagram
A state diagram can be used to visualize the transitions between states and the conditions for each transition based on the incoming bit (`in`).

## Conclusion
This FSM-based sequence detector effectively detects the specific sequence `110100` in a serial input stream. It operates synchronously with the clock and provides an output signal (`out`) whenever the sequence is detected. The design ensures that the system is ready to detect multiple occurrences of the sequence in a continuous input stream.

## Contact

- [Linkedin](https://www.linkedin.com/in/dattpanchal04/)
- Email: dattpanchal2904@gmail.com
