# About the example report

`Example_Lateral_Load_Path_QAQC_Review.docx` is a worked sample output, not
a live drawing set. It comes from this skill's first real test: an actual
public bid-document set for an institutional renovation project. It is the
same set used for the V2 gravity skill's example, so the two reports can be
read side by side.

The drawings belong to a real project, prepared by real professionals who
never agreed to have their work critiqued in public. Publishing their
project name, number, or location next to a QA/QC review would be an
unwanted public critique of their work. That isn't the point of this
example.

**What was changed:**

- The project name, location, project number, and bid date are removed or
  replaced with `[redacted]` placeholders.
- The design firms (architect and structural engineer) are not named.

**What was not changed:** the substance is as found:

- the systems identified;
- the trace;
- every finding.

The drawing PDF itself is not included in this repo.

## What this test exercised, and what it didn't

The set is a crawl-space floor repair in an existing building. Its general
notes say the structure is not being brought up to current code for wind
or seismic loads. So the test mainly exercised:

- system identification and the design-basis checks, which caught a
  structural/architectural SDC inconsistency;
- the "contact is not proof of connection" rule on new work, including
  diaphragm sheathing replacement and positive connection to supports;
- masonry pier detailing;
- nonstructural anchorage;
- existing-building handling.

It did **not** exercise a complete new lateral system: no shear wall,
braced frame, moment frame, collector, or hold-down design. A second test
on a new-construction set is still needed.

The test also exposed gaps in the skill's references, listed as Finding 7
in the report. The report is kept as it was produced, but three of the
gaps have since been closed:

- **Code edition (closed).** The project is outside California and uses
  IBC 2021 / ASCE 7-16, while the references were written to ASCE 7-22.
  The skill now reviews against the editions the project's jurisdiction
  adopts.
- **Existing buildings (closed).** IEBC alteration triggers for lateral
  systems weren't covered. They are now in `reference/existing_buildings.md`.
- **Nonstructural components (closed).** Suspended ceilings (ASTM E580),
  partitions, and elevators and lifts weren't covered. They are now in
  `reference/nonstructural_and_nonbuilding.md`.
- **Wind (still open).** The wind basis is not covered.

If you want to see the skill work on a real project, run it against your
own drawing set. This example shows the output format and the kind of thing
the skill catches; it doesn't replace that.
