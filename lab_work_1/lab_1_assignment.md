# 🧪 Assignment – Lab 1  
## Installation and Configuration of Simatic Manager (STEP 7 Professional 2017)

---

## 🧩 Task Overview  

In this lab, students will install and configure **STEP 7 Professional 2017** to enable programming of Siemens S7 PLCs. By the end of this task, each student should have a fully operational development environment.

_All required files (installation package and license activator) are located in the `src/` folder._

---

## 🎯 Objectives  

- [ ] Set up the STEP 7 Professional 2017 software  
- [ ] Activate the license using the provided tool  
- [ ] Address common installation and launch challenges  
- [ ] Validate environment readiness for programming S7 PLCs  

---

## 🧱 Expected Outcomes  

Students should submit evidence of:

- A successful installation and activation  
- A configured base project (“Lab1_TEST_S7”) targeting S7-300/400 series  
- Inclusion of CPU hardware configuration (e.g., 315-2 DP)  
- Properly set MPI/DP communication parameters  
- Creation of basic ladder logic blocks and confirmation of offline compilation  

---

## ⚙️ Instructions  

### ➤ Installation Procedure  

1. Extract files to a **non-system disk** to avoid conflicts  
2. Launch installer to unpack components  
3. Run `setup.exe`, select required modules  
4. Accept the license terms and provide necessary permissions  
5. Allow system to restart as prompted  
6. Confirm completion via installer message  

### ➤ Activation Steps  

1. Choose “Defer license transfer” if prompted  
2. Run `SIM_EKB_Install_2018_11_14.exe` as Administrator  
3. Follow the utility's standard activation procedure  
4. Confirm successful license application  

### ➤ First Launch  

- Run **Simatic Manager** with administrative privileges  
- Confirm clean launch without errors  

---

## 🧪 Configuration Checklist  

- [ ] Select target PLC family (S7-300/400)  
- [ ] Create a new project file  
- [ ] Insert and configure CPU module  
- [ ] Set MPI/DP communication parameters  
- [ ] Validate configuration using “Save and Compile”  
- [ ] Create and edit OB1 block with sample ladder logic  
- [ ] Verify offline compilation success  

---

## 🚨 Troubleshooting Tips  

| Issue                         | Suggested Solution               |
|------------------------------|----------------------------------|
| Restart prompts               | Use Restart—not Shutdown         |
| Activation warnings           | Follow SIM_EKB activation steps  |
| Launch errors                 | Use “Run as Administrator”       |

---

## 🧾 Final Notes  

After completing all steps, your system should be ready to program Siemens S7 PLCs. Successful activation and base configuration of Simatic Manager ensure a stable starting point for future labs.

Feel free to use this file as your go-to reference when setting up new projects or revisiting the environment. It’s designed to be practical and adaptable, not tied to formal deadlines.

> May your setup stay smooth, your ladder logic flow clean, and your diagnostics stay silent. 💡