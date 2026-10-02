# Masonry Lateral Systems: Seismic Design and Detailing Reference

This file covers reinforced masonry (CMU and clay) as a seismic
force-resisting system: governing documents, system selection and
R/Ω₀/C_d, the capacity-design rules for special walls and coupling beams,
the ASCE 7-22 modifications to TMS 402, and prescriptive detailing for SDC
D–F. It also covers existing unreinforced masonry (URM) bearing-wall
buildings and URM infill in moment frames. Read it whenever the SFRS
includes masonry walls, a masonry wall frame, or masonry built into a
moment-frame bay, and whenever the project is a URM retrofit.

**Code edition note.** ASCE 7-22 §14.4 and Chapter 23 reference **TMS
402-16 and TMS 602-16**, and the ASCE 7-22 modifications (§14.4.3 through
§14.4.6) are written against that edition's numbering. The 2024 IBC /
2025 CBC may reference a newer edition (TMS 402-22) (verify: IBC/CBC).
TMS section references below use the current TMS chapter layout. ASCE
7-22 items marked as such are confirmed; **all TMS 402 content is from
knowledge and confirmation against TMS 402 is pending**, so those items
carry "(verify: TMS 402)".

The typical masonry SFRS on current projects is the **special reinforced
masonry shear wall**.

## 1. Governing documents and design methods

### Documents

- Masonry structures and their connections are designed, built, and
  quality-controlled per:
  - **IBC (CBC) Chapter 21**;
  - **TMS 402**, the masonry building code;
  - **TMS 602**, the masonry specification.
- TMS 402 and TMS 602 are joint publications, commonly called the "TMS
  code and specification."
- **Naming.** The documents used to carry a triple designation (TMS
  402/ACI 530/ASCE 5 and TMS 602/ACI 530.1/ASCE 6). Starting with the
  2016 editions, ACI and ASCE dropped their designations, so the current
  names are just **TMS 402-xx** and **TMS 602-xx** (verify: TMS 402).
  Accept either name on the drawings, but an "ACI 530" citation signals a
  pre-2016 edition; confirm the edition is the one the governing building
  code adopts.
- **California public schools and hospitals** (DSA / HCAI-OSHPD) use
  **CBC Chapter 21A**, which has stricter masonry provisions: for example,
  masonry must be **grouted solid** and **special inspection** is
  required (verify: IBC/CBC).

### IBC Chapter 21 section map (verify: IBC/CBC)

| Section | Older IBC | Current IBC |
|---|---|---|
| 2106 | Seismic design | Seismic design (now largely points to ASCE 7 / TMS 402) |
| 2107 | ASD | ASD, via TMS 402 Ch. 8 with modifications |
| 2108 | SD | SD, via TMS 402 Ch. 9 with modifications |
| 2109 | Empirical design | Empirical design of **adobe** masonry |

### Design methods

- Three methods exist: **allowable stress design (ASD)**, **strength
  design (SD)**, and **empirical design**.
- **Empirical design is retired for the SFRS.**
  - TMS 402-16 moved empirical design of masonry to an **appendix**
    (verify: TMS 402).
  - It can't be used for the SFRS above **SDC A/B**, and it is limited by
    wind speed and building height (verify: TMS 402).
  - For this review, empirical design is **not accepted for any element
    of the SFRS** (project standard). In SDC C or above, an empirically
    designed shear wall is a finding.

### What to check on the drawings / calcs

- General notes cite **TMS 402 / TMS 602** at the edition the governing
  IBC/CBC adopts, and IBC/CBC Chapter 21 (or **21A** for DSA/HCAI-OSHPD
  work).
- General notes give **f'm**, **unit type** (CMU or clay), **grout**
  (strength/type), **grouting extent** (solid vs. partial), and **special
  inspection** requirements.
- The design method (ASD or SD) is stated in the calcs and is consistent
  throughout; no element of the SFRS is designed empirically.
