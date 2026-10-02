# Steel Systems — Lateral Load Path Reference

This file covers steel seismic force-resisting systems (SFRS): moment
frames (SMF / IMF / OMF), braced frames (OCBF / SCBF / EBF / BRBF), dual
systems with a special moment frame, and special plate shear walls. Read it
whenever the drawings or calcs show a steel lateral system. Use it to confirm
that the system is identified and permitted, that the R / Ω₀ / C_d match
ASCE 7-22 Table 12.2-1, that the connections are backed by prequalification
or testing, and that the lateral load path through the frame is actually
detailed. Capacity checks are out of scope. The review confirms that the
required items are shown.

For the general design basis (R, Ω₀, C_d, ρ, SDC, irregularities) see
`seismic_design_basis.md`. For collector forces and diaphragm-to-frame
transfer see `diaphragms_and_collectors.md`. For anchor rods, footings and
soil see `foundations_and_geotechnical.md`.

## Steel lateral systems at a glance

- Steel lateral systems are **braced frames** or **moment frames**. Special
  plate shear walls exist but are uncommon.
- **Braced frames are the more common choice** because they are easier to
  detail than a true moment connection. A moment frame appears when the
  loads (or the architecture) call for one.
- Each system carries different R, Ω₀, C_d, height limits and detailing, so
  a frame drawn as one system but designed with another's coefficients is a
  broken design basis even when every member works.
- A **moment connection** at a beam-column joint is a system-identification
  clue: it signals lateral-system framing. A **shear tab** is a shear-only
  (gravity) connection. See "Tie-in to the gravity skill (V2)" below.

## Moment-resisting frames

### How a moment frame resists seismic force

- A moment frame is a **ductile** system: it resists seismic forces beyond
  the elastic range and absorbs energy by **yielding of the beams at
  predetermined plastic hinge locations**.
- Members are proportioned so the **columns do not buckle**. The
  **beam-column joint (panel zone)** gets special detailing so it stays
  intact through repeated inelastic cycles.
- Depending on relative strengths, inelastic action can occur as:
  - a **flexural plastic hinge in the beam** (intended);
  - a flexural plastic hinge in the **column** (not intended);
  - **shear yielding of the panel zone** (the column web between the beam
    flanges).
- Panel zone integrity is what lets the frame dissipate earthquake energy
  without collapse.

### Strong column / weak beam (SCWB)

- SCWB is the **design principle**: the **column must be stronger than the
  fully yielded beam**, so the beam hinges and the column does not yield.
  The principle still applies to all current special moment frames.
- Target behavior: large inelastic rotation from **flexural yielding at the
  beam hinge**, with only limited, essentially elastic yielding in the panel
  zone.
- Do not describe the pre-Northridge welded-flange / bolted-web detail as
  "the" SCWB connection. It was a connection **type** intended to force beam
  hinging, but it fractured at the **weld** before the beam could hinge.

### Moving the hinge away from the column face

Two strategies keep the plastic hinge out of the welded joint:

1. **Reinforce the beam at the connection**, so the connection is stronger
   than the beam just beyond it.
2. **Reduce the beam section** at the chosen hinge location: the **reduced
   beam section (RBS)**, or "dog bone". The top and bottom flanges are
   trimmed a set distance from the column face. The cut is usually a
   **circular radius cut, finished smooth** (verify: AISC 358).

### Panel zone, doubler plates and continuity plates

- **Doubler plates** are added on one or both sides of the **column web**.
  They reinforce the **column panel zone**, raising its shear strength and
  web crippling capacity. They do not reinforce the beam.
- **Continuity plates** (column stiffeners) are placed in line with the beam
  flanges. They carry the beam flange forces across the column web.
- Both are load-path elements: the beam flange force has to cross the column
  through these plates and their welds. A plate that is called for in the
  calcs but not detailed, or detailed without welds to the column, leaves the
  joint without its intended force transfer.

### Northridge (1994): what failed and why

