# Existing Buildings — Code Path and Lateral Evaluation Triggers

Read this file whenever the project is work on an existing building:
repair, alteration, renovation, addition, or change of occupancy. In these
projects the question usually isn't "does the lateral system meet the new
building code?" It's two others:

1. Does this scope **trigger** a lateral evaluation or upgrade under the
   jurisdiction's existing building code?
2. Does the new work **break or weaken** the existing lateral path?

The documents should answer both. A general note saying "existing
structure not brought up to current code" isn't enough by itself. It
states a conclusion without the compliance path that supports it.

**Verification status.** The existing-building code items here are from
engineering knowledge of the **IEBC (2018/2021/2024)** and the **California
Existing Building Code (CEBC)**. They are tagged "(verify: IEBC)" or
"(verify: CEBC)". Section numbers shift between editions, so confirm them
against the edition the jurisdiction adopts. The ASCE 7 provisions cited
are confirmed against ASCE 7-22, and the same provisions exist in ASCE 7-16.

## 1. Identify the code path

- **Which existing building code applies.**
  - Most US jurisdictions use the IEBC at the edition matching their IBC.
    For example, IBC 2021 pairs with IEBC 2021.
  - California uses the **CEBC** (Title 24, Part 10).
  - Public schools (DSA) and hospitals (HCAI) in California have their
    own provisions (verify: CEBC).
- **Which compliance method the design uses.** The IEBC offers three, and
  the documents should state one (verify: IEBC):
  1. **Prescriptive** (IEBC Chapter 5);
  2. **Work area** (Chapters 6–12): repairs, alteration Levels 1, 2, and
     3, change of occupancy, additions, and historic buildings;
  3. **Performance** (Chapter 13).

  The method decides which triggers apply.
- **Classify the work.** The common categories are:
  - **repair** of damage;
  - **alteration** (for the work area method, Level 1, 2, or 3 depending
    on the extent of reconfiguration and the work area);
  - **addition**;
  - **change of occupancy**, including a change to a higher risk
    category.

  A single project can include more than one.

## 2. Lateral evaluation triggers

All of the following are verify: IEBC / CEBC. Exact wording and section
numbers vary by edition.

### Alterations

- **The 10% rule.** An alteration that increases the **seismic or wind
  demand-capacity ratio** of any existing lateral load-carrying element by
  **more than 10%** generally requires that element, or the structure, to
  meet the lateral requirements, typically at reduced seismic forces.
  Common ways an alteration does this:
  - added mass, such as rooftop equipment, new heavy floor finishes or
    topping, or a mezzanine;
  - removing or opening up existing shear walls or braces;
  - creating a new irregularity.

  An alteration that **decreases the lateral capacity** of an existing
  element triggers the same requirement.
- **Prohibited irregularities.** An alteration can't create a structural
  irregularity that the code prohibits for the SDC, unless the structure
  is shown to comply.
- **Extensive alterations (Level 3, roughly > 50% of the building area).**
  These can trigger specific seismic upgrades even without a demand
  increase. Examples:
  - wall anchorage for concrete and masonry walls;
  - URM parapet bracing;
  - bracing of URM walls.

  These typically apply in SDC C and above, or in moderate-to-high
  seismic regions.
- **Substantial structural alteration.** Where more than about 30% of the
  floor and roof area has been structurally altered within a period of
  years, a full lateral evaluation (and retrofit if needed) is triggered.

### Repairs

- **Substantial structural damage** (to the lateral system) triggers an
  evaluation. Where the building fails it, the damaged building is
  rehabilitated, typically to reduced seismic forces.
- **Less than substantial damage** may be repaired to pre-damage
  condition.
- A crawl-space floor repair like the one in the example report is
  normally below these thresholds. Even so, the work must not reduce the
  lateral capacity of the existing elements it touches.

### Additions

- A **structurally independent** addition (separated by a seismic joint)
  is designed as new construction. The existing building is checked only
  for any effect the addition has on it.
- A **structurally dependent** addition can increase demand on existing
  lateral elements. The 10% rule applies to them, and the addition must
  have its own complete load path.

### Change of occupancy

- A change to a **higher risk category** generally requires the whole
  building to meet the seismic requirements for the new risk category,
  typically at reduced seismic forces.
- Smaller changes may be exempt (verify: IEBC).

### Reduced seismic forces and evaluation standards

