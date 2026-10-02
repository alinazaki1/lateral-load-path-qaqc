# Concrete: Seismic Systems, Detailing, and Existing Buildings

This file covers reinforced concrete seismic force-resisting systems (SFRS):
materials, confinement, capacity design, moment frames, special structural walls
and boundary elements, coupling beams, splices, deformation compatibility, and
older non-ductile concrete. Read it whenever a lateral element, or anything the
lateral load passes through, is cast-in-place concrete, and when reviewing a
retrofit of or addition to an existing concrete building.

**Code basis.** Written to ASCE 7-22 for system selection and coefficients
(use the edition the project's jurisdiction adopts; see SKILL.md). Section
numbers here are **ACI 318-19**, the edition the 2025 CBC adopts through the
2024 IBC (verify: 2024 IBC / 2025 CBC adoption). ACI CODE-318-25 is published
but not yet adopted; **a re-check of this file against ACI CODE-318-25 is
pending.** Untagged ACI items were confirmed against the ACI 318-19 text. For
R/Ω₀/C_d and SDC background see `seismic_design_basis.md`; for anchorage of
walls and columns into footings and pile caps see
`foundations_and_geotechnical.md`.

## How Chapter 18 Scales with SDC

ACI ties seismic detailing to the SDC (§18.2.1). Know the tier before checking
any detail.

| SDC | Chapter 18 requirements |
|---|---|
| A | None |
| B | §18.2.2 only; ordinary moment frames per §18.3 |
| C | §18.2.2, 18.2.3, 18.13; intermediate moment frames per §18.4 |
| D–F | §18.2.2–18.2.8 and 18.12–18.14; special systems per §18.6–18.11 |

- Ordinary RC walls need no Chapter 18 detailing (§18.2.1.6(b)).
- Every member also satisfies Chapters 1–17 (§18.2.1.2), which is how rules
  such as the column first-tie location (§10.7.6.2) reach special frames.
- The material limits below (§18.2.5, 18.2.6, 20.2.2.5) apply to SMF and
  special walls (including coupling beams and piers), not to every member.

## Materials

### Concrete strength (Table 19.2.1.1)

| Application | Min f'c |
|---|---|
| General | 2,500 psi |
| Special moment frames; special walls with Grade 60 or 80 bars | 3,000 psi |
| Special walls with Grade 100 bars | 5,000 psi |
| Foundations in SDC D–F (except light residential stud-wall buildings ≤ 2 stories) | 3,000 psi |
| Drilled shafts, precast nonprestressed driven piles | 4,000 psi |
| Precast prestressed piles | 5,000 psi |

- **Lightweight concrete** in special moment frames, special walls, and their
  foundations: **f'c ≤ 5,000 psi** unless tests show equivalent performance
  (§19.2.1.1(d)).
- **Exposure-driven f'c:** durability classes (Table 19.3.2.1) often set f'c
  above the seismic minimum. Exposure Class **S2** requires w/cm ≤ 0.45 and
  **f'c ≥ 4,500 psi** (R19.3.2); F3 and C2 go higher. A high f'c may be a
  durability requirement, not a seismic one.
- **Environmental (water/wastewater) structures:** f'c ≥ 4,500 psi (verify: ACI
  350).

### Reinforcing steel (§20.2.1, 20.2.2.5)

- Bars must be **deformed**; plain bars or wire only for **spirals**
  (§20.2.1.1), and plain spiral bars must be A615, A706, A955, or A1035
  (§20.2.1.4).
- **Special moment frames, special structural walls** (including coupling beams
  and wall piers), and **anchor reinforcement in SDC C–F** use:
  - **(a) ASTM A706:** Grade 60 or 80 in special moment frames; Grade 60, 80, or
    100 in special walls. Grade 100 walls need f'c ≥ 5,000 psi.
  - **(b) ASTM A615 Grade 60 only**, with **all four** conditions:
    1. actual yield (mill tests) ≤ f_y + 18,000 psi (≤ 78 ksi for Grade 60);
    2. actual tensile ≥ 1.25 × actual yield;
    3. minimum fracture elongation in 8 in.: 14% for #3–#6, 12% for #7–#11, 10%
       for #14 and #18;
    4. minimum uniform elongation: 9% for #3–#10; 6% for #11, #14, #18.
- **A615 Grade 40, 80, and 100 are not permitted** in special systems (Grade
  80/100 for low-cycle fatigue; Grade 40 is no longer listed).
- Tensile-to-yield ratio: A706 Grade 60 and 80 rely on the ASTM A706
  specification; Table 20.2.1.3(b) sets **1.17 for A706 Grade 100**.
- ACI 318-14 (older projects / existing drawings): A615 Grade 40 or 60 with only
  conditions 1 and 2. Not acceptable on new work.
- **Why:** a bar much stronger than specified makes the member stronger in
  flexure than designed, which can shift failure to brittle shear or move the
  hinge into the column. The f_u/f_y ratio ensures strain hardening, which
  spreads yielding along the member instead of concentrating it at one crack.
- **Welding:** A706 is the weldable grade (controlled chemistry and carbon
  equivalent), so welded bars and bars with welded couplers should be A706.
  Welding A615 needs a chemistry check (verify: AWS D1.4).