**Pre-Northridge standard connection:** beam flanges welded to the column
flange with **complete-joint-penetration (CJP) welds**, beam web bolted to a
shear tab with high-strength bolts.

**Observed damage** in special moment frames was concentrated **at the
beam-column connections**:

- cracking at the **beam bottom flange weld** to the column flange,
  propagating into the **column flange and web** and into the beam bottom
  flange;
- in some cases, cracking along the beam web shear plane and fracture of the
  **top flange weld**;
- joint distress that fractured the column flange and part of the web.

**Causes identified by research:**

- stress concentration at the bottom flange weld;
- **low-toughness weld metal**;
- poor construction quality control;
- large member sizes that had never been tested;
- actual steel strength differing from specified values;
- **triaxial restraint** at the middle of the beam flange at the column
  face. This restraint suppresses yielding, so the material fractures
  instead of yielding.

**Response:** FEMA published **FEMA 350** (new design), **351** (evaluating
existing buildings), **352** (repair) and **353** (quality assurance). This
work fed into the AISC Seismic Provisions (AISC 341) and the
prequalified connection standard (AISC 358).

**Post-Northridge welded-flange improvements:** the bottom flange weld
backing is removed, the root is back-gouged, and a reinforcing fillet weld
is added (verify: AISC 358). These belong to **welded flange** connections,
not to the side plate system.

### Connection qualification: prequalified vs. tested

- Every SMF moment connection configuration must either be shown
  by **cyclic testing** to reach the required inelastic rotation and
  strength, or be a **prequalified connection** (verify: AISC 341).
- **Prequalified connections (AISC 358):** examples include the RBS and
  bolted end plates. Each type has its own limits on beam and column size,
  depth and other parameters (verify: AISC 358).
- **Column depth limit, current rule:** prequalification is **not** limited
  to W12 and W14 columns. That limit is outdated. AISC 358 now prequalifies
  some types with **deeper columns, up to W36 for some types** (verify: AISC
  358). Check the column against the limits of the specific connection.
- **Current editions:** AISC 341-22 and AISC 358-22 (verify: AISC 341 /
  AISC 358).
