# Wood Lateral Systems: Diaphragms, Shear Walls, and Connections

This file covers the lateral load path through light-frame wood buildings
(typically multifamily residential, up to mid-rise): wood structural panel
(WSP) diaphragms, subdiaphragms and crossties, wood shear walls (including
walls with openings), overturning and hold-downs, sill anchorage, and the
connections that link them. Read it whenever the SFRS or any diaphragm in the
set is wood, or when a wood roof or floor braces concrete or masonry walls.
The two-story link-by-link chain in "Wood connections" is the model trace for
any wood building. SDPWS, NDS, and IBC/CBC chapter 23 items not yet checked
against the documents carry a "(verify: …)" tag; do not treat them as
confirmed.

General diaphragm theory, collector design forces, and the Ω₀ rules live in
`diaphragms_and_collectors.md`; R/Ω₀/C_d, ρ, and irregularities live in
`seismic_design_basis.md`; the trace method itself is in
`load_path_methodology.md`. Written to ASCE 7-22. Use the edition the
project's jurisdiction adopts (see SKILL.md).

## WSP diaphragms

### Materials

- **Wood structural panels (WSP):** plywood, OSB, composite panels. WSP gives
  the highest capacity of the sheathing materials.
- Other diaphragm sheathing: plaster, particleboard, fiberboard, lumber
  (straight or diagonal). Cross-laminated timber (CLT) is also seen.
- ASCE 7-22 references AWC **SDPWS-21** for wood diaphragm and shear wall
  design.

### Construction rules

- Panels at least **4 ft × 8 ft**; a **2 ft** minimum dimension is allowed at
  boundaries and at changes in framing (verify: SDPWS-21).
- **Blocked:** all four panel edges bear on framing or blocking **and are
  nailed** to it. **Unblocked:** only two sides bear on framing. This is the
  key distinction: capacity, the layout case, and the aspect ratio limit all
  depend on it.
- Boundary and panel-edge nailing: **2 in. to 6 in. o.c.** (6 in. maximum).
- **Field nailing** (to intermediate framing): **12 in. o.c.** where supports
  are spaced **less than 48 in.**; **6 in. o.c.** maximum where supports are
  48 in. o.c. or more (verify: SDPWS-21).
- Nails at least **3/8 in.** from panel edges.
- Framing and blocking nail face: **2 in. nominal** minimum.
- Framing and blocking nail face **3 in. nominal** minimum, with **staggered**
  nails, at adjoining panel edges where (a) nail spacing is **2½ in. o.c. or
  less**, or (b) **10d common** nails are at **3 in. o.c.** (or less, with a
  minimum-penetration condition) (verify: SDPWS-21).
- **High-load diaphragms** (two or three rows of edge fasteners): field
  nailing typically **12 in. o.c. where supports are at 32 in. or closer**,
  6 in. o.c. maximum otherwise. Note the tighter 32 in. threshold versus 48 in.
  for ordinary diaphragms (verify: SDPWS-21).
- **California public schools (DSA) and hospitals (HCAI, formerly OSHPD):**
  staples are not allowed as WSP diaphragm fasteners; nails only (CBC 2306.2)
  (verify: 2025 CBC section number).

### Sizing and checking workflow (retrace it in both directions)

The engineer sizes a WSP diaphragm, and the reviewer retraces it, in five
steps. Repeat every step for the other load direction, because turning the
load 90° changes almost every input.

**Step 1: Orient the diaphragm to the load.** Treat it as a simple beam lying
flat, supported by the wall lines at each end.

- **Span (L)** is across the load, between supporting wall lines; **depth
  (d)** is along the load.
- **Chords** run across the load (the flanges); **collectors / struts /
  drags** run with the load and deliver it into the walls.
- Rotate the load 90° and span becomes depth, chords become collectors.

**Step 2: Find the unit shear.**

- Uniform load w (plf, strength level) along the span: reaction
  **V_max = w·L/2**, spread over the full depth.
- **Unit shear (ASD): v_max = 0.7·V_max / d = 0.7·w·L / (2d)** (plf).
- The 0.7 comes from the ASCE 7-22 ASD seismic combination 8
  (1.0D + 0.7E_v + 0.7E_h). Gravity contributes nothing to in-plane diaphragm
  shear, so it reduces to 0.7·E_h, with **E_h = ρ·Q_E and ρ = 1.0** for
  diaphragm forces from F_px (ASCE 7-22 §12.3.4.1, item 7). Transfer forces
  from offset walls are a separate case (see `diaphragms_and_collectors.md`).
- ASCE 7-16 (older projects / existing reports) writes the same combination as
  D + 0.7E; the result is identical.
- If w is already an ASD value, the 0.7 must not be applied again. Check which
  level the calc's loads are at.

**Step 3: Identify the sheathing layout case (1 through 6).** The SDPWS
diaphragm tables group panel layouts into six cases, set by two questions:
which way the **continuous panel joints** run relative to the framing
(joists/purlins), and whether the **load** acts across or along those joints.

