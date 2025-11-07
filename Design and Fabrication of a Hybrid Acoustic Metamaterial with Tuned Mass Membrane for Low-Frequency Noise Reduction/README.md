# 🎓 Design and Fabrication of a Hybrid Acoustic Metamaterial with Tuned Mass Membrane for Low-Frequency Noise Reduction

### 🔍 **Overview**
This project builds upon the Helmholtz resonator-based acoustic metamaterial by **Arpat Gupta and Sourabh Dogra**, extending it into a hybrid configuration by integrating a **tuned mass membrane**. 
The hybrid aims to improve low-frequency sound attenuation (200–1200 Hz) by coupling Helmholtz resonance with membrane dynamics and performing a parametric study on attached mass shape and size.

### 🧠 **Objectives**
- Fabricate the reference Helmholtz-type acoustic metamaterial design.  
- Integrate a **membrane with variable attached mass** to create a hybrid resonator.  
- Perform a **parametric study** to analyze how **mass shape and size** affect Sound Transmission Loss (STL).  
- Compare experimental measurements with simulation predictions.

---

### ⚙️ **Design & Fabrication**
- **Base design:** Adopted the Helmholtz AMM geometry from Gupta & Dogra and modeled the structure in **SolidWorks**.  
- **Membrane integration:** Added a membrane layer at the resonator opening and attached tunable mass elements (tested shapes: circular, square, triangular).  
- **Fabrication:** Prototypes produced using **3D printing (PLA)** and manual membrane assembly.  
- **Specimen dimensions:** Ø **100 mm** diameter, **50 mm** thickness.  

---

### 🧪 **Experimental Setup**
- **Standard followed:** ASTM E2611 for four-microphone impedance tube configuration.  
- **Instrumentation:** High-accuracy microphones (×4), **NI 4499 DAQ**, LabVIEW for acquisition.  
- **Data flow:** Time-domain amplitudes → exported → FFT in Python → STL computed using the ASTM E2611 formulation implemented in Python.  
- **Mounting:** Designed speaker clamp and AMM clamping systems in SolidWorks to ensure repeatable and airtight mounting.

---

### 🖥️ **Simulation**
- **Software:** ANSYS Workbench 2023 R1.  
- **Modeling:** Fluid–Solid Interaction (FSI) in an impedance-tube domain with PLA solids and air as fluid.  
- **Parametric study:** Swept attached-mass geometries and sizes, and compared STL predictions across configurations.

---

### 📈 **Key Results**
- The tuned mass membrane introduced **additional bandgaps** and increased STL at specific resonance ranges.  
- **Mass shape & size** strongly influenced bandgap location and width; **Star-shaped + Triangular-shaped masses** gave the most balanced STL improvement across the studied band.  
- Hybrid configuration produced **clear STL enhancement** versus the original Helmholtz-only baseline, validating resonance coupling as an effective strategy.

---

### 📌 **How STL was computed (brief)**
1. Acquire synchronized pressure signals from four microphones using NI 4499 DAQ and LabVIEW.  
2. Export time-domain signals and compute FFT (Python).  
3. Apply ASTM E2611 equations to derive transfer functions and compute **Sound Transmission Loss (STL)** vs frequency.  
4. Validate experimental STL against ANSYS FSI simulation results.

---

### 🧾 **Key Learnings**
- Hands-on integration of **mechanical design, DAQ, and signal processing**.  
- Practical experience applying **ASTM E2611** for multi-microphone impedance tube measurements.  
- Understanding of resonance coupling between Helmholtz and membrane resonators and how attachment mass geometry tunes bandgaps.

---

### 📎 **References**
- R. M. Plate, S. Dogra, and A. Gupta, “Design , Manufacturing , and Acoustical Analysis of a Helmholtz,” pp. 630–641, 2021.  
- ASTM E2611 — *Standard for impedance tube 4-microphone measurements*  

