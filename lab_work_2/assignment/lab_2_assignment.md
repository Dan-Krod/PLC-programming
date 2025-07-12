# 🧪 Assignment – Lab 2  
## Configuration of VIPA PLC in SIMATIC Manager & Logic Simulation in S7-PLCSIM  

---

## 🧩 Task Overview  

In this lab, you'll configure a VIPA 200V PLC system using **SIMATIC Manager (STEP 7)**, create control logic using **Function Block Diagram (FBD)** language, and simulate system behavior via **S7-PLCSIM**. Logic design should be supported by a truth table, Karnaugh map, and Boolean minimization techniques.

_All supplementary materials, including logic files and diagrams, are available in the `src/` folder. Detailed procedures are described in `lab_2_methodological_instructions.pdf`._

---

## 🎯 Objectives  

- [ ] Set up VIPA 200V PLC configuration in SIMATIC Manager  
- [ ] Design FBD-based control logic for outputs Q0.1 and Q0.3  
- [ ] Simulate behavior using S7-PLCSIM  
- [ ] Create and minimize logic expressions using truth tables and Karnaugh maps  
- [ ] Document logical structure and program responses  

---

## 📂 Reference Folder: `src/`  

```plaintext
📁 src/
├── FBD_Program_1.png                  
├── FBD_Program_2.png                  
├── truth_table_Q01_Q03.md            
├── karnaugh_map_Q01_Q03.png          
├── minimized_logic_expressions.txt   
├── simulation_results_PLCSIM_program_1.png 
└── simulation_results_PLCSIM_program_2.png 
```

---

## ⚙️ Instructions  

### 🔹 Step 1: PLC Station Setup  
- Launch SIMATIC Manager and create a new project  
- Add VIPA 200V CPU and I/O modules  
- Assign symbolic addresses for inputs:  
  - I0.0 → A  
  - I0.1 → B  
  - I0.2 → C  
  - I0.3 → D  
  - I0.4 → E  

### 🔹 Step 2: FBD Programming  
- Create OB1 block for the control logic  
- Implement logic targeting Q0.1 and Q0.3 outputs using FBD  
- Use Network blocks to maintain hierarchical clarity  
- Save and compile the project (ensure no errors)  

### 🔹 Step 3: Logic Analysis  
- Build a truth table for all input permutations  
- Use Karnaugh maps to simplify logic expressions  
- Document final minimized Boolean forms  
```plaintext
Q0.1 = A'·B·C'·D'·E'
Q0.3 = B'·C·D·E + A·B'·C·D + A·B'·C·E + A·B'·D·E
```

### 🔹 Step 4: Simulation in S7-PLCSIM  
- Load your project into S7-PLCSIM  
- Simulate input states  
- Verify correct logical outputs  
- Capture screenshots of successful program execution  

---

## 🧾 Final Notes  

Once completed, your setup should demonstrate proper PLC configuration, stable simulation output, and well-documented logic design. Use the methodological guide for any additional clarification (`lab_2_methodological_instructions.pdf`). You may also use this document as a reference for future labs and logic structuring.

> When logic flows cleanly and all outputs behave — you know you’re on the right track. ⚡