| Case | Continuous panel joints run... | Load acts... |
|---|---|---|
| 1 | across the framing | across the continuous joints |
| 2 | with the framing | across the continuous joints |
| 3 | across the framing | along the continuous joints |
| 4 | with the framing | along the continuous joints |
| 5 | both ways (grid, no stagger) | in one direction |
| 6 | both ways (grid, no stagger) | in the other direction |

- Cases 1-4 have staggered panels (joints line up one way only); Cases 5-6
  line up both ways.
- The case matters mainly for **unblocked** diaphragms: Case 1 gets the higher
  unblocked value, Cases 2-6 share a lower one (verify: SDPWS-21).
- The same diaphragm can be a different case in each load direction.

**Step 4: Pick sheathing and fastening, then compare.** Capacity depends on
the panel (thickness, grade, orientation), framing width, edge support
(blocked or not), and fastening (type, penetration, spacing, number of rows).

- **Nailed:** SDPWS diaphragm tables (4.2A, 4.2B, 4.2C) give **nominal** unit
  shears (plf) for Douglas fir-larch or southern pine framing with common or
  galvanized box nails, with separate seismic and wind columns (wind values
  are higher; use the column matching the load) (verify: SDPWS-21 table
  numbers).
- **Stapled:** IBC Tables 2306.2(1) and 2306.2(2) give **allowable** values,
  already reduced (verify: 2025 CBC table numbers).
- **Nominal to design value** (diaphragms and shear walls alike)
  (verify: SDPWS-21):

  | Load | ASD: divide by | LRFD: divide by |
  |---|---|---|
  | Seismic | 2.8 | 2.0 (φ = 0.5) |
  | Wind | 2.0 | 1.25 |

- **Pass/fail (seismic, ASD): v_max ≤ SDPWS nominal ÷ 2.8.**

**Step 5: Check proportions and deflection.**

| Horizontal diaphragm | Max L/W |
|---|---|
| WSP, unblocked | 3:1 |
| WSP, blocked | 4:1 |
| Single straight lumber sheathing | 2:1 |
| Single diagonal lumber sheathing | 3:1 |
| Double diagonal lumber sheathing | 4:1 |

(verify: SDPWS-21)

- Blocking buys a longer, narrower diaphragm (4:1 vs. 3:1).
- Deflection limit: walls and other elements attached to the diaphragm must be
  able to follow its deflection without damage.

### Open-front and cantilevered wood diaphragms

Open-front or cantilevered wood diaphragms are analyzed as **semirigid**
(sometimes rigid), never as flexible (project standard).
See the diaphragm-type rules in `diaphragms_and_collectors.md`. This option is
not available at all where the wood system resists concrete or masonry walls
(see that section below).

### What to check on the drawings / calcs (diaphragms)

- The diaphragm schedule states, for each diaphragm: blocked or unblocked,
  sheathing type/grade/thickness, nail size and type, boundary / edge / field
  nail spacing, number of rows, and framing width where 3x is required.
- The calc runs Steps 1-5 in **both** directions: span and depth, layout case,
  v_max, and capacity vs. v_max for each.
- The load level is consistent: 0.7 applied once, to strength-level forces.
- Capacity for an unblocked diaphragm is taken from the unblocked column and
  the correct layout case.
- 3x framing (or equivalent) with staggered nailing is shown where nail
  spacing triggers it.
- L/W is within the table limit for the sheathing and blocking condition.
- Chords and collectors are identified in both directions and have
  continuity details (splices) along their length.
- Open-front or cantilevered diaphragms are analyzed as semirigid or rigid.

### Common findings (diaphragms)

- Unblocked diaphragm with capacity taken from the blocked table.
- 2x framing where 3x members with staggered nails are required.
- Unblocked diaphragm longer than 3:1 (or any diaphragm over its L/W limit).
- Staples specified on a DSA or HCAI project.
- Schedule silent on blocked vs. unblocked, or on field nailing.
- Open-front wood diaphragm analyzed as flexible.

## Subdiaphragms and crossties (heavy walls on a wood diaphragm)

**The problem.** A concrete or masonry wall pulls away from a wood roof or
floor out-of-plane. In SDC C-F that pull must be carried by **continuous ties
running chord to chord** across the diaphragm; the sheathing cannot be the tie
(ASCE 7-22 §12.11.2.2.1). Running every joist continuously across the
building is impractical.

**The solution.** A **subdiaphragm** along each heavy wall collects the wall
anchorage from many framing members and delivers it to a few **main
continuous crossties**, so full-length ties are needed only at subdiaphragm
edges.

- A subdiaphragm is a complete diaphragm: its own **subchords**, its own
  continuous ties (**subpurlins / subcrossties**), and a reaction carried
  across the building by the **main crossties**.
- **Maximum proportion 2.5:1** (ASCE 7-22 §12.11.2.2.1).
- Subpurlins span between subchords. The subdiaphragm bends under the wall
  anchorage and hands its reaction to the crossties at its boundaries. Each
  crosstie runs the **full depth of the building** (chord to chord); its force
  is the reaction collected from the subdiaphragms it serves.
- The arrangement is needed **in both directions**: walls on every side get
  subdiaphragms and crossties, with continuous collectors along the perimeter.
