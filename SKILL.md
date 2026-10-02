---
name: lateral-load-path-qaqc
description: QA/QC review that traces the lateral (seismic) load path through a structural drawing set -- diaphragm, chords, collectors, shear walls or frames, hold-downs and anchorage, foundation, soil -- verifying the actual connection mechanism and force direction at each junction instead of assuming continuity. Also checks the seismic design basis against ASCE 7-22 and detailing against the system claimed (ACI 318-19, AISC 341/358, SDPWS, TMS 402). Covers wood, steel, concrete, masonry, wall anchorage, irregularities, nonstructural anchorage, and geotechnical/foundation items. Use whenever drawings or seismic calcs are uploaded and the ask is to trace or QA/QC the lateral or seismic load path or lateral system, even without the words "load path" (e.g. "are the collectors detailed", "check the seismic design basis", "does the hold-down stack reach the footing", "what happens at this discontinuous wall"). Companion to gravity-load-path-qaqc, general-notes-qaqc, and spec-qaqc. Produces a Word QAQC report.
---

# Lateral Load Path QA/QC

Traces the lateral load path through a structural drawing set the way a
structural engineer would. Start where the load enters a diaphragm. Follow
it to the boundaries, into collectors, down each vertical element story by
story, through the overturning and base-shear anchorage, and into the
foundation and soil. At each step, confirm the connection actually resists
force in the direction that matters.

This is **V3 of a skill family** and the companion to
`gravity-load-path-qaqc` (V2). It **does not compute forces or check
capacities**. It establishes and QA/QCs what the lateral load path *is*. It
checks that the design basis and detailing shown are consistent with the
code for the system claimed. It flags every link it can't confirm from the
documents.

## Governing standards

- **Use the code editions the project's jurisdiction adopts.** Read them
  from the general notes or code sheet: the IBC/CBC edition and the ASCE 7,
  ACI 318, AISC, SDPWS, and TMS editions it references. Record them in
  Step 1. If the documents don't state an edition, that's a finding.
- **The references are written to the latest editions:** ASCE 7-22 (2025
  CBC, 2024 IBC) and ACI 318-19, both checked against the code text.
- **When the project is on an earlier edition** (for example IBC 2021,
  which references ASCE 7-16):
  - review against that edition;
  - cite provisions that read the same in both editions directly;
  - where a 7-22 rule differs (site classes and PGA_M, the F_p equation,
    irregularity definitions, ρ conditions, Chapter 15 thresholds, and so
    on), don't write a finding against the 7-22 rule. Note the difference,
    state the requirement of the adopted edition, and tag it "(verify:
    ASCE 7-16)" if that text isn't available;
  - the 7-16 forms labeled in the references help here.
- **Existing buildings** follow the jurisdiction's existing building code
  (IEBC or CEBC) rather than the new-building provisions. See
  `reference/existing_buildings.md`.
- **AISC 341/358, AWC SDPWS-21 and NDS, TMS 402/602, and the IBC/CBC**
  items in the references are from engineering knowledge and are tagged
  **"(verify: …)"**. Treat a "(verify)" item as a prompt to check, not as
  settled fact. Don't write a hard finding on a "(verify)" item alone:
  phrase it as "confirm".
- Items marked **"(project standard)"** are deliberate review rules that
  go beyond the code minimum. State them as such in findings.

## What you need

- **Minimum:**
  - the structural general notes, with the seismic design basis;
  - roof and floor framing or diaphragm plans;
  - shear wall or frame elevations or a schedule;
  - the foundation plan;
  - typical lateral details: diaphragm nailing or deck attachment,
    collectors, hold-downs, anchorage.
- **For a full review:**
  - the complete structural set;
  - the seismic and lateral calcs (base shear, distribution, diaphragm
    classification, drift, ρ, collector forces);
  - the geotechnical report;
  - shop or delegated-design submittals for proprietary items
    (prequalified moment connections, BRBs, hold-down systems).
- **Helpful:**
  - the gravity load path review (`gravity-load-path-qaqc`) for the same
    project;
  - the general notes review (`general-notes-qaqc`).

## Reference files

Read `reference/load_path_methodology.md` first. Then read the files that
match the systems found:

- `reference/load_path_methodology.md`: the tracing method, the "contact
  is not proof of a lateral connection" rule, finding types, wind, and
  existing buildings.
- `reference/seismic_design_basis.md`: ground motion, SDC, systems and
  R/Ω₀/C_d, combinations of systems, irregularities, ρ, procedure, base
  shear, drift, separation, and load combinations. It includes the
  general-notes seismic block checklist.
- `reference/diaphragms_and_collectors.md`: F_px, flexible / rigid /
  semirigid, torsion, chords, collectors with overstrength, wall anchorage,
  and subdiaphragms.
- `reference/wood.md`: WSP diaphragms and shear walls, hold-downs, openings
  methods, the two-story link-by-link chain, ledgers and cross-grain rules,
  cripple walls, and mid-rise reference gaps.
