# Lateral Load Path Tracing — Methodology

This file describes the cross-material method for tracing a lateral (seismic,
and where applicable wind) load path through a drawing set. Every material
follows it. The material files (`wood.md`, `steel.md`, `concrete.md`,
`masonry.md`) give the connection mechanisms to look for at each junction.
`seismic_design_basis.md` and `diaphragms_and_collectors.md` give the code
basis for the forces each link has to carry. Read this file first.

## What a lateral trace is (and isn't)

A gravity trace follows load *down* through bearing. A lateral trace
follows load *sideways and then down*, and it has more ways to break. The
load has to:

1. **originate** somewhere: building mass at each level for seismic, or
   wind pressure on walls and roof;
2. get **into a diaphragm**;
3. travel **across the diaphragm** to its boundaries;
4. be **collected** into the vertical elements;
5. go **down each vertical element**, story by story;
6. be **anchored** at the base;
7. go **through the foundation** into the soil.

Overturning creates a **second path**, tension and compression at the ends
of each vertical element, which must also be continuous to the foundation.

This skill establishes and QA/QCs **what the lateral load path is**, and
whether the drawings and calcs show the code-required basis for each link.
It does not compute forces or check capacities. Where a code force level
matters for a link (for example, a collector designed with Ω₀), the skill
checks that the drawings or calcs **show** that basis. It does not check
whether the number is right.

## The rule that matters most: contact is not proof of a lateral connection

Same principle as the gravity skill, with lateral-specific traps. Two
elements touching, aligned, or "clearly fastened" doesn't mean lateral
force passes between them **in the direction that matters**.

- **Wood:**
  - Sheathing only transfers diaphragm shear into a wall or collector
    through the **specified edge nailing** into a member that is itself
    connected (blocking, top plate, rim, ledger).
  - A ledger fastened to a concrete or masonry wall carries gravity. It
    does **not** carry out-of-plane wall anchorage force unless separate
    straps or ties are provided. **Cross-grain bending and cross-grain
    tension** in ledgers are not permitted lateral mechanisms.
  - Toenails and nails in withdrawal are not lateral anchorage.
- **Steel:**
  - A simple shear tab carries gravity shear. It is not a moment
    connection and not a collector splice unless detailed for axial force.
  - A deck welded to a beam transfers diaphragm shear only if the beam is
    connected to the frame for that axial force.
  - Vertical slots in a connection release vertical load, but they can
    still carry lateral force (see the V2 gravity skill).
  - Horizontal slots release lateral force in the slot direction.
- **Cast-in-place concrete:** monolithic concrete says nothing about
  lateral transfer. **Reinforcement continuity** decides it: collector or
  drag bars developed into the wall, chord bars spliced, dowels across the
  cold joint.
- **Precast concrete:** connections between pieces must be detailed for
  shear, axial force or both. Bearing alone transfers no lateral force.
- **Masonry:** transfer from a diaphragm into a wall happens through
  **embedded anchors and bond beams**. Dowels, not mortar bond, carry
  shear and overturning into the foundation.
- **Any material:** a slotted, isolated, or "seismic joint" connection is
  intentionally **not** a lateral connection. Make sure the path doesn't
  rely on one.

At every junction, name the **actual mechanism** and the **direction of
force** it resists. If the drawings don't show one, that's a finding
("unconfirmed"), not an assumption of continuity.

## The steps

### Step 1 — Identify the system and design basis

Before tracing, record:

- **Jurisdiction and code editions:**
  - the building code (IBC / CBC edition) and the ASCE 7, material
    standard, and existing building code editions it references;
  - whether the project is new construction, an addition, an alteration,
    a repair, or a change of occupancy.

  These set which provisions apply (see SKILL.md, "Governing standards",
  and `existing_buildings.md`).
- **Lateral system in each principal direction:** shear walls, braced
  frames, moment frames, dual, cantilever column, and so on. Record
  material and detailing level (special, intermediate, ordinary), and the
  ASCE 7-22 Table 12.2-1 row.