### What to check on the general notes

- f'c meets Table 19.2.1.1 per element (SMF, special walls, SDC D–F
  foundations, piles, shafts; 5,000 psi with Grade 100 wall bars). Lightweight
  concrete in a special system or its foundation: ≤ 5,000 psi or test data.
- Exposure class is stated and f'c and w/cm agree with it. A mismatch is a
  durability finding, not a seismic one.
- Special-system rebar is **A706**, or **A615 Grade 60 with all four
  supplementary requirements** and mill certificates to verify them.
- Grade 80 only as A706 in SMF or special walls; Grade 100 only as A706 in
  special walls with f'c ≥ 5,000 psi.
- Welded bars are A706, with AWS D1.4 referenced.

### Common findings

- "A615 Grade 60" with no supplementary requirements in a special system.
- A615 Grade 40, 80, or 100 in a special system.
- The ACI 318-14 rebar note carried over from an old master note.

## Confinement, Hoops, and Hooks

Unconfined concrete is brittle. Closely spaced, closed transverse
reinforcement restrains the core's lateral expansion, raising its strength and
especially its ultimate strain (ductility), prevents longitudinal bar buckling,
and adds shear strength. After the cover spalls the core carries the load, so
confinement steel is sized from the core area A_ch. ACI strength design does not
credit confined strength f'cc directly (that belongs to nonlinear models such as
Mander); the benefit appears as spacing and A_sh rules. Spiral columns get
**0.85P_o vs 0.80P_o** maximum axial strength (Table 22.4.2.1) and φ = 0.75 vs
0.65 for compression-controlled sections (verify: ACI Table 21.2.2).

### Definitions (ACI 318-19 Chapter 2)

- **Seismic hook:** bend **≥ 135°**, extension **≥ max(6d_b, 3 in.)**, engaging
  the longitudinal bars and projecting into the interior of the hoop. **Circular
  hoops** may use a 90° bend.
- **Hoop:** a closed tie or continuously wound tie. A closed tie may be several
  pieces, each with seismic hooks at both ends, but not interlocking headed
  bars. A 90° standard tie hook is **not** a seismic hook.
- **Crosstie:** a continuous bar with a **135° seismic hook at one end** and a
  hook **≥ 90° with a 6d_b extension** at the other (the 3 in. minimum belongs
  to the 135° end), engaging **peripheral longitudinal bars**. Successive
  crossties on the same bars **alternate their 90° ends**, because a 90° hook
  can open once the cover spalls.
- **Two-piece beam hoops (§18.6.4.3):** a stirrup with seismic hooks at both
  ends closed by a crosstie. Consecutive crossties alternate 90° hooks to
  opposite sides; where a slab confines only one side, 90° hooks go on the slab
  side.
- **SMF columns with P_u > 0.3A_g f'c or f'c > 10,000 psi (§18.7.5.2):** every
  perimeter bar is supported by a hoop corner or seismic hook (crossties get
  135° hooks both ends), and **h_x ≤ 8 in.**

### What to check on column, beam, and boundary element details

- Hoops (SMF columns, beam hinge zones, boundary elements): 135° hooks with
  max(6d_b, 3 in.) extensions. Crossties: one 135° and one 90° end, 90° ends
  alternated, hooks on perimeter bars. Where P_u > 0.3A_g f'c or f'c > 10 ksi:
  135° hooks both ends, h_x ≤ 8 in.
- **Finding:** 90° hooks both ends, or standard tie hooks, in a special system.

## Capacity Design and Plastic Hinges

A concrete SFRS is a moment frame, shear walls, coupled walls, or a dual
combination. Energy is dissipated at **predetermined plastic hinges** detailed
to **yield in flexure**, the ductile mode. Every brittle mode at the hinge
(shear, anchorage, connection, instability, bar buckling) gets **more strength
than the hinge's flexural capacity**, so it cannot occur first.

- **Moment frames:** **beams next to the column face**, not the joint (which
  stays elastic); columns hinge only at the base. **Walls:** the **wall base**.
  **Coupled walls:** **coupling beams yield first**, then **piers at the base**.

Everything else in the SFRS, its connections, and the rest of the structure must
(1) stay elastic, (2) have more shear strength than the maximum shear developed
when the hinges yield, (3) avoid instability, anchorage failure, and bar
buckling, and (4) stay deformation-compatible with the SFRS.

### How ACI 318-19 implements it

- **Probable moment strength M_pr:** **1.25 f_y**, φ = 1.0; the concrete
  counterpart of expected strength in steel (`steel.md`).
- **SMF beam shear (§18.6.5.1):** V_e = (M_pr1 + M_pr2)/ℓ_n plus gravity shear.
- **SMF column shear (§18.7.6.1):** from M_pr; need not exceed the shear from
  the beams' M_pr at the joints, but not less than the analysis shear.
- **V_c = 0** in beam and column hinge zones where earthquake shear is at least
  half the total and P_u < A_g f'c/20 (§18.6.5.2, 18.7.6.2).
- **Strong column / weak beam** (ΣM_nc ≥ (6/5)ΣM_nb) and **joint shear** at
  1.25 f_y: see "SMF Beam-Column Joints".