- Sized with the same tables and method as the main diaphragm. Because it
  carries concentrated anchorage, a subdiaphragm usually needs **tighter
  fastener spacing** than the main diaphragm around it.

**Anchorage force** (ASCE 7-22 §12.11.2.1, Eq. 12.11-1):

- **F_p = 0.4·S_DS·k_a·I_e·W_p**, not less than **0.2·k_a·I_e·W_p**, and not
  less than **5 psf × the wall area tributary to the anchor** (the 5 psf floor
  is the ASCE 7-22 addition).
- **k_a = 1.0 + L_f/100**, between 1.0 and 2.0. **L_f is the span of the main
  flexible diaphragm** that braces the wall, measured between vertical lateral
  elements in the direction checked, **not** the subdiaphragm span.
- **W_p is the wall only**, not the diaphragm. Per anchor level:
  - Intermediate floor: w_wall·(h_w1/2 + h_w2/2) (half the story below plus
    half the story above).
  - Roof with parapet: w_wall·(h_w2/2 + h_parapet).

**Crosstie splices at glulam hinges** (cantilevered/suspended beam systems):
the splice at a beam hinge is detailed to pass **axial tie force only**, often
with **slotted holes** so it does not pick up moment or gravity. The slot
tells you which force goes through. For the lateral trace, the question at
each hinge is whether the tie force is actually continuous across it.

### What to check on the drawings / calcs (subdiaphragms)

- At every concrete or masonry wall with a wood roof or floor, the
  subdiaphragms, their subchords and subpurlins, and the main crossties at
  their edges are identified on plan, in both directions.
- Subdiaphragm proportion is 2.5:1 or less.
- Anchor force uses k_a from the **main** diaphragm's L_f, W_p of the wall
  only, and the 5 psf tributary-area minimum.
- Crossties are continuous chord to chord, with a splice detail at every
  break, including glulam hinges.
- Subdiaphragm nailing is shown (often tighter than the main field).
- Finding if: no continuous crossties (sheathing relied on as the tie); k_a
  from the subdiaphragm span; a crosstie broken at a glulam hinge with no tie
  splice; subdiaphragms in one direction only.

## Wood shear walls

Shear walls support the diaphragm edges and carry its wind and seismic
reactions down to the foundation. Wall deflection is limited by the tighter of
what attached elements can tolerate and the ASCE 7-22 story drift limit
(§12.12, Table 12.12-1, Δ from δ_DE).

**The three-way split.** A wood shear wall resists lateral load with three
separate elements, one per force component, and every wall in the trace must
show all three: **shear** -> sheathing and its nailing; **tension**
(overturning uplift) -> hold-downs at the chord; **compression** (overturning
toe) -> compression studs / end posts. A wall with sheathing but no hold-down,
or a hold-down with no chord post to attach to, has a broken path.

### Parts of the wall and what each does in the load path

| Part | Role |
|---|---|
| Collector / double top plate | Receives the diaphragm reaction along the wall top; drags in load from beyond the wall ends |
| Sheathing + edge nailing | Carries **shear** from top plate to sill; edge and boundary nailing is where it transfers |
| Field nailing | Holds the panel to intermediate studs; not the main shear path |
| Studs and blocking | Back the panel edges; blocking makes a blocked wall |
| Chords (end posts, often doubled) | Take the **overturning couple**: tension one end, compression the other |
| Hold-downs | Carry chord **tension** into the foundation or the wall below |
| Sill plate + anchor bolts | Carry base **shear** (sliding) into the foundation |

### Sheathing allowed by SDC

- Options: WSP (plywood, OSB, composite), fiberboard, particleboard, gypsum
  board, plaster, lumber.
- **SDC E or F: WSP only.**
- **SDC D: no fiberboard and no particleboard** shear walls.
  (SDPWS 4.3.7.x) (verify: SDPWS-21)

### Construction requirements (WSP shear walls)

- Panels at least 4 ft × 8 ft; 2 ft minimum dimension at boundaries and
  framing changes.
- **Blocked is the default.** Unblocked is allowed only for walls **16 ft tall
  or less** meeting the SDPWS unblocked-wall provisions (4.3.5.3)
  (verify: SDPWS-21).
- Edge and boundary nailing 2 in. to 6 in. o.c.; studs 24 in. o.c. maximum.
- Field nailing 12 in. o.c., **except** 6 in. o.c. maximum where panels are
  3/8 or 7/16 in. **and** studs are at 24 in. o.c. (verify: SDPWS-21).
- Nails at least 3/8 in. from panel edges.
- Minimum panel thickness by stud spacing and grade: SDPWS Tables 4.3A, 4.3B
  (nails); IBC Table 2306.3(1) (staples) (verify: SDPWS-21 / 2025 CBC).
- **Wall type labels:** a common convention maps edge nailing 6, 4, 3, 2 in.
  o.c. to types A, B, C, D. Labels vary by office; always read the project's
  own shear wall schedule.

### Aspect ratio (h/b_w)

- **h:** clear height, top of foundation (or diaphragm below) to underside of
  diaphragm framing above.
- **b_w:** **sheathed** length, in the direction of force.

