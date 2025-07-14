# 🛠 PLC-Programming – Siemens S7 Labs with FBD & Simulation(STEP 7) 

This repository contains a structured set of lab assignments focused on Siemens S7 PLC programming using **Function Block Diagram (FBD)** logic in **SIMATIC STEP 7 (Professional 2017)** with simulations conducted via **S7-PLCSIM**. It serves as a practical learning suite for students and engineers engaged in industrial automation training.

---

## 📁 Repository Structure

```
PLC-programming/
├── lab_work_1/
│   ├── assignment/         # Instructional assignment file (Lab 1)
│   └── src/                # Installation instructions, screenshots, configs
├── lab_work_2/
│   ├── assignment/         # Instructional assignment file (Lab 2)
│   └── src/                # FBD program visuals, truth tables, Karnaugh maps
├── lab_work_3/
│   ├── assignment/         # Instructional assignment file (Lab 3)
│   └── src/                # OB1 logic diagrams, timing tables, simulation outputs
├── lab_work_4/
│   ├── assignment/         # Instructional assignment file (Lab 4)
│   └── src/                # Code lock networks, memory tracking, simulation cycles
├── README.md               # This documentation file
```
Each `lab_work_X` folder contains:
- `assignment/` → a structured lab brief with task description, objectives, logic checklist, and final remarks  
- `src/` → reference files such as logic screenshots, truth tables, Karnaugh maps, simulation results, symbol tables, and commentary

---

## 🔧 Technologies & Tools Used

| Component          | Description                                           |
|--------------------|-------------------------------------------------------|
| PLC Series         | Siemens S7 (VIPA 200V modules)                        |
| Programming Tool   | SIMATIC STEP 7 Professional 2017                      |
| Simulation Platform| S7-PLCSIM                                             |
| Logic Language     | **Function Block Diagram (FBD)**                      |
| Timer Types Used   | `S_PULSE`, `S_ODT`, `S5T` format (STEP 7 standard)    |
| Logic Features     | Symbolic mapping, SR-triggers, memory structuring     |
| Memory Structures  | Inputs (I), Outputs (Q), Markers (M), Timers (T) |
| Design Techniques  | SR-triggers, symbolic mapping, Boolean minimization |

---


## 🧪 Lab Overview

There are **4 practical lab assignments**, each focusing on different aspects of industrial automation and PLC workflow design:

| Lab # | Title                                  | Focus Area                                  |
|-------|----------------------------------------|----------------------------------------------|
| 1     | STEP 7 Installation & Setup            | Software configuration for PLC programming   |
| 2     | FBD Programming & Boolean Design       | Logic synthesis, simulation, Karnaugh mapping|
| 3     | Timer Logic – Traffic Light Control    | Sequential time-based control with S7 timers |
| 4     | Code Lock System with SR-Logic         | Secure input sequence, latch memory logic    |

All lab tasks are fully documented and designed for reproducible execution. All tasks use OB1 blocks with symbolic addressing and modular design methodology.

---

## 📌 Summary

This repository provides a coherent learning path for mastering Siemens S7 logic design using structured lab work. Emphasis is placed on:
- Visual logic building using FBD  
- Simulation with PLCSIM  
- Use of memory markers and timers  
- Sequential control for industrial logic

Assignments can serve as templates for real-world applications in automation, diagnostics, and control system design.

---

## ⚠️ Usage & Copyright

All materials provided in this repository are original and intended for educational and training purposes. **Copying, distributing, or reproducing any part of this content without explicit permission from the author is strictly prohibited.**

> If you'd like to reuse, adapt, or reference any part of the materials — please contact the repository author.