- **Design basis from the general notes and calcs:**
  - risk category and I_e;
  - site class;
  - S_DS and S_D1;
  - SDC;
  - R, Ω₀, C_d, and ρ in each direction;
  - analysis procedure;
  - base shear;
  - drift limit.

  Check these for **internal consistency** and against the code
  permissions (system allowed in the SDC, height limit, procedure
  permitted). See `seismic_design_basis.md`.
- **Diaphragm at each level:**
  - material (wood sheathing, steel deck with or without fill, concrete
    slab);
  - classification (flexible, rigid, or semirigid) **and how the calcs
    treated it**.

  See `diaphragms_and_collectors.md`.
- **Irregularities** identified, or that should have been, and their
  consequences.
- **Foundation type** and the geotech report's seismic items. See
  `foundations_and_geotechnical.md`.
- **Heavy nonstructural components or nonbuilding structures** supported
  by the building (rooftop equipment, tanks, screens). See
  `nonstructural_and_nonbuilding.md`.

This becomes the **System Identification and Design Basis** section of the
report.

### Step 2 — Trace the typical line of resistance in full, in each direction

Lateral load is traced **per direction**. For each principal direction,
pick the most representative line of resistance, such as a typical
interior shear wall line or a typical braced bay, and trace it from the
roof to the soil:

1. **Load into the diaphragm.**
   - **Seismic:** the diaphragm's own mass plus tributary walls.
   - **Out-of-plane walls** (concrete, masonry, heavy cladding) span
     vertically to the diaphragm through the **wall anchorage**. Name the
     anchor, its spacing, and what it connects to: a continuous crosstie
     or subdiaphragm, not a ledger alone.
2. **Across the diaphragm.** Name the sheathing, deck or slab, its
   attachment, and the **chords** at the boundaries perpendicular to the
   load. Confirm chord continuity: splices, straps, rebar.
3. **Into the vertical element.**
   - Where the vertical element is shorter than the diaphragm depth, name
     the **collector or drag strut**, how it's spliced along its length,
     and how it connects into the wall or frame.
   - Note the force level the code requires for it (Ω₀ in SDC C–F, with
     the light-frame wood exception).
4. **Down the vertical element, story by story.**
   - **Walls:** sheathing and nailing, or reinforcement.
   - **Frames:** beam, brace, connections, panel zone.
   - At each floor, confirm the story above **lands on** the element
     below, or that a transfer path is designed (see Step 3).
5. **Overturning path.**
   - Tension and compression at each end of the element: hold-downs and
     posts, boundary bars, columns.
   - Confirm they are **continuous** through every floor to the foundation.
6. **Base anchorage.** Name how base shear and uplift get into the
   foundation:
   - anchor bolts and sill plates;
   - hold-down anchors;
   - dowels;
   - base plates and anchor rods;
   - shear lugs or embedded plates.
7. **Foundation and soil.**
   - Name the footing, grade beam, mat, or pile cap that resists the
     overturning couple and sliding.
   - Name the geotech values it relies on: bearing, friction, passive.
   - Note any ties between footings where required.

This trace gets the most detail in the report. It's the baseline every
other line of resistance is compared against.

### Step 3 — Scan for atypical conditions and trace each one individually

Compare every other line of resistance, level, and diaphragm zone against
the typical trace. **Individually trace** any condition that could change
the lateral path, especially:

- **Discontinuities in the vertical system:**
  - in-plane offsets;
  - out-of-plane offsets;
  - a wall or frame that stops at a level (a podium, setback, or open
    ground floor).

  Each needs a **transfer path** (transfer diaphragm, transfer beam or
  column) designed for the code-required force. Supporting elements
  usually need Ω₀ (§12.3.3.4).
- **Re-entrant corners, large openings, and diaphragm discontinuities.**
  These need chords or collectors around them and a force path past them.
- **Stepped or split-level diaphragms.** The force has to get from one
  level to the other through a designed element.
- **Lines of resistance with a different system or material:**
  - a steel frame in a wood building;
  - a concrete core with a steel gravity frame;
  - a vertical combination, with system limits that follow
    `seismic_design_basis.md`.
