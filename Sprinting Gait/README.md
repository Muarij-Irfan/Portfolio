# 🏃‍♂️ Sprinting Gait Simulation Using Theo Jansen Mechanism

## **Overview**
This project explores the **biomechanics of sprinting gait** and the adaptation of a **Theo Jansen mechanism** for simulating sprinting motion in a 1-DOF underactuated gait rehabilitation robot.  
It builds upon the work of **Dr. Sung Yul Shin**, whose gait trainer was designed for walking gait, by extending the concept to high-speed **sprinting cycles**.

---

## **Key Objectives**
- Study the **biomechanical phases of sprinting**: start, drive, maximum speed, and deceleration.  
- Simulate **sprinting gait cycles** using an optimized Theo Jansen mechanism.  
- Perform **kinematic analysis** of the lower limb motion (thigh and shin).  
- Construct and analyze a **CAD model** in SolidWorks for motion and power characteristics.  
- Fabricate a working **physical model** for validation and demonstration.

---

## **Research Background**
Two key biomechanical data sources were used:
1. **Fiorese et al.** — Provided regression equations to predict kinematics of maximal sprinting.  
2. **Japan Association of Athletic Federations (JAAF)** — Provided detailed gait data from elite sprinters in major competitions.

The acquired data helped in defining **joint trajectories** and **ankle path generation**, which guided the optimization of the Theo Jansen linkage.

---

## **Simulation and Analysis**

### **Trajectory Modelling**
- The trajectory of the hip, knee, and ankle joints was modelled using **MATLAB**.  
- Optimization minimized the error between a healthy sprinter’s gait and the generated Theo Jansen trajectory.

### **Kinematic Analysis in SolidWorks**
- Motion studies were conducted to analyze:
  - **Power Consumption**
  - **Motor Torque**
  - **Foot Linear Velocity**
  - **Foot Linear Acceleration**

**Simulation Speed:** 300 RPM  
**Output:** Realistic sprinting cycle replication.

---

## **CAD Model and Fabrication**
- The CAD model was constructed using the optimized Theo Jansen linkage dimensions.  
- Fabrication was done using a **wooden base** and **acrylic sheet ground link**.  
- Multi-layer design ensured all links moved in parallel planes without interference.  
- Motor and pin joints were precisely aligned using drilled holes across all layers.

---

## **Applications**
- 🏃‍♂️ **Athletic Training:** Enhances sprinting technique and speed optimization.  
- 🦿 **Rehabilitation:** Assists in gait recovery, prosthetic design, and therapy.  
- 🤖 **Robotics:** Improves bipedal locomotion efficiency.  
- 🧠 **Biomechanics:** Supports advanced gait and motion research.  
- 🎮 **Virtual Reality & Gaming:** Enhances realism in motion simulations.

---

![Trajectory](images/trajectory_plot.png)

---

## **Tools Used**
- **MATLAB** – Trajectory and optimization  
- **SolidWorks** – CAD design and motion analysis  
- **ANSYS** – Structural validation  
- **Arduino & DC Motor** – Physical actuation for prototype

⭐ *If you find this project interesting, consider giving it a star on GitHub!*