- On DSA/HCAI-OSHPD projects, walls are **solid grouted** and the
  Chapter 21A provisions are invoked (verify: IBC/CBC).

## 2. Seismic design philosophy

- Masonry walls are built from **concrete masonry units (CMU)** or **clay
  masonry units** (brick).
- The masonry SFRS is either:
  - **masonry shear walls**, or
  - **masonry wall frames**: piers/columns joined by coupling beams.

### Masonry shear walls

- Shear walls come in three detailing levels, **ordinary, intermediate,
  and special**, each with its own detailing requirements (TMS 402 and
  ASCE 7) for dissipating earthquake energy.
- **Goal:** ductile behavior with adequate warning before failure. The
  wall must fail by **yielding of the vertical (tension) steel before the
  masonry crushes**.
- **Enough steel to get past cracking: M_n ≥ 1.3 M_cr.**
  - If the flexural strength barely exceeds the cracking moment, the load
    dumps into too little steel when the masonry cracks, and the failure
    is sudden and brittle.
  - In current TMS 402 strength design, this minimum is tied to the
    reinforcement limits and cracking-moment check in **Chapter 9**
    (verify: TMS 402). Older editions carried it under a different
    section number.
  - It is a minimum-steel rule for **strength design** and matters most
    for **lightly reinforced walls**, where cracking can govern.
- **Shear capacity design (special walls).** Diagonal shear cracking
  causes sudden, brittle collapse, so the wall must yield in flexure
  before it can fail in shear (the same idea as concrete special walls;
  see `concrete.md`).
  - **SD:** φV_n ≥ the shear corresponding to **1.25 M_n**; **V_n need
    not exceed 2.5 V_u** (TMS 402 Ch. 7) (verify: TMS 402).
  - **ASD:** the design shear is increased by **1.5** instead (verify:
    TMS 402).
  - Applies to **special** walls, not ordinary or intermediate walls.

### Masonry wall frames

- The lateral system is **piers or columns linked by coupling beams**. In
  practice it is a perforated wall with rows of window openings: the
  piers are the masonry between windows; the coupling beams are the
  masonry above and below them. Same concept as concrete coupled shear
  walls.
- For ductile behavior, **flexural yielding is limited to two places**:
  - the **coupling beams at the face of the piers**;
  - the **base of the piers/columns**.
- The piers are designed for the shear that develops when the **coupling
  beams reach their nominal flexural strength** (hinge), protecting them
  against shear cracking.
- **No separate ASCE 7-22 row.** Table 12.2-1 has no masonry wall frame
  or masonry moment frame entry. A wall frame is designed and detailed
  under the **special reinforced masonry shear wall** system. TMS 402
  carries the wall-frame provisions: pier and beam proportions and the
  strong-pier / weak-beam intent (verify: TMS 402).
- Typical reinforcing:
  - **Piers:** vertical bars in grouted cells, horizontal bars hooked
    around the end bars.
  - **Coupling beams:** a bond-beam course with top and bottom bars, plus
    vertical stirrups in the cells.

### Coupling beams, ASCE 7-22 §14.4.5.2 (adds to TMS 402)

- Coupling beams must reach their nominal moment or shear strength
  **before either shear wall does**.
- Required strength:

  **φV_n ≥ 1.25(M₁ + M₂)/L_c + 1.4V_g**

  where M₁ and M₂ are the nominal moments at the beam ends, L_c is the
  clear length between walls, and V_g is the unfactored gravity shear.
- Where a **concrete floor or roof** acts with the beam, M_n includes the
  slab reinforcement within a width of **6 × the slab thickness**. This
  raises the beam's flexural strength and therefore its required shear,
  so omitting the slab steel is unconservative.

### What to check on the drawings / calcs

- Strength-design walls show the **M_n ≥ 1.3 M_cr** check, especially
  lightly reinforced walls (verify: TMS 402).