- **Tested / proprietary connections:** acceptable when backed by
  qualification testing and the manufacturer's approval. Examples:
  - **Side plate connection:** the beam frames between **two parallel side
    plates** that connect it to the column. The beam flanges are **not
    welded directly to the column**. Beam and column are fillet-welded to
    the side plates, which carry the moment around the joint (verify:
    manufacturer's qualification / AISC 358).
  - **Slotted web (slotted beam) connection.**

### ASCE 7-22 Table 12.2-1: moment-resisting frame systems

| System | R | Ω₀ | C_d | SDC D | SDC E | SDC F |
|---|---|---|---|---|---|---|
| C.1 Steel special moment frame (SMF) | 8 | 3 | 5½ | NL | NL | NL |
| C.3 Steel intermediate moment frame (IMF) | 4½ | 3 | 4 | 35 ft (12.2.5.7) | NP (12.2.5.7) | NP (12.2.5.7) |
| C.4 Steel ordinary moment frame (OMF) | 3½ | 3 | 3 | NP (12.2.5.6) | NP (12.2.5.6) | NP (12.2.5.6) |

NL = no height limit. NP = not permitted, except as the referenced section
allows. ASCE 7-22 §12.2.5.6 (OMF) and §12.2.5.7 (IMF) give limited
exceptions, e.g. light single-story buildings. An IMF or OMF in SDC D–F
needs an explicit statement of which exception it relies on.

### What to check on the drawings / calcs: moment frames

- [ ] The moment frame is identified as **SMF, IMF or OMF** on the plans or
      general notes, and R / Ω₀ / C_d match the table row above.
- [ ] The system is permitted for the project's SDC and height. An IMF or OMF
      in SDC D–F cites the §12.2.5.6 / §12.2.5.7 exception it uses.
- [ ] Each SMF connection is identified as a **named AISC 358
      prequalified type** or a **named tested / proprietary system**, with
      the governing standard edition or manufacturer approval referenced.
- [ ] The beam and column sizes fall within the **limits of that specific
      connection** (column depth, beam depth, flange thickness, etc.). Do not
      apply a blanket W12/W14 column limit.
- [ ] The RBS (if used) is dimensioned: cut location from the column face,
      cut length, depth and radius, and a smooth finish.
- [ ] A **SCWB check** is shown in the calcs at each SMF joint (column
      stronger than the yielded beams).
- [ ] **Panel zone** shear is checked. Where it does not work alone,
      **doubler plates** are detailed on the column web, with thickness,
      extent and welds to the column.
- [ ] **Continuity plates** are detailed in line with the beam flanges where
      the calcs require them, with thickness and welds to the column flanges
      and web.
- [ ] Welded-flange connections show the post-Northridge requirements
      (backing removal, back-gouge, reinforcing fillet) and a notch-tough
      weld filler specification (verify: AISC 341 / AISC 358).
- [ ] **Protected zones** at the hinge regions are marked (see "Protected
      zones" below).
- [ ] The column base fixity (fixed or pinned) matches the analysis model
      (see "Tie-in to the gravity skill (V2)").

## Braced frames

Braced frames resist lateral force mainly through **axial force in the
braces**, and they **limit deflection and drift**. There are three types:

1. **Concentrically braced frames (CBF):** ordinary (OCBF) and special
   (SCBF).
2. **Eccentrically braced frames (EBF).**
3. **Buckling-restrained braced frames (BRBF).**

### Concentrically braced frames (CBF)

**Configurations:** X, V, inverted V (V and inverted V are called
**chevron** bracing), single diagonal, and K bracing (restricted, see below).

**Main limitation:** a CBF cannot provide **reversible** inelastic
deformation. Once a brace buckles, it loses strength and does not return to
its original shape.

#### OCBF (ordinary)

- Expected to provide only **limited** inelastic deformation in a major
  earthquake. For that reason it is designed with load combinations
  **including overstrength (Ω₀)** (verify: AISC 341).
- The Ω₀ forces apply mainly to the **brace connections**, and for V and
  inverted-V configurations to the **beams**, rather than to every member
  (verify: AISC 341).
- **K bracing is not permitted** (verify: AISC 341).
- Building frame system permitted in **all SDCs except F**, apart from the
  footnote j cases below.
- Height: no limit in SDC A, B, C. **35 ft** in SDC D and E.
- **Footnote j (60 ft exception), current rule:** an OCBF may go to **60 ft
  only in single-story buildings** with a roof dead load **not over 20
  psf**, and in **penthouse** structures. The 60 ft limit does **not** apply
  to multistory buildings, even with a light roof (ASCE 7-22 Table 12.2-1,
  footnote j).
- Footnote j is also attached to the SDC F entry, so the same limited cases
  appear to be allowed in SDC F (verify: ASCE 7-22 Table 12.2-1 footnote j
  for SDC F).

#### SCBF (special)

- Expected to provide **significant** inelastic deformation in a major
  earthquake, mainly through **brace buckling** and **brace yielding in
  tension**.
- **K bracing and tension-only bracing are not permitted** (verify: AISC
  341).
- Building frame system permitted in **all SDCs**.
- Height: no limit in SDC A, B, C. **160 ft** in SDC D and E. **100 ft** in
  SDC F (increase allowed under §12.2.5.4).

### Eccentrically braced frames (EBF)

- An economical, ductile seismic system. The brace connects to the beam so
  that a **short segment of beam, the link**, is left between the brace and
  a column, or between two braces.
- **Link location:** the ASCE 7-22 definition allows the link either **next
  to a column** or **between two braces** at mid-span of the beam (e.g.
  inverted V with a center link).
- **The link is the fuse.** Once the elastic capacity is exceeded, **shear
  or flexural yielding of the link** gives a ductile response and can absorb
  significant inelastic deformation. Because the link yields first, the
  other members are not overstressed.
- EBFs can also be designed to limit frame deformation, reducing damage to
  nonstructural components under cyclic loading.
- **Link behavior:** **short links yield in shear** (most ductile, and
  preferred). **Long links yield in flexure.** Intermediate links do both
  (verify: AISC 341).
- **Link stiffeners:** web stiffeners are required on both sides of the web
  at the brace end of the link and at intervals along the link (verify:
  AISC 341).
- **Capacity design:** the braces, the beam outside the link, and the
  columns are designed for the link's **expected (overstrength) capacity**,
  not just the analysis forces, so the link is always the part that yields
  (verify: AISC 341).
- **Link-to-column connections:** a link that frames into a column needs a
  link-to-column connection that is **prequalified or tested**, like an SMF
  connection. This is one reason the mid-span link is common (verify: AISC
  341).
- Building frame system permitted in **all SDCs**. Height: no limit in SDC
  A, B, C. **160 ft** in SDC D and E. **100 ft** in SDC F (increase allowed
  under §12.2.5.4).

### Buckling-restrained braced frames (BRBF)

- Concentric braces designed to **yield in both tension and compression,
  with no buckling**.
- A **steel core** carries the axial force. Buckling is prevented by a
  casing around the core: **all-steel**, or a **mortar-filled steel tube**.
- Because the core cannot buckle, inelastic behavior is **axial yielding of
  the steel core**, giving excellent ductility and energy dissipation.
- **Configurations:** V, inverted V, or a combination. Single-diagonal
  configurations are also used. **K bracing is not permitted** (verify:
  AISC 341).
- **Delegated, tested braces:** BRBs are usually **proprietary, tested
  braces**. The drawings typically specify the **core area and yield
  strength**, with brace design delegated to the manufacturer and backed by
  qualification tests (verify: AISC 341).
- **Adjusted brace strength:** gussets and beams are designed for the
  brace's **adjusted strength** in tension and compression. Compression is
  slightly higher than tension (verify: AISC 341).
- Height limits are the same as EBF and SCBF.

### ASCE 7-22 Table 12.2-1: building frame systems (braced frames, SPSW)

| System | R | Ω₀ | C_d | SDC D | SDC E | SDC F |
|---|---|---|---|---|---|---|
| B.1 Steel EBF | 8 | 2 | 4 | 160 ft | 160 ft | 100 ft |
| B.2 Steel SCBF | 6 | 2 | 5 | 160 ft | 160 ft | 100 ft |
| B.3 Steel OCBF | 3¼ | 2 | 3¼ | 35 ft (j) | 35 ft (j) | NP (j) |
| B.26 Steel BRBF | 8 | 2½ | 5 | 160 ft | 160 ft | 100 ft |
| B.27 Steel special plate shear wall | 7 | 2 | 6 | 160 ft | 160 ft | 100 ft |

(j) = footnote j: OCBF up to 60 ft in single-story buildings with roof
dead load ≤ 20 psf, and in penthouse structures.

### §12.2.5.4 height increase

- ASCE 7-22 §12.2.5.4 allows the **160 ft** limit to increase to **240 ft**
  in SDC D and E, and the **100 ft** limit to increase to **160 ft** in SDC
  F, where the conditions of that section are met (e.g. no extreme
  torsional irregularity).
- It applies to **EBF, SCBF, BRBF and SPSW**. It does not apply to OCBF.
- A braced frame or SPSW taller than 160 ft (SDC D/E) or 100 ft (SDC F)
  must cite §12.2.5.4 and show that its conditions are satisfied.

### What to check on the drawings / calcs: braced frames

- [ ] The braced frame type is stated (**OCBF, SCBF, EBF or BRBF**), and R /
      Ω₀ / C_d match the Table 12.2-1 row.
- [ ] Height is within the SDC limit. An **OCBF over 35 ft** in SDC D/E is
      acceptable only as a **single-story** building with roof DL ≤ 20 psf
      or a penthouse (footnote j). Any taller EBF / SCBF / BRBF / SPSW cites
      §12.2.5.4.
- [ ] **No K bracing** in an OCBF, SCBF or BRBF. **No tension-only
      bracing** in an SCBF (verify: AISC 341).
- [ ] **OCBF:** brace connections (and V / inverted-V beams) are designed
      for Ω₀ or expected-strength forces, and the calcs show it (verify:
      AISC 341).
- [ ] **EBF:** the link is identified on the elevations, with length and
      **link stiffeners** detailed. A link framing into a column references
      a **prequalified or tested link-to-column connection**. Braces, beam
      outside the link, and columns are sized for the link's overstrength
      (verify: AISC 341).
- [ ] **BRBF:** the brace schedule gives **core area and yield strength**
      and names the tested brace manufacturer (delegated design). Gusset and
      beam design use the brace's **adjusted strengths** (verify: AISC 341).
- [ ] Each brace end has a **gusset detail** (plate size, welds or bolts to
      beam and column, brace-to-gusset connection). "Typ." gussets are
      matched to the brace sizes they serve.
- [ ] **Protected zones** are marked (EBF links; see below).

## Dual systems with special moment frames

- **SCBF, EBF, BRBF and SPSW** can be combined with a **special moment frame
  (SMF)** as a dual system, permitted in **all SDCs with no height limit**.
- **Why:** the **moment frame adds redundancy** (a backup line of
  resistance if braces degrade) and the **braced frame adds stiffness**, so
  the dual system gets both.
- **25% rule:** the moment frame must be able to resist at least **25% of
  the design seismic forces** on its own (ASCE 7-22 §12.2.5.1; see
  `seismic_design_basis.md`).
- **The coefficients change.** A dual system with an SMF raises Ω₀ to 2½,
  and for SCBF raises R from 6 to 7 (C_d 5 → 5½). The general notes must
  use the **dual-system row**, not the building frame row.
- **"No height limit" requires a special moment frame.** With an IMF
  (E.1), an SCBF dual system is limited to 35 ft in SDC D and is not
  permitted in SDC E and F.

### ASCE 7-22 Table 12.2-1: dual systems

| System | R | Ω₀ | C_d | SDC D | SDC E | SDC F |
|---|---|---|---|---|---|---|
| D.1 SMF + steel EBF | 8 | 2½ | 4 | NL | NL | NL |
| D.2 SMF + steel SCBF | 7 | 2½ | 5½ | NL | NL | NL |
| D.13 SMF + steel BRBF | 8 | 2½ | 5 | NL | NL | NL |
| D.14 SMF + steel SPSW | 8 | 2½ | 6½ | NL | NL | NL |
| E.1 IMF + steel SCBF | 6 | 2½ | 5 | 35 ft | NP | NP |

### What to check on the drawings / calcs: dual systems

- [ ] The general notes state the system as a **dual system** and use the
      dual-system R / Ω₀ / C_d, not the building frame or moment frame row.
- [ ] The moment frame is an **SMF** if the building relies on "no height
      limit". An IMF + SCBF dual system is ≤ 35 ft in SDC D and not used in
      SDC E/F.
- [ ] The calcs include a documented check that the **SMF alone resists at
      least 25%** of the design seismic forces (§12.2.5.1).

## Special plate shear walls (SPSW)

- **Vertical steel infill (web) plates**, one story high and one bay wide,
  connect to the surrounding steel beams and columns.
- Installed in one or more bays for the **full height** of the building,
  they form a stiff **cantilever wall**, similar in behavior to a reinforced
  concrete shear wall (compare `concrete.md`).
- Inelastic capacity comes from **web plate yielding** and **plastic hinge
  formation**.
- The thin web plate buckles and then yields through **tension field
  action** (diagonal tension bands). Plastic hinges form in the
  **horizontal boundary elements (HBEs, the beams)**. The HBEs and the
  **vertical boundary elements (VBEs, the columns)** are designed to stay
  essentially elastic under the plate's tension field, apart from the HBE
  hinges (verify: AISC 341).
- Uncommon in practice, but it exists and should be recognized.
- Table 12.2-1 row B.27: R = 7, Ω₀ = 2, C_d = 6. Height 160 ft in SDC D and
  E, 100 ft in SDC F, with the §12.2.5.4 increase available. As a dual
  system with an SMF (D.14): R = 8, Ω₀ = 2½, C_d = 6½, no height limit.

### What to check on the drawings / calcs: SPSW

- [ ] The system is identified as a special plate shear wall, with the B.27
      (or D.14 dual) coefficients.
- [ ] Web plate thickness and its connection to the HBEs and VBEs
      are detailed along all four edges.
- [ ] HBE and VBE design accounts for the web plate tension field, not just
      the frame analysis forces (verify: AISC 341).

## Protected zones

- **What they are:** regions expected to undergo large inelastic strain:
  - **SMF plastic hinge regions** (e.g. the RBS cut and the beam length
    around it);
  - **EBF links**.
- **The rule:** no welded attachments, shot pins (powder-actuated
  fasteners), or other penetrations in a protected zone (verify: AISC
  341).
- **Drawings:** protected zones should be **marked on the frame
  elevations** and called out in the notes.

### What to check on the drawings / calcs: protected zones

- [ ] Protected zones are shown on the SMF and EBF elevations, with a
      general note prohibiting attachments.
- [ ] No deck support angle, pour stop, cladding clip, embed, shear stud or
      other attachment is detailed inside a protected zone. Check the
      architectural and deck edge details as well as the structural details.
- [ ] Penetrations through a beam web (for MEP) are not located in an RBS or
      link region.

## Braced-frame load path

Trace the seismic force through every member change and confirm that each
junction has a detail:

1. **Diaphragm** → shear transfers from the deck into the beams or
   collectors on the frame line (see `diaphragms_and_collectors.md`).
2. **Collector (drag strut)** → carries the accumulated diaphragm force
   along the frame line to the braced bay. The collector-to-frame connection
   must be designed for the collector axial force.
3. **Upper gusset** at the beam-column joint → the force enters the brace.
   This is where the force changes members.
4. **Brace** → carries the force down the bay as axial tension or
   compression.
5. **Lower gusset** at the lower beam-column (or column-base) joint → the
   force leaves the brace.
6. **Column** → carries the vertical component of the brace force (uplift
   and compression, i.e. overturning).
7. **Base plate** → transfers shear, uplift and compression from the column
   to the foundation.
8. **Anchor rods** → anchor the base plate into the concrete.
9. **Foundation** → grade beam or footing, which delivers the force to the
   soil (see `foundations_and_geotechnical.md`).

The **collector-to-frame connection** and the **gusset connections** are
where the force changes members. Both must be **detailed, not assumed**. A
gravity shear tab at a collector-to-column joint, with no note or detail for
the collector axial force, is a gap in the load path.

### What to check on the drawings / calcs: braced-frame load path

- [ ] Every braced bay has an elevation that shows the brace, both gussets,
      the beam and column sizes, and the base.
- [ ] The **collector-to-frame connection** is detailed for the collector
      axial force (from `diaphragms_and_collectors.md`), not left as a
      standard gravity shear tab.
- [ ] **Gusset connections** at top and bottom of each brace are detailed:
      gusset plate size and thickness, gusset-to-beam and gusset-to-column
      welds or bolts, and the brace-to-gusset connection.
- [ ] The column carries the brace's vertical component to a base detail
      with **anchor rods for uplift**, a defined **shear transfer**, and a
      foundation element under the braced bay on the foundation plan.

## Tie-in to the gravity skill (V2)

The V2 companion skill (`gravity-load-path-qaqc`, its `steel.md`) already
covers the following. Do not repeat that review here. Read the lateral
implications instead:

- **Shear tabs:** shear-only beam-to-column connections that intentionally
  provide no moment continuity. A shear tab means gravity framing. A moment
  connection means a moment frame, which this file covers.
- **Slotted holes at W27 and deeper beams:** vertical slots that let deep
  beam ends rotate as pinned connections. Where such a beam also serves as a
  collector or frame beam, confirm that the lateral force has its own
  detailed transfer.
- **Pinned base plates:** the V2 default is a pinned base unless the
  drawings show a fixed base.
  - **Braced frame base:** typically **pinned**. The brace and column carry
    the lateral force as axial force, so the base sees shear, uplift and
    compression, not moment.
  - **Moment frame base:** may be **fixed or pinned**, but it **must match
    the analysis assumption**. A model with fixed bases needs a base plate,
    anchor rods and foundation detailed to resist that moment. A pinned base
    with a fixed-base model (or the reverse) is a finding.

## What to check on the drawings / calcs: summary

The per-topic lists above hold the detail. At minimum, every steel lateral
review covers these four areas:

1. **System identification and coefficients.** The SFRS is named (SMF / IMF
   / OMF / OCBF / SCBF / EBF / BRBF / SPSW, or a dual system). R, Ω₀ and C_d
   match the correct ASCE 7-22 Table 12.2-1 row, including the
   **dual-system row** where applicable. The system is permitted for the SDC
   and height, and any exception it relies on (§12.2.5.4, §12.2.5.6,
   §12.2.5.7, footnote j) is cited explicitly.
2. **Connection prequalification evidence.** Each SMF moment connection and
   each EBF link-to-column connection is named as an **AISC 358
   prequalified** type or a **tested / proprietary** system, with member
   sizes inside that type's limits (no blanket W12/W14 assumption). BRBs
   reference qualification tests and a named manufacturer (verify: AISC 341
   / AISC 358).
3. **Panel zone, continuity plate and doubler detailing.** Panel zone shear
   and SCWB checks appear in the calcs. **Doubler plates** (column web) and
   **continuity plates** (in line with the beam flanges) are shown where
   required, with thickness and welds to the column.
4. **Collector-to-frame and gusset connections.** Both are **detailed, not
   assumed**: the collector-to-frame connection for the collector axial
   force, and gussets at both ends of every brace. The path continues
   through column, base plate and anchor rods to the foundation, and base
   fixity matches the analysis.

## Common findings

- Moment frame drawn with a generic "welded flange" detail and **no
  reference to a prequalified or tested connection**.
- Connection prequalification rejected or accepted using the outdated
  **W12/W14-only** column limit instead of the actual AISC 358 limits for
  that connection type.
- R / Ω₀ / C_d taken from the **building frame row** (e.g. SCBF R = 6, Ω₀ =
  2) when the structure is a dual system with an SMF (R = 7, Ω₀ = 2½), or
  the reverse.
- Dual system claimed with **no documented 25% SMF check** (§12.2.5.1).
- **IMF or OMF in SDC D–F** with no stated §12.2.5.6 / §12.2.5.7 exception.
- **OCBF over 35 ft** in SDC D/E in a multistory building, justified with
  the 60 ft / 20 psf footnote, which applies only to **single-story**
  buildings and penthouses.
- Braced frame or SPSW over 160 ft (SDC D/E) or 100 ft (SDC F) with no
  §12.2.5.4 justification.
- **K bracing** in an OCBF, SCBF or BRBF, or **tension-only bracing** in an
  SCBF (verify: AISC 341).
- Doubler or continuity plates required by the calcs but **missing from the
  details**, or shown without welds.
- Doubler plates described as beam reinforcement (they reinforce the
  **column** panel zone).
- Side plate connection specified with welded-flange items (backing removal,
  reinforcing fillet) mixed in, or a welded flange connection missing them.
- EBF link not identified, or link stiffeners not detailed. EBF braces and
  columns sized only for analysis forces instead of link overstrength
  (verify: AISC 341).
- BRB schedule missing core area / yield strength or the delegated-design
  manufacturer reference.
- Deck, cladding or other attachments detailed into an **SMF hinge region
  or EBF link** (protected zone).
- Collector-to-frame connection shown as a standard gravity shear tab with
  no provision for collector axial force.
- Gusset connections labeled "typ." or left to the fabricator with no design
  basis.
- Moment frame base fixity on the drawings **inconsistent with the
  analysis model**.