- Where an evaluation or retrofit is triggered, the existing building code
  usually allows **reduced seismic forces**: about 75% of the new-building
  forces, or **ASCE 41** with the edition's specified performance objective
  (verify: IEBC / CEBC).
- For URM bearing-wall buildings, the existing building code appendix
  (IEBC / CEBC Appendix A1) gives special procedures. See `masonry.md`.
- Other building types have their own appendix chapters (verify: IEBC):
  - wood cripple walls and sill anchorage;
  - concrete tilt-up wall anchorage;
  - soft, weak, or open-front wood stories.

## 3. New work that touches the existing lateral path

Even when no upgrade is triggered, new work must not break the existing
path. Check each of these:

- **Diaphragm sheathing removed and replaced** (floor leveling, re-roofing,
  new openings).
  - The replacement panels need a specified thickness and grade, edge,
    boundary, and field nailing, and blocking where the existing diaphragm
    is blocked.
  - Panels at walls must restore the **boundary nailing** into the member
    that carries shear into the wall.
  - "Remove and replace sheathing" with no nailing specification is an
    unconfirmed link in the lateral path.
- **New openings** in existing shear walls, brick walls, or diaphragms.
  - They reduce capacity.
  - Look for a calc showing the reduction is within the trigger, or for
    new chords and collectors around the opening.
- **Added mass:**
  - rooftop units and solar;
  - new partitions or finishes on a light roof;
  - added stories or mezzanines.

  Look for the demand-increase check.
- **New members bearing on existing walls or piers** (beams, brackets,
  ledgers).
  - Each new beam, girder, or truss needs a **positive connection to its
    supports** for a horizontal force parallel to the member, at least 5%
    of the D+L reaction (ASCE 7-22 and 7-16 §12.1.4).
  - Anchors into existing masonry or concrete need a stated design basis,
    such as an anchor type and capacity source.
  - In URM, adhesive anchors are often subject to **field testing**
    requirements (verify: IEBC/CEBC Appendix A1).
- **New piers, posts, or columns** in crawl spaces and basements.
  - Even when they are gravity-only, they need lateral restraint at the
    top and base consistent with the SDC.
  - New masonry piers in the higher SDCs need the detailing the masonry
    standard requires (see `masonry.md`, verify: TMS 402).
- **Nonstructural components added or replaced**: ceilings, partitions,
  lifts, equipment. These follow the current Chapter 13 requirements for
  the building's SDC, even when the structure is existing. See
  `nonstructural_and_nonbuilding.md`. A component that needs an SDC
  requires the documents to **state** one.

## 4. What to check on the drawings / calcs

- The general notes state:
  - the **existing building code edition**;
  - the **compliance method**;
  - the **classification of the work** (repair, alteration level,
    addition, change of occupancy).
- The documents give a basis for whether a lateral evaluation is
  triggered. Either:
  - a short statement or calc that demand isn't increased beyond the
    trigger and capacity isn't reduced; or
  - the evaluation or retrofit itself.

  "Not brought up to current code" alone is a finding: a design-basis
  inconsistency or omission.
- The seismic design parameters (risk category, site class, S_DS, S_D1,
  SDC) are stated wherever any new element or component depends on them.
  Examples:
  - the architectural notes require ceilings "per SDC D";
  - equipment anchorage;
  - new piers.

  An architectural SDC with no structural basis is a design-basis
  inconsistency.
- Every link of the existing lateral path that the new work touches is
  detailed, especially:
  - replaced sheathing;
  - new connections to existing walls;
  - new openings.
- Existing-condition information (as-builts, field verification notes,
  testing) is enough to support any reliance on existing elements.
- Where an upgrade is triggered, the retrofit has a complete load path:
  new elements to the foundation, and a collection path from the existing
  diaphragm.

## 5. Common findings

- "Existing structure not brought up to current code" with no compliance
  method, trigger evaluation, or seismic parameters.
- The architectural or MEP notes cite an SDC that appears nowhere on the
  structural sheets.
- Diaphragm sheathing replaced with no sheathing or nailing
  specification. The architectural and structural sheets each defer to
  the other.
- New beams shimmed onto new piers with no positive connection (§12.1.4),
  and piers with no dowel to their bases.
- Adhesive anchors into existing brick with no design basis or testing
  requirement.
- Added rooftop equipment or mass with no demand-increase check.
- New openings in existing lateral walls with no capacity check.
- An existing URM, soft-story wood, or non-ductile concrete building type
  that goes unremarked. Recommend owner awareness even when no upgrade is
  triggered.
