# Seismic Design Basis

This file covers the seismic design basis that the general notes and the
seismic calcs must state consistently: site class and ground motions, risk
category and I_e, SDC, period, the SFRS and its R/Ω₀/C_d, ρ,
irregularities, the analysis procedure, base shear (C_s limits), drift,
separation, and the load combinations with E_h, E_v, and E_mh. Read it at
the start of a review, before tracing the load path, to confirm the basis
is complete, consistent, and current. Diaphragm forces, chords,
collectors, accidental torsion, and F_p wall anchorage are in
`diaphragms_and_collectors.md`.

**Code edition: use the one the project's jurisdiction adopts.**

- This file is written to ASCE 7-22, which the 2025 CBC adopts for permit
  applications from January 1, 2026. California projects submitted earlier
  may legitimately remain on the 2022 CBC / ASCE 7-16.
- Outside California, the adopted IBC edition sets the ASCE 7 edition. For
  example, IBC 2021 references ASCE 7-16 and IBC 2024 references ASCE 7-22
  (verify: the jurisdiction's adoption).
- On a project under an earlier edition, review against that edition. The
  labeled ASCE 7-16 forms here help. Don't write findings against 7-22-only
  rules.
- Flag a 7-16 basis as superseded **only** when the jurisdiction and the
  permit date call for 7-22.

## Levels, stories, and the base

Drawing labels vary (Level 1, L1, 1st Floor, Ground, Podium, T.O. Slab).
Before checking anything stated per story, map the labels to ASCE
numbering, counting from the base, and state the mapping in the report.

- **Base** (ASCE 7-22 §11.2): where horizontal ground motions are
  considered imparted to the structure. Not necessarily the ground floor;
  a podium or basement can move it.
- **Levels** (§11.3): i = 1 is the first level above the base, so the
  American "2nd floor" is ASCE level 1.
- **Story** (§11.2): the space between the tops of two successive floor
  surfaces (topmost: top of floor to top of roof). Story x is below level
  x, and **h_sx** is its height (h_x − h_(x−1)).
- **Story above grade plane** (§11.2): top floor or roof surface more than
  6 ft above grade plane, or more than 12 ft above finished ground at any
  point on the perimeter. This is what "stories above grade plane" limits
  mean (e.g. §12.2.3.3).

## Ground motions and site class

- The design spectrum is based on **MCE_R** (risk-targeted maximum
  considered earthquake) parameters; the design level is **two-thirds** of
  MCE_R.
- **General procedure** (§11.4): uniform-risk, used for most buildings.
  7-22 also provides a **multi-period design spectrum** (§11.4.5.1), used
  by C_s Method 1.
- **Site-specific procedure** (§11.4.7): a **site response analysis**
  modifies shaking for the soil; a **ground motion hazard analysis** (PSHA
  or DSHA) defines the shaking. Under 7-22 a ground motion hazard analysis
  is *permitted* for any structure but *required* for none. Seismically
  isolated structures take their MCE_R spectrum from §11.4 (§17.3.1).
- 7-22 has no F_a/F_v site coefficient tables and uses intermediate site
  classes (e.g. CD, DE). F_a/F_v values in the notes indicate a 7-16 basis.

**Site Class F (§20.2.1).** The only mandatory site-specific procedure in
7-22 is the site response analysis (§21.1) for Site Class F. Check the
exceptions before treating "Site Class F, no site response analysis" as a
finding.

| Site Class F condition | Exception |
|---|---|
| Soils vulnerable to failure or collapse under seismic loading (liquefiable, quick/highly sensitive clays, collapsible weakly cemented soils) | T ≤ 0.5 s on liquefiable soils: site class may be assigned per §20.2 and spectrum taken from §11.4, for spectral accelerations only |
| Peats and/or highly organic clays > 10 ft thick | None |
| Very high plasticity clays > 25 ft thick with PI > 75, in a profile otherwise CD, D, DE, or E | Not required for SDC A or B (from S_DS and S_D1) |
| Soft/medium stiff clays > 120 ft thick with undrained shear strength < 1,000 psf | Not required for SDC A or B (from S_DS and S_D1) |

ASCE 7-16 (older projects / existing reports): §11.4.8 required a ground
motion hazard analysis for isolated and damped structures on sites with
S_1 ≥ 0.6g. Not in 7-22.

## Risk category, I_e, and SDC

| Risk Category | I_e (ASCE 7-22 Table 1.5-2) |
|---|---|
| I or II | 1.0 |
| III | 1.25 |
| IV | 1.5 |

- I_e raises design forces for buildings whose performance matters more:
  Risk Category IV (essential, must stay operational) +50%, III +25%, I/II
  life safety only. The tighter drift for higher risk categories comes
  from Δ_a (Table 12.12-1), not from I_e.
- **SDC (§11.6):** where **S_1 ≥ 0.75**, Risk Category I-III is **SDC E**
  and Risk Category IV is **SDC F**. Otherwise the SDC is the **more
  severe** of Table 11.6-1 (from S_DS) and Table 11.6-2 (from S_D1).

## Fundamental period

**T_a = C_t · h_n^x** (§12.8.2.1, Eq. 12.8-8)

- C_t and x come from **Table 12.8-2** (confirmed, ASCE 7-22):

  | Structure type | C_t | x |
  |---|---|---|
  | Steel moment frames (frames resist 100% and aren't enclosed by stiffer elements) | 0.028 | 0.8 |
  | Concrete moment frames (same condition) | 0.016 | 0.9 |
  | Steel EBF (Table 12.2-1 line B1 or D1) | 0.03 | 0.75 |
  | Steel BRBF | 0.03 | 0.75 |
  | All other systems | 0.02 | 0.75 |

  These depend on the system because period comes period comes
  from stiffness and mass and the system sets stiffness (a moment frame is
  more flexible than a wall or braced frame of the same height). Period
  reflects stiffness; ductility sets R, not T.
- **h_n** (§11.2): base to the **highest level of the SFRS**; for sloped
  roofs, the average roof height. Excludes parapets and penthouses.
- Alternates: **T_a = 0.1N** for concrete or steel moment frames up to 12
  stories (Eq. 12.8-9); Eq. 12.8-10 for masonry or concrete shear walls up
  to 120 ft.
- For drift only, the computed period may be used without the C_u·T_a cap
  (§12.8.6.2).

## Seismic force-resisting systems

The categories match the lettered groups of ASCE 7-22 Table 12.2-1. The
system sets R, Ω₀, C_d, the SDC permissions, and the height limit.

| Category | System | Key points |
|---|---|---|
| A | Bearing wall | Same walls carry most gravity load and resist seismic. Low redundancy. |
| B | Building frame | Separate gravity frame (not a moment frame) and lateral walls or braced frames. Lateral failure doesn't take the gravity system with it. |
| C | Moment-resisting frame | Moment connections carry gravity and lateral load. Redundant through connection flexure, but flexible: large drifts can damage nonstructural elements. |
| D | Dual, special moment frame | Walls or braced frames plus a complete special moment frame as a secondary system. |
| E | Dual, intermediate moment frame | As D, with intermediate detailing. |
| F | Shear wall-frame, ordinary RC moment frames and ordinary RC shear walls | Shear wall-frame interactive system: R 4½, Ω₀ 2½, C_d 4. NL in SDC B, NP in C–F (confirmed, ASCE 7-22 Table 12.2-1, §12.2.5.8). Not expected in California. |
| G | Cantilever column | Columns fixed at base, free at top, carry gravity and lateral. Lateral failure is also gravity failure. Steel special cantilever columns: R 2½, Ω₀ 2½, C_d 2½, **35 ft** in all SDCs. Steel ordinary cantilever columns: R 1¼, Ω₀ 1¼, C_d 1¼, 35 ft in B and C, NP in D–F (confirmed, Table 12.2-1, §12.2.5.2). |
| H | Steel not specifically detailed for seismic (excluding cantilever columns) | R 3, Ω₀ 3, C_d 3. NL in SDC B and C, NP in D–F (confirmed, ASCE 7-22 Table 12.2-1). |

- **Dual systems (D, E):** the moment frames must resist **at least 25%
  of the design seismic forces**; total resistance is shared in proportion
  to rigidity (§12.2.5.1).
- Typical systems: concrete, special reinforced concrete shear walls;
  masonry, special reinforced masonry shear walls; steel, braced frames
  (easier to detail) or moment frames where loads call for one. Detailing
  is in `wood.md`, `steel.md`, `concrete.md`, and `masonry.md`.

## Design coefficients: R, Ω₀, C_d

| Coefficient | Represents | Source |
|---|---|---|
| R | Ductility | Table 12.2-1 |
| Ω₀ | Overstrength (reserve capacity beyond the design force) | Table 12.2-1 |
| C_d | Inelastic displacement amplification | Table 12.2-1 |
| ρ | Redundancy (redistribution after yielding) | §12.3.4 |

- **R** lets the structure yield at predetermined locations without losing
  vertical load capacity, so it is designed for V = V_E / R. R reduces
  forces to a **strength** level, not allowable stress (Table 12.2-1
  footnote).
- **Ω₀** captures members sized above minimum, extra energy dissipation,
  resistance factors, and actual material strengths above nominal. The
  maximum force that can develop is V_M = Ω₀ · V.
- **Flexible diaphragm reduction** (Table 12.2-1 footnote): where tabulated
  Ω₀ ≥ 2.5, Ω₀ may be reduced by **subtracting 0.5** for flexible
  diaphragms (3.0 becomes 2.5). It is not halved.
- R, Ω₀, and C_d are a set from one system row. Whatever R governs, Ω₀ and
  C_d come from the same row.
- **Where the Table 12.2-1 values live in this skill.** The confirmed
  ASCE 7-22 rows are tabulated in the material files:
  - wood light-frame walls: `wood.md`;
  - steel frames, braced frames and plate walls: `steel.md`;
  - RC frames and walls: `concrete.md`;
  - masonry walls: `masonry.md`.

  For a system not tabulated there, look up the governing row in ASCE 7-22
  Table 12.2-1 and confirm R, Ω₀, C_d, the SDC permission, and the height
  limit.
- **Light-frame wall rows (confirmed, ASCE 7-22 Table 12.2-1):**

  | Row | System | R | Ω₀ | C_d | D | E | F |
  |---|---|---|---|---|---|---|---|
  | A.16 | Light-frame (wood) walls, WSP sheathed (bearing wall) | 6½ | 3 | 4 | 65 ft | 65 ft | 65 ft |
  | B.23 | Same, building frame | 7 | 2½ | 4½ | 65 ft | 65 ft | 65 ft |
  | A.17 | Light-frame (CFS) walls, WSP or steel sheet (bearing wall) | 6½ | 3 | 4 | 65 ft | 65 ft | 65 ft |
  | A.18 | Light-frame walls, all other shear panel materials (bearing wall) | 2 | 2½ | 2 | 35 ft | NP | NP |
  | B.25 | Same, building frame | 2½ | 2½ | 2½ | 35 ft | NP | NP |
  | A.19 | Light-frame (CFS) flat strap bracing | 4 | 2 | 3½ | 65 ft | 65 ft | 65 ft |

  All of these are NL in SDC B and C.

## Combinations of systems (§12.2.3)

Where different SFRSs resist seismic forces in the **same direction**, the
**most stringent** Table 12.2-1 limitation applies. Members common to
different systems are detailed for the **highest R** of the connected
systems (§12.2.4).

### Vertical combinations (§12.2.3.1)

1. **Lower system has the lower R** (e.g. wood over a concrete podium):
   the upper system may use its own R, Ω₀, C_d; the lower system shall use
   its own. **Forces transferred from the upper into the lower system are
   amplified by R_upper / R_lower.** This is a load path junction (shear
   out of the wood walls into the podium).
2. **Upper system has the lower R** (e.g. concrete over wood): **both**
   systems use the upper system's R, Ω₀, C_d, because the stiffer system
   above limits how the lower one can deform.

Rule of thumb: **R cannot increase going down the building.** Exceptions:
rooftop structures up to two stories and 10% of total weight; other
supported systems weighing 10% or less of the structure; detached one- and
two-family light-frame dwellings. With three or more stacked systems,
apply §12.2.3.1 to each adjoining pair (commentary C12.2.3.1).

### Two-stage analysis (§12.2.3.2)

A two-stage ELF procedure for a **flexible upper portion over a rigid
lower portion** (classic case: mid-rise wood over a concrete podium). The
portions may be analyzed separately only if **all** of these hold:

1. Lower portion stiffness ≥ **10 ×** upper. Stiffness of each portion =
   its §12.8 base shear ÷ elastic displacement at its top, fixed at its
   base (lower portion loaded with the amplified upper reactions).
2. Period of the whole structure ≤ **1.1 ×** the period of the upper
   portion fixed at the top of the lower portion.
3. Upper portion designed with its own R and ρ.
4. Lower portion designed with its own R and ρ, **still meeting
   §12.2.3.1** (commentary: not exempted).
5. Upper reactions amplified by **(R/ρ)_upper / (R/ρ)_lower, not less than
   1.0**, applied to E_h (shear and overturning). Gravity and vertical
   seismic effects pass down unscaled.
6. Upper portion by ELF or modal response spectrum; lower portion by ELF.
7. Upper portion height, measured from its own base, within the Table
   12.2-1 limit for its system.
8. Horizontal Type 4 or vertical Type 3 irregularity at the transition:
   also amplify per §§12.3.3.4, 12.10.1.1, and 12.10.3.3, **in addition
   to** item 5.

| Rule | Section | Upper-to-lower force scaled by |
|---|---|---|
| Vertical combination, lower system has lower R | §12.2.3.1 | R_upper / R_lower |
| Two-stage analysis | §12.2.3.2 | (R/ρ)_upper / (R/ρ)_lower, ≥ 1.0 |

The two don't conflict: E_h = ρ·Q_E already carries ρ_upper, so the
two-stage factor equals Q_E × (R_upper/R_lower) × ρ_lower, the same R
ratio with the lower portion's ρ, plus the floor of 1.0. **Don't apply the
R/ρ ratio on a project not using two-stage analysis.**

### Horizontal combinations (§12.2.3)

- Different SFRSs in the same direction on the same story: R shall not
  exceed the **least R** in that direction, and Ω₀ and C_d match the
  governing system.
- **Dual systems are not horizontal combinations**; they have their own
  Table 12.2-1 row.
- **Independent lines of resistance (§12.2.3.3):** each line may use the
  least R on that line if the building is Risk Category I or II, two
  stories or less above grade plane, and light-frame or flexible
  diaphragms. Diaphragm design then uses the least R of any system in that
  direction. "Flexible" must be shown per §12.3.1.1, not assumed (see
  `diaphragms_and_collectors.md`).

### What to check on the drawings / calcs (system and coefficients)

- The notes name the SFRS **in each direction** by its Table 12.2-1 system
  name, not a generic "shear walls".
- R, Ω₀, and C_d are stated and all match one Table 12.2-1 row. Ω₀ or C_d
  from a different row than R is a finding.
- The system is permitted in the SDC and within its height limit.
- An Ω₀ reduced for a flexible diaphragm starts from tabulated Ω₀ ≥ 2.5,
  subtracts 0.5, and the diaphragm is shown to be flexible.
- Dual system: calcs show the moment frames resist ≥ 25%.
- Vertical combination: both systems and the §12.2.3.1 case are
  identified; forces into a lower-R lower system are amplified by
  R_upper / R_lower; if the upper system has the lower R, both use its
  coefficients.
- Two-stage: all eight conditions are shown, especially the 10×
  stiffness and 1.1× period checks. Any missing condition means two-stage
  is not demonstrated.
- Horizontal combination: one (least) R per direction, unless §12.2.3.3 is
  claimed with all three conditions shown.

## Irregularities (§12.3.2)

The set should declare the irregularities present (or "none") per
direction, and the calcs should apply the consequences. **Any
irregularity** removes the option of capping S_DS at 1.0 for C_s
(§12.8.1.3).

### Horizontal (Tables 12.3-1, 12.3-1a)

| Type | Definition | Consequences |
|---|---|---|
| 1 Torsional | > 75% of a story's lateral strength at or on one side of the center of mass, **or** TIR > 1.2 | Graded by TIR (below) |
| 2 Reentrant corner | Both projections beyond the corner > 20% of the plan dimension | SDC D-F: 25% increase (§12.3.3.5) |
| 3 Diaphragm discontinuity | Opening > 25% of gross enclosed diaphragm area, or > 50% change in effective diaphragm stiffness story to story | SDC D-F: 25% increase (§12.3.3.5) |
| 4 Out-of-plane offset | Discontinuity in a lateral force path, e.g. out-of-plane offset of a vertical element | SDC B-F: overstrength on supporting elements and connections (§12.3.3.4); SDC D-F: 25% increase (§12.3.3.5); 3D model (§12.7.3) |
| 5 Nonparallel system | Vertical elements not parallel to the major orthogonal axes | SDC C: no Independent Directional Procedure (§12.5.3); SDC D-F: orthogonal combinations (§12.5.4); 3D model (§12.7.3) |

**TIR = Δ_max / Δ_avg** (Eq. 12.3-2, §12.3.2.1.1), per story and per
accidental torsion case, from **story drifts** (not total displacements),
ELF with A_x = 1.0. Δ_avg averages the two opposing edges. TIR **does not
apply to flexible diaphragms**. Consequences are cumulative:

| TIR | Consequences |
|---|---|
| > 1.2 (or the 75%-strength condition) | SDC C-F: 3D model (§12.7.3). SDC D-F: orthogonal combinations (§12.5.4); amplified accidental torsion (§§12.8.4.2, 12.8.4.3); drift at the edge with the largest drift (§12.8.6); 25% increase (§12.3.3.5) |
| > 1.4 | SDC D-F: no increased height limits per §12.2.5.4. Damping systems: minimum base shear (§18.2.1.1) |
| > 1.4 in both directions | SDC D-F: ρ = 1.3 for the whole structure, both directions (§12.3.4.2.1) |
| > 1.6 | SDC D-F: mass offset restrictions in modal response spectrum analysis (§12.9.1.5) |

The **25% increase** (§12.3.3.5, SDC D-F, horizontal Types 1-4 and
vertical Type 3) applies to §12.10.1.1 diaphragm forces at the irregular
level, for diaphragm connections and collectors and their connections,
unless forces already include overstrength. Details are in
`diaphragms_and_collectors.md`. Tables 12.3-1 and 12.3-1a print §12.3.3.4
and §12.3.3.5 in some places where the requirement belongs to the other
section; cite the section whose text contains it, as above.

ASCE 7-16 (older projects / existing reports): torsion was split into 1a
and 1b, and 1b was prohibited in SDC E and F. 7-22 has no torsion-based
prohibition.

### Vertical (Table 12.3-2)

7-22 removed the weight (mass) irregularity and renumbered the rest
(7-16 → 7-22): 1a → 1a, 1b → 1b, 2 mass → removed, 3 → 2, 4 → 3,
5a → 4a (threshold changed), 5b → 4b.

| Type | Definition | Consequences |
|---|---|---|
| 1a Soft story | Stiffness < 70% of the story above, or < 80% of the average of the three above | None referenced |
| 1b Extreme soft story | < 60% of the story above, or < 70% of the average of the three above | Not permitted in SDC E or F (§12.3.3.1) |
| 2 Vertical geometric | SFRS horizontal dimension > 130% of an adjacent story's | None referenced |
| 3 In-plane discontinuity | In-plane offset of a vertical element creating overturning demands on supporting elements | SDC B-F: overstrength on supporting elements and connections (§12.3.3.4); SDC D-F: 25% increase (§12.3.3.5) |
| 4a Weak story | Lateral strength < 100% of the story above (7-16: 80%) | Not permitted in SDC E or F unless ≥ 80% of the story above (§12.3.3.1) |
| 4b Extreme weak story | Lateral strength < 65% of the story above | Not permitted in SDC D-F (§§12.3.3.1, 12.3.3.2). SDC B/C: two stories or 30 ft max unless the story resists Ω₀ × the §12.8 force (§12.3.3.3) |

Story lateral strength = total strength of all SFRS elements resisting the
story shear in that direction.

**Exceptions (§12.3.2.2):** Types 1a and 1b don't apply (1) where no story
drift ratio exceeds 130% of the story above (ignoring torsion and the top
two stories), or (2) to one-story buildings in any SDC or two-story
buildings in SDC B, C, or D. Commentary Figure C12.3-2 still uses 7-16
numbering; follow Table 12.3-2.

### Irregularities on the load path

- **Walls that don't stack:** an in-plane offset is vertical Type 3; an
  offset onto a different wall line is horizontal Type 4. Both trigger
  §12.3.3.4 overstrength on the supporting elements and are load path
  breaks to trace (`load_path_methodology.md`).
- Soft and weak stories (1a/1b, 4a/4b) are the garage-level condition in
  wood-over-podium and tuck-under parking buildings.

### What to check on the drawings / calcs (irregularities)

- Irregularities are declared per direction with 7-22 numbering. A mass
  irregularity or 7-16 numbering indicates a 7-16 basis.
- Plans show an undeclared condition: non-stacking or offset walls, large
  reentrant corners, large openings, nonparallel walls, open-front garage
  stories.
- Each declared irregularity shows its consequences: 3D model, orthogonal
  combinations, overstrength on supporting elements, 25% increase, ρ.
- Weak story checked at 100%, not 80%.
- A prohibited irregularity for the SDC (1b, 4a, 4b in E/F; 4b in D) is a
  finding unless an exception is shown.
- TIR is computed from story drifts with A_x = 1.0 and not claimed for a
  flexible diaphragm.

## Redundancy factor, ρ (§12.3.4)

ρ is 1.0 or 1.3; 1.3 penalizes low redundancy.

**ρ = 1.0 is permitted for (§12.3.4.1):** SDC B or C; drift and P-delta;
nonstructural components; nonbuilding structures not similar to buildings;
collectors, splices, and connections designed with overstrength; members
and connections where overstrength combinations are required; diaphragm
forces from F_px (Eq. 12.10-1 and its limits); structures with damping
systems; walls designed for out-of-plane forces and their anchorage; and
(new in 7-22) diaphragm forces from §12.10.4.

**SDC D-F: ρ = 1.3 unless Condition 1 or 2 is met (§12.3.4.2).** ρ = 1.3
may always be used without checking.

- **Condition 1.** For each story resisting more than 35% of the base
  shear in the direction of interest, with notional removal of any one
  Table 12.3-3 element: (a) at least **two bays of SFRS framing on each
  side of the center of mass** (new in 7-22); (b) story strength reduced
  **no more than 35%** (7-16: 33%); (c) no Type 1 torsional irregularity
  with **TIR > 1.4** (7-16: no extreme torsional irregularity). Systems
  with no Table 12.3-3 elements need not consider Condition 1.
- **Condition 2 (deemed to comply).** No horizontal irregularities in the
  direction of interest at any level, **and** at least **two bays of
  perimeter SFRS framing on each side** at each story resisting more than
  35% of the base shear.
- **Override (§12.3.4.2.1):** in SDC D-F, TIR > 1.4 in **both** directions
  at any level means ρ = 1.3 everywhere, both directions, no exceptions.

**Table 12.3-3, what is notionally removed:**

| Lateral element | Removal to check |
|---|---|
| Braced frames; light-frame walls with flat strap bracing | An individual brace or its connection |
| Moment frames | Moment resistance at both ends of a single beam |
| Shear walls or wall piers with h/L > 1.0 | A shear wall bay or pier, or its connections |
| Cantilever columns | Moment resistance at the base of a single column |

- Walls with h/L ≤ 1.0 need not be removed; if every element in a
  direction is such a wall, the layout is deemed redundant.
- The 35% threshold covers all stories of low-rise buildings and most of
  tall ones, excluding penthouses and upper stories.
- **Shear wall bays:** concrete and masonry, bays = wall length ÷ story
  height. **Light-frame walls (wood structural panel, gypsum wallboard),
  bays = 2 × wall length ÷ story height (project standard).** ASCE 7-22
  Table 12.3-3 defines a bay only as length ÷ story height, rounded down;
  the 2× form is from ASCE 7-16 §12.3.4.2. When a report relies on it, say
  so, e.g. "light-frame bays counted as 2 × L/h_sx per the reviewer's
  convention; ASCE 7-22 Table 12.3-3 defines a bay as L/h_sx."
- Removal is notional; the structure isn't designed for the loss. Losing a
  wall line can still leave a diaphragm, chord, or collector short (see
  `diaphragms_and_collectors.md`).

### What to check on the drawings / calcs (ρ)

- ρ is stated per direction. In SDC D-F, ρ = 1.0 without a Condition 1 or
  2 justification is a finding.
- Condition 2 claimed with a horizontal irregularity is a finding.
- Condition 1 without the "two bays each side of the center of mass" test,
  or at 33%, indicates a 7-16 basis.
- TIR > 1.4 in both directions with ρ = 1.0 anywhere is a finding.
- Light-frame bay counts state their basis.
- ρ = 1.0 for drift, overstrength combinations, or F_px is correct.

## Analysis procedure (§12.6)

- Permitted: **ELF** (§12.8), **modal response spectrum analysis**
  (§12.9.1), **linear response history analysis** (§12.9.2), or an
  AHJ-approved procedure. Nonlinear response history (Chapter 16) is
  permitted for any structure.
- **7-22 removed the ELF restrictions** (7-16 Table 12.6-1). Don't flag
  ELF on a tall or irregular building by itself.
- MRSA and LRHA always need a 3D model; ELF permits 2D in some cases, but
  irregularities can require 3D (§12.7.3: Type 1 in SDC C-F, Types 4
  and 5).

## Base shear, ELF (§12.8)

**V = C_s · W** (Eq. 12.8-1), W per §12.7.2. Two methods for C_s
(§12.8.1.1):

- **Method 1 (new in 7-22): C_s = S_a / (R/I_e)** (Eq. 12.8-2), with S_a
  from the multi-period spectrum (§11.4.5.1) at T; if T is below the
  period of peak S_a, use the peak. Not permitted where the multi-period
  spectrum isn't available from the USGS Seismic Design Geodatabase
  (§11.4.5, Exception 2).
- **Method 2: C_s = S_DS / (R/I_e)** (Eq. 12.8-3), which need not exceed
  **S_D1 / [T·(R/I_e)]** for T ≤ T_L (Eq. 12.8-4), or
  **S_D1·T_L / [T²·(R/I_e)]** for T > T_L (Eq. 12.8-5).
- **Lower limits, both methods:** **C_s ≥ 0.044·S_DS·I_e ≥ 0.01**
  (Eq. 12.8-6); where **S_1 ≥ 0.6**, **C_s ≥ 0.5·S_1 / (R/I_e)**
  (Eq. 12.8-7).
- **S_DS cap (§12.8.1.3):** C_s may use S_DS = 1.0 (not less than 70% of
  actual S_DS) only if **all** apply: no irregularities; five stories or
  fewer; T ≤ 0.5 s; ρ permitted to be 1.0; not Site Class E or F; Risk
  Category I or II; R ≥ 3.

**Vertical distribution (§12.8.3):** **F_x = C_vx · V** (Eq. 12.8-12),
**C_vx = w_x·h_x^k / Σ w_i·h_i^k** (Eq. 12.8-13). k = 1 for T ≤ 0.5 s,
k = 2 for T ≥ 2.5 s, and between, k = 2 or linear interpolation
(k = 0.75 + 0.5T). **Story shear V_x = Σ F_i** from level x up
(Eq. 12.8-14).

### What to check on the drawings / calcs (base shear)

- The notes state the procedure, C_s, W, and V per direction.
- Recompute S_DS/(R/I_e) from the stated values; a C_s that doesn't match
  is a finding.
- The upper limit uses a period consistent with the system and h_n (C_t
  and x match the system; h_n excludes parapets and penthouses).
- The lower limits are checked (Eq. 12.8-7 where S_1 ≥ 0.6).
- An S_DS = 1.0 cap with any irregularity, more than five stories, Site
  Class E/F, Risk Category III/IV, or R < 3 is a finding.
- Method 1 is used only where the multi-period spectrum is available.

## Drift (§§12.8.6, 12.12.1)

**δ_DE = C_d · δ_e / I_e + δ_di** (§12.8.6.3, Eq. 12.8-16)

- **δ_e:** elastic displacement from the design forces, including
  accidental torsion and torsional amplification as applicable.
- **Load level (§12.8.6.1):** 1.0 on E_h **with expected gravity**, not
  less than 1.0D + 0.5L (L reduced per that section). Not the factored
  combinations, and not seismic alone. Seismic forces are already strength
  level; "service level" is a wind drift term.
- For drift, Eq. 12.8-6 need not be considered, the period need not be
  capped at C_u·T_a (§12.8.6.2), and ρ = 1.0.
- **Dividing by I_e** backs out the force scaling: a stronger building
  doesn't make the ground move more.
- **δ_di:** diaphragm deformation at the design earthquake, including
  §12.10 forces (new in 7-22).
- **Design story drift Δ** (§12.8.6.5): difference in δ_DE at the centers
  of mass at the top and bottom of the story. Diaphragm deformation may be
  neglected, but diaphragm rotation must be included in SDC C-F with a
  horizontal Type 1 irregularity.

**Limit: Δ ≤ Δ_a for every story** (§12.12.1, Table 12.12-1):

| Structure | RC I or II | RC III | RC IV |
|---|---|---|---|
| Non-masonry-shear-wall structures, 4 stories or less above the base, with interior walls, partitions, and ceilings designed for the drifts | 0.025h_sx | 0.020h_sx | 0.015h_sx |
| Masonry cantilever shear wall structures | 0.010h_sx | 0.010h_sx | 0.010h_sx |
| Other masonry shear wall structures | 0.007h_sx | 0.007h_sx | 0.007h_sx |
| All other structures | 0.020h_sx | 0.015h_sx | 0.010h_sx |

- No drift limit for single-story structures whose interior walls,
  partitions, and ceilings are designed for the drift (separation still
  applies).
- **Moment frames only, SDC D-F (§12.12.1.1): Δ ≤ Δ_a / ρ.**

ASCE 7-16 (older projects / existing reports): δ_x = C_d·δ_xe/I_e, with no
diaphragm term.

### What to check on the drawings / calcs (drift)

- δ_DE uses C_d from the governing row and divides by I_e. Using R instead
  of C_d, or omitting I_e, is a finding.
- δ_e comes from 1.0E_h with expected gravity, not factored combinations.
- The Δ_a row fits the building (the 0.025 row needs four stories or less,
  no masonry shear walls, and components designed for the drift), and the
  risk category column is right.
- Moment-frame-only systems in SDC D-F check Δ_a / ρ.
- With horizontal Type 1 in SDC D-F, drift is checked at the edge with the
  largest drift.
- δ_DE includes δ_di; the 7-16 δ_x form indicates a 7-16 basis.

## Structural separation (§12.12.2)

- Structures on the same property, and portions split by seismic joints,
  must be separated enough to move without impact.
- **Adjacent structures:** **δ_SS = √(δ_DE1² + δ_DE2²)** (Eq. 12.12-2),
  δ_DE at the adjacent edges, including torsion and diaphragm deformation
  (commentary C12.12.2). Contact can only occur up to the shorter
  building's height, so evaluate both there.
- **Property line not common to a public way:** set back at least the
  structure's **own δ_DE**, not an SRSS of two buildings.
- Smaller separations are permitted where justified by rational analysis
  of inelastic response.
- Rigid shear wall buildings with rigid diaphragms whose deflections can't
  reasonably be estimated: commentary cites older guidance of at least
  1 in. plus ½ in. per 10 ft of height above 20 ft.
- **Members spanning between structures (§12.12.3):** supports and
  connections are designed for **δ_MCE = 1.5·R·δ_e/I_e + δ_di**
  (Eq. 12.8-17; R, not C_d), with the structures moving in **opposite
  directions** and the **absolute sum** of displacements (not SRSS).

ASCE 7-16 (older projects / existing reports): §12.12.3,
δ_MT = √(δ_M1² + δ_M2²), δ_M = C_d·δ_max/I_e.

### What to check on the drawings / calcs (separation)

- Seismic joints and gaps to adjacent buildings are dimensioned and backed
  by a δ_SS or δ_DE calc.
- Property-line setback uses the building's own δ_DE.
- Any member, seat, or bearing spanning a joint is sized for δ_MCE as an
  opposite-direction absolute sum.

## Seismic load effects and combinations (§§12.4, 2.3.6, 2.4.5)

### E_h and E_v (§12.4.2)

- **E = E_h + E_v** (Eq. 12.4-1) and **E = E_h − E_v** (Eq. 12.4-2).
  Earthquake adds to D in compression and counteracts D in tension.
- **E_h = ρ · Q_E** (Eq. 12.4-3). Q_E is the internal effect (axial,
  shear, moment) of horizontal forces from V or F_p. E_h is an effect,
  already scaled by ρ, not a horizontal force (e.g. the tension-compression
  couple from a lateral shear). Where §12.5.3/§12.5.4 require it, Q_E comes
  from forces in two orthogonal directions simultaneously.
- **E_v = 0.2 · S_DS · D** (Eq. 12.4-4a). Where §11.9 vertical ground
  motions are required, E_v = 0.3·S_av·D (Eq. 12.4-4b). E_v may be zero in
  SDC B, and in E = E_h − E_v for foundation soil-structure interface
  demands.
- For a wood shear wall, combination 7 governs the hold-down (least dead
  load resisting uplift) and combination 6 the compression studs
  (`wood.md`).

### Overstrength, E_m (§12.4.3)

- **E_m = E_mh + E_v** (Eq. 12.4-5) where earthquake adds to gravity;
  **E_m = E_mh − E_v** (Eq. 12.4-6) where it counteracts gravity. This is
  the code form: E_mh stays positive because seismic forces reverse
  anyway, and only E_v flips (LRFD 7 reads 0.9D − E_v + E_mh).
- **E_mh = Ω₀ · Q_E** (Eq. 12.4-7), with Q_E from V, F_px, or F_p. E_mh
  need not exceed **E_cl**, the capacity-limited effect (§11.3); where a
  material standard requires capacity-limited design, E_cl is used
  (§12.4.3.2). ρ = 1.0 with overstrength.
- **Overstrength on the load path:** collectors, splices, and connections
  (§12.10.2.1, SDC C-F), and elements supporting discontinuous walls or
  frames and their connections (§12.3.3.4). **Wood exception
  (§12.10.2.1):** where braced entirely by wood light-frame shear walls,
  collectors use the regular combinations with §12.10.1.1 forces, not
  overstrength (`diaphragms_and_collectors.md`).

### LRFD (§2.3.6) and ASD (§2.4.5)

| | Combination |
|---|---|
| LRFD 6 | 1.2D + E_v + E_h + L + 0.15S |
| LRFD 7 | 0.9D − E_v + E_h |
| ASD 8 | 1.0D + 0.7E_v + 0.7E_h |
| ASD 9 | 1.0D + 0.525E_v + 0.525E_h + 0.75L + 0.1S |
| ASD 10 | 0.6D − 0.7E_v + 0.7E_h |

- With overstrength, E_mh replaces E_h. In ASD, allowable stresses may
  then use a **1.2 increase** (not combined with other increases, except
  NDS adjustment factors).
- Expanded LRFD maximum: **(1.2 + 0.2·S_DS)·D + 1.2F + ρ·Q_E + f₁·L +
  f₂·H + 0.15S**; minimum: **(0.9 − 0.2·S_DS)·D + 0.9F + ρ·Q_E + f₂·H**.
- **f₁** (L): 0.5 permitted where L_o ≤ 100 psf, except garages and places
  of public assembly (1.0). **f₂** (H, lateral earth pressure): 1.6 where H
  adds to the principal effect, 0.9 where it resists and is permanent, 0
  otherwise. F takes D's factor. S is p_f or p_s. Seismic need not be
  combined with wind.
- **Alternative (§2.3.7, permitted):** split H into H_eb (earth/bulk: 1.6
  adding at maximum ground water; 0.9 resisting if permanent at minimum
  ground water; else 0) and H_w (ground water: 1.0 adding at maximum; 1.0
  resisting with permanent soil at minimum; else 0).
- ASD 10: 0.6D may be 0.9D for special reinforced masonry shear walls
  meeting §14.4.2.
- The IBC's own combinations name the snow factor f₂; read f₂ from context
  in notes citing the IBC (verify: IBC).

ASCE 7-16 (older projects / existing reports): LRFD used **0.2S**, not
0.15S.

### What to check on the drawings / calcs (load combinations)

- 7-22 combinations are used; 0.2S in LRFD 6 indicates a 7-16 basis.
- E_v = 0.2·S_DS·D uses the project S_DS, and is subtracted in the
  minimum-gravity combinations (0.9D − E_v; 0.6D − 0.7E_v).
- E_h carries the stated ρ (1.3·Q_E where ρ = 1.3).
- Overstrength uses E_m = E_mh ± E_v with Ω₀ from the governing row, on
  collectors (except wood light-frame buildings) and elements supporting
  discontinuous walls or frames.
- Hold-down and anchorage uplift use the minimum-gravity combination (LRFD
  7 / ASD 10).

## What to check in the general notes seismic block

Missing items are findings, and so are items that disagree with each other
or with the calcs.

- Code edition stated, and consistent with the jurisdiction's adopted
  building code and the permit date. Examples: ASCE 7-22 / 2025 CBC, or
  7-16 / 2022 CBC or IBC 2021.
- Risk category and I_e (Table 1.5-2).
- Site class (7-22 class names); for Site Class F, the site response
  analysis or the exception relied on.
- S_S, S_1, S_DS, S_D1 (and T_L where used), matching the geotechnical
  report (`foundations_and_geotechnical.md`).
- SDC, consistent with S_DS, S_D1, risk category, and the S_1 ≥ 0.75
  override.
- SFRS per direction with Table 12.2-1 name, R, Ω₀, C_d; permitted in the
  SDC and within its height limit.
- Vertical or horizontal combination identified; two-stage stated where
  used.
- ρ per direction.
- Irregularities (or "none") per direction.
- Analysis procedure and C_s method.
- C_s, W, and design base shear V per direction.
- Drift limit (Δ_a row and value) and joint/separation widths where
  applicable.
- Load combination basis (LRFD or ASD, 7-22).

## Common findings

- 7-16 basis on a permit submitted after January 1, 2026 (signs: F_a/F_v,
  mass irregularity, 7-16 irregularity numbering, weak story at 80%, ρ at
  33%, 0.2S, δ_x without δ_di).
- SDC not the more severe of the two tables, or the S_1 ≥ 0.75 override
  missed.
- R, Ω₀, C_d from different rows, or the system not permitted in the SDC
  or above its height limit.
- Ω₀ halved for a flexible diaphragm, or reduced when tabulated Ω₀ < 2.5.
- Horizontal combination designed with the higher R, or a dual system
  forced to the lower R.
- Wood over podium: no R_upper/R_lower amplification into the podium;
  two-stage claimed without the 10× stiffness and 1.1× period checks; R/ρ
  ratio used without two-stage.
- ρ = 1.0 in SDC D-F with no justification; Condition 2 claimed with a
  horizontal irregularity; light-frame bay basis not stated.
- Non-stacking walls with no irregularity declared and no overstrength on
  the supporting elements.
- S_DS cap used where §12.8.1.3 isn't met; C_s lower limits not checked.
- Drift from factored combinations, without C_d or I_e, or against the
  wrong Δ_a row or column.
- Property-line setback as SRSS of two buildings; members bridging a joint
  not sized for δ_MCE.

**Not findings under 7-22:**
- ELF on a tall or irregular building.
- Site Class F without site response analysis where an exception applies.
- No ground motion hazard analysis for an isolated or damped structure.
- No Ω₀ on collectors in a building braced entirely by wood light-frame
  shear walls.
- ρ = 1.0 for drift, overstrength combinations, or F_px.
- A gypcrete-topped wood floor (nonstructural topping ≤ 1½ in.) treated as
  flexible where each line meets the allowable drift (§12.3.1.1).
