# 🧪 Assignment – Lab 3  
## Timer Operations and Memory Management in SIMATIC STEP 7: Traffic Light Control

---

## 🧩 Task Overview  

In this lab, you’ll develop a traffic light control system using **SIMATIC STEP 7** and simulate its behavior in **S7-PLCSIM**. The system will use timer functions (**S_PULSE**, **S_ODT**) and memory blocks to manage sequential light transitions. This assignment emphasizes memory structuring, time-based automation logic, and simulation analysis.

> Refer to `lab_3_methodological_instructions.pdf` for full details, signal mapping, and logic breakdowns.

---

## 🎯 Objectives  

- [ ] Configure inputs, outputs, markers, and timers for control logic  
- [ ] Design time-driven logic segments using S7 timers  
- [ ] Implement traffic light functionality in **OB1** using symbolic addressing  
- [ ] Simulate and verify system performance using S7-PLCSIM  
- [ ] Document output behavior and timing accuracy  

---

## 📂 Reference Folder: `src/`  

```plaintext
📁 src/
├── symbol_table.png                     
├── OB1_logic_segments.png              
├── program_comments.md                 
├── timing_diagram.png                  
├── simulation_cycle_results_#1.png     
└── simulation_cycle_results_#2.png     
```

---

## ⚙️ Instructions  

### 🔸 Step 1: Initial Setup  
- Create a STEP 7 project for VIPA 200V PLC  
- Assign symbolic memory areas (I, Q, M, T) per `symbol_table.csv`:  
  - I2.0 → Start  
  - Q2.0 → Green  
  - Q2.1 → Yellow  
  - Q2.2 → Red  
  - T1–T5 for phase delays and impulses  

### 🔸 Step 2: OB1 Logic Structure  
Organize the logic into four functional segments:

<table>
  <thead>
    <tr>
      <th>Segment</th>
      <th>Timer</th>
      <th>Output</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>🔵 Startup</td>
      <td>T5 (<code>S_ODT</code>)</td>
      <td>M0.2, then Q2.0</td>
      <td>Initiate Green Phase</td>
    </tr>
    <tr>
      <td>🟢 Green</td>
      <td>T2 (<code>S_PULSE</code>)</td>
      <td>Q2.0</td>
      <td>Hold for 13s</td>
    </tr>
    <tr>
      <td>🟡 Yellow</td>
      <td>T3 or T4</td>
      <td>Q2.1</td>
      <td>3s after green, 2s after red</td>
    </tr>
    <tr>
      <td>🔴 Red</td>
      <td>T1</td>
      <td>Q2.2</td>
      <td>Hold for 17s</td>
    </tr>
  </tbody>
</table>

- Use FBD or LAD style (per guide)  
- Apply timer blocks and internal markers  
- Comment each network segment (see `program_comments.md`)  
- Compile without errors  

### 🔸 Step 3: Simulation  
- Open S7-PLCSIM and load the compiled project  
- Simulate input cycles, observe output timing  
- Capture loop transitions and validate proper cycling  
- Use `timing_diagram.png` to compare against expected durations  

---

## 🧾 Final Notes  

Once completed, your traffic light program should exhibit smooth, time-controlled transitions, proper symbolic memory usage, and stable simulation results. This assignment is designed to reinforce core concepts of **industrial timing control** and memory mapping in PLC environments.

> When timers and transitions fall perfectly into place, automation flows like clockwork. 🕒