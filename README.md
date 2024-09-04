# Security-Vault-FPGA-project

## Project Overview

This project, named "Security Vault," is part of the Digital Hardware Design lab. The objective is to implement a security vault system using Verilog and an FPGA board. The system is controlled by a finite state machine (FSM) with distinct states and transitions to manage user access.

## Team Members

- **Akash Tayade** (BT21ECE085)
- **Himanshu Kohade** (BT21ECE086)
- **Mihir Sangale** (BT21ECE080)
- **Manav Pandya** (BT21ECE098)

## Aim

To implement the DHD project "Security Vault" using Verilog and an FPGA board.

## Apparatus

- FPGA KIT
- Quartus Software

## Working

The Verilog code implements a security vault system controlled by an FSM. Here's a brief overview of its functionality:

1. **Initialization**
   - On reset (`reset_n` signal), the system initializes to the IDLE state with all LEDs turned off.

2. **State Transition**
   - The FSM transitions between states based on inputs and the current state.
   - In the IDLE state, if the `sensor_entrance` signal is activated, it transitions to the WAIT_PASSWORD state.

3. **Password Entry**
   - In the WAIT_PASSWORD state, the system waits for a predefined duration (`counter_wait`) before checking the entered password.
   - If the correct password (`password_1` and `password_2`) is entered within the time limit, it transitions to the RIGHT_PASS state; otherwise, it transitions to the WRONG_PASS state.

4. **System Behavior**
   - In the RIGHT_PASS state, the system blinks the green LED to indicate successful access.
   - If the `sensor_exit` signal is activated in the RIGHT_PASS state, it returns to the IDLE state.
   - If both entrance and exit sensors are active, it transitions to the STOP state.
   - In the STOP state, it continuously blinks the red LED until the correct password is entered again.

5. **LED Output**
   - LED outputs (`RED_LED` and `GREEN_LED`) provide visual feedback on the system's state.

## State Diagram

The FSM includes states such as IDLE, WAIT_PASSWORD, RIGHT_PASS, WRONG_PASS, and STOP, with transitions based on sensor inputs and password correctness.
![image](https://github.com/user-attachments/assets/7c725b8d-283b-4be2-83a7-598344c05b16)


## Code Overview

1. **Counter Management**
   - An `always` block manages a counter (`counter_wait`) for timing within the security vault module, triggering operations on the positive clock edge or reset signal.

2. **Finite State Machine**
   - Another `always` block defines the FSM behavior, determining the next state based on the current state and various inputs.

3. **LED and Display Control**
   - A third `always` block governs the LED outputs and hexadecimal displays based on the FSM state, ensuring visual feedback aligns with the system's state.

## Output

The system provides visual feedback through LED indicators and hexadecimal displays, reflecting the current state and actions of the security vault system.

## Full Project Report
For a detailed explanation of the project, please refer to the full project report available [here](https://drive.google.com/file/d/1O5SnSSdRiz8tldTs2gE2HY6uC1a7dmNr/view?usp=sharing).

