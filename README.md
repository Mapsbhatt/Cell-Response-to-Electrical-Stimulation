# ⚡ COMSOL Simulation: Cellular Response to Electrical Stimulation

This project uses COMSOL to simulate the electrical behavior of a biological cell subjected to current injection and electric field stimulation. The study models both stationary and time-dependent voltage responses, capturing intracellular potential (Vi), extracellular potential (Ve), and transmembrane voltage (Vm) under various biophysical conditions.

---

## 🧬 Simulation Summary

- **Geometry**: 2D circular cell (radius = 50 μm) in a saline bath (4 mm × 4 mm)
- **Materials**: 
  - Saline for bath
  - Cytoplasm for cell interior
  - Membrane with RC model (contact impedance):  
    Rs = 2.5 kΩ·cm², Cs = 1 μF/cm²
- **Stimulus**: 
  - Current source: 0.5 μA/cm
  - External E-field: ±1 V at bath edges

---

## 🧪 Key Results

### 🔁 Part 1: Stationary Current Injection (Centered)

📸 **Electric Potential & Streamlines**
- Shown in: Fig 1: Vi and Current Streamlines

> The intracellular potential (Vi) forms a radial gradient. Streamlines represent outward current flow from a central injection source — consistent with monopolar symmetry.

📈 **Transmembrane Profile (Vi, Ve, Vm)**

- Vi ≈ 40 mV (flat across angles)
- Ve ≈ 0 mV (near grounded)
- Vm ≈ 40 mV (uniform)

- Fig 2: Vi, Ve, Vm vs θ

> Confirms radial symmetry and validates the boundary conditions.

---

### 🔄 Part 2: Asymmetric Injection (Off-center Stimulus)

- Stimulus moved to (0.75 rc, 0)

Shown in : Movie-1.gif

> Dynamic asymmetry develops in Vi and Vm. The membrane voltage still peaks around the source side, but becomes angularly asymmetric.

📊 Extracted time series:  
See `Vm(t)_data.xlsx` to find pulse width for Vm to reach +15 mV.

**Result**: ~4.2 ms (from the data)

---

### ⏱️ Part 3: Time-Dependent Voltage Evolution

#### Low Temporal Resolution (2 ms steps)

- Smooth ramp-up of Vm
- Temporal rise visible but not sharply resolved

#### High Temporal Resolution (0.2 ms, 0.02 ms, 0.002 ms)

- Shown in: Fig 6 Panels A–F

> Finer steps reveal fast initial dynamics. Membrane potential Vm rises sharply then levels off — consistent with RC charging behavior.

---

### 🌐 Part 4: Electric Field Stimulation

- External ±1 V applied at bath walls
- Instant polarization with field distortion

#### Vi, Ve, Vm respond instantly:
> Vm ≠ Vi due to field coupling across membrane

#### Electric field amplification at poles:

- Shown in: Fig 5A: Vi Field Distortion
- SHown in: Fig 5B: Field Intensity Map

> Electric field lines focus near the membrane poles due to dielectric mismatch.

---

### ⚗️ Part 5: Parameter Sensitivity Experiments

| Experiment | Change | Result |
|-----------|--------|--------|
| **a)** Membrane R ×10 | Slower Vm rise | Larger time constant |
| **b)** Saline & cytoplasm resistivity ×10 | Slower dynamics | Same final Vm |
| **c)** Current injection + R ×10 | Sharper Vm spike | Higher peak |
| **d)** Injection + medium resistivity ×10 | Minimal Vm change | Membrane dominates |

📈 All shown in `Fig. 7–10`

---

## 📂 Project Files

| File | Description |
|------|-------------|
| `COMSOL.mph` | COMSOL model with all studies |
| `Movie-1.gif` | Dynamic Vi + streamline animation |
| `Vm(t)_data.xlsx` | Time series data for threshold analysis |
| `Supplement-Doc.pdf` | Experimental commentary and figure callouts |

---

## 🧠 Scientific Takeaways

- **Vm arises from Vi – Ve** and is sensitive to boundary location and symmetry
- **RC time constants** govern rise times during stimulation
- **Field stimulation** causes nearly instant changes — unlike current injection
- **Membrane resistance** strongly modulates both peak amplitude and dynamics
- **Medium resistivity** has less effect under current injection than under field

---

## 👨‍🔬 Author

Manan Bhatt  
Johns Hopkins University — Applied Bioelectrical Engineering  
COMSOL HW #6 — Spring 2025
