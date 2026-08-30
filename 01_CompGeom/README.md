
---

# `01_CompGeom/README.md`

The final CompGeom campaign established G2 at **141.591 m² wetted area**, 11 OpenVSP geoms, 16 meshes and 13,888 triangles. It also confirmed actual trimming where the corrected lift struts intersected the wing and fuselage. :contentReference[oaicite:2]{index=2}

```markdown
# 01 — CompGeom Geometry Validation

## Purpose

This directory contains the OpenVSP CompGeom geometry-validation campaign for
the Tyche R2-T1 G1.3 aircraft.

The primary purpose of the campaign was to verify:

- correct component inclusion;
- exposed wetted areas;
- component intersections;
- installation trimming;
- left/right symmetry;
- mesh progression;
- lift-strut attachment;
- nacelle installation;
- landing-gear installation;
- and suitability of the released geometry for subsequent drag and aerodynamic
  analysis.

CompGeom is used here as a geometry and surface-intersection validation tool.

It is not used to determine aircraft aerodynamic coefficients.

---

## Released Geometry

Aircraft:

`Tyche R2-T1`

Geometry release:

`G1.3`

The G1.3 model is the released analysis-ready aircraft geometry.

---

## CompGeom Analysis Sets

The campaign uses a progressive geometry build-up.

| Set | Included Geometry | Purpose |
|---|---|---|
| G0_BARE_AIRFRAME | Fuselage + main wing + horizontal tail + vertical tail | Baseline airframe |
| G1_NACELLE_AIRFRAME | G0 + left/right nacelles | Nacelle installation and intersection |
| G2_COMPLETE_AIRFRAME | G1 + lift struts + fixed landing gear | Complete unpowered aircraft |
| G3_POWERED_AIRCRAFT | G2 + propeller/actuator-disc representation | Powered-analysis configuration |

G3 does not require a separate wetted-area CompGeom closure because actuator
discs do not represent conventional wetted aircraft surfaces.

---

## Final CompGeom Results

| Configuration | Final Exposed Wetted Area | Status |
|---|---:|---|
| G0_BARE_AIRFRAME | 128.118 m² | PASS |
| G1_NACELLE_AIRFRAME | 134.486 m² | PASS |
| G2_COMPLETE_AIRFRAME | 141.591 m² | PASS |

### G2 Complete-Airframe Mesh

Final G2 state:

- OpenVSP geoms: **11**
- CompGeom meshes: **16**
- triangles: **13,888**
- total exposed wetted area: **141.591 m²**

G2 is the accepted complete clean-aircraft geometry for subsequent
parasite-drag and VSPAERO analysis.

---

## G0 — Bare Airframe

The G0 baseline consists of:

- fuselage;
- main wing;
- horizontal tail;
- vertical tail.

Final exposed areas:

| Component | Wetted Area |
|---|---:|
| Fuselage | 44.529 m² |
| Main wing | 59.599 m² |
| Horizontal tail | 16.074 m² |
| Vertical tail | 7.917 m² |
| **Total** | **128.118 m²** |

This configuration establishes the reference airframe before nacelle, strut and
landing-gear installation.

---

## G1 — Nacelle Airframe

G1 introduces the two installed nacelles.

Final total wetted area:

`134.486 m²`

Each nacelle contributes approximately:

`3.718 m²`

of exposed wetted area.

The reduction in main-wing exposed area relative to G0 is consistent with
nacelle/wing intersection trimming.

Left and right nacelle results were symmetric.

G1 was accepted for subsequent configuration build-up.

---

## G2 — Complete Unpowered Aircraft

G2 adds:

- left and right lift struts;
- main landing-gear legs;
- main wheels;
- nose-gear leg;
- nose wheel.

Final total wetted area:

`141.591 m²`

Relative to G1, the permanent strut and landing-gear installation increases
exposed wetted area by approximately:

`7.105 m²`

or approximately:

`5.28%`

---

## Lift-Strut Attachment Closure

An earlier geometry state showed insufficient intersection between the lift
struts and adjoining wing/fuselage surfaces.

The geometry was subsequently corrected so that the struts penetrate the
adjoining components sufficiently for CompGeom to trim the buried surface.

In the final accepted G2 configuration:

- each lift strut has approximately `2.223 m²` theoretical area;
- each has approximately `2.130 m²` exposed wetted area;
- main-wing wetted area reduces due to installation trimming;
- fuselage wetted area also reduces due to installation trimming.

The reduction between theoretical and exposed strut area, together with
concurrent wing/fuselage trimming, confirms that the final strut attachments
intersect rather than terminate in free space.

This resolved the original lift-strut geometry concern.

---

## Accepted Mesh Warnings

The CompGeom campaign repeatedly generated symmetric mesh merges involving:

- MainWing;
- HTail.

These were tracked through the configuration progression.

No additional unexpected warnings were introduced by the accepted final G2
configuration.

The persistent symmetric merge behaviour was therefore treated as an accepted
model characteristic rather than evidence of a new geometry failure.

---

## Final Engineering Decision

`G2_COMPLETE_AIRFRAME — PASS`

The final G1.3 complete-aircraft geometry passed the CompGeom validation gate
for:

- component installation;
- exposed area consistency;
- left/right symmetry;
- strut attachment;
- nacelle trimming;
- fixed landing-gear inclusion;
- and progression to subsequent aerodynamic analysis.

---

## Suggested Directory Structure

```text
01_CompGeom/
├── README.md
├── G0_BARE_AIRFRAME/
│   ├── raw/
│   ├── exports/
│   └── figures/
├── G1_NACELLE_AIRFRAME/
│   ├── raw/
│   ├── exports/
│   └── figures/
├── G2_COMPLETE_AIRFRAME/
│   ├── raw/
│   ├── exports/
│   └── figures/
└── diagnostic/
    └── previous_strut_attachment/
