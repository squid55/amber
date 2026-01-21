# Amber-PIM: Initial Exploration of Register-Level PIM Concepts

This project utilizes the open-source Amber ARMv2-compatible core to study the fundamental integration of Processing-In-Memory (PIM) concepts. The current focus is on modifying the register bank architecture to evaluate data-path efficiency and control logic for memory-centric computing.

---

## Project Objectives

* **Architectural Analysis:** Understanding the trade-offs of placing arithmetic units within the register file versus the standard ALU.
* **Hardware Modification:** Customizing the `a23_register_bank.v` to support instruction-triggered internal operations.
* **Functional Verification:** Ensuring correct data flow and timing through RTL simulation.

---

## Current Implementation

The current version implements a basic addition unit within the register bank to test the control interface.

### Control Signals

* **i_pim_en:** Activation signal for the PIM logic path.
* **i_pim_opcode [2:0]:** 3-bit operation code.
* `3'b001`: Addition ()



### Data Path Logic

The design uses a dedicated adder and a multiplexer to update the target register within a single clock cycle when the PIM enable signal is asserted.

---

## Simulation Results

The logic was verified using the Vivado Simulator to ensure the hardware accurately reflects the intended design.

* **Test Case:** Preloading  with a base value and adding a secondary input via the PIM opcode.
* **Observation:** The register value updates immediately on the next clock edge following the `i_pim_en` pulse.

<img width="1067" height="453" alt="image" src="https://github.com/user-attachments/assets/0536a33b-58b3-4ca1-9ef9-da821419f2b9" />
<img width="1067" height="453" alt="image" src="https://github.com/user-attachments/assets/393cd892-a73f-4ef8-a1f7-7101e14fe3c2" />
<img width="1067" height="453" alt="image" src="https://github.com/user-attachments/assets/5f2bbaff-6336-40e1-845a-416f59a8e4b4" />

