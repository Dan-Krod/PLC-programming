# Assignment Report – Lab 3  
## Investigation of Timer Operations and Memory Structure in SIMATIC STEP 7 – Traffic Light Control  
---

## 🧩 Task Description

Develop a traffic light control system in **SIMATIC STEP 7**, using memory blocks and timer functions. Configure relevant memory regions and simulate sequential light transitions using **S7-PLCSIM**. Timer types applied include **S_PULSE** and **S_ODT**.

All source materials, screenshots, logic diagrams, and symbolic address mappings are located in the `src/` folder.

---

## 🎯 Objectives  

- [ ] Explore S7 memory architecture (inputs, outputs, markers, and timers)  
- [ ] Implement On-Delay and Pulse timers in the traffic light logic  
- [ ] Create and comment logic segments in **OB1**  
- [ ] Simulate time-driven control using S7-PLCSIM  
- [ ] Analyze switching timing and output behavior  

---

## 📂 Folder Contents (`src/`)  

```plaintext
📁 src/
├── symbol_table.png                       # Table of assigned symbolic addresses
├── OB1_logic_segments.png                 # Screenshot of full logic blocks
├── program_comments.md                    # Detailed segment-level explanations
├── timing_diagram.png                     # Visualized light sequence with T1–T4
├── simulation_cycle_results_#1.png        # Captured simulation of full traffic light loop
└── simulation_cycle_results_#2.png        # Captured simulation of full traffic light loop
```

---

## ⚙️ Procedure Overview  

### 🔹 Initial Setup  

✅ PLC type: VIPA 200V series  
✅ Project created and OB1 opened  
✅ Inputs, outputs, markers, and timers assigned symbolically:  
- `I2.0` — Start button  
- `Q2.0` — Green light  
- `Q2.1` — Yellow light  
- `Q2.2` — Red light  
- Timers:  
  - `T1` – Red (17s)  
  - `T2` – Green (13s)  
  - `T3` – Yellow after green (3s)  
  - `T4` – Yellow after red (2s)  
  - `T5` – Initial delay (On-Delay)

_All symbolic mappings are defined in `symbol_table.csv`._

---

### 🔹 Logic Structure (OB1 Segments)  

The logic is structured into four main OB1 segments:

1. **Startup & Initial Impulse**  
   - Elements: `I2.0`, `T5 (S_ODT)`, `M0.2`, `T2 (S_PULSE)`  
   - Output: `Q2.0` – Green

2. **Green Segment**  
   - Timer: `T2`  
   - Output: `Q2.0`

3. **Yellow Segment**  
   - Timer: `T3` or `T4` depending on direction  
   - Output: `Q2.1`

4. **Red Segment**  
   - Timer: `T1`  
   - Output: `Q2.2`

> Detailed block comments and logic breakdowns are documented in `program_comments.pdf`.  
> Logic visualization in `OB1_logic_segments.png`.

---

## ⏱ Light Timing Cycle  

<table>
  <thead>
    <tr>
      <th>Phase</th>
      <th>Output</th>
      <th>Timer</th>
      <th>Duration</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Green Light</td>
      <td>Q2.0</td>
      <td>T2</td>
      <td>13 s</td>
    </tr>
    <tr>
      <td>Yellow After Green</td>
      <td>Q2.1</td>
      <td>T3</td>
      <td>3 s</td>
    </tr>
    <tr>
      <td>Red Light</td>
      <td>Q2.2</td>
      <td>T1</td>
      <td>17 s</td>
    </tr>
    <tr>
      <td>Yellow After Red</td>
      <td>Q2.1</td>
      <td>T4</td>
      <td>2 s</td>
    </tr>
    <tr>
      <td>Repeat</td>
      <td>—</td>
      <td>—</td>
      <td>—</td>
    </tr>
  </tbody>
</table>

Timing diagram illustration is in `timing_diagram.png`.

---

## ✅ Results & Reflection  

The traffic light control cycle executed flawlessly in the simulation. Transitions were smooth, and timers triggered correctly with no overlaps.  

- 🟢 Green light held for 13 seconds (`Q2.0`)  
- 🟡 Yellow triggered for 3 seconds after green (`Q2.1`)  
- 🔴 Red active for 17 seconds (`Q2.2`)  
- 🟡 Second yellow followed for 2 seconds before loop restart  

The simulation (`simulation_cycle_results.png`) confirmed all output timings were synchronized.  

Key outcomes:
- ✅ Timers configured and tested successfully in STEP 7  
- ✅ Symbolic memory layout enhanced code clarity  
- ✅ Loop cycling was deterministic and stable  
- ✅ Logic blocks are reusable and modular  

This lab strengthened understanding of time-controlled automation logic in real industrial scenarios.