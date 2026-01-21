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

<img width="943" height="400" alt="image" src="https://github.com/user-attachments/assets/45cccb48-d316-4c7b-8b69-dbb285fb259b" />


### Data Path Logic

The design uses a dedicated adder and a multiplexer to update the target register within a single clock cycle when the PIM enable signal is asserted.

---

## Simulation Results

The logic was verified using the Vivado Simulator to ensure the hardware accurately reflects the intended design.

* **Test Case:** Preloading  with a base value and adding a secondary input via the PIM opcode.
* **Observation:** The register value updates immediately on the next clock edge following the `i_pim_en` pulse.

<img width="948" height="665" alt="image" src="https://github.com/user-attachments/assets/a9ac5316-b554-4208-889a-673c3164cfaa" />