| Shear wall sheathing | Max h/b_w |
|---|---|
| WSP, blocked | 3.5:1 |
| WSP, unblocked | 2:1 |
| Diagonal lumber sheathing | 2:1 |
| Structural fiberboard | 3.5:1 |
| Particleboard, blocked | 2:1 |
| Gypsum wallboard | 2:1 |
| Portland cement plaster | 2:1 |

(verify: SDPWS-21)

- **Slender single WSP wall (seismic), h/b_w > 2:1:** multiply unit shear
  capacity by **(1.25 − 0.125·h/b_w)** (SDPWS 4.3.3.2). It is 1.0 at 2:1 and
  about 0.81 at 3.5:1. Whether SDPWS-21 also applies it to wind
  (verify: SDPWS-21).
- **Slender fiberboard wall (seismic), h/b_w > 1:1:** multiply by
  **(1.09 − 0.09·h/b_w)** (verify: SDPWS-21).
- **Several segments in one wall line (2:1 < h/b_w ≤ 3.5:1):** a slender
  full-height segment sharing a line with other segments has its capacity
  multiplied by **2·b_w/h** instead. This is a stiffness factor, not a
  strength factor: a slender segment is softer, so at the deflection the whole
  line shares it would otherwise be assigned more load than it can carry
  (verify: SDPWS-21 section number).

### Capacity and adjustments

- Capacity depends on panel thickness and grade, framing width, and fasteners
  (type, penetration, spacing).
- **Nails:** SDPWS Tables 4.3A, 4.3B give **nominal** unit shears (DF-L or SP
  framing, common or galvanized box nails). **Staples:** IBC Table 2306.3(1)
  gives **allowable** values. Nominal-to-design factors are the same as for
  diaphragms (seismic ÷2.8 ASD / ÷2.0 LRFD; wind ÷2.0 ASD / ÷1.25 LRFD)
  (verify: SDPWS-21).
- Tabulated values assume sheathing on **one side**, **2:1** aspect ratio,
  **all edges blocked**, and at least **2 in.** nominal framing. Any departure
  gets an adjustment.
- **Both faces, same capacity each side:** 2 × the one-side value
  (SDPWS 4.3.5.4.1) (verify: SDPWS-21).
- **Both faces, different capacity:** the larger of 2 × the weaker side or the
  stronger side alone (SDPWS 4.3.5.4.2) (verify: SDPWS-21).
- **Dissimilar materials on the two faces** (e.g. WSP one side, gypsum the
  other) are not additive for **seismic**; only for wind, with limits
  (verify: SDPWS-21).
- **Unblocked walls:** read the table at 6 in. edge nailing, then multiply by
  the unblocked adjustment factor **C_ub** (verify: SDPWS-21).
- **Heavily loaded walls, SDC D-F, allowable unit shear > 350 plf** (nominal
  980 plf = 350 × 2.8) (verify: SDPWS-21):
  - framing at abutting panel edges at least a single 3x or two 2x fastened
    together;
  - staggered nailing at panel joints and into the sill plate;
  - sill plate size and anchorage per the SDPWS sill/anchor provisions.

### Unit shear in a wall: top vs. bottom (ASD)

The wall's share of story shear, V_w (lb), enters at the top. For walls,
**E_h = ρ·Q_E with ρ = the building's value (1.0 or 1.3, ASCE 7-22 §12.3.4)**,
not the 1.0 used for diaphragms.

- **v_top = 0.7·ρ·V_w / b_w** (plf)
- **v_bot = 0.7·ρ·(V_w + C_s·W_w) / b_w** (plf); the wall's own inertia is
  added on the way down. For light wood walls v_bot ≈ v_top.

| Design item | Use |
|---|---|
| Collector / drag at the top of the wall | v_top, with ρ = 1.0 |
| Sheathing grade, thickness, nail size and spacing | v_bot |
| Anchorage to the wall below or foundation (sill / anchor bolts) | v_bot |

- **Anchor bolt spacing = bolt capacity (lb) ÷ v_bot (plf).**
- Collectors in a light-frame wood building are designed at the diaphragm
  force level (ρ = 1.0) and are exempt from Ω₀ (ASCE 7-22 §12.10.2.1, wood
  light-frame exception). The 25% increase on collectors and their
  connections for horizontal irregularity Types 1-4 and vertical Type 3 in
  SDC D-F still applies, except where designed with Ω₀; see
  `diaphragms_and_collectors.md`. (ASCE 7-16 lists these as horizontal 1a,
  1b, 2, 3, 4 and vertical Type 4.)

### Overturning and hold-downs

Lateral load tips the wall. Wood buildings are light, so dead load rarely
holds the heel down and a mechanical hold-down is usually needed.

- **Overturning (about the compression toe):** V_w at height h; wall inertia
  C_s·W_w at h/2.
- **Resisting:** wall weight W_w at b_w/2; tributary dead load W_DL (plf) × b_w
  at b_w/2. Vertical earthquake E_v acts upward and **reduces** resistance.
- **RM/OTM < 1.0 means net uplift:** hold-downs are required at **both** ends,
  because the load reverses.