- **Special wall shear (§18.10.3.1), new in 318-19:** **V_e = Ω_v·ω_v·V_u ≤
  3V_u**.
  - **Ω_v (flexural overstrength):** for h_wcs/ℓ_w > 1.5, the greater of
    M_pr/M_u and 1.5 (lower by detailed analysis, not below 1.0); otherwise 1.0.
  - **ω_v (higher-mode amplification)**, where h_wcs/ℓ_w ≥ 2.0: 0.9 + n_s/10 for
    n_s ≤ 6; 1.3 + n_s/30 ≤ 1.8 otherwise; n_s not less than 0.007h_wcs.

### What to check on the calcs

- SMF beam and column shears from M_pr (V_c = 0 where §18.6.5.2 / 18.7.6.2
  apply); special wall shear V_e = Ω_v·ω_v·V_u ≤ 3V_u with Ω_v, ω_v shown.
- **Finding:** design shears taken straight from the analysis in a special
  system (§18.6.5, 18.7.6, 18.10.3).

## RC Seismic Systems in ASCE 7-22

RC moment frames are ordinary, intermediate, or special, named for the level of
detailing provided to dissipate energy.

- **OMF:** essentially no special detailing; **not permitted in SDC C–F**. In
  SDC B, §18.3 requires at least **two continuous bars top and bottom** in
  beams, continuous bottom bars ≥ ¼ of the maximum bottom steel anchored to
  develop f_y at the support face, and a shear check (from column moment
  strength) for columns with **ℓ_u ≤ 5c₁**, against short-column shear failure.
- **IMF:** limited special detailing (§18.4); **not permitted in SDC D–F**.
- **SMF:** full detailing per §18.6–18.8. Footnote m: covers precast and
  cast-in-place.
- **Walls:** ordinary walls are **not permitted in SDC D–F**; special walls per
  §18.10.

### ASCE 7-22 Table 12.2-1: RC moment frames

| System | R | Ω₀ | C_d | B | C | D | E | F |
|---|---|---|---|---|---|---|---|---|
| C.5 Special RC moment frame | 8 | 3 | 5½ | NL | NL | NL | NL | NL |
| C.6 Intermediate RC moment frame | 5 | 3 | 4½ | NL | NL | NP | NP | NP |
| C.7 Ordinary RC moment frame | 3 | 3 | 2½ | NL | NP | NP | NP | NP |

### ASCE 7-22 Table 12.2-1: RC walls (height limits in ft)

| System | R | Ω₀ | C_d | D | E | F |
|---|---|---|---|---|---|---|
| A.1 Special RC shear wall (bearing wall) | 5 | 2½ | 5 | 160 | 160 | 100 |
| B.4 Special RC shear wall (building frame) | 6 | 2½ | 5 | 160 | 160 | 100 |
| A.2 / B.5 RC ductile coupled walls | 8 | 2½ | 8 | 160 | 160 | 100 |
| D.3 Special RC shear wall + SMF (dual) | 7 | 2½ | 5½ | NL | NL | NL |
| D.4 RC ductile coupled walls + SMF (dual) | 8 | 2½ | 8 | NL | NL | NL |
| A.3 / B.6 Ordinary RC shear wall | 4 / 5 | 2½ | 4 / 4½ | NP | NP | NP |

- **RC ductile coupled walls** are new in ASCE 7-22 (based on ACI 318-19
  §18.10.9). Footnote q: **h_n ≥ 60 ft** required.
- The §12.2.5.4 height increase (to 240 ft in SDC D/E, 160 ft in F) covers
  ductile coupled walls and **cast-in-place** special RC walls.

### What to check on the general notes / design criteria

- The RC system is permitted for the SDC. **Findings:** OMF in SDC C or above;
  IMF or ordinary walls in SDC D or above.
- R, Ω₀, C_d match the correct row (bearing wall vs. building frame vs. dual),
  and the height is within the limit.
- R = 8 ductile coupled walls only where h_n ≥ 60 ft and §18.10.9 is met.

## SMF Beams (§18.6)

### Geometry and longitudinal steel (§18.6.2, 18.6.3)

- **ℓ_n ≥ 4d**; **b_w ≥ the lesser of 0.3h and 10 in.**; projection beyond the
  column on each side ≤ the lesser of c₂ and 0.75c₁ (wide beams).
- **ρ ≤ 0.025 (Grade 60), ≤ 0.02 (Grade 80)**; at least **two continuous bars
  top and bottom**.
- Positive moment strength at a joint face ≥ ½ the negative strength there; at
  every section, strength ≥ ¼ of the maximum at either joint face.
- **No lap splices (§18.6.3.3)** within joints, within **2h of the column
  face**, or within 2h of any other section where flexural yielding is likely.
  2h is measured from **each** joint face. Laps elsewhere are enclosed by hoops
  at **s ≤ min(d/4, 4 in.)**.

### Transverse steel (§18.6.4)

- **Hoops over 2h** from the column face toward midspan at both ends, and on
  both sides of any other section where yielding may occur.