- Special walls are designed for the shear at **1.25 M_n** (SD, capped at
  2.5 V_u) or **1.5×** the design shear (ASD), not just the analysis
  shear (verify: TMS 402).
- A wall frame is classified as a special reinforced masonry shear wall
  system, and the calcs show the pier shear designed for coupling-beam
  hinging.
- Coupling beams meet **φV_n ≥ 1.25(M₁ + M₂)/L_c + 1.4V_g**, with slab
  steel within 6t included in M_n where a concrete slab acts with the
  beam (ASCE 7-22 §14.4.5.2).
- Pier elevations show horizontal bars hooked around the end vertical
  bars; coupling-beam details show top and bottom bars and stirrups.

## 3. System selection: ASCE 7-22 Table 12.2-1

Confirmed against ASCE 7-22 Table 12.2-1. Height limits are in feet; NL =
not limited, NP = not permitted.

| System | R | Ω₀ | C_d | B | C | D | E | F |
|---|---|---|---|---|---|---|---|---|
| A.8 Special reinforced (bearing wall) | 5 | 2½ | 3½ | NL | NL | 160 | 160 | 100 |
| B.17 Special reinforced (building frame) | 5½ | 2½ | 4 | NL | NL | 160 | 160 | 100 |
| A.9 Intermediate reinforced (bearing) | 3½ | 2½ | 2¼ | NL | NL | NP | NP | NP |
| B.18 Intermediate reinforced (building frame) | 4 | 2½ | 4 | NL | NL | NP | NP | NP |
| A.10 Ordinary reinforced (bearing) | 2 | 2½ | 1¾ | NL | **160** | NP | NP | NP |
| B.19 Ordinary reinforced (building frame) | 2 | 2½ | 2 | NL | **160** | NP | NP | NP |
| A.11 / B.20 Detailed plain | 2 | 2½ | 1¾ / 2 | NL | NP | NP | NP | NP |
| A.12 / B.21 Ordinary plain | 1½ | 2½ | 1¼ | NL | NP | NP | NP | NP |
| D.11 Special reinforced + SMF (dual) | 5½ | 3 | 5 | NL | NL | NL | NL | NL |
| D.12 Intermediate reinforced + SMF (dual) | 4 | 3 | 3½ | NL | NL | NP | NP | NP |

Key points:

- **SDC D–F:** only **special reinforced** masonry walls (160/160/100 ft).
  Intermediate and ordinary are NP.
- **SDC C:** ordinary reinforced walls are limited to **160 ft**.
- **Plain (unreinforced) masonry**, detailed or ordinary, is limited to
  **SDC B**.
- The **dual-system** rows raise Ω₀ to **3**.
- **Prestressed** and **AAC** masonry rows also exist (AAC ordinary
  reinforced: 35 ft in SDC C). Look them up directly if the project uses
  either.
- See `seismic_design_basis.md` for how R, Ω₀, C_d, and ρ flow into the
  analysis.

### What to check on the drawings / calcs

- The stated masonry system (bearing wall vs. building frame vs. dual)
  matches the **R, Ω₀, C_d** used in the calcs and on the general notes.
- In **SDC D–F**, the walls are **special reinforced**; any intermediate
  or ordinary masonry SFRS is a finding.
- In **SDC C**, ordinary reinforced walls are within **160 ft**.
- No plain masonry in the SFRS above **SDC B**.

## 4. ASCE 7-22 §14.4 modifications to TMS 402

Confirmed against ASCE 7-22. These add to or override TMS 402-16.