- **Open-front or cantilevered diaphragms**, and torsionally irregular
  plans.
- **Elements not part of the SFRS** that could still be engaged:
  - gravity columns (deformation compatibility, §12.12.4);
  - rigid infill or partial-height walls against frames (§12.7.4);
  - stairs.
- **Nonstructural components and nonbuilding structures** with their own
  anchorage path.
- **Foundation conditions that differ:**
  - a different footing type;
  - a step in the foundation;
  - a liquefiable or sloping zone;
  - a retaining condition with seismic earth pressure.

Lines that match the typical trace are recorded as matching. Don't re-trace
them one by one; that buries the conditions that need a careful look.

### Step 4 — Verify the mechanism at every junction, against the material reference

At each junction traced in Steps 2 and 3:

- Confirm the drawings show the **material-appropriate mechanism** (see
  the "contact is not proof" rule above and the material files).
- Confirm the **detailing level matches the system claimed**. Examples:
  - a "special" concrete wall has boundary elements where triggered;
  - an SCBF has no K bracing;
  - an SMF connection is prequalified or tested;
  - wood shear walls meet the aspect-ratio and hold-down rules.
- Where the code requires a specific **force level** for the link, check
  that the calcs or notes **state** it:
  - collectors and their connections (Ω₀);
  - elements supporting discontinuous walls or frames (Ω₀);
  - wall anchorage (F_p with k_a);
  - diaphragm F_px and the transfer forces.
- Prefer **project-specific details and schedules** over typical/standard
  details. If a typical detail is the only support for a connection, say so
  in the appendix.

### Step 5 — Produce the report

See SKILL.md for the report structure. Findings fall into four types, and
each finding should name its type:

1. **Broken or unconfirmed load path.** A link with no shown mechanism, or
   a mechanism that doesn't resist force in the needed direction.
2. **Design-basis inconsistency.** Coefficients, SDC, system, procedure,
   or drift values that don't agree with each other or with the code.
3. **Detailing non-conformance.** A detail that doesn't meet the
   requirement for the system level claimed.
4. **Reference gap.** A system or condition the reference files don't
   cover, such as a mid-rise wood rod tie-down system, a podium transfer,
   or wind-governed design. Flag it; don't invent rules.

## Wind

The tracing method above is the same for wind. The load originates as
pressure on the building envelope instead of mass. The **component and
cladding** pressures load the out-of-plane wall and roof spans. The
**MWFRS** pressures load the diaphragms and vertical elements.

**The reference files in this skill are seismic-focused.** Wind load
determination (ASCE 7-22 Chapters 26–31) is not yet covered. When wind
governs a line of resistance, or the project is in a low-seismic,
high-wind area:

- trace the path the same way;
- note in Scope & Limitations that the wind basis wasn't independently
  reviewed;
- flag it as a reference gap.

The wood file gives the SDPWS wind conversion factors, which differ from
the seismic factors.

## Both directions and orthogonal effects

- Trace **both principal directions**. A building can have a complete
  path in one direction and a broken one in the other. Narrow buildings
  often have plenty of walls in the long direction and almost none in the
  short direction.
- Where ASCE 7-22 §12.5 requires orthogonal combination (100% + 30%), such
  as for columns or walls common to two intersecting systems, confirm the
  calcs address it.

## Existing buildings

See `existing_buildings.md` for the code path: the existing building
code compliance method, the triggers that require a lateral evaluation,
and what the documents should show. In addition, for retrofit, alteration,
or addition projects:

- The evaluation basis is usually the **Existing Building Code / ASCE 41**,
  not ASCE 7. Note which one the documents use.
- Trace the existing path too. The common breaks in older buildings are:
  - **wall-to-diaphragm anchorage** (URM, older concrete tilt-up);
  - **cripple walls and sill anchorage** (wood);
  - **non-ductile concrete columns and joints**;
  - **missing collectors**.

  See the existing-building sections of each material file.
- New lateral elements must have their own complete path to the
  foundation, **and** a way to collect load from the existing diaphragm.