- **First hoop ≤ 2 in.** from the column face.
- **Hinge-zone spacing ≤ the smallest of** d/4; **6d_b (Grade 60) or 5d_b (Grade
  80)**, d_b = smallest primary flexural bar (not skin steel); 6 in.
- **Lateral support (§18.6.4.2), new in 318-19:** flexural bars nearest the
  tension and compression faces are laterally supported, supported bars **≤ 14
  in. apart**; skin reinforcement exempt.
- **Elsewhere:** stirrups with **seismic hooks both ends** at **≤ d/2**
  (§18.6.4.6).
- **P_u > A_g f'c/10 (§18.6.4.7):** column-type hoops (§18.7.5.2–18.7.5.4) in
  the 2h zones.

### What to check on beam elevations and schedules

- 2h hoop zone at each end (and at any other yielding section); first hoop ≤ 2
  in. from the face.
- Hinge-zone spacing ≤ min(d/4, 6d_b or 5d_b for Grade 80, 6 in.); stirrups ≤
  d/2 elsewhere with seismic hooks both ends.
- No laps in the joint or within 2h of either face; other laps hooped at ≤
  min(d/4, 4 in.).
- Two continuous bars top and bottom; bottom strength at face ≥ ½ top; ρ ≤
  0.025 / 0.02; ℓ_n ≥ 4d; b_w and wide-beam limits met.
- Supported top and bottom bars ≤ 14 in. apart in the hoop zone; 135° hooks;
  two-piece hoops alternate crosstie 90° ends.

### Common findings

- Beams with no 2h hoop zone called out.
- Laps within 2h of the joint face (a gravity-beam habit).

## SMF Columns (§18.7)

### Geometry and longitudinal steel

- Least dimension **≥ 12 in.**; least/greatest **≥ 0.4**.
- **0.01 ≤ ρ_g ≤ 0.06.** The 6% includes doubled bars at laps, so laps cap ρ at
  about 3–4% in practice and make the lap region congested.
- Circular-hoop columns: at least **six** bars (§18.7.4.2).
- **§18.7.4.3, new in 318-19:** **1.25ℓ_d ≤ ℓ_u/2**. Large bars in short columns
  fail this; it guards against bond-splitting.
- **Laps (§18.7.4.4):** **center half** of the clear height only, designed as
  **tension lap splices** (Class B, project standard), enclosed at the
  **hinge-zone spacing** (§18.7.5.2, 18.7.5.3). Never at the floor line.

### Transverse steel

- **ℓ_o (§18.7.5.1)** from **each joint face**, and both sides of any section
  where yielding is likely: ≥ the largest of the largest column dimension,
  **ℓ_u/6**, and **18 in.**
- **Spacing within ℓ_o (§18.7.5.3)** ≤ the smallest of:
  1. ¼ of the least column dimension;
  2. **6d_b (Grade 60) or 5d_b (Grade 80)**, smallest longitudinal bar;
  3. **s_o = 4 + (14 − h_x)/3** in., with 4 in. ≤ s_o ≤ 6 in. (h_x = 14 in.
     gives 4 in.; h_x = 8 in. gives the 6 in. cap).
- **h_x** (spacing of bars supported by hoop corners or crosstie legs) **≤ 14
  in.**, or **≤ 8 in.** where P_u > 0.3A_g f'c or f'c > 10 ksi.
- **First hoop at s/2 (§10.7.6.2):** bottom hoop ≤ ½ the spacing above the
  footing or slab (§10.7.6.2.1); top hoop ≤ ½ the spacing below the lowest slab
  reinforcement, or **3 in.** below the shallowest beam's reinforcement where
  beams frame all four sides (§10.7.6.2.2). Applies through §18.2.1.2.
- **Outside ℓ_o (§18.7.5.5):** ≤ min(6d_b, 6 in.).
- **A_sh (§18.7.5.4, Table 18.7.5.4).** Rectangular hoops with P_u ≤ 0.3A_g f'c
  and f'c ≤ 10 ksi: greater of **0.3(A_g/A_ch − 1)f'c/f_yt** and
  **0.09f'c/f_yt**. Above either limit, add **0.2k_f k_n P_u/(f_yt A_ch)**,
  where k_f = f'c/25,000 + 0.6 ≥ 1.0 and k_n = n_l/(n_l − 2) (n_l = supported
  perimeter bars). Spirals use 0.45(...), 0.12(...), and 0.35k_f P_u/(f_yt
  A_ch).
- **Thick cover (§18.7.5.7):** cover outside the confining steel > 4 in. needs
  added reinforcement at ≤ 4 in. cover and ≤ 12 in. spacing.
- **Columns under discontinued stiff members (§18.7.5.6)**, such as a wall that
  stops above: full-height confinement where P_u > A_g f'c/10 (A_g f'c/4 if
  forces were Ω₀-amplified), extending **ℓ_d into the discontinued member** and
  **12 in. into a footing or mat**. Cross-check the Ω₀ requirement for
  discontinuities in `seismic_design_basis.md`.

### What to check on column schedules and elevations

- Section ≥ 12 in.; aspect ≥ 0.4; 1% ≤ ρ_g ≤ 6% including laps.
- ℓ_o dimensioned top and bottom, ≥ max(column dimension, ℓ_u/6, 18 in.).
- Spacing in ℓ_o ≤ min(h_min/4, 6d_b or 5d_b, s_o); h_x ≤ 14 in. (8 in. where
  triggered); crossties alternate 90° ends.