| Item | Requirement |
|---|---|
| Bar size | Max **#9** bar |
| Bar diameter | ≤ **¼ of the least clear dimension** of the cell, course, or collar joint |
| Bar area | ≤ **4% of the cell area** |
| Splices in special walls (§14.4.4.1.2) | **No lap or welded splices in the plastic hinge zone** where it applies (below) |
| Anchorage to diaphragms and chords (§14.4.5.1) | Anchors connecting SFRS masonry to **diaphragms and chords** must be **governed by steel yielding**, or designed for **2.0 × the factored force** |
| Wall ties | **Corrugated sheet metal anchors are not permitted** (veneer ties) |
| Concrete abutting masonry | Where the joint is not a designed separation joint, the concrete is **roughened to 1/8 in. amplitude** and bonded like masonry |

### Splices in hinge zones, §14.4.4.1.2

- Applies where **M/(V_u d_v) > 1.5** and the seismic load needed to
  reach the nominal shear capacity is **more than 80%** of the load
  needed to reach the nominal flexural capacity.
- Then lap splices and welded splices are **not allowed in the plastic
  hinge zone** of special reinforced walls.
- The hinge zone extends at least **0.15 × the distance from the point
  of zero moment to the point of maximum moment**.

### Anchorage, §14.4.5.1

- The steel-yield-or-2.0× rule is **in addition to** the out-of-plane
  wall anchorage force (F_p with k_a) covered in
  `diaphragms_and_collectors.md` and `wood.md`. Both apply to a masonry wall anchored to a diaphragm.
- See `diaphragms_and_collectors.md` for the chord and collector
  connections into bond beams.

### What to check on the drawings / calcs

- No bar larger than **#9** in masonry; bar diameter ≤ **¼** of the cell
  (or course/collar joint) least clear dimension; bar area ≤ **4%** of
  the cell area.
- In special walls where §14.4.4.1.2 applies, wall elevations and splice
  schedules show **no lap or welded splices in the hinge zone**
  (≥ 0.15 × zero-moment-to-max-moment distance), typically at the base.
- Diaphragm-to-wall and chord-to-wall anchors are either shown to be
  **steel-yield-governed** or designed for **2.0×** the factored force.
- Veneer tie specifications exclude **corrugated sheet metal** ties.
- Concrete cast against masonry (slabs, columns, stems) is either a
  detailed separation joint or **roughened to 1/8 in.** and bonded.

## 5. Construction details of special masonry shear walls (SDC D, E, F)

Prescriptive minimums for special reinforced masonry shear walls (TMS 402
Ch. 7) (verify: TMS 402). The numbers match the special reinforced wall
prescriptive minimums.

### Reinforcement amounts and spacing

| Item | Requirement |
|---|---|
| Both directions | Vertical **and** horizontal steel, **continuous around corners and intersections** |
| Total | **A_v + A_h ≥ 0.002 A_g** |
| Each direction | **≥ 0.0007 A_g** |
| Vertical vs. shear steel | A_v ≥ **⅓ of the required shear (horizontal) reinforcement** |
| Spacing, each direction | ≤ min(**⅓ wall length D_w**, **⅓ wall height H**, **48 in.**) |

- The "⅓" rule is stated in TMS 402 against the required **shear**
  reinforcement; since the horizontal steel is the shear steel, this is
  the same as "⅓ of the required horizontal steel" (verify: TMS 402).

### Required #4 (0.2 in.²) bars

- **Vertical** #4 minimum (verify: TMS 402):
  - at **corners and intersections**;
  - within **16 in. of each side of openings**;
  - within **8 in. of each side of movement joints**;
  - within **8 in. of the ends of walls**;
  - at a maximum spacing of **48 in.**
- **Horizontal** #4 minimum (verify: TMS 402):
  - at the **top and bottom of openings**, extending past the opening at
    least **24 in. or 40d_b**;
  - **continuously at roof and floor levels** that are structurally
    connected, and at the **top of walls**;
  - at the **bottom of the wall** or top of the foundation where doweled;
  - at a maximum spacing of **48 in.**

### Hooks, bond beams, and dowels

- **Horizontal shear steel is anchored around the vertical end bars with
  a standard hook** (verify: TMS 402). This is the masonry equivalent of
  anchoring wall steel in a concrete boundary element; without it the
  shear steel can't develop at the wall end.
