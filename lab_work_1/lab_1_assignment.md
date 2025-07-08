# Assignment Report – Lab 1  
## Installation and Configuration of Simatic Manager (STEP 7 PRO 2017)
---

## 🧩 Task Description

The objective is to familiarize students with the process of preparing a software environment for programming Siemens S7 PLCs using **STEP 7 Professional 2017**.  
The core deliverable is a configured and licensed copy of Simatic Manager, enabling practical work with industrial controllers.

_All reference files (installation package and license activator) are provided in the `src/` folder._


---

## 🎯 Objectives

- [ ] Install and set up **STEP 7 Professional 2017**.
- [ ] Activate the software using the provided utility.
- [ ] Resolve typical installation and startup issues.
- [ ] Validate the environment for programming Siemens S7 PLCs.

---

## 📂 Folder Contents (`src/`) 

```plaintext
📁 src/
├── STEP 7 PRO 2017 - Instructions for installation.pdf       
└── Configuring VIPA modules in STEP 7 Simatic Manager.pdf                      
```

---

## ⚙️ Procedure Overview 

### ➤ Installation Workflow  
1. A non-system disk is selected for file extraction to avoid conflicts with system processes.  
2. The initial installer is launched to unpack all components.  
3. `setup.exe` is initiated, and only necessary modules are selected.  
4. The license agreement is accepted, and permissions for system modifications are granted.  
5. During installation, the system undergoes multiple restarts (without full shutdown).  
6. Upon completion, a confirmation message is displayed.

### ➤ Activation Process  
- After installation, the option to **defer license transfer** is chosen.  
- The utility `SIM_EKB_Install_2018_11_14.exe` is launched with administrative privileges.  
- Four standard steps are followed to apply the license key.  
- No activation errors are encountered.

### ➤ First Launch and Optimization  
- Simatic Manager is launched successfully.  
- For stability, the program is executed with administrator rights.



### 🛠 Basic Configuration of Simatic Manager

After successful installation and activation, the following initial configuration steps were performed to ensure a working development environment for S7 PLCs:

- 🔹 **Selected PLC Family**: Configured for S7-300/400 series development  
- 🔹 **Created a new project**: “Lab1_TEST_S7” as a base project structure  
- 🔹 **Added Hardware Configuration**: Inserted CPU (e.g., 315-2 DP) into hardware config  
- 🔹 **Configured MPI/DP Interface**: Set interface parameters for future simulations or device communication  
- 🔹 **Verified HW Configuration**: Used “Save and Compile” to ensure no configuration conflicts  
- 🔹 **Opened Programming Blocks**: Accessed OB1, created example ladder logic block for connectivity check  
- 🔹 **Simulated compile**: Ensured the project compiles without errors using offline mode

---

### 🚧 Issues Encountered and Resolved

<table>
  <thead>
    <tr>
      <th>Challenge</th>
      <th>Resolution</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Software required multiple restarts</td>
      <td>Used <strong>Restart</strong> instead of Shutdown</td>
    </tr>
    <tr>
      <td>Activation warning messages</td>
      <td>Resolved via SIM_EKB utility</td>
    </tr>
    <tr>
      <td>Launch errors</td>
      <td>Solved by using <strong>Run as Administrator</strong></td>
    </tr>
  </tbody>
</table>

--- 

## 🧠 Results & Reflection 

Simatic Manager (STEP 7 PRO 2017) was successfully installed, activated, and configured to support development with Siemens S7 PLCs. The environment now runs smoothly, and all essential components operate without errors.

Key outcomes include:

- ✅ **Stable Installation**: Choosing a non-system disk and allowing system restarts ensured a clean setup.  
- 🔑 **License Activation**: The provided SIM_EKB utility applied the key without issue, avoiding delays.  
- ⚙️ **First Launch Readiness**: Running the program as administrator resolved initial access errors.  
- 🧱 **Configuration Success**: The hardware setup for S7-300/400 series was completed, including CPU insertion, MPI/DP interface parameters, and sample ladder logic blocks. Compilation tests confirmed that the project builds successfully in offline mode.  

This lab reinforced procedural accuracy during installation, attention to detail during activation, and confidence in managing industrial development environments. Through hands-on steps and resolution of common errors, the exercise deepened understanding of PLC programming infrastructure and created a functional base for upcoming programming labs.