- First hoop at s/2 top and bottom (3 in. below beam steel with beams on all
  four sides); mid-height spacing ≤ min(6d_b, 6 in.).
- Laps only in the center half, Class B, at hinge-zone spacing; 1.25ℓ_d ≤ ℓ_u/2.
- A_sh calc for each column type, with the k_f k_n P_u term where triggered.
- Columns under discontinued walls: full-height confinement, extended into the
  wall above and 12 in. into the footing.

### Common findings

- A generic tie spacing (for example "#4 @ 12") carried through ℓ_o.
- **Laps at the floor line**, typical for gravity columns but **not allowed in
  SMF columns**.
- Missing ℓ_o dimension.

## SMF Beam-Column Joints (§18.7.3, 18.8)

### Strong column / weak beam

A column failure can collapse a whole story; a beam failure stays local to its
floor. Stronger columns force the hinges into the beams.

- **ΣM_nc ≥ (6/5)ΣM_nb** at every joint, for beam moments in **both sway
  directions** (§18.7.3.2).
- Moments are summed at the joint faces. M_nc uses the factored axial force
  giving the **lowest** column strength. M_nb for T-beams includes **slab
  reinforcement** within the §6.3.2 effective flange width where the slab is in
  tension and the bars are developed; this raises M_nb and is easy to miss.
- **Exception (§18.7.3.1):** not required where the column is discontinuous
  above the joint (for example, at the roof) and its factored axial force under
  E is below A_g f'c/10.
- **A column that fails (§18.7.3.3)** can't be counted toward lateral strength
  or stiffness and must satisfy §18.14.

### Joint reinforcement and geometry

- **General rule (§18.8.3.1):** same transverse reinforcement as the column
  hinge zone, through the joint.
- **Relaxed case (§18.8.3.2):** beams on **all four sides**, each **≥ ¾ of the
  column width**: amount may be halved and spacing relaxed to **6 in.** The
  §18.7.5.7 thick-cover rule also applies.
- **Joint shear (§18.8.2.1, 18.8.4):** beam bar forces at 1.25 f_y; V_u at joint
  mid-height with the column shear consistent with beam M_pr; V_n per Table
  18.8.4.3.
- **Joint depth (§18.8.2.3)** for beam bars passing through, ≥ the greatest of:
  **20d_b/λ** of the largest Grade 60 bar (λ = 0.75 lightweight, so ≈
  **26.7d_b**); **26d_b** of the largest Grade 80 bar; **h/2** of any SFRS beam
  framing in. Joints with Grade 80 beam bars must be **normalweight**
  (§18.8.2.3.1).
- **Terminated beam bars (§18.8.2.2):** extend to the **far face of the confined
  core**, developed per §18.8.5.
- **Wide beams (§18.8.3.3):** beam bars outside the column core need confining
  transverse reinforcement unless a transverse beam provides it.

### What to check on joint details and calcs

- Strong-column / weak-beam calc at each joint, both directions, **including
  slab steel in M_nb**; failing columns treated per §18.14.
- Joint hoops shown through the joint depth at hinge-zone spacing; relaxed 6 in.
  only with four confining beams each ≥ ¾ column width.
- Joint depth ≥ 20d_b (Grade 60, normalweight), 26.7d_b (Grade 60, lightweight),
  or 26d_b (Grade 80), and ≥ h/2 of framing beams; Grade 80 beam bars only in
  normalweight joints.
- Hooked or headed beam bars reach the far face of the confined core.
- Joint shear calc uses 1.25 f_y.

### Common findings

- Joint hoops omitted ("column ties stop at the beam").
- Relaxed 6 in. joint spacing at an exterior or corner joint.
- Strong-column / weak-beam check without slab reinforcement.

## Special Structural Walls (§18.10)

### Web reinforcement and curtains

- **ρ_l and ρ_t ≥ 0.0025** (§18.10.2.1); where V_u ≤ λ√f'c A_cv, ρ_t may drop to
  Chapter 11 values. Reinforcement contributing to V_n is continuous and
  distributed across the shear plane.
- Where h_w/ℓ_w ≤ 2.0, **ρ_l ≥ ρ_t** (§18.10.4.3).
- **Spacing ≤ 18 in.** (§18.10.2.1). The general 3 × thickness limit also
  applies and governs below 6 in. thickness (verify: ACI §11.7.2.1).
- **Two curtains (§18.10.2.2)** where **V_u > 2λ√f'c A_cv or h_w/ℓ_w ≥ 2.0**
  (whole-wall h_w and ℓ_w). The slenderness trigger is new in 318-19:
  single-curtain slender walls were linked to out-of-plane instability.
- **Wall-end steel (§18.10.2.4), new in 318-19:** walls with h_w/ℓ_w ≥ 2.0 and a
  single critical section need minimum longitudinal reinforcement concentrated
  at the ends.
