# ⚡ COMSOL Simulation: Cellular Response to Electrical Stimulation

This COMSOL-based project simulates how an isolated biological cell responds to various forms of electrical stimulation. It incorporates both stationary and time-dependent studies to model intracellular and extracellular potentials, as well as the transmembrane voltage (Vm), under controlled current injection and external electric fields.

---

## 🧪 Project Summary

### Key Goals
- Model steady-state and dynamic voltage distributions across a cell membrane
- Analyze effects of current injection vs. external field stimulation
- Visualize spatial and temporal profiles of Vi, Ve, and Vm
- Study response sensitivity to biophysical parameters

### Cell & Medium
- 2D circular cell (radius = 50 μm) in saline bath (4 mm x 4 mm)
- Material domains:
  - Cytoplasm (cell interior)
  - Saline (bath)
  - Cell membrane (boundary with contact impedance)

---

## ⚙️ Simulation Components

### 1️⃣ Stationary Response – Current Injection
- Line current source at center (0,0) with 0.5 μA/cm
- Membrane impedance:  
  - Resistance: 2.5 kΩ·cm²  
  - Capacitance: 1 μF/cm²
- Mesh: Extra fine

📊 **Outputs**:
- Electric potential and streamlines (Vi, Ve)
- Transmembrane voltage Vm (Vi - Ve) as a function of polar angle θ

📈 `Fig. 1 & Fig. 2`: Symmetric and asymmetric injection patterns

---

### 2️⃣ Time-Dependent Study
- Stimulus repositioned to (0.75rc, 0)
- Time-dependent solution from 0–20 ms in 2 ms steps, refined down to 0.0002 ms resolution

📈 `Fig. 3 & Fig. 4`: Temporal evolution of Vi, Ve, and Vm

📌 **Vm Threshold Test**:  
How long does it take for Vm to reach +15 mV?  
→ Extracted from `HW6-Vm(t).xlsx`

🎞️ `HW6-Movie-1.gif`: Animation of Vm evolution over time (2 fps)

---

### 3️⃣ External Electric Field Stimulation

- Field applied via ±1 V on opposing bath walls
- Line current source disabled
- Cell remains centered in bath

📈 `Fig. 5 & Fig. 6`:  
- Immediate steady-state observed  
- Vm ≠ Vi due to differing boundary conditions  
- Large sinusoidal variation in all signals

---

## 🔁 Parametric Studies

### Part 5: Biophysical Variations

| Condition | Change | Observation |
|----------|--------|-------------|
| Membrane R ↑ ×10 | Slower Vm rise | Increased time constant |
| Medium resistivity ↑ ×10 | Slower Vm change | Less current flow |
| Current source external | (2rc, 0) | Vm spatial profile shifts |  
| External field vs. current injection | Field → instant response | Vm shape varies |

All results shown in `Fig. 7–10`.

---

## 📂 Project Files

| File | Description |
|------|-------------|
| `HW6-COMSOL.mph` | Main model (all parts) |
| `HW6-Vm(t).xlsx` | Vm time series from transient study |
| `HW6-Movie-1.gif` | Animated potential evolution |
| `Bhatt-HW6-Doc.pdf` | Final report with figures and conclusions |

---

## 📌 Key Learning Points

- Transmembrane voltage arises from differences in inner and outer potentials
- Vm builds slower under current injection than with external field
- Changing membrane or medium properties directly affects time constants
- Vm can be extracted using COMSOL's curve + dataset join tools
- Visualization of streamlines and spatial profiles aids understanding of cell polarization

---

## 👨‍🔬 Author

Manan Bhatt  
Johns Hopkins University — Applied Bioelectrical Engineering  
COMSOL HW #6 — Spring 2025