- **Bond beams** at floor and roof lines make the wall act with the
  diaphragm: they carry the chord and collector forces. See
  `diaphragms_and_collectors.md`, and `wood.md` for ledger-to-masonry
  anchorage.
- **Foundation dowels:** vertical bars are doweled into the foundation
  with a hooked dowel lapped to the wall bar. See
  `foundations_and_geotechnical.md`.

### Stack bond

- Where units are laid in **stack bond** (not running bond), special
  walls need **more horizontal steel**: a minimum horizontal ratio and
  bond beams at **≤ 24 in.** (verify: TMS 402).
- Stack bond is common in architectural CMU and easy to miss; check the
  architectural elevations and the masonry spec, not just the structural
  sheets.

### Grouting

- In SDC D and above, special walls are often **fully grouted**.
  Partially grouted walls are allowed in the base code with **reduced
  shear strength** (verify: TMS 402).
- CBC **Chapter 21A** requires **solid grouting** for DSA/HCAI-OSHPD
  projects (verify: IBC/CBC).

### Masonry columns

- **Lateral ties** enclose the longitudinal bars at **8 in. max spacing**.
- TMS 402 requires tighter tie spacing in SDC D and above; **8 in.**
  spacing and **3/8 in.** ties are the familiar values, and the ties must
  be **embedded in grout** (verify: TMS 402).

### What to check on the drawings / calcs

- Wall elevations or typical details show **A_v + A_h ≥ 0.002 A_g**, each
  direction **≥ 0.0007 A_g**, and spacing **≤ min(L/3, H/3, 48 in.)**.
- Vertical steel is at least **⅓ of the required shear steel**.
- **#4 vertical bars** at corners, intersections, wall ends, each side of
  openings, and each side of movement joints, within the distances above.
- **#4 horizontal bars** at the top and bottom of walls, at each floor and
  roof line, and above and below openings with the required extension.
- Horizontal steel is **continuous around corners** and **hooked around
  the end vertical bars**.
- **Bond beams** are shown at every floor and roof line where the
  diaphragm connects.
- **Dowels** to the foundation match the wall vertical bars (size and
  spacing) and are lapped to them.
- Where **stack bond** appears, the extra horizontal steel / bond beams
  at ≤ 24 in. are shown.
- Grouting extent (solid vs. partial) on the drawings matches the shear
  strength assumed in the calcs.
- Masonry column ties are shown at **≤ 8 in.**, embedded in grout.

## 6. Existing unreinforced masonry (URM) buildings

URM buildings are among the worst earthquake performers: **brittle,
stiff, and hazardous** to occupants. The typical URM building has **wood
roofs and floors** acting as diaphragms, bearing on the masonry walls.

### Typical earthquake damage

1. **Out-of-plane wall failure**: weak flexural capacity and/or the wall
   separating from the roof. Most common at **cantilevered parapets**.
   Partial collapse with the wall falling outward is the typical result.
2. **In-plane wall failure** from the **weak shear strength of the mortar
   joints**: **X cracking**, or **stepped diagonal cracking** along the
   head and bed joints.
3. **Wall-to-roof separation** from inadequate roof-to-wall anchorage.
4. **Broken roof or floor diaphragms.**

Other typical damage: corner cracking at windows; shear cracking in the
piers between openings; roof trusses and floor framing pulling off their
wall supports; parapet damage; falling hazards from badly cracked
masonry.

### Why URM fails this way

- The wood diaphragm is **flexible**, so the long walls deflect
  out-of-plane with it.
- Joists typically **just bear on a ledge or pocket** in the wall, held
  by friction or by widely spaced "government anchors."
- Once the anchorage fails, the wall is a tall, **unsupported**
  unreinforced panel, and it falls out.
- That is why **wall anchorage is the first retrofit priority**.