- **Shear caps (§18.10.4.4–5):** walls sharing a lateral force, V_n ≤ 8√f'c A_cv
  total; any single vertical segment ≤ 10√f'c A_cw; horizontal segments and
  coupling beams ≤ 10√f'c A_cw. Design shear is amplified per §18.10.3.1 (see
  "Capacity Design").

### Splices and development (§18.10.2.3)

The wall base is treated like a beam hinge zone.

- **(a)** Except at the top of a wall, bars extend **12 ft above** where no
  longer needed, but need not extend more than ℓ_d above the next floor.
- **(b)** Where yielding is likely, bars are developed for **1.25ℓ_d**.
- **(c)** **No laps in boundary regions** over **h_sx above and ℓ_d below** a
  critical section where yielding is likely (h_sx need not exceed 20 ft).
  Boundary regions are the boundary element lengths plus a wall thickness past
  any intersecting wall.
- **(d)** Mechanical and welded splices per §18.2.7 and 18.2.8.

### Boundary element triggers

- **Displacement-based (§18.10.6.2)**, usually governing. Applies to walls with
  **h_wcs/ℓ_w ≥ 2.0**, continuous base to top, with one critical section.
  - Required where **1.5δ_u/h_wcs ≥ ℓ_w/(600c)**, δ_u/h_wcs ≥ 0.005.
  - Extends above and below the critical section ≥ the greater of **ℓ_w and
    M_u/4V_u**.
  - New in 318-19: also **b ≥ √(0.025cℓ_w)** or a drift-capacity check,
    **δ_c/h_wcs ≥ 1.5δ_u/h_wcs** (Eq. 18.10.6.2b).
- **Stress-based (§18.10.6.3):** at boundaries **and edges of openings** where
  extreme-fiber compression under factored loads including E (linear, gross
  section) exceeds **0.2f'c**; may stop where it drops below **0.15f'c**.
- Older codes (pre-1999 ACI) sized boundary elements as columns carrying all
  gravity load plus overturning. Current ACI treats them as confined regions
  that let the wall end reach large compressive strains. Do not flag a boundary
  element for failing to carry all vertical load on its own.

### Special boundary element detailing (§18.10.6.4)

- **(a) Length** ≥ the larger of **c − 0.1ℓ_w** and **c/2**.
- **(b) Compression zone width b ≥ h_u/16.**
- **(c)** h_w/ℓ_w ≥ 2.0 walls with **c/ℓ_w ≥ 3/8**: **b ≥ 12 in.**
- **(d) Flanged sections:** include the effective flange and extend **≥ 12 in.
  into the web**.
- **(e) Transverse steel:** per SMF column rules, but spacing ≤ **⅓ of the least
  boundary element dimension**.
- **(f) h_x ≤ the lesser of 14 in. and ⅔ of the thickness**; hoop legs ≤ 2 ×
  thickness; adjacent hoops overlap ≥ the lesser of 6 in. and ⅔ thickness (⅔
  limits new in 318-19).
- **(g) A_sh (Table 18.10.6.4(g)):** greater of 0.3(A_g/A_ch − 1)f'c/f_yt and
  0.09f'c/f_yt, with A_g and A_ch over the boundary element only.
- **(h)** Floor slab concrete within the boundary element **≥ 0.7f'c of the
  wall**.
- **(i)** Web vertical bars near the critical section: crossties with seismic
  hooks both ends at ≤ 12 in. vertical spacing.
- **(j) Base:** hoops extend **ℓ_d into the support**, or **12 in. into a
  footing, mat, or pile cap**.
- **(k) Horizontal web bars** extend to **within 6 in. of the wall end** and
  develop f_y **within the confined core** by standard hooks or heads. Straight
  bars only where the core is long enough and web A_s f_y/s ≤ the boundary
  element's A_sh f_yt/s. The boundary element anchors the wall's shear steel in
  confined concrete.

### Where special boundary elements are not required (§18.10.6.5)

- **(a)** Horizontal bars at the wall edge have a **standard hook around the
  edge bars** or **U-stirrups** spliced to them, unless V_u < λ√f'c A_cv.
- **(b)** If the boundary longitudinal ratio exceeds **400/f_y**, the ends need
  ties per §18.7.5.2(a)–(e), at vertical spacing per Table 18.10.6.5(b):

| Bar grade | Near the critical section | Elsewhere |
|---|---|---|
| Grade 60 | min(6d_b, 6 in.) | min(8d_b, 8 in.) |
| Grade 80 | 5d_b | 6d_b |
| Grade 100 | 4d_b | 6d_b |

### What to check on wall elevations, sections, and boundary element details

