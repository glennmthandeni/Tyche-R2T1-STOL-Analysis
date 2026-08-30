# 00 — Project Control

## Tyche R2-T1 Analysis and Validation Archive

This directory contains the configuration-control, numerical-authority,
release-status and evidence-management documents governing the Tyche R2-T1
engineering analysis repository.

The purpose of this directory is to provide a single entry point for determining:

- which aircraft configuration is current;
- which geometry release is authoritative;
- which analysis results are released;
- which values are assumptions rather than directly validated quantities;
- which analyses were rejected or superseded;
- which limitations remain open;
- and which source has precedence when duplicate values occur elsewhere.

---

## Controlled Aircraft State

| Control Item | Released State |
|---|---|
| Aircraft | Tyche R2-T1 |
| Architecture | Twin segregated parallel-hybrid STOL aircraft |
| Geometry release | G1.3 |
| Fuselage length | 10.750 m |
| Structural / mass release | S1.0 |
| Aerodynamic production model | Thin lifting system |
| Stability production model | G5 |
| Numerical authority | CVR-1.0 |
| Competition | RAeS International Light Aircraft Design Competition 2025–26 |

G1.3 is the released analysis-ready aircraft geometry.

G1.4–G1.6 are diagnostic geometry-repair configurations and must not be
presented as released aircraft configurations.

Earlier geometry and analysis states remain in the repository only where they
provide useful audit or development history.

---

## Numerical Authority

The primary numerical authority for the repository is:

`Tyche_R2T1_Final_Controlled_Values_Register`

The Controlled Values Register should be consulted before reusing any numerical
result found in individual analysis folders.

Unless explicitly superseded by a later controlled release, values identified
in the CVR take precedence over:

1. preliminary sizing calculations;
2. intermediate analysis notes;
3. architecture-screening studies;
4. historical solver outputs;
5. draft design-report values;
6. superseded geometry releases.

---

## Evidence Hierarchy

The principal project-control sources are:

### Controlled Values Register — CVR-1.0

Defines the released numerical state of the aircraft.

Typical status labels include:

- `FINAL` — released result for project use;
- `REPORT BASIS` — deliberate design or performance assumption;
- `VALIDATION` — executed analysis supporting a design statement;
- `CONDITIONAL` — acceptable only with the stated limitation;
- `HOLD` — unresolved item that must retain qualification;
- `SUPERSEDED` — historical value that must not be used as current;
- `DO NOT USE` — rejected model or result.

### Analysis and Validation Evidence Log

Records the chronological engineering analysis campaign, including:

- CompGeom geometry checks;
- Parasite Drag Tool analysis;
- clean-aerodynamic model selection;
- VSPAERO convergence studies;
- G5 stability and control derivatives;
- CG and static-margin closure;
- VMC solver investigation;
- analytical VMC closure;
- forward-CG rotation and trim analysis;
- landing-gear reaction closure.

The Evidence Log is the detailed audit trail.

It is not intended to override the Controlled Values Register when a later
controlled value exists.

---

## Analysis Release Chain

| Release / Campaign | Purpose | Status |
|---|---|---|
| G1.3 | Released OpenVSP geometry | FINAL |
| G1.4–G1.6 | Diagnostic geometry repairs | DIAGNOSTIC |
| G0/G1/G2 CompGeom | Geometry/intersection validation | ACCEPTED |
| PDT | Parasite-drag build-up | EXECUTED |
| CA-G0–CA-G3 | Clean-aero model development and convergence | EXECUTED |
| CA-G3 | Final clean aerodynamic polar | FINAL |
| G5 | Stability/control production model | FINAL |
| SM6.3B | Munk–Multhopp fuselage correction | FINAL |
| SM6.4 | CG/static-margin closure | FINAL |
| VMC7.1–VMC7.3 | Powered VSPAERO OEI investigation | REJECTED FOR FINAL COEFFICIENT USE |
| VMC7.4 | Analytical OEI equilibrium | CONDITIONAL FINAL METHOD |
| FG8.0–FG8.4 | Forward-CG control and gear closure | FINAL CONCEPTUAL EVIDENCE |
| CVR-1.0 | Numerical configuration authority | FINAL |

---

## Important Configuration-Control Rules

### Geometry

Use:

`G1.3`

Do not revert to earlier G1.1 geometry or the earlier fuselage length.

The released fuselage length is:

`10.750 m`

---

### Aerodynamic Model

The released production aerodynamic model is:

`MainWing + HTail + VTail + lift struts`

using the VSPAERO thin lifting-surface formulation with propulsion off.

The mixed thin/thick complete-aircraft branch was investigated but ultimately
rejected as a production source because the assembled thick-body model remained
physically unsuitable after the geometry-repair campaign.

Its aerodynamic coefficients must not be used for final aircraft claims.

---

### Parasite Drag

Executed OpenVSP Parasite Drag Tool values are:

| Case | CD0 |
|---|---:|
| Geometry build-up | 0.018985 |
| Operational build-up | 0.021501 |
| Adverse upper build-up | 0.023067 |

The separate value:

`CD0 = 0.0283`

is a deliberately conservative performance basis.

It must **not** be described as an OpenVSP-validated or PDT-derived value.

---

### High-Lift Quantities

The following values remain bounded design/analytical inputs:

- unpowered take-off `CL,max = 2.40`;
- powered take-off `CL,max = 2.76`;
- landing `CL,max = 3.30`.

The executed Fowler-control analyses do not constitute direct validation of the
complete slat + double-slotted Fowler high-lift system.

---

## Recommended Contents of This Directory

Typical contents may include:

```text
00_Project_Control/
├── README.md
├── Controlled_Values_Register/
├── Analysis_Evidence_Log/
├── Release_Register/
├── Configuration_Control/
└── Historical_Audits/