### California and code context

- The **URM Law (SB 547, 1986)** required local jurisdictions in the
  high-seismic zone to inventory URM buildings and set up mitigation
  programs (verify: California URM law).
- Retrofits typically follow the **Existing Building Code, Appendix
  Chapter A1** (seismic strengthening of URM bearing-wall buildings), or
  **ASCE 41** (verify: IEBC/CEBC Appendix A1; verify: ASCE 41).
- Appendix A1 uses special procedures: wall **h/t limits**, pier
  **rocking vs. shear**, and diaphragm **demand-capacity ratios**
  (verify: IEBC/CEBC Appendix A1).
- The evaluation basis for a URM retrofit is **Appendix A1 or ASCE 41,
  not ASCE 7**.

### Typical URM retrofit elements

1. **Wall-to-diaphragm tension anchors** (through-bolts with plates, or
   adhesive anchors tested on site) at every floor and roof, at close
   spacing.
2. **Shear anchors**, separate from the tension ties, to transfer
   diaphragm shear into the wall.
3. **Parapet bracing**, or parapet removal and replacement.
4. **Out-of-plane wall bracing** (strongbacks) where h/t exceeds the
   limits.
5. **Diaphragm strengthening**: plywood overlay and crossties
   (subdiaphragms). The anchorage and subdiaphragm rules in `wood.md`
   (k_a, crossties, no cross-grain bending or cross-grain tension on
   ledgers) are exactly what a URM retrofit relies on.
6. **New in-plane elements** where the URM piers are too weak: steel
   moment or braced frames, concrete or shotcrete walls, and **shotcrete
   overlays** on the URM.

### What to check on the drawings / calcs

Each of the following must be on a URM retrofit set; a missing one is a
finding.

- **Tension anchors at every floor and roof line**, with spacing and
  **on-site testing** called out.
- **Separate shear transfer** from diaphragm to wall (not relying on the
  tension anchors).
- **Parapet bracing** (or removal/replacement).
- **Out-of-plane h/t check**, or strongback bracing where h/t exceeds the
  limits.
- **Diaphragm evaluation or upgrade** (overlay, crossties,
  subdiaphragms).
- **In-plane check of the piers** (rocking vs. shear), or new in-plane
  elements.
- The stated evaluation basis is **Appendix A1 or ASCE 41**, not ASCE 7.
- **New work touching an existing URM wall** (additions, new openings):
  a new opening changes pier shear and rocking and must be justified in
  the calcs.

## 7. URM infill in moment frames

### Behavior

- URM infill usually fills the bays of **steel or concrete moment
  frames**.
- The infill is **much stiffer** than the frame and **interlocks** with
  it, so it **attracts the seismic force** and carries it itself until it
  fails. That keeps the moment frame from behaving as ductilely as it was
  meant to.
- **Typical damage:**
  1. **Out-of-plane wall failure** from weak flexural capacity.
  2. **In-plane failure of the infill** from weak shear strength (X
     cracking).
  3. **Joint shear failure** at the frame's **beam-column connections**.

### ASCE 7-22 §12.7.4, Interaction Effects (confirmed)

- Applies where a **moment frame is enclosed or adjoined by more rigid
  elements** that are not part of the SFRS.
- The frame must be designed so the **action or failure of those
  elements doesn't impair** its gravity or seismic capacity.
- The effect of the rigid elements must be included **at the design
  story drift Δ**.
- Those elements must also be considered in the **irregularity** check
  (§12.3.2). Infill on upper floors but not at an open ground floor
  creates a **soft or weak story**.

### Strut mechanism (verify: TMS 402; verify: ASCE 41)

- Once the infill cracks, it acts as a **diagonal compression strut**
  from corner to corner of the bay.
- The strut force concentrates at the **beam-column corners**, causing
  **joint shear failures** and **column shear failures** near the top and
  bottom of the columns.
