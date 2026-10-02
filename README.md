# lateral-load-path-qaqc

## What it does

This Claude skill traces the lateral (seismic) load path through a
structural drawing set the way a structural engineer would. The trace
follows each link in order:

1. where the load enters each diaphragm, including out-of-plane wall
   anchorage;
2. across the diaphragm to its chords;
3. into collectors and drag struts;
4. down every shear wall, braced frame, or moment frame, story by story;
5. through the hold-downs and base anchorage;
6. through the foundation and into the soil.

At every junction it checks for the actual, material-appropriate
mechanism, and the direction of force it resists. It doesn't assume a
path is continuous just because two members touch or are fastened
together. A ledger bolted to a masonry wall carries gravity, but it isn't
wall anchorage. A shear tab isn't a collector splice.

It also checks the seismic **design basis**:

- risk category, SDC, and system;
- R / Ω₀ / C_d and ρ;
- irregularities, procedure, and drift;
- diaphragm classification;
- collector overstrength.

It checks these against **ASCE 7-22**, and checks the detailing against
the level of system claimed (special / intermediate / ordinary). It covers
wood, steel, concrete, and masonry, as well as:

- diaphragms;
- nonstructural anchorage;
- nonbuilding structures;
- geotechnical and foundation items.

The output is a Word QAQC report: the typical line of resistance traced in
full in each direction, every atypical condition traced individually, and
typed findings.

**This is V3 of a skill family.** It is the lateral companion to
[`gravity-load-path-qaqc`](https://github.com/alinazaki1/gravity-load-path-qaqc)
(V2). It doesn't calculate forces or check capacities. It establishes and
QA/QCs what the lateral load path *is*, and flags anywhere the documents
don't support it.

The tool works as a reasoning workflow inside Claude. It relies on model
judgment guided by the reference material in `reference/`, not mechanical
pattern-matching.

## Status: v1 draft, one real-set test

The skill is built from my own engineering judgment and dictated domain
knowledge across four material systems and the ASCE 7 seismic provisions.
It has been run once against a real public bid-document set: the same
crawl-space renovation set used for the V2 gravity example (see
`examples/`). That test exercised the design-basis checks, new-work
connections into an existing lateral path, masonry pier detailing,
nonstructural anchorage, and existing-building handling. It did **not**
exercise a complete new lateral system (shear walls, frames, collectors,
hold-downs), so a second test on a new-construction set is still needed.
If you try it, I'd like to hear what it catches and what it misses.

How the reference material has been checked:

- **Code editions follow the project's jurisdiction.**
  - The references are written to **ASCE 7-22** (2025 CBC / 2024 IBC), and
    its provisions were checked against the standard's text.
  - On a project under an earlier edition, for example IBC 2021 / ASCE
    7-16, the skill reviews against that edition. It notes where 7-22
    differs instead of writing findings against it.
  - ASCE 7-16 forms appear as labeled notes in the references.
- **ACI 318-19** provisions were checked against the code text. A re-check
  against ACI CODE-318-25 is planned for when it's adopted.
- **AWC SDPWS-21 / NDS, AISC 341 / 358, TMS 402 / 602, IBC/CBC, IEBC/CEBC, and
  ASME A18.1** items
  are from engineering knowledge and are tagged `(verify: …)` in the
  references. The skill treats them as "confirm" prompts, not hard
  findings.

Known gaps, which the skill flags as reference gaps rather than guessing:

- **Wind:** the tracing method applies, but wind load determination
  (ASCE 7-22 Ch. 26–31) isn't covered.
- **Mid-rise wood:** rod tie-down systems and shrinkage, compression
  posts, podium transfer, and non-stacking walls.
- **Other systems:** composite steel-concrete systems, seismic isolation
  and damping, and nonlinear analysis.

Contributors are encouraged to report gaps, false positives, missed
inconsistencies, and format improvements through GitHub issues or pull
requests.

## Using this skill

For Claude Code or compatible clients, copy the `lateral-load-path-qaqc/`
folder into `.claude/skills/`. Claude detects it automatically. For
packaged installations, use the `skill-creator` tool to turn the folder
into a `.skill` file that works in Cowork sessions.

## Repo contents

- `SKILL.md`: the skill definition and five-step review workflow.
- `reference/load_path_methodology.md`: the lateral tracing method and the
  "contact is not proof of a lateral connection" rule.
- `reference/seismic_design_basis.md`: ASCE 7-22 design basis checks.
- `reference/diaphragms_and_collectors.md`: diaphragms, chords,
  collectors, torsion, and wall anchorage.
- `reference/wood.md`, `steel.md`, `concrete.md`, `masonry.md`:
  material-specific lateral systems, detailing, and connection mechanisms.
- `reference/foundations_and_geotechnical.md`: anchorage, foundations,
  liquefiable sites, and retaining walls.
- `reference/nonstructural_and_nonbuilding.md`: ASCE 7-22 Chapters 13 and
  15, including ceilings, partitions, and elevators/lifts.
- `reference/existing_buildings.md`: the existing building code path and
  lateral evaluation triggers.
- `reference/master_template.docx`: the report template.
- `examples/`: a redacted example report from the first real-set test,
  with a disclaimer describing what was redacted and what the test did
  and didn't exercise.

## Companion skills

- [`gravity-load-path-qaqc`](https://github.com/alinazaki1/gravity-load-path-qaqc)
  traces the gravity load path.
- [`general-notes-qaqc`](https://github.com/alinazaki1/general-notes-qaqc)
  reviews the General Notes sheet(s).

All of them are personal, noncommercial projects. I built them from my own
engineering judgment, on my own time, and I'm sharing them for other
engineers to try, break, and improve.

## Disclaimer

This skill helps a qualified engineer with QA/QC. It doesn't replace
engineering judgment, the engineer of record's responsibility, or plan
check. Verify every finding against the governing code and the project
documents.

## License

PolyForm Noncommercial License 1.0.0 allows free noncommercial use,
modification, and sharing. Commercial use requires the licensor's
permission. See `LICENSE.md`.
