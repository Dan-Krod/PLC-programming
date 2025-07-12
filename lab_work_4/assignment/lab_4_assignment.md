# 🧪 Assignment – Lab 4  
## Code Lock Control with Memory and Timing Logic in SIMATIC STEP 7

---

## 🧩 Task Overview  

In this lab, you'll design a digital code lock using **SIMATIC STEP 7**, triggered by a specific input sequence: **0 → 6 → 1 → 3**. The control logic uses SR-trigger networks, memory markers, and pulse timers to manage validation and timed unlocking. Simulation is done using **S7-PLCSIM**.

> Full implementation guidance and logic references are available in `lab_4_methodological_instructions.pdf`.

---

## 🎯 Objectives  

- [ ] Assign and configure symbolic memory, input, and output areas  
- [ ] Use SR-trigger logic and memory bits to track input steps  
- [ ] Design logic that unlocks only when the full correct sequence is entered  
- [ ] Add timer logic for timed unlocking and automatic reset  
- [ ] Simulate all behaviors and transitions in S7-PLCSIM  

---

## 📂 Reference Folder: `src/`  

```plaintext
📁 src/
├── symbol_table_code_lock.csv         
├── code_lock_OB1_networks.pdf         
├── block_descriptions.md              
├── code_sequence_result_log.txt       
└── simulation_output_lock_cycle.png   
```

---

## ⚙️ Instructions  

### 🔸 Step 1: Memory & Input Mapping  

- Inputs:  
  - `I0.0` → “0”  
  - `I0.6` → “6”  
  - `I0.1` → “1”  
  - `I0.3` → “3”  
- Memory bits used:  
  - `M20.0–M23.0` → Valid input states  
  - `M10.0–M13.0` → Edge detection  
  - `M1.6` and `M2.0` → Unlock state and output  

Refer to `symbol_table_code_lock.csv` for full memory mapping.

### 🔸 Step 2: Logic Construction in OB1  

1. Use **SR triggers** to manage progression through input sequence  
2. Apply edge detection on each digit to control sequence tracking  
3. Reset sequence if incorrect input is detected  
4. Use Boolean condition: `M20.0 ∧ M21.0 ∧ M22.0 ∧ M23.0` to confirm correct code  
5. Trigger **pulse timer (`S_PULSE`)** to open lock for 3.11 seconds  

Reference logic segments and comments in `code_lock_OB1_networks.pdf` and `block_descriptions.md`.

### 🔸 Step 3: Simulation  

- Launch project in S7-PLCSIM  
- Simulate the full unlock flow by entering digits sequentially  
- Observe behavior when incorrect digits are entered  
- Capture and confirm output timing behavior  

Output cycle is visualized in `simulation_output_lock_cycle.png`.

---

## 🧾 Final Notes  

Upon completion, your code lock logic should:
- Respond only to the exact input sequence (0-6-1-3)  
- Remain locked when sequence is broken  
- Open for the specified duration (3.11s) when correct sequence is met  
- Reset properly using edge detection and marker bits  

> Precise memory logic yields reliable access control — no shortcuts allowed. 🧠🔐