- ρ_l, ρ_t ≥ 0.0025; spacing ≤ 18 in.; ρ_l ≥ ρ_t where h_w/ℓ_w ≤ 2.0.
- Two curtains where V_u > 2λ√f'c A_cv **or** h_w/ℓ_w ≥ 2.0.
- Trigger method identified and calculated per wall (c, δ_u, h_wcs, or 0.2f'c);
  boundary elements at openings where the stress method triggers them.
- Boundary elements dimensioned: length ≥ max(c − 0.1ℓ_w, c/2); height ≥
  max(ℓ_w, M_u/4V_u) each side of the critical section; b ≥ h_u/16 (≥ 12 in.
  where c/ℓ_w ≥ 3/8); √(0.025cℓ_w) or drift check; flanges per (d).
- Boundary hoops: spacing ≤ ⅓ least dimension and column limits; h_x ≤ min(14
  in., ⅔ thickness); A_sh over the boundary element; hoops extend ℓ_d or 12 in.
  into the footing, mat, or pile cap.
- Horizontal web bars run to within 6 in. of the end and hook or head into the
  confined core; slab f'c within the boundary element ≥ 0.7 × wall f'c.
- Where special boundary elements aren't required: edge hooks or U-stirrups, and
  Table 18.10.6.5(b) ties where ρ at the end > 400/f_y.
- No boundary-bar laps within h_sx above / ℓ_d below the critical section; bars
  developed 1.25ℓ_d where yielding is likely.

### Common findings

- Boundary element missing or not dimensioned.
- Horizontal wall bars stop short of the boundary core.
- Single curtain in a slender wall.
- Boundary bars lapped in the hinge zone at the wall base.

## Coupling Beams and Ductile Coupled Walls (§18.10.2.5, 18.10.7, 18.10.9)

Coupled walls meet all special wall rules. Coupling beam reinforcement depends
on the clear span to depth ratio ℓ_n/h and the shear stress.

- **ℓ_n/h ≥ 4 (§18.10.7.1):** an **SMF beam** (§18.6) with the wall boundary as
  the column, including the 2h hoop zones (hoops full length are common and
  conservative). The §18.6.2.1(b) and (c) width limits may be waived if lateral
  stability is shown. Longitudinal bars developed **1.25ℓ_d** into the wall
  (§18.10.2.5(a)).
- **2 ≤ ℓ_n/h < 4 (§18.10.7.3):** diagonal **or** conventional reinforcement.
- **ℓ_n/h < 2 with V_u ≥ 4λ√f'c A_cw (§18.10.7.2):** **diagonals required**,
  unless loss of the beam's stiffness and strength is shown not to impair
  vertical load capacity, egress, or nonstructural components.
  - V_n = 2A_vd f_y sin α ≤ **10√f'c A_cw**; α follows the beam geometry.
  - Each group: **at least four bars in two or more layers**.
  - Diagonals developed **1.25ℓ_d** in tension into the walls
    (**§18.10.2.5(b)**). Older editions used 1.0ℓ_d, under §18.10.7.4.
- **Confining the diagonals (§18.10.7.4):**
  - **(c) Each diagonal group:** cage ≥ b_w/2 by b_w/5 out-to-out; A_sh per the
    (i)/(ii) expressions; spacing along the diagonal ≤ 6d_b of the smallest
    diagonal bar; legs ≤ 14 in. apart; perimeter bars at 0.002b_w s each way,
    spaced ≤ 12 in.
  - **(d) Full beam section:** transverse spacing ≤ min(6 in., 6d_b of the
    diagonals); crossties and hoop legs ≤ 8 in. apart each way. Usually easier
    to build, since the diagonal cages don't have to thread past each other.
- **Ductile coupled walls (§18.10.9)**, required for the ASCE 7-22 R = 8 rows:
  **all** coupling beams ℓ_n/h ≥ 2; ℓ_n/h ≤ 5 at **≥ 90% of levels**; each wall
  pier h_w/ℓ_w ≥ 2; plus ASCE 7-22 h_n ≥ 60 ft. Otherwise the system is a
  special wall (R = 5 or 6), not R = 8.

### What to check on coupling beam details and wall elevations

- ℓ_n/h stated for every coupling beam; reinforcement type matches ℓ_n/h and
  shear stress.
- Diagonals where ℓ_n/h < 2 and V_u ≥ 4λ√f'c A_cw, ≥ 4 bars per group in two or
  more layers; V_n ≤ 10√f'c A_cw.
- Diagonal embedment into each pier ≥ **1.25ℓ_d**, dimensioned on the detail;
  conventional longitudinal bars likewise 1.25ℓ_d.
- Confinement option (c) or (d) shown with spacing, leg spacing, and (for c)
  perimeter bars.
- R = 8 only with all §18.10.9 limits met and h_n ≥ 60 ft.

### Common findings

- Diagonal bars embedded less than 1.25ℓ_d (for example, 1.0ℓ_d).
- R = 8 ductile coupled walls that miss a §18.10.9 limit or h_n ≥ 60 ft.

## Splices: Lap, Mechanical, and Welded

### Tension lap splices (Table 25.5.2.1)

- **Class A:** greater of **1.0ℓ_d** and 12 in.; only where A_s,provided /
  A_s,required ≥ 2.0 **and** ≤ 50% of bars are spliced within the lap.
- **Class B:** greater of **1.3ℓ_d** and 12 in.; all other cases.
- **Use Class B in seismic members** (project standard).
- Lap location limits: §18.6.3.3 (beams), §18.7.4.4 (columns), §18.10.2.3(c)
  (walls); see each member section.

### Mechanical couplers (§18.2.7, 25.5.7)

- **Type 1:** develops ≥ **1.25f_y**. **Type 2:** develops the **specified
  tensile strength** of the bar.
- **Only Type 2 couplers on Grade 60 bars may be used at any location**,
  including hinge zones (§18.2.7.2); the one exception is precast connections
  (§18.9.2.1(c)).
- **All other couplers** (every Type 1, and Type 2 on Grade 80 or 100) stay out
  of 2h from column or beam faces in SMF and away from critical sections where
  yielding is likely: bar stress there can exceed what they reliably carry.
- **Walls** follow the same §18.2.7 rules (§18.10.2.3(d)); no separate wall
  exception.

### Welded splices and welding (§18.2.8)

- Welded splices meet §25.5.7 (≥ 1.25f_y) and are **not permitted** within 2h of
  column or beam faces in SMF or near yielding critical sections (§18.2.8.1). No
  grade exception like the Type 2 rule.
- **Welding stirrups, ties, inserts, or similar elements to required
  longitudinal bars is not permitted** (§18.2.8.2); crossing welds embrittle the
  bar locally.
- Welded bars are A706; welding per AWS D1.4 (R18.2.8.1).

### What to check on general notes, typical details, and elevations

- Lap tables give Class B for seismic members, with the 12 in. minimum.
- Coupler notes specify **Type 1 or Type 2** and bar grade. A coupler in a hinge
  zone is acceptable only as Type 2 on Grade 60.
- **Finding:** a Type 1, unspecified, or Type 2 on Grade 80/100 coupler, or a
  welded splice, within 2h of a joint face or at a yielding critical section,
  **including the wall base**.
- No welding of ties, embeds, or inserts to longitudinal bars (check embed and
  anchor details at walls and columns).

## Deformation Compatibility (ASCE 7-22 §12.12.4, ACI §18.14)

Members outside the SFRS still go through the building's drift and must keep
carrying gravity load while they do.

- **ASCE 7-22 §12.12.4:** in SDC D–F, every component not in the SFRS must be
  adequate for gravity loads **plus the effects of δ_DE**, considering the
  stiffening effect of adjoining rigid structural and nonstructural elements. RC
  frame members not designated part of the SFRS must comply with **ACI §18.14**.
- **ACI §18.14:** non-SFRS members are evaluated for gravity combinations,
  including vertical ground motion, acting with the design displacement δ_u.
  Detailing depends on whether induced moments and shears exceed design strength
  (§18.14.3.2 vs. §18.14.3.3). **If δ_u effects aren't explicitly checked, the
  stricter §18.14.3.3 detailing applies.**
- Columns failing strong-column / weak-beam (§18.7.3.3) fall under §18.14.
  Older editions put this rule in ACI 318 §21.11.

### What to check on the calcs and gravity framing

- In SDC D–F, gravity columns and slab-column connections are checked at δ_DE /
  δ_u, or detailed to §18.14.3.3. This is commonly missed; always ask for it.
- Where new work ties into an existing non-ductile frame, the old columns'
  ability to follow the new system's drift is addressed.

## Existing Non-Ductile Concrete Buildings

### Background and deficiencies

Concrete frames built before about **1976** generally lack ductile detailing.
Ductile frame detailing entered the UBC in the late 1960s and ACI 318-71
(Appendix A); after the 1971 San Fernando earthquake the 1976 UBC made major
seismic changes. The Los Angeles non-ductile concrete ordinance targets
buildings permitted under pre-1977 codes (verify: code history and LA ordinance
cutoff). Treat 1976 as a **screening date**, not a bright line; the detailing on
the drawings or in the field is what matters.

- **Inadequate confinement:** small, widely spaced, **open 90°-hook ties**.
- **Inadequate laps:** too short, or in the wrong place such as a plastic hinge;
  column laps just above the floor, often only 20–24d_b (verify: practice).
- **Joints** without enough shear strength; often no ties through the joint
  (verify: practice).
- **Weak column / strong beam** frames.
- Discontinuous bottom beam bars that can pull out under reversal; captive or
  short columns from partial infill or spandrels; flat-plate punching with no
  shear reinforcement; soft or weak first stories; discontinuous shear walls on
  unconfined columns (verify: practice).

Typical earthquake damage:

1. **Column hinging** (weak column / strong beam), risking story collapse.
2. **Brittle column shear:** X-cracking from inadequate ties; little warning.
3. **Column compression:** crushing and bar buckling from unconfined concrete.
4. **Joint failure:** X-cracking from inadequate joint shear strength.

### Code path

Existing buildings are evaluated and retrofitted under the **California Existing
Building Code (CEBC)** using **ASCE 41** (Tier 1 screening, Tier 2, Tier 3), not
ASCE 7 new-building detailing. ASCE 41 treats non-ductile columns as
force-controlled or low-ductility members (verify: CEBC / ASCE 41).

### What to check on as-builts, evaluation reports, and retrofit drawings

- Evaluation basis is CEBC / ASCE 41, not ASCE 7 (verify: CEBC).
- As-builts document tie size, spacing, and hook type (90° vs. 135°); lap
  location and length; joint ties; column vs. beam strength; short columns.
- The retrofit addresses **each** identified deficiency (for example, FRP or
  steel column jackets, new shear walls or frames, joint strengthening).
- For additions or new lateral elements tied to the old frame, deformation
  compatibility of the existing columns under the new drift is addressed.
