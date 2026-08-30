
---

# `02_Parasite_Drag/README.md`

The executed PDT values are precisely controlled as **0.018985 / 0.021501 / 0.023067**, while `0.0283` must remain explicitly labelled as a conservative performance basis rather than a PDT validation result. :contentReference[oaicite:3]{index=3}

```markdown
# 02 — Parasite Drag

## Purpose

This directory contains the Tyche R2-T1 zero-lift parasite-drag build-up
performed using the OpenVSP Parasite Drag Tool (PDT).

The objective is to establish a traceable estimate of aircraft parasite drag
from the released G1.3 geometry and to provide an executed drag build-up for
comparison with the deliberately conservative drag value used in aircraft
performance calculations.

---

## Aircraft and Geometry

Aircraft:

`Tyche R2-T1`

Geometry release:

`G1.3`

Principal geometry:

- wing area: `30.000 m²`;
- wing span: `16.400 m`;
- fuselage length: `10.750 m`;
- fixed tricycle landing gear;
- external lift struts;
- twin nacelles;
- propulsion-off aerodynamic reference configuration.

The complete-aircraft geometry was cleared through the preceding CompGeom
campaign before PDT results were accepted.

---

## Final PDT Results

| Drag Case | CD0 | Status |
|---|---:|---|
| Geometry build-up | **0.018985** | EXECUTED |
| Operational build-up | **0.021501** | EXECUTED |
| Adverse upper build-up | **0.023067** | EXECUTED |
| Conservative performance basis | **0.0283** | REPORT BASIS |

The first three values are the executed OpenVSP PDT build-up.

The final value, `CD0 = 0.0283`, is intentionally more conservative than the
executed PDT range.

---

## Critical Interpretation Rule

### `CD0 = 0.0283` is NOT a PDT validation result.

It is retained as a deliberately conservative aircraft-performance basis.

Do not describe it as:

- OpenVSP validated;
- PDT predicted;
- CFD validated;
- VSPAERO validated;
- experimentally validated.

Correct language is:

> The executed PDT build-up produced CD0 values between 0.018985 and 0.023067,
> while CD0 = 0.0283 was retained as a deliberately conservative performance
> basis.

---

## Drag Cases

### Geometry Build-Up

`CD0 = 0.018985`

Represents the lower executed geometry-based drag build-up.

This case is useful as the lower bound of the controlled PDT analysis.

---

### Operational Build-Up

`CD0 = 0.021501`

Represents the preferred operational PDT build-up including additional
allowances associated with a realistic in-service aircraft rather than an ideal
geometry-only surface.

This value is the principal executed PDT reference used when forming the
nominal clean interpretation polar.

---

### Adverse Upper Build-Up

`CD0 = 0.023067`

Represents the executed upper PDT build-up.

It is used to provide a more adverse drag interpretation and uncertainty bound.

---

## Relation to the Clean VSPAERO Campaign

PDT supplies the parasite-drag component.

VSPAERO supplies the lifting-system induced-drag behaviour.

The two are combined only at the interpretation/post-processing level.

The nominal clean interpretation polar is:

```text
CD = 0.0216437 + 0.0446077 CL²
