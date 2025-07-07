# Assignment Report – Lab 1  
## Installation and Configuration of Simatic Manager (STEP 7 PRO 2017)
---

## 🧩 Task Description

The objective of this lab was to familiarize students with the process of preparing a software environment for programming Siemens S7 PLCs using **STEP 7 Professional 2017**.  
The core deliverable is a configured and licensed copy of Simatic Manager, enabling practical work with industrial controllers.

The installation package and license activator are provided in the `src/` folder of this repository.

---

## 🎯 Objectives

- Install and set up **STEP 7 Professional 2017**.
- Activate the software using the provided utility.
- Resolve typical installation and startup issues.
- Validate the environment for programming Siemens S7 PLCs.

---

## 📂 Repository Structure

```
📁 src/
├── STEP 7 PRO 2017 - Instructions for installation.pdf       
└── Configuring VIPA modules in STEP 7 Simatic Manager.pdf                      
```

---

## ⚙️ Execution Summary

### ➤ Installation Workflow
1. Chose a non-system disk to extract files to avoid system conflicts.
2. Launched the initial installer to unpack all components.
3. Initiated `setup.exe` and selected necessary modules only.
4. Accepted the license agreement and permitted system modifications.
5. System required **multiple restarts** during installation (not full shutdowns).
6. Upon completion, confirmation message appeared.

### ➤ Activation Process
- Post-installation, chose the option to **defer license transfer**.
- Launched the utility `SIM_EKB_Install_2018_11_14.exe` as administrator.
- Followed four standard steps to apply the license key.
- No activation errors occurred.

### ➤ First Launch and Optimization
- Launched Simatic Manager successfully.
- For stability, program is run as administrator.

---

## 🚧 Issues Encountered and Resolved

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

## 🛠 Basic Configuration of Simatic Manager

After successful installation and activation, the following initial configuration steps were performed to ensure a working development environment for S7 PLCs:

- 🔹 **Selected PLC Family**: Configured for S7-300/400 series development  
- 🔹 **Created a new project**: “Lab1_TEST_S7” as a base project structure  
- 🔹 **Added Hardware Configuration**: Inserted CPU (e.g., 315-2 DP) into hardware config  
- 🔹 **Configured MPI/DP Interface**: Set interface parameters for future simulations or device communication  
- 🔹 **Verified HW Configuration**: Used “Save and Compile” to ensure no configuration conflicts  
- 🔹 **Opened Programming Blocks**: Accessed OB1, created example ladder logic block for connectivity check  
- 🔹 **Simulated compile**: Ensured the project compiles without errors using offline mode

These steps ensured that the environment is not only installed but is also fully operational and ready for controller-specific work.