**Hold-down force:** uplift governs when earthquake opposes gravity, so use
the minimum-dead-load ASD combination, **ASCE 7-22 combination 10:
0.6D − 0.7E_v + 0.7E_h**, with E_v = 0.2·S_DS·D and E_h = ρ·Q_E. The dead load
factor becomes **(0.6 − 0.14·S_DS)**.

- **OTM = 0.7·ρ·(V_w·h + C_s·W_w·h/2)**
- **RM = (0.6 − 0.14·S_DS)·(W_w·b_w/2 + W_DL·b_w²/2)**
  (V_w, W_w in lb; W_DL in plf; b_w, h in ft)
- **T = (OTM − RM) / b_w** when OTM > RM.
- Conservative, ignoring dead load and wall inertia: **T = 0.7·ρ·V_w·h / b_w**.
- Typical hardware: a proprietary hold-down bolted or screwed to the end post,
  anchored through the sill into the concrete or masonry below.
- **Multi-story walls:** overturning at a lower story includes the overturning
  from the walls stacked above, so hold-down forces **accumulate** down the
  building. Check that the calc carries the upper-story uplift into each
  lower hold-down.

### Worked example: hold-down force

A 12 ft long, 16 ft tall wood shear wall shares a line with an 8 ft wall.

- **Wall shear:** the line collects 185 plf (strength level) over a 26 ft
  tributary length (6 + 12 + 8 ft), split by wall length:
  V_w = 185 × 26 × 12/(12 + 8) = **2,886 lb**.
- **Inputs:** W_w = 20 psf × 16 ft × 12 ft = **3,840 lb**; C_s = 0.22;
  S_DS = 1.2; roof dead load W_DL = 140 plf; ρ = 1.0.
- **OTM** = 0.7 × (2,886 × 16 + 0.22 × 3,840 × 16/2) = 0.7 × (46,176 + 6,758)
  = **37,054 lb-ft**
- **RM** = (0.6 − 0.14 × 1.2) × (3,840 × 12/2 + 140 × 12²/2)
  = 0.432 × (23,040 + 10,080) = **14,308 lb-ft**
- **T** = (37,054 − 14,308) / 12 = **1,895 lb** per hold-down, both ends.
- The 0.7 converts strength-level seismic to ASD, so the 185 plf must be a
  strength-level value. If a calc applies 0.7 to a load that is already ASD,
  the overturning is understated by 30%.

### Sill plate anchor bolts: prescriptive minimums

These are the IBC conventional light-frame provisions (IBC 2308)
(verify: 2025 CBC section numbers).

| Item | Minimum |
|---|---|
| End distance, each end of each sill piece | 4 in. min, 12 in. max; at least 2 bolts per piece |
| Spacing | 6 ft o.c. max; 4 ft max for buildings over 2 stories above grade plane |
| Embedment into concrete or masonry | 7 in. min |
| Diameter | ½ in. for SDC A-D; ⅝ in. for SDC E |
| Washers | Standard for SDC A-C; 3 in. × 3 in. × 0.229 in. plate washers for SDC D-E |

For **engineered** shear walls, SDPWS requires 3 × 3 × 0.229 in. plate
washers at shear wall anchor bolts regardless of SDC (verify: SDPWS-21).
Engineered spacing comes from bolt capacity ÷ v_bot.

### System selection ties to ASCE 7-22

- Light-frame wood walls sheathed with WSP rated for shear resistance: Table
  12.2-1 row **A.16** (bearing wall system) and **B.23** (building frame);
  walls with shear panels of all other materials: **A.18 / B.25**
  (confirmed, ASCE 7-22 Table 12.2-1). ASCE 7-16 (older projects /
  existing reports) listed the WSP bearing wall system as A.15.

  | Row | System | R | Ω₀ | C_d | SDC D | SDC E | SDC F |
  |---|---|---|---|---|---|---|---|
  | A.16 | Light-frame (wood) walls, WSP (bearing wall) | 6½ | 3 | 4 | 65 ft | 65 ft | 65 ft |
  | B.23 | Light-frame (wood) walls, WSP (building frame) | 7 | 2½ | 4½ | 65 ft | 65 ft | 65 ft |
  | A.18 | Light-frame walls, other shear panel materials (bearing wall) | 2 | 2½ | 2 | 35 ft | NP | NP |
  | B.25 | Same (building frame) | 2½ | 2½ | 2½ | 35 ft | NP | NP |
  | G.6 | Timber frames (cantilever column) | 1½ | 1½ | 1½ | 35 ft | NP | NP |

  All of these are NL in SDC B and C, except timber frames (35 ft in B and C).
  On a flexible wood diaphragm, Ω₀ = 3 may be reduced by 0.5 to 2.5
  (Table 12.2-1 footnote b).
- **ρ:** a WSP wall with h/b_w > 1.0 is a Table 12.3-3 "remove one element"
  case; for light-frame walls the number of bays is counted as
  **2 × L/h_sx**. See `seismic_design_basis.md`.

### What to check on the drawings / calcs (shear walls)

- Trace every wall part by part using the parts table: diaphragm-to-top-plate
  transfer, sheathing and edge nailing, chord and hold-down at **both** ends,
  sill plate and anchor bolts at the base. Each link has a detail or schedule
  callout.
