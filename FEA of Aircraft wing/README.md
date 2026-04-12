# 🛩️ Finite Element Analysis (FEA) of an Aircraft Wing

---

## 🔍 Overview

This report presents a comprehensive structural and dynamic FEA of a swept, tapered aircraft wing. Five studies were conducted: initial structural analysis, mesh sensitivity, element type sensitivity, material benchmarking, and modal analysis. All simulations used ANSYS Mechanical APDL 2020 R1 with the wing fixed at the root and loaded under Wing-Up (lift) and Wing-Down (weight/ground) conditions.

**Wing Geometry (SolidWorks):**
- Span: 11,518 mm | Root chord: 4,876 mm | Tip chord: ~1,100 mm
- Structural depth at root: 3,642 mm

---

## Section 1 — Initial Wing Design

**Yield Strength of baseline material: 345 MPa**

### Stress Distribution

| Condition | Max Von Mises Stress | vs. Yield |
|---|---|---|
| Wing-Up | 1.11 GPa | ⚠ ~3.2× above yield |
| Wing-Down | 411 MPa | ⚠ Marginally above yield |

### Displacement Contour

| Condition | Max Deformation | Location |
|---|---|---|
| Wing-Up | 4.2 mm | Wing tip |
| Wing-Down | 1.5 mm | Wing tip |

**Key Insight:** The initial design fails structurally under Wing-Up loading. The Wing-Down case also marginally exceeds yield at stress concentrations near the root. Both indicate a need for material upgrade or geometric reinforcement.

---

## Section 2 — Mesh Sensitivity Analysis

Four mesh densities were tested under both loading conditions to assess convergence.

### Results Summary

| Elements | Wing-Up Max Stress | Wing-Up Max Disp | Wing-Down Max Disp |
|---|---|---|---|
| 211 | ~1.37 GPa | 1.47 mm | 0.49 mm |
| 549 | ~1.95 GPa | 1.33 mm | 0.44 mm |
| 8,617 | ~960 MPa | 5.15 mm | 5.04 mm |
| 27,541 | ~997 MPa | 5.28 mm | 5.17 mm |

> Results stabilise between 8,617 and 27,541 elements, confirming convergence in that range.

### Evaluation

**Q: How does mesh size affect accuracy and convergence?**
Accuracy increases with element count. Coarse meshes underestimate peak stresses significantly, leading to non-conservative results.

**Q: How does mesh size affect computational cost?**
Finer meshes require more computational time and memory. The trade-off must be managed based on acceptable error tolerance.

**Q: What is the optimal mesh size?**
**6,889 elements** at 0.1 m element side length — best balance of accuracy and computational efficiency.

---

## Section 3 — Element Sensitivity Analysis

Two ANSYS shell element types compared at equivalent mesh density.

### Results Summary

| Parameter | Shell181 (4-node, Linear) | Shell281 (8-node, Quadratic) |
|---|---|---|
| Wing-Up Max Stress | ~960 MPa | ~1,142 MPa |
| Wing-Up Max Deformation | 5.15 mm | 4.03 mm |
| Wing-Down Max Stress | ~183 MPa | ~408 MPa |
| Wing-Down Max Deformation | 5.04 mm | 3.94 mm |
| Nodes per element | 4 | 8 |

### Evaluation

**Q: How does element type affect accuracy and convergence?**
Shell281 (8-node) achieves convergence with fewer elements and provides higher accuracy in capturing stress gradients, particularly near geometric transitions and the root fixity.

**Q: How does element type affect computational cost?**
Shell281 requires more memory per element (8 nodes vs. 4), but converges faster overall, reducing total solve time compared to Shell181 at equivalent accuracy.

**Q: What is the optimal element type?**
**Shell281 (8-node quadratic)** — superior accuracy, fewer elements needed for convergence, lower overall computational time.

---

## Section 4 — Material Analysis

Three aerospace alloys evaluated under identical loading conditions.

### Physical & Cost Properties

| Material | Density (kg/m³) | Volume (m³) | Mass (kg) | Cost/Weight ($/kg) | Total Cost ($) |
|---|---|---|---|---|---|
| Al 2024-T3 | 2,780 | 5.38 | 14,956 | 4.5 | 67,304 |
| Al 7075-T6 | 2,810 | 5.38 | 15,118 | 5.2 | 78,613 |
| Ti-6Al-4V | 4,430 | 5.38 | 23,833 | 40.0 | 953,336 |

