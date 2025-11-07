# 🧱 Evaluation of Simply Supported Beam using Finite Element Method (FEM)

### 🔍 **Overview**
This project involves the **design and analysis of a simply supported beam** that can withstand a **10 kg load** while minimizing **deflection** and **mass**.  
The objective was to design the **strongest and lightest** beam using either theoretical calculations or **simulation-based methods (ANSYS)** and validate the results through experiment.

The competition goal was to achieve the **lowest ω (performance parameter)** value, defined as:

ω = αδ + β/10

where:  
- **α** = Deflection of the beam (mm)  
- **β** = Mass of the beam (grams)  
- **δ** = Deflection coefficient = 1.2  

---

### 🧠 **Concept: Fully Stressed Beam**
A **fully stressed beam** is designed such that the **maximum stress** throughout its length reaches the **allowable stress limit** of the chosen material.  
This ensures that the material’s full strength is utilized efficiently — minimizing weight without compromising safety.  
The concept is crucial in **aerospace**, **civil**, and **mechanical design** applications, where **strength-to-weight ratio** is key.

---

### ⚙️ **Simulation Setup (ANSYS Workbench)**
- **Software:** ANSYS Workbench 2023 R1  
- **Model Type:** 3D Static Structural  
- **Boundary Conditions:**
  - Simply supported ends  
  - Point load applied at mid-span (to simulate 10 kg load)  
- **Material:** Structural Steel  
  - Young’s Modulus: *2×10⁵ MPa*  
  - Poisson’s Ratio: *0.3*  
  - Density: *7850 kg/m³*  

---

### 📐 **Optimization Method**
The beam’s height (**h₀**) was optimized to minimize **ω** (combined deflection and mass factor).  
A range of heights were tested, and for each, **deflection** and **mass** were obtained through FEM simulation.  
The optimal beam design was selected based on minimum ω value.


ω = αδ + β/10


where δ = 1.2.

---

### 📊 **Results**
| Parameter | Symbol | Value | Unit |
|------------|---------|--------|------|
| Maximum Deflection | α | 1.44 | mm |
| Average Stress | — | 21 | MPa |
| Mass | β | 0.052556 | kg |
| Performance Index | ω | 6.988 | — |

> **Note:** The maximum stress occurred at the point of load application and was not considered for overall stress comparison. Instead, stress near the loaded section was used for evaluation.

---

### 🖼️ **Figures & Simulation Outputs**
> Add your simulation results or experimental setup photos here.  
> Place them in a folder named `images/` in this project directory, then use the following markdown snippet:

```markdown
![Beam Setup](images/beam_setup.png)
*Simply supported beam setup in ANSYS.*

![Deflection Contour](images/deflection_contour.png)
*Deflection contour showing maximum displacement at mid-span.*

![Stress Distribution](images/stress_distribution.png)
*Stress distribution across beam length.*