- Each hold-down anchors into something: the foundation, or a hold-down /
  strap / rod in the wall below that continues the path.
- Shear wall schedule vs. SDC: sheathing type allowed (WSP only in SDC E-F; no
  fiberboard or particleboard in SDC D).
- Blocked vs. unblocked: unblocked only up to 16 ft, with C_ub applied.
- Aspect ratio within the table limit, using the **sheathed** length; the
  (1.25 − 0.125·h/b_w) or 2·b_w/h factor applied where h/b_w > 2:1.
- Both-faces capacity taken per the both-faces rules; no dissimilar-material
  addition for seismic.
- Walls over 350 plf allowable in SDC D-F show 3x (or 2-2x) framing at panel
  edges and staggered nailing, including at the sill.
- ρ in the wall shear is the building's ρ; collector force uses ρ = 1.0.
- Hold-down force uses the (0.6 − 0.14·S_DS) dead load factor, the 0.7 applied
  once, and accumulated uplift from stories above.
- Sill bolt size, spacing, embedment, and plate washers are consistent with
  the SDC and with v_bot.
- Wall types on the plans match the schedule, and the schedule matches the
  calc.

### Common findings (shear walls)

- No hold-down (or no chord post) at one end of a wall or segment.
- No detail for how diaphragm shear reaches the top plate.
- Unblocked wall over 16 ft.
- Sheathing type not permitted for the SDC (e.g. fiberboard in SDC D, non-WSP
  in SDC E-F).
- Plan wall types that do not appear in the schedule, or that disagree with
  the calc.

## Shear walls with openings

SDPWS allows three methods for a wall line with door and window openings. The
required hold-downs and detailing differ, so the drawings must make clear
which method was used.

**Segmented (traditional):**
- Each full-height piece between openings is its own shear wall.
- **Every segment needs hold-downs at both ends.**
- Sheathing above and below openings is ignored for stiffness and strength.
- Line capacity = sum of segment capacities, each with its own aspect-ratio
  adjustment.

**Force transfer around openings (FTAO):**
- The line is one wall, openings included. Sheathed panels above and below
  openings act as **coupling beams**, passing shear around the opening from
  pier to pier.
- Requires a **rational analysis** of the wall and boundary forces at each
  opening corner.
- Requires detailing that **extends past the opening** far enough to develop
  those forces: typically **straps and blocking** above and below the opening
  running into the adjacent piers, plus tighter sheathing nailing.
- Each pier stays within the SDPWS pier aspect ratio limits
  (verify: SDPWS-21).
- Hold-downs at the **ends of the whole wall**, not at every pier.

**Perforated shear wall:**
- The whole wall, with a **test-based (semi-empirical) reduction**: capacity is
  a percentage of the same wall with no openings, set by opening sizes.
- Limits (verify: SDPWS-21):
  - full-height segment at **each end**;
  - nominal unit shear **≤ 2,435 plf**, one or both sides sheathed;
  - where the wall jogs out of plane, each side of the jog is its own
    perforated wall;
  - **collector along the full length**;
  - top and bottom at **constant elevations** (no steps);
  - **20 ft maximum height**.
- Hold-downs at the wall ends; the bottom plate is anchored for uplift along
  its length between the ends (verify: SDPWS-21).

| | Segmented | FTAO | Perforated |
|---|---|---|---|
| What counts as the shear wall | Each full-height segment | Whole wall, openings included | Whole wall, openings included |
| Sheathing above/below openings | Ignored | Carries shear (coupling beam) | Covered by the empirical reduction |
| Hold-downs | Both ends of **every** segment | Ends of the wall | Ends of the wall |
| Extra detailing | None | Straps + blocking around openings, closer nailing | Full-length collector; limits above |
| Relative capacity | Sum of segments | Higher than perforated | Lower than FTAO |

### What to check on the drawings / calcs (openings)

- The method used for each wall line with openings is stated (calc or
  schedule).
- **Segmented:** a hold-down at every segment end.
- **FTAO:** straps and blocking above and below each opening, developed into
  the piers; pier aspect ratios within limits; the rational analysis is in
  the calc.
- **Perforated:** full-height segments at both ends, full-length collector,
  constant top and bottom elevations, height ≤ 20 ft, nominal shear
  ≤ 2,435 plf, bottom plate anchored between the ends.

### Common findings (openings)

- Segmented wall line with hold-downs only at its extreme ends.
- FTAO claimed with no strapping or blocking shown around openings.
- Perforated wall with a stepped top or bottom plate, or no full-height end
  segment.
- Method not stated, so the required details cannot be confirmed.

## Wood walls and diaphragms resisting concrete or masonry walls

Concrete and masonry walls generate large seismic forces, and a wood system
carrying them can deflect too much for the heavy walls. SDPWS limits wood
shear walls and diaphragms resisting forces from concrete or masonry walls to
**one-story** buildings, except **two stories** are allowed when **all** of
these hold (verify: SDPWS-21):

