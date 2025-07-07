# Assignment Report – Lab 2  
## Configuration of PLC and Programmer in SIMATIC Manager + Simulation in S7-PLCSIM  
---

## 🧩 Task Description

Set up and configure a VIPA 200V PLC system within **SIMATIC Manager (Step7)**. Develop and simulate logic using the **FBD (Function Block Diagram)** language in **S7-PLCSIM**. Supplement the logic design by generating a truth table, Karnaugh map, and minimized Boolean expressions.

_All reference files (program listings, tables, logic expressions, screenshots) are provided in the `src/` folder._

---

## 🎯 Objectives  

- [ ] Configure VIPA 200V series PLC modules in SIMATIC Manager  
- [ ] Develop a control logic program using FBD  
- [ ] Simulate and verify program behavior in **S7-PLCSIM**  
- [ ] Design and minimize logic using a truth table and Karnaugh map  
- [ ] Document all logical operations, outputs, and test results  

---

## 📂 Folder Contents (`src/`)  

```plaintext
📁 src/
├── FBD_Program_1.png                    # Screenshot of synthesized FBD program 1
├── FBD_Program_2.png                    # Screenshot of synthesized FBD program 2
├── truth_table_Q01_Q03.md               # Full truth table for outputs Q0.1 and Q0.3
├── karnaugh_map_Q01_Q03.png             # Karnaugh map visualization
├── minimized_logic_expressions.txt      # Final Boolean expressions for Q0.1 and Q0.3
├── simulation_results_PLCSIM_program_1.png       # Screenshot of simulation results of program 1 in S7-PLCSIM
└── simulation_results_PLCSIM_program_2.png       # Screenshot of simulation results of program 2 in S7-PLCSIM
```

---

## ⚙️ Procedure Overview  

### 🔹 Setup & Configuration  
✅ Launch SIMATIC Manager  
✅ Create new project with VIPA 200V PLC station  
✅ Add CPU and I/O modules according to provided specifications  
✅ Configure symbolic inputs:  
- I0.0 → A  
- I0.1 → B  
- I0.2 → C  
- I0.3 → D  
- I0.4 → E  

### 🔹 FBD Programming  
✅ Create OB1 block  
✅ Implement logic using FBD for Q0.1 and Q0.3  
✅ Organize operations in **Network blocks**, apply logical hierarchy  
✅ Save and compile without errors  

### 🔹 Logic Design (Boolean + Minimization)  
✅ Construct full **truth table** based on assignment variant  
✅ Apply **Karnaugh map** technique to minimize each output function  
✅ Document minimized Boolean expressions:
```plaintext
Q0.1 = A'·B·C'·D'·E'
Q0.3 = B'·C·D·E + A·B'·C·D + A·B'·C·E + A·B'·D·E
```

### 🔹 Simulation  
✅ Launch S7-PLCSIM  
✅ Load project and simulate I/O conditions  
✅ Test program responsiveness  
✅ Validate output correctness for all logical states  

---

## 🧠 Results & Reflection  

The lab objective was fully achieved. The entire development flow—from hardware configuration to logic synthesis, and final simulation—was successfully executed without runtime errors.

Key Results:
- 📌 Correct FBD logic synthesized and tested (`FBD_Program_1.png`, `FBD_Program_2.png`)
- 📌 Accurate truth table and minimized Karnaugh-based logic (`truth_table_Q01_Q03.pdf`, `karnaugh_map_Q01_Q03.png`)
- 📌 Logic outputs Q0.1 and Q0.3 behaved as expected across tested input permutations (`simulation_results_PLCSIM.png`)
- 📌 Clean, modular structure of project and reusability ensured via `project_OB1_backup.zip`

This assignment solidified hands-on skills in configuring PLC systems, applying formal logic design, and developing functional control solutions through visual programming paradigms. These competencies lay the groundwork for real-world automation and diagnostic scenarios.