### Structural Results

| Parameter | Al 2024-T3 | Al 7075-T6 | Ti-6Al-4V |
|---|---|---|---|
| Wing-Up Max Stress | 96 MPa | **90.83 MPa ✓** | 264.15 MPa |
| Wing-Up Max Deflection | **1.154 mm ✓** | 1.799 mm | 1.924 mm |
| Wing-Down Max Stress | **18.3 MPa ✓** | 30.44 MPa | 30.03 MPa |
| Wing-Down Max Deflection | 0.391 mm | 0.401 mm | **0.241 mm ✓** |

### Analysis

**Wing-Up:**
- Best stress performance: **7075-T6** (90.83 MPa)
- Least deflection: **2024-T3** (1.154 mm)
- Most cost-effective: **2024-T3** ($4.5/kg)

**Wing-Down:**
- Best stress performance: **2024-T3** (18.3 MPa)
- Least deflection: **Ti-6Al-4V** (0.241 mm) — but at ~14× the cost

### Conclusion
- Minimising stress in both conditions → **Al 7075-T6**
- Minimising deflection overall → **Ti-6Al-4V** (cost-prohibitive at $953k)
- Best balance of strength, weight, and cost → **Al 2024-T3**

---

## Section 5 — Modal Analysis

Free-vibration modal analysis extracted the first 4 natural frequencies. Both Wing-Up and Wing-Down configurations yield identical frequency sets, confirming the result is geometry/stiffness-driven, not load-path-dependent.

### Natural Frequencies & Mode Displacements

| Mode | Frequency (Hz) | Wing-Up Max Disp (mm) | Wing-Down Max Disp (mm) |
|---|---|---|---|
| 1 | 0.28702 | 5.15 | 7.19 |
| 2 | 0.31658 | 7.05 | 7.05 |
| 3 | 0.33037 | 7.88 | 7.88 |
| 4 | 0.38309 | 7.97 | 7.97 |

> All four modes are tightly clustered between 0.287–0.383 Hz. Higher modes show progressively larger displacements while the mode shape character remains broadly similar.

### Evaluation

**Q: How does modal analysis differ from static structural analysis?**
Modal analysis extracts natural frequencies and mode shapes for dynamic behaviour assessment. Static structural analysis determines displacements, stresses, and strains under fixed loads. Modal analysis provides no stress output — it informs resonance avoidance and vibration control design.

**Q: How does natural frequency vary with mode number?**
Higher modes correspond to higher natural frequencies, each associated with a distinct mode shape. The progression here is 0.287 → 0.317 → 0.330 → 0.383 Hz.

**Q: How does mode shape vary with mode number?**
Increasing mode number increases the average displacement amplitude across wing elements, but the overall deformed shape remains broadly similar — concentrated near the root attachment and mid-span regions.

**Q: How can modal analysis help avoid resonance?**
By identifying the wing's natural frequencies, engineers can ensure operational excitation sources (engine harmonics, gust frequencies, landing gear dynamics) do not coincide with these values. The results also guide the placement and sizing of vibration damping systems.

---

## Key Takeaways

| Study | Optimal Choice | Reason |
|---|---|---|
| Mesh | 6,889 elements (0.1 m size) | Converged accuracy, manageable cost |
| Element Type | Shell281 (8-node quadratic) | Higher accuracy, fewer elements at convergence |
| Material | Al 2024-T3 | Best strength/weight/cost balance |
| Structural Risk | Wing-Up loading | Max stress (1.11 GPa) far exceeds yield (345 MPa) |
| Dynamic Risk | Modes 1–4: 0.287–0.383 Hz | Low-frequency range; avoid in operational excitation |

---

## Skills Demonstrated

- Finite Element Analysis — ANSYS Mechanical APDL 2020 R1 (structural & modal)
- CAD Modelling — SolidWorks (2D drawings, 3D wing geometry)
- Mesh Convergence & Sensitivity Analysis
- Shell Element Theory — Shell181 vs. Shell281 comparison
- Aerospace Material Assessment — Al 2024-T3, Al 7075-T6, Ti-6Al-4V
- Modal / Vibration Analysis — natural frequency extraction and mode shape interpretation
- Technical Report Writing