1. Shear walls blocked on all edges.
2. Shear walls in the two stories line up.
3. Story-to-story shear wall height 12 ft maximum.
4. Deflection within the ASCE 7-22 drift limits (§12.12.1).
5. Lower-story sheathing at least 15/32 in. thick.
6. The diaphragm is **not** designed to transfer load by rotation and does
   **not** cantilever past the outermost shear wall.

Condition 6 means the open-front / cantilevered diaphragm approach is not
available here.

**Check:** a wood lateral system resisting concrete or masonry walls in more
than one story (or two stories without all six conditions), or with a
cantilevered or rotation-based diaphragm, is a finding.

## Collectors in wood buildings

- Collectors are needed at diaphragm boundaries, where shear walls stop or
  jog, and at reentrant corners, to keep the diaphragm from tearing locally
  and to keep its deformation compatible with the walls.
- In wood the collector is often the double top plate (see the parts table); check that its splices and its connection into each wall are detailed.
- Force level and the 25% irregularity increase: see "Unit shear in a wall"
  above and `diaphragms_and_collectors.md`.

## Wood connections

### Basics

- Every connection keeps the path **continuous to the foundation**: from
  where the force starts, through the connection, into the supporting member.
- **Positive connection required.** A wood member simply bearing on its
  support, with no fastener, does not count for lateral load.
- Fasteners: nails, bolts, lag screws, shear plates, proprietary connectors.
- **Shear (lateral) loading:** load perpendicular to the fastener; may have
  more than one shear plane. **Withdrawal:** load along the fastener.
- **Nails in tension:** for anchorage of concrete or masonry walls to wood
  diaphragms in SDC C-F, toenails and nails in withdrawal are prohibited
  (ASCE 7-22 §12.11.2.2.3). A broader prohibition covering all wood lateral
  connections in SDC C-F may also apply (verify: SDPWS-21 / IBC). Treat any
  nail in withdrawal or tension-loaded toenail in the lateral path as a flag.

### Fastener capacity (NDS)

| Connection | NDS table(s) |
|---|---|
| Nail, wood-to-wood, single shear (side grain) | 12N |
| Nail, WSP to wood | 12Q, 12R |
| Bolt, wood-to-wood, single and double shear | 12A, 12F |
| Bolt, wood to concrete | 12E |

(verify: NDS edition used on the project)

- **Z' = Z × applicable adjustment factors**: load duration, wet service,
  temperature, end grain, diaphragm, group action, geometry/spacing, toenail
  (NDS Table 11.3.1 lists which apply). For wind and seismic in **ASD**, the
  load duration factor **C_D = 1.6**; LRFD uses the time effect factor λ
  instead (1.0 for seismic) (verify: NDS).
- **Proprietary** straps, ties, plates, hold-downs: use the manufacturer's
  values, with the model number called out.
- The diaphragm and shear wall tables assume staples, common nails, or
  galvanized box nails. Any other fastener, including a field substitution,
  needs the tables' footnote adjustments. Nails are identified by size and
  type, e.g. **8d common = 2½ in. × 0.131 in. diameter**.

### The lateral load path in a two-story wood building, link by link

This is the model lateral trace for light-frame wood, roof to foundation.
**Every arrow is a physical connection that must be shown on the drawings.**
Use it as the checkpoint list for each shear wall line; extend it one floor
at a time for taller buildings.

**In-plane shear (sliding):**

1. **Roof sheathing -> rim / end blocking** over the wall: diaphragm
   **boundary nailing** (spacing from the diaphragm schedule).
2. **End blocking -> second-story double top plate:** **proprietary framing
   anchors** (clip angles), or horizontal wood blocking nailed to the plate
   (NDS nail values).
3. **Top plate -> shear wall sheathing:** shear wall **edge nailing**.
4. **Sheathing -> second-story bottom (sole) plate:** edge nailing. Shear here
   is the roof diaphragm shear **plus** the wall's own inertia (v_bot).
5. **Bottom plate -> second-floor rim / end blocking:** **sole plate nailing
   or screws** down through the floor sheathing.
6. **Second-floor diaphragm joins in:** its shear enters the same rim/end
   blocking through its **boundary nailing**. From here down, the force is
   **cumulative** (roof + second floor).
7. **Rim / end blocking -> first-story double top plate:** framing anchors or
   blocking, as in link 2.
8. **Top plate -> first-story sheathing -> sill plate:** shear wall edge
   nailing at top and sill.
9. **Sill plate -> foundation:** **anchor bolts**, carrying the total in-plane
   shear into the concrete.

**Overturning (uplift):**

- **Story to story:** the end posts of the upper wall are tied to the end
  posts of the wall below with a **floor-to-floor tie** (a steel strap nailed
  or bolted to both posts, running past the floor framing), carrying the
  upper wall's uplift into the lower wall.
- **At the foundation:** **hold-downs** at the ends of the first-story walls
  anchor the **accumulated** uplift into the foundation.

**Most common gaps:**
- Link 2 or 7: nothing specified to move diaphragm shear from blocking into
  the top plate. Sheathing "touching" the plate is not a connection.
- Link 5: sole plate nailing through the floor not called out.
- Missing floor-to-floor tie, so upper-wall uplift has no path past the floor.

### Wood diaphragm to a concrete or masonry wall (ledger)

