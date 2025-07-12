
---

## 🟢 Initial Timer and Start Button Segment

- `I2.0 ("Start")`: Input from the start button  
- `T5 (S_ODT)`: On-delay timer to introduce a delay before activation  
- `M0.2`: Normally closed contact used as a condition check  
- `T2 (S_PULSE)`: Pulse timer for generating a short activation pulse  
- `Q2.0 ("Green")`: Output to activate the green light  

---

## ✅ Green Light Control Segment

- `I2.0 ("Start")`: Start button input  
- `T2 (S_PULSE)`: Pulse timer for the green light  
- `Q2.0 ("Green")`: Output for green signal activation  

---

## 🟡 Yellow Light Control Segment

- `I2.0 ("Start")`: Start button input  
- `T3 (S_PULSE)`: Pulse timer for the yellow light  
- `Q2.1 ("Yellow")`: Output for yellow signal activation  

---

## 🔴 Red Light Control Segment

- `I2.0 ("Start")`: Start button input  
- `T4 (S_PULSE)`: Pulse timer for the red light  
- `Q2.2 ("Red")`: Output for red signal activation  

---