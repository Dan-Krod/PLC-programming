## 🔐 Structure & Operation of the Lock Control Algorithm

The organizational block `OB1` acts as the central execution loop of the digital code lock system. It cycles continuously, executing all control stages to maintain synchronization and logical operations throughout the program.

### Core Functional Stages:

- **Key Input Handling**: Each button press is captured and stored in designated memory variables  
- **Code Verification**: The entered sequence is compared against a predefined combination  
- **Timed Lock Control**: Unlocking is managed via a timer that defines how long the lock remains open  

---

## 🧠 Network Logic Descriptions

### 🔸 Network 1: Logical Processing of Key Presses

- Utilizes `AND` logic and `SR` (Set-Reset) triggers to determine valid entry conditions  
- Sets state flags like `M1.0`, `M1.2`, and `M1.4` to indicate correct digit entry  
- Inputs: `I0.2`, `I0.4`, `I1.0` monitor user interactions  
- SR triggers (`M20.0`, `M21.0`, `M22.0`, `M23.0`) persistently store button states  

### ⏱️ Network 2: Unlock Timer Control

- If the entered password is valid, `S5T#3S110M` pulse timer activates for **3.11 seconds**  
- This sets `M1.6`, triggering the unlock mechanism  
- When the timer completes, `M2.0` is set to signal lock deactivation  

### 🔘 Network 3: Button "0" Handling

- Pressing `I0.0` toggles `M10.0`, recording digit **"0"**  
- A `P` (positive edge detection) function prevents misreads from long presses  

### 🔘 Network 4: Button "6" Handling

- `I0.6` sets `M11.0`, capturing digit **"6"**  
- Includes a positive edge mechanism (`P`) for input stability  

### 🔘 Network 5: Button "1" Handling

- On `I0.1` press, `M12.0` is triggered for digit **"1"**  
- Edge detection ensures consistent reading  

### 🔘 Network 6: Button "3" Handling

- `I0.3` alters `M13.0`, registering digit **"3"**  
- Uses positive edge detection for debounce protection  

### ✅ Network 7: Password Verification

- Compares stored entries `M20.0`, `M21.0`, `M22.0`, `M23.0` with the valid sequence **"0-6-1-3"**  
- If all values are set, `M90.0` is activated, allowing the lock to open  
- Step-by-step logic validation helps prevent false activations or security breaches  