A ledger connection carries **three different forces**, each with its **own**
path:

| Force | Path |
|---|---|
| **Gravity** (dead and live) | Joist -> hanger -> ledger -> anchor bolts -> wall |
| **In-plane shear** (diaphragm force parallel to the wall) | Sheathing -> edge/boundary nails -> ledger -> anchor bolts -> wall |
| **Out-of-plane** (wall pulling away) | Wall -> **wall anchor** (strap, tie, or hold-down) -> joist / purlin / subpurlin -> diaphragm, **bypassing the ledger** |

- The out-of-plane anchor connects to the framing member, or an embedded strap
  runs straight onto the framing and blocking (length and embedment
  specified).
- Keep the offset between sheathing and anchorage small; anchorage
  eccentricity must be designed for (ASCE 7-22 §12.11.2.2.6).

**Why the ledger cannot carry the out-of-plane force** (ASCE 7-22
§12.11.2.2.3, SDC C-F):
- **Cross-grain bending:** with the ledger as the only connection, the anchor
  bolt and the sheathing edge nails form a couple that twists the ledger
  across its grain. Prohibited.
- **Cross-grain tension:** the edge nails pull the ledger perpendicular to its
  grain. Prohibited.
- The same section bars toenails and nails in withdrawal for this anchorage,
  and does not allow the sheathing to serve as the tie.

### What to check on the drawings / calcs (connections)

- Every link in the two-story chain (and its extension for each added story)
  has a detail, schedule entry, or callout.
- Links below each floor (lower-story nailing, sole plate and sill
  anchorage) are sized for the cumulative shear from all levels above.
- Proprietary hardware is called out by model, with the manufacturer's
  capacity in the calc.
- No lateral link relies on bearing alone, nails in withdrawal, or
  tension-loaded toenails.
- At every concrete or masonry wall with a wood roof or floor: all three
  ledger paths are present, the out-of-plane anchor bypasses the ledger, and
  anchorage eccentricity is addressed.
- Substituted fasteners (not common or galvanized box nails) carry the table
  footnote adjustments.

### Common findings (connections)

- Ledger with anchor bolts and hangers but **no out-of-plane wall anchor**: the
  classic finding, because the out-of-plane force would go into the ledger in
  cross-grain bending.
- Blocking-to-top-plate transfer (links 2 and 7) not detailed.
- No floor-to-floor strap between stacked chord posts.
- Hardware callout without a model number or capacity.

## Cripple walls and older existing wood buildings

### Cripple walls

- Short stud walls between the foundation and the first floor of a raised
  (crawl-space) building. Studs at least the size of the studs above.
- They must be **braced**, because a failed cripple wall takes the whole
  building down:
  - **14 in. or less:** solid blocking.
  - **Over 14 in.:** braced per the IBC conventional-construction bracing
    table for SDC A-C, and the IBC SDC D-E cripple wall provisions for D and
    E (IBC 2308) (verify: 2025 CBC section and table numbers).

### Older existing wood buildings

Older wood buildings typically lack a complete, clearly defined lateral load
path, because current SDC D-F requirements did not exist when they were
built. Common conditions: gypsum or plaster shear walls, diagonally sheathed
diaphragms, missing out-of-plane wall anchorage.

| Typical earthquake damage | Missing or weak link |
|---|---|
| Building slides off its foundation | No sill bolts / foundation anchorage |
| Cripple wall collapse (weak story) | Cripple walls unsheathed, or only lap siding or thin panels |
| Soft or weak first story (large racking) | Large garage or parking openings in the first story |
| Chimney failure | Unreinforced brick, or no anchorage to the roof |
| Hillside house failure | Undersized braces, piers, or posts below |
| Entry canopy collapse | Poor anchorage to the main roof |
| Gas / water line rupture | Lines unable to move with the building |

**Check:** on renovation and retrofit projects, call out any of these
missing links, and note where the drawings are silent on existing conditions
(e.g. whether existing sill bolts or cripple wall sheathing exist) rather than
assuming them. Evaluation and retrofit criteria come from ASCE 41 and the
California Existing Building Code, which this reference does not cover.

## Not yet covered (reference gaps)

The topics below, mostly mid-rise conditions (4-5 story wood, often over a
concrete podium), are not covered by this reference. When the review meets
one, report it as a **reference gap**: describe what the drawings show, list
the open questions, and recommend engineer review. Do not invent rules for
them.

- **Mid-rise tie-down systems:** discrete hold-downs at each floor vs.
  **continuous rod tie-down** systems; **wood shrinkage and take-up
  devices**; what makes the tension path continuous vs. broken from floor to
  floor.
- **Compression posts:** stacking of chord/compression posts floor to floor,
  continuous bearing all the way down, and crushing at plates.
- **Podium base transfer:** shear wall anchor bolts and hold-down anchorage
  into the podium slab, and the transfer into the podium (relates to the
  vertical-combination and two-stage analysis rules in
  `seismic_design_basis.md`).
- **Non-stacking shear walls:** walls that do not stack floor to floor
  (in-plane vs. out-of-plane offsets) and what supports the discontinuous
  wall.
