# Assignment Report – Lab 4  
## Timer Operation and Memory Structure in SIMATIC STEP 7 – Code Lock Control System  
---

## 🧩 Task Description 

Design and implement a digital code lock using **SIMATIC STEP 7**, with a specific input sequence (0-6-1-3) to unlock the system. The control algorithm uses SR-trigger logic and memory markers. The lock opens for a set time if the correct sequence is entered; otherwise, it resets.

All source files, screenshots, symbolic tables, and program descriptions are located in the `src/` folder.

---

## 🎯 Objectives  

- [ ] Explore memory blocks (M), inputs (I), and outputs (Q) in S7 controllers  
- [ ] Use SR-triggers to track step-by-step code entry  
- [ ] Design a logic sequence that handles correct and incorrect input  
- [ ] Implement timing control for lock activation  
- [ ] Simulate behavior using **S7-PLCSIM** and analyze lock states  

---

## 📂 Folder Contents (`src/`)  

```plaintext
📁 src/
├── symbol_table_code_lock.csv         # Symbolic address mappings (I/Q/M)
├── code_lock_OB1_networks.pdf         # Full screenshot of logic networks in OB1
├── block_descriptions.md              # Commentary on program logic and each network
├── code_sequence_result_log.txt       # Step-by-step state transitions during testing
├── simulation_output_lock_cycle.png   # Visual result of lock opening and closing sequence
```

---

## ⚙️ System Description  

The code lock expects the user to enter the sequence: **0 → 6 → 1 → 3**  
If entered correctly, the lock opens for **3.11 seconds**, then automatically closes.

### 🔹 Implementation Strategy  
- Memory flags (`M1.0`, `M1.2`, `M1.4`, `M1.6`, etc.) store valid input steps  
- Buttons wired to inputs:  
  - `I0.0` → Key “0”  
  - `I0.6` → Key “6”  
  - `I0.1` → Key “1”  
  - `I0.3` → Key “3”

### 🔹 Logic Summary (by Network)  

1. **Network 1**:  
   Handles first digits and SR-triggered memory tracking.  
   Inputs activate `M20.0` to `M23.0` if correct key pressed in order.

2. **Network 2**:  
   Activates pulse timer `S5T#3S110MS` when full sequence is correct.  
   Sets `M1.6` (lock open) and starts duration tracking.

3. **Networks 3–6**:  
   Handle individual digit presses with positive edge detection (P):  
   `M10.0` for “0”, `M11.0` for “6”, etc.  
   These flags reset if incorrect digit follows.

4. **Network 7**:  
   Logic check for full code: `M20.0 ∧ M21.0 ∧ M22.0 ∧ M23.0`  
   If true → triggers lock opening condition (`M90.0 = 1`)

---

## ⏱ Timing & Behavior  

<table>
  <thead>
    <tr>
      <th>Sequence Step</th>
      <th>Input</th>
      <th>Memory Bit</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1st</td>
      <td>I0.0</td>
      <td>M20.0</td>
      <td>Correct key “0” pressed</td>
    </tr>
    <tr>
      <td>2nd</td>
      <td>I0.6</td>
      <td>M21.0</td>
      <td>Key “6”, after “0”</td>
    </tr>
    <tr>
      <td>3rd</td>
      <td>I0.1</td>
      <td>M22.0</td>
      <td>Key “1”, after “6”</td>
    </tr>
    <tr>
      <td>4th</td>
      <td>I0.3</td>
      <td>M23.0</td>
      <td>Final key “3” → unlock!</td>
    </tr>
  </tbody>
</table>

- Timer: `S_PULSE` set to `S5T#3S110MS` (lock opens for 3.11s)  
- Output controlled via marker `M2.0`  
- Full cycle visualized in `simulation_output_lock_cycle.png`  

---

## ✅ Results & Reflection  

Simulation showed expected functionality across multiple test inputs:

- ✅ Entering incorrect digits resets the sequence  
- ✅ Only exact 0-6-1-3 opens the lock  
- ✅ Lock remains open for 3.11 seconds, then returns to secure state  
- ✅ SR-latch behavior verified using marker bits and conditional resets  
- ✅ No glitching from repeated digits (e.g. 2-6-6-0 did not trigger unlock)  

> All logical flow and behavior analysis is provided in `code_sequence_result_log.txt` and `block_descriptions.pdf`.

This lab built strong hands-on skills in managing state-based logic using memory bits, edge detection, and timers within S7 PLC systems. The code lock algorithm could be easily adapted into secure access control or keypad-controlled automation scenarios.