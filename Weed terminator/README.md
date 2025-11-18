# 🤖 **Weed Terminator: AI-Powered Laser Agricultural Rover for Precision Weed Removal**

## 🔍 **Overview**

The *Weed Terminator* project focuses on developing a low-cost, autonomous agricultural rover that detects and eliminates weeds using AI-based computer vision and a CO₂ blue laser module. By integrating machine learning, robotics, and renewable energy, the system offers a chemical-free, sustainable solution for precision weeding — particularly suited to Pakistani farmlands where herbicide costs and soil degradation are major concerns.

---

## 🧠 **Objectives**

* Develop a machine learning model capable of real-time weed detection.
* Fabricate a fully functional rover integrating mechanical, electrical, and software subsystems.
* Use laser-based thermal treatment to eliminate weeds without herbicides.
* Evaluate mechanical performance, laser penetration capacity, and system reliability in field testing.
* Demonstrate a low-cost, scalable prototype suitable for small and medium-scale farms.

---

## ⚙️ **Design & Fabrication**

* **Mechanical Structure:**
  SolidWorks-based chassis made from 2 mm mild steel beams; optimized for weight distribution, stability, and farm-ready durability.
* **Locomotion:**
  R390 DC motors controlled via L298 H-bridge; 4-inch high-traction rubber wheels for uneven soil.
* **Power System:**
  12V, 20Ah sealed dry battery with integrated 10W solar panel & PWM charge controller.
* **Actuation & Aiming:**
  MG995 servo-based pan-tilt mount for precise laser direction control.
* **Laser Assembly:**
  20W, 450 nm blue laser module with adjustable focus and active cooling.
* **Electronics:**
  Arduino Uno for real-time control; Python-based AI detection on external processing unit (laptop due to GPU constraints).

---

## 🧪 **Data & Machine Learning Workflow**

* **Dataset:** Thousands of field images collected from local farmlands under varying lighting, soil types, and weed growth stages.
* **Labeling:** Processed via Roboflow for bounding-box annotations and dataset split.
* **Model:** YOLO-based deep learning architecture optimized for fast inference and small target detection.
* **Pipeline:**
  Camera feed → Model inference in Python → Target coordinates → Arduino → Servo aiming → Laser firing.
* **Validation:** Accuracy, confidence scores, latency, and false-positive analysis performed using test datasets and field trials.

---

## 🧪 **Experimental Setup**

* **Laser testing:** Exposure time, penetration depth, and energy required per weed calculated analytically and validated experimentally.
* **Mechanical testing:**

  * Bending stress
  * Deflection
  * Factor of Safety
  * Torque & power requirement
  * Battery life & consumption
* **Field validation:**
  Real-time weed detection & laser firing tested in small agricultural plots with varying weed densities.

---

## 🖥️ **Simulation & Tools**

* **CAD:** SolidWorks for mechanical assembly, load checks, and prototype integration.
* **Software:** Python, OpenCV, YOLO, VS Code.
* **Control:** Arduino IDE for motor + servo control, PWM handling.
* **Dataset Management:** Roboflow for augmentation & preprocessing.

---

## 📈 **Key Results**

* The model successfully detected weeds in real time with high confidence under diverse field conditions.
* Laser tests confirmed that a 20W blue laser can thermally damage weed meristems with controlled exposure times.
* Mechanical analysis showed stresses safely within material limits; chassis demonstrated stability on uneven surfaces.
* Solar-battery hybrid system sustained rover operation with moderate duty cycle.
* Prototype demonstrated the feasibility of chemical-free, automated weed removal.

---

## 📌 **How Weed Elimination Works (Brief)**

1. Camera captures the farm surface.
2. AI model identifies weed coordinates.
3. Servo mount aligns the laser to the target.
4. Laser delivers controlled energy to the meristem.
5. Weed growth is halted with no soil damage or chemical residue.

---

## 🧾 **Key Learnings**

* Training robust deep-learning models requires diverse, real-field datasets.
* Laser weeding is highly effective when meristem targeting is precise.
* Hardware-software synchronisation is critical for real-time field robotics.
* Renewable-energy integration extends rover autonomy and reduces operating costs.
* Mechanical design must balance weight, stability, and energy consumption for off-road performance.