- `reference/steel.md`: SMF/IMF/OMF, SCBF/OCBF/EBF/BRBF, plate shear walls,
  connections, protected zones, and the braced-frame load path.
- `reference/concrete.md`: ACI 318-19 Chapter 18 (materials, confinement,
  SMF beams, columns and joints, special walls, boundary elements, coupling
  beams, splices, §18.14) and non-ductile existing concrete.
- `reference/masonry.md`: special reinforced masonry walls, ASCE 7-22 §14.4
  changes, prescriptive reinforcement, URM, and infill.
- `reference/foundations_and_geotechnical.md`: the end of the path,
  anchorage, overturning and sliding, geotech report requirements,
  liquefaction (§12.13.9), PGA_M, and retaining walls.
- `reference/nonstructural_and_nonbuilding.md`: the Chapter 13 F_p,
  anchorage of equipment and components, suspended ceilings, partitions,
  elevators and platform lifts, and Chapter 15 nonbuilding structures and
  their interface with the building.
- `reference/existing_buildings.md`: the existing building code path
  (IEBC / CEBC), lateral evaluation triggers for alterations, repairs,
  additions, and changes of occupancy, and new work that touches an
  existing lateral path.
- `reference/master_template.docx`: the report template.

If the set shows a system or condition these files don't cover, don't force
it into the nearest category. Examples: wind-governed design, a mid-rise
wood rod tie-down system, a podium transfer slab, composite systems,
seismic isolation, or nonlinear response history. Flag it as a **reference
gap** so the references can grow from real projects.

## Step 1: System identification and design basis

Record, per `load_path_methodology.md` Step 1:

- the lateral system in **each direction**, with its Table 12.2-1 row;
- the full seismic design basis from the general notes and calcs;
- the diaphragm type at each level and its classification;
- irregularities;
- the foundation type;
- supported heavy components.

Check the basis for internal consistency and code permission using the
general-notes checklist in `seismic_design_basis.md`.

## Step 2: Trace the typical line of resistance in full, per direction

For each principal direction, pick the representative line of resistance
and trace it link by link: load into the diaphragm (including out-of-plane
wall anchorage), diaphragm and chords, collector into the vertical element,
down each story, the overturning tension and compression path, base
anchorage, foundation, and soil. **Name the mechanism and force direction
at every junction.** This trace gets the most detail in the report.

## Step 3: Trace every atypical condition individually

Compare all other lines, levels, and diaphragm zones against the typical
trace. Individually trace anything that changes the path:

- in-plane or out-of-plane discontinuities and transfers;
- re-entrant corners and openings;
- stepped diaphragms;
- a different system or material on a line;
- open-front or cantilever diaphragms;
- gravity elements and infill that could be engaged;
- heavy components;
- different foundation conditions.

Lines that match the typical condition are noted as matching, not
re-traced.

## Step 4: Verify mechanism, detailing level, and force basis

At every junction:

- Confirm the drawings show the **material-appropriate mechanism**.
- Confirm the **detailing matches the system level claimed** (special /
  intermediate / ordinary).
- Where the code sets a force level for the link (collectors and their
  connections with Ω₀, elements supporting discontinuities, wall anchorage
  F_p, diaphragm F_px and transfer forces), confirm the calcs or notes
  **state** that basis.
- Use project-specific details over typical details.

## Step 5: Producing the report

Build the Word report from `reference/master_template.docx`, with this
structure:

1. **Cover / title page:** project identification.
2. **Executive Summary:**
   - the systems in each direction;
   - the SDC;
   - the number of lines traced;
   - headline findings, grouped by type.
3. **Scope & Limitations:**
   - lateral load path and seismic basis only;
   - the code editions reviewed against, and, for existing buildings, the
     existing building code path;
   - no calculations or capacity checks;
   - documents not available;
   - wind basis not independently reviewed, unless covered;
   - "(verify)"-level items listed as confirmation requests.
4. **System Identification & Design Basis:** Step 1, including a table of
   the stated vs. expected basis values (SDC, R, Ω₀, C_d, ρ, procedure,
   drift limit, diaphragm classification).
5. **Load Path Trace:**
   - the typical line in each direction, traced link by link;
   - then each atypical condition, individually traced.

   Each link names the element, the mechanism, and the drawing reference.
6. **Findings:** numbered, each tagged with its type (broken/unconfirmed
   path, design-basis inconsistency, detailing non-conformance, reference
   gap), the location and sheet reference, the governing code section, and
   a recommended action.
7. **Appendix:**
   - the details and schedules relied on;
   - typical details used where no project-specific detail exists;
   - "(verify)" items needing confirmation against SDPWS, AISC, TMS, or
     IBC/CBC.

Deliver the finished report via SendUserFile, and save it to the user's
connected folder if one is available.
