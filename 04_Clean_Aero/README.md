
---

# `04_Clean_Aero/README.md`

CA-G3 is the actual production clean-aero result: `CL0 = 0.43349`, `CLα = 5.6161 rad⁻¹`, zero-lift angle `−4.422°`, `k = 0.044608`, `e = 0.7959`, with nominal clean `L/Dmax ≈ 16.09`. :contentReference[oaicite:5]{index=5} The CA-G3 final polar spans α = −4° to +10° and the accepted repeatability check reproduced the earlier 4° solution extremely closely. :contentReference[oaicite:6]{index=6}

```markdown
# 04 — Clean Aerodynamic Analysis

## Purpose

This directory contains the Tyche R2-T1 clean-aircraft aerodynamic campaign
performed using VSPAERO.

The campaign was designed to:

- identify a physically defensible aerodynamic production model;
- establish clean lift behaviour;
- quantify induced drag;
- assess pitching-moment behaviour;
- investigate mesh sensitivity;
- investigate wake sensitivity;
- verify numerical repeatability;
- and provide aerodynamic inputs for performance and stability analysis.

The final clean-aero release is:

`CA-G3`

---

## Production Model

The released aerodynamic production model is the propulsion-off thin
lifting-system representation:

```text
MainWing
+ HTail
+ VTail
+ Lift Struts