- The frame's intended mechanism (beam hinging per strong column / weak
  beam) never develops.

### Captive (short) columns

- **Partial-height infill** (for example, masonry to sill height)
  shortens the column's effective length.
- Its shear demand (≈ 2M_p / clear height) jumps, and the column fails in
  **shear**.
- One of the most common non-ductile failure patterns; it ties to the
  older non-ductile concrete frame conditions in `concrete.md`.

### How new design handles infill (verify: TMS 402)

- **Isolate it (non-participating infill).** Provide a **gap** at the
  top and sides of the infill, sized for the design drift, and brace the
  infill out-of-plane with **slip connections** so the frame can drift
  without engaging the wall. TMS 402 covers this in its infill appendix.
- **Or design it in (participating infill).** Use a strut-model design
  per TMS 402, and design the frame and its connections for the strut
  forces. Uncommon in high-seismic US practice.

### Existing frames with infill

- ASCE 41 has specific procedures for **frames with infill**: equivalent
  strut modeling, infill in-plane and out-of-plane checks, and
  frame-infill interaction. Steel and concrete frames with URM infill are
  their own building types in ASCE 41 (verify: ASCE 41).

### What to check on the drawings / calcs

- **New buildings:** wherever masonry (or any rigid wall) is shown inside
  a **moment-frame bay**, either:
  - the drawings show an **isolation gap** at top and sides (sized for
    drift) and **out-of-plane slip anchors**; or
  - the calcs include the **interaction** per ASCE 7-22 §12.7.4 (frame
    and connections designed for the infill effects at Δ).
- **Partial-height walls against columns** (sill-height masonry, stair or
  mechanical walls): check for the **captive column** condition. Look for
  a gap detail, or the column designed for the short-column shear.
- **Irregularity check:** infill that stops at one level (open ground
  floor, retail frontage) is included in the soft/weak story evaluation
  (§12.3.2).
- **Existing frames with URM infill:** the ASCE 41 evaluation addresses
  infill out-of-plane stability, in-plane strut capacity, column and
  joint shear from the strut force, and soft-story conditions.

## Common findings

- Empirically designed masonry shear wall in SDC C or above, or any
  empirical design used for the SFRS.
- Intermediate or ordinary reinforced masonry used as the SFRS in SDC
  D–F; plain masonry in the SFRS above SDC B; ordinary reinforced walls
  over 160 ft in SDC C.
- R/Ω₀/C_d in the calcs don't match the stated masonry system (bearing
  wall vs. building frame vs. dual).
- Special walls designed for the analysis shear only, with no 1.25 M_n
  (SD) or 1.5× (ASD) shear amplification.
- Coupling beams checked without the 1.25(M₁ + M₂)/L_c + 1.4V_g demand,
  or with slab steel omitted from M_n.
- Lap or welded splices in the hinge zone of a special wall where
  §14.4.4.1.2 applies; bars larger than #9 or over ¼ of the cell
  dimension.
- Diaphragm-to-wall anchors neither steel-yield-governed nor designed
  for 2.0×.
- Horizontal steel not hooked around the end vertical bars; missing #4
  bars at corners, ends, openings, or top/bottom of wall; missing bond
  beams at floor or roof lines.
- Stack bond shown architecturally with no added horizontal steel.
- Grouting extent on the drawings inconsistent with the calcs, or partial
  grouting on a CBC Chapter 21A project.
- Corrugated sheet metal veneer ties specified.
- URM retrofit set missing tension anchors at a level, separate shear
  transfer, parapet bracing, h/t check, diaphragm evaluation, or pier
  in-plane check; retrofit evaluated to ASCE 7 instead of Appendix A1 or
  ASCE 41.
- Rigid infill tight against a moment frame with neither an isolation
  gap nor a §12.7.4 interaction check; partial-height infill creating an
  unaddressed captive column; infill that stops at one level not carried
  into the soft/weak story check.
