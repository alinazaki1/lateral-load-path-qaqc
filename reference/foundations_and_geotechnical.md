# Foundations and Geotechnical Hazards — Lateral Load Path Reference

This file covers the end of the lateral trace: how base shear and
overturning get into the foundation and soil, and the earthquake-induced
geotechnical hazards that can defeat that last link (fault rupture,
liquefaction and lateral spreading, landslides, and seismic pressure on
retaining walls). Read it when the trace reaches the foundation, when
reviewing the geotechnical report against the structural drawings, or
when the site is near a fault, a slope, or on potentially liquefiable soil.
Written to ASCE 7-22. Use the edition the project's jurisdiction adopts
(see SKILL.md). ASCE 7-22 items below are confirmed, and IBC/CBC,
California statute, and practice items carry a "(verify: …)" tag.

## Where the lateral load path ends

The lateral trace terminates at the foundation and the soil. Every force
traced down through diaphragms, collectors, and vertical elements (see
`load_path_methodology.md` and `diaphragms_and_collectors.md`) has to
leave the structure here, so confirm each of these:

- **Base shear transfer.** Shear in each vertical element gets into the
  foundation through a real mechanism: anchor bolts, dowels, or embedded
  plates, sized and spaced for the element's shear (verify: material
  chapters — see `wood.md`, `steel.md`, `concrete.md`, `masonry.md`).
- **Overturning.** The foundation under each shear wall or frame resists
  the overturning couple: uplift at one end (hold-downs, anchor rods,
  dead load, pile tension) and added compression at the other (bearing or
  pile compression) (verify: ASCE 7-22 §12.13).
- **Sliding.** The foundation resists base shear by friction and passive
  pressure, using the values the geotechnical report gives (verify:
  ASCE 7-22 §12.13 / practice).
- **Footing interconnection.** Footings are tied together where required
  so they don't move apart during shaking (verify: ASCE 7-22 §12.13). On
  liquefiable sites, the tie requirements of §12.13.9.2.1.1 apply (see
  below; confirmed).
- **Geotech report reflected.** Bearing, friction, passive pressure,
  wall pressures, and hazard mitigation in the structural drawings and
  calcs match the geotechnical report's recommendations.

### What to check on the drawings / calcs

- Every vertical element of the SFRS has a shown anchorage detail into
  its foundation; no element "ends in air" at the foundation plan.
- Overturning uplift and compression at each SFRS element are resolved
  into a foundation element that is drawn and sized (verify: ASCE 7-22
  §12.13).
- The sliding check uses the report's friction coefficient and passive
  pressure, not an assumed value (verify: practice).
- Footing ties or grade beams are shown where required (verify: ASCE 7-22
  §12.13), and per §12.13.9.2.1.1 on liquefiable sites.
- The soil values in the general notes match the geotech report.

## Geotechnical report requirements (ASCE 7-22 §11.8.2, §11.8.3)

The report is the source of every soil value and hazard conclusion the
structure relies on, so its presence and completeness are the first
check at the foundation.

### §11.8.2 — all structures in SDC C–F

- **Required for** any structure assigned to **SDC C, D, E, or F**.
- **Must evaluate:**
  - slope instability;
  - liquefaction;
  - total and differential settlement;
  - surface displacement from faulting, or from seismically induced
    lateral spreading or lateral flow.
- **Must recommend** mitigation measures for the hazards found.
- **Exception:** the AHJ may accept prior evaluations of nearby sites with
  similar soil conditions.

### §11.8.3 — additional items for SDC D–F

1. **Dynamic seismic lateral earth pressures** on basement and retaining
   walls, from **design earthquake** motions.
2. **Liquefaction, permanent ground displacement, and strength loss**,
   evaluated at the **MCE_G peak ground acceleration (PGA_M)**, with an
   earthquake magnitude and source characteristics consistent with it
   (see the PGA_M section below).
3. **The consequences:**
   - settlement;
   - lateral soil movement and lateral soil loads on foundations;
   - loss of bearing and lateral resistance;
   - **pile downdrag**;
   - increased lateral pressure on walls;
   - **flotation of buried structures**.
4. **Mitigation measures:** selection of foundation type and depth,
   selection of structural system, and ground improvement.

**IBC/CBC tie-in.** In SDC D–F, the report includes dynamic seismic
lateral earth pressures on foundation and retaining walls supporting more
than **6 ft of backfill** (verify: IBC/CBC §1803.5.12).

**California mapped hazard zones.** The State maps Seismic Hazard Zones for
liquefaction and earthquake-induced landslides; sites inside a zone need a
site-specific investigation before permitting, following CGS Special
Publication 117A (verify: California Seismic Hazards Mapping Act, 1990).

### What to check on the drawings / calcs

- A geotech report exists for any SDC C–F structure. A missing report is
  a finding.
- It addresses all four §11.8.2 hazards (slope, liquefaction, settlement,
  surface displacement), even if only to rule them out.
- For SDC D–F it also gives dynamic wall pressures, liquefaction at PGA_M
  with the magnitude stated, the consequences list, and mitigation.
- The report's date and code basis are compatible with the project's
  ASCE 7-22 design basis (see PGA_M below).
- In California: the site's Seismic Hazard Zone status (liquefaction,
  landslide) is stated (verify: California SHMA).

## Fault rupture

### Behavior

- In **shallow earthquakes** the rupture can reach the **ground surface**,
  with **lateral offsets of up to several feet**. How much the surface
  deforms depends on the **fault type** and the **depth and nature of the
  surface soils**.
- **Strike-slip** faults move horizontally. **Normal** and
  **reverse/thrust** faults add **vertical offset**, which matters for
  foundations and for gravity-flow lines.
- A rupture crossing a footprint can **tear apart light buildings**. Under
  **heavy buildings** (e.g. multistory concrete) it has been observed to
  **deflect around the footprint**, because the building's weight raises
  the confining pressure beneath it. This is observed behavior, **not a
  design basis**.
- Major earthquakes can also cause **regional ground subsidence** over
  large areas.

### ASCE 7-22 §11.8.1 — siting in SDC E/F

A structure in **SDC E or F** shall not be located where a known potential
exists for an active fault to cause surface rupture at the structure. Put
simply: **it can't be on a fault.** This is a **siting prohibition, not a
design case** — no foundation design satisfies it.

### California: Alquist-Priolo Earthquake Fault Zoning Act

(verify: Alquist-Priolo Act, 1972)

- Inside a mapped **Earthquake Fault Zone**, a **fault investigation** is
  required before building structures for human occupancy.
- Such structures can't be placed **across an active fault trace**; a
  **setback** is required, commonly **50 ft** unless the study justifies
  otherwise.

### Pipelines and lifelines crossing a fault (brief)

Surface rupture is especially damaging to lifelines: buried gas and liquid
pipelines, roads and railroads, and transmission and communication towers.
The design parameters are the direction and amount of fault movement, the
pipe's orientation to the fault, the support type (above ground) or
backfill (buried), and the pipe size and material.

- **Buried pipe crossing a strike-slip fault at nearly 90°:** the offset
  puts the pipe in high shear and can break it. Mitigate with a **widened
  trench** backfilled with **loose granular material** through the
  crossing zone so the pipe moves through the soil instead of being
  sheared by it.
- **Above-ground pipe crossing at nearly 90°:** with supports kept **as
  far from the fault line as possible**, damage is unlikely; moderate
  movement causes bending, which **sliding supports** greatly reduce.
- **Above-ground pipe nearly parallel to a strike-slip fault:** slip
  mostly stretches or shortens the pipe. Depending on the sense of slip
  and the pipe's skew:

  | Fault slip | Pipe skew | Result |
  |---|---|---|
  | Left-lateral | One skew | **Compression.** Even small offsets can **buckle** the pipe. |
  | Left-lateral | Opposite skew | **Tension.** Can **yield** the pipe or **fail a joint**. |
  | Right-lateral | Either skew | Same two outcomes, reversed. |

- **Practice** (verify: ALA lifeline guidelines): orient **steel** pipe so
  fault movement puts it in **tension** (continuous welded steel stretches
  ductilely but buckles in compression); use **flexible or ball-joint
  couplings** near the fault and **shutoff valves** on both sides; avoid
  brittle materials (cast iron, unreinforced concrete) across the fault.

Lifelines are usually civil/MEP scope; see also
`nonstructural_and_nonbuilding.md`.

### What to check on the drawings / calcs

- For SDC E/F, the geotech report states that no known active fault
  rupture potential exists at the structure (§11.8.1). If it doesn't say,
  that is a finding.
- In California, the Alquist-Priolo zone status is stated; where inside a
  zone, the fault study and setback are documented and the footprint
  respects the setback (verify: Alquist-Priolo Act).
- Where normal or reverse faulting is near the site, vertical offset is
  addressed for foundations and gravity-flow lines.
- Utilities crossing a fault or liquefiable zone have flexible
  connections at the building entry (verify: practice; flag even if
  outside structural scope).

## Liquefaction

### Mechanism

- **Liquefaction** is a sudden, temporary loss of soil shear strength and
  stiffness caused by shaking. It occurs in **saturated sandy soils**:
  shaking raises the **pore water pressure**, which pushes the grains
  apart so they slide past one another. Shear strength, and with it
  bearing capacity, drops; near zero, the soil **flows like a fluid**.
- **Results:** loss of bearing capacity, large settlement, **lateral
  spreading**, surface cracking, and **sand boils** (ejected water and
  fine grains).

### Susceptibility

- **Loose sands.**
- **Uniformly graded sands.** Same-size grains leave large voids the
  grains can collapse into. A well-graded soil has small grains filling
  the gaps, so it is denser and more stable.
- **Sands shallower than about 50 ft.** This is a common screening depth,
  not a hard limit; deeper layers are evaluated case by case (verify:
  practice).
- **Young deposits** (Holocene) — they tend to be loose and are the most
  susceptible.
- **Shallow groundwater** is essential. Dry sand doesn't liquefy, though
  it can still densify and settle (verify: practice).
- **Not only clean sand:** low-plasticity silts and some gravels can also
  liquefy (verify: practice).

### Effect on foundations

- **Shallow foundations** (spread footings) are much more vulnerable than
  **deep foundations**, because liquefaction removes their bearing.
- **Deep foundations** (piles, drilled shafts) pass load **through the
  liquefiable layer** to competent soil or rock below — e.g. bypassing
  ~50 ft of loose sand to bear on bedrock. They still lose capacity in
  the liquefied layer and pick up downdrag (see §12.13.9.3 below).
- **Lateral spreading** damages structures both below and above grade.

### Mitigation by ground improvement

- **Densification:** excavate and recompact, or densify in place —
  vibro-compaction, dynamic compaction, stone columns, compaction
  grouting.
- **Solidification:** grouting to cement loose sand together — permeation
  grouting, jet grouting, deep soil mixing.
- **Drainage:** lower groundwater and relieve pore pressure — gravel or
  wick drains.

The core three (compaction, drainage, grouting) are standard; the
specific named methods are practice (verify: practice). The report should
state the chosen method and the **post-improvement verification** criteria
(CPT/SPT targets) (verify: practice).

## PGA_M for the liquefaction evaluation

§11.8.3 item 2 requires liquefaction and strength loss to be evaluated at
**PGA_M**, with a consistent magnitude and source. ASCE 7-22 changed how
PGA_M is obtained.

### ASCE 7-22 rule

- PGA_M is taken **directly** from either:
  1. a **site-specific study** (§11.4.7 / §21.5), or
  2. the **USGS Seismic Design Geodatabase**, which tabulates PGA_M **for
     each site class**, including the intermediate classes **BC, CD, and
     DE**.
- The Chapter 22 maps show **PGA_M for default site conditions**, not a
  rock PGA to be multiplied up. There is **no F_PGA** and no
  PGA_M = F_PGA × PGA equation in 7-22.
- **Site-specific floor (§21.5.3):** a site-specific PGA_M is the lesser
  of the probabilistic and deterministic values, but **not less than 80%**
  of the geodatabase PGA_M for the site class.
- **Default site class (§11.4.3):** where soil properties aren't known,
  values come from the most critical of Site Classes **C, CD, and D**.
- **Consistent magnitude:** the triggering analysis needs a magnitude
  consistent with PGA_M, and the report should state which one it used.
  This is usually the mean or modal magnitude from USGS deaggregation
  (verify: practice).

Site class and the rest of the seismic design basis are covered in
`seismic_design_basis.md`.

### ASCE 7-16 (older projects / existing reports)

Under 7-16, **PGA_M = F_PGA × PGA**, where PGA is the mapped MCE_G value
(rock) and F_PGA is a site coefficient by site class and PGA level
(interpolated; Site Class F needs a site response analysis). Where Site
Class D was the default, F_PGA was not less than **1.2**. Use this only to
read older reports and existing-building work.

**On a 7-22 project, a report showing F_PGA × PGA is a finding:** it was
prepared to ASCE 7-16 and must be updated or reconciled with the 7-22
design basis.

### What to check on the drawings / calcs

- The report's PGA_M comes from the geodatabase for the **correct site
  class** (matching the site class used in the structural seismic design),
  or from a site-specific study meeting the **80% floor** (§21.5.3).
- No F_PGA, and no "rock PGA × site coefficient" step, appears in a report
  supporting a 7-22 design.
- Where site class is defaulted, the most critical of C, CD, and D was
  used (§11.4.3).
- The earthquake magnitude used for triggering is stated.

## Foundations on liquefiable sites (ASCE 7-22 §12.13.9)

This is the structural side of liquefaction: what the drawings must show
once the report finds a problem.

### Applicability

- **Applies** when the report identifies liquefaction, permanent ground
  displacement, or strength loss under **MCE_G** motions.
- The structure must be designed for those effects **and also** for the
  normal seismic loads as if liquefaction did not occur. Two design cases,
  not one.
- **Exception (shallow foundations):** §12.13.9 does not apply if the
  report shows negligible permanent horizontal displacement, no loss of
  bearing or lateral resistance, and differential settlement no more than
  **¼ of the Table 12.13-3 threshold**.
  - The printed text cites "**Table 12.3-3**" here; this is almost
    certainly a misprint for **Table 12.13-3**. Read it as 12.13-3 and
    don't write a finding against a design that does so.
- **Not applicable to flow failure or long-runout landslides.** Where the
  report shows either, the hazard must be **mitigated**; it can't be
  designed for. A structural design that "resists" flow failure is a
  finding.

### Shallow foundations — permitted limits

Shallow foundations are permitted only where **both** limits are met.

**Table 12.13-2 — permanent horizontal ground displacement:**

| Risk Category | Maximum displacement |
|---|---|
| I / II | 18 in. |
| III | 12 in. |
| IV | 4 in. |

**Table 12.13-3 — differential settlement:** limits range from **0.0075L**
(single-story concrete or masonry, RC I/II) down to **0.002L** (RC IV).
Read the specific row for the structure type and RC from the table.

Larger differential settlement is allowed only if the structure is shown to
keep **≥ 67% residual strength** (RC II/III), or to stay within nominal
strength (RC IV).

### Footing ties (§12.13.9.2.1.1)

Where permanent displacement exceeds **3 in.**:

- Ties along each column or wall line are designed for
  **F_tie = 0.5μP_u** in **both tension and compression**, with μ
  defaulting to **0.5**.
- Footings are tied into a **slab on ground ≥ 5 in. thick with
  ρ ≥ 0.0025 each way**, or into a **post-tensioned slab** with
  **≥ 100 psi** effective precompression.

### Mats (§12.13.9.2.1.2)

- **Top and bottom reinforcement both ways**, designed for the
  differential settlement. Alternatively, detail per ACI 318-19
  §18.13.3.1.

### Deep foundations (§12.13.9.3)

- **Downdrag** from seismic settlement is treated and factored as a
  **seismic load**.
- Pile **axial and lateral capacity is reduced** through the liquefied
  layer.
- **Concrete piles** are confinement-detailed (ACI 318-19 §18.13.5.5) to
  **7 × the pile dimension below the deepest liquefiable layer** (see
  `concrete.md`).
- **Where lateral spreading occurs:**
  - piles get a **nonlinear analysis** for the imposed soil displacement;
  - they must keep **≥ 67% of lateral strength**;
  - H-piles and unfilled pipe piles meet the **highly ductile**
    width-thickness limits of AISC 341 (see `steel.md`).
- **Pile cap ties** include the lateral spreading pressures.

### What to check on the drawings / calcs

- Where the report finds liquefaction under MCE_G, the calcs show **both**
  the liquefied case and the non-liquefied seismic case.
- Shallow foundations: the report's permanent displacement is within
  Table 12.13-2 for the RC, and differential settlement within Table
  12.13-3 (or the 67% residual-strength / nominal-strength demonstration
  is provided).
- Where displacement > 3 in.: ties on every column and wall line sized for
  0.5μP_u (tension and compression), and a slab ≥ 5 in. with ρ ≥ 0.0025
  each way (or PT slab ≥ 100 psi) to which footings are tied.
- Mats: top and bottom bars both ways, or ACI 318-19 §18.13.3.1 detailing.
- Piles: downdrag included as a seismic load; reduced capacity through the
  liquefied layer; confinement extends 7× the pile dimension below the
  **deepest** liquefiable layer (compare the pile detail's confinement
  zone to the boring logs / report layer depths).
- Lateral spreading: a nonlinear pile analysis exists, the 67% lateral
  strength criterion is met, steel H/pipe pile sections meet highly
  ductile limits, and pile cap ties carry spreading pressures.
- Ground improvement: method, extent, and verification criteria appear in
  the structural notes or specs (verify: practice).

## Landslides

### Behavior

- Earthquakes trigger **deep** slides (slow or rapid) and **shallow,
  fast-moving** slides.
- Expect them on coastal bluffs, mountain and hillside slopes, and rock
  slopes shaken at **Modified Mercalli Intensity VI or higher**.
- **Pseudo-static mechanism:**
  - horizontal inertia **a_h(W/g)** pushes the mass outward along the
    failure surface, reducing stability;
  - upward vertical acceleration **a_v(W/g)** offsets part of the weight,
    reducing the normal force and therefore the friction on the failure
    surface, reducing stability further.

### Analysis (practice)

(verify: practice / CGS SP 117A)

- The slope is analyzed with a **seismic coefficient k_h**, usually a
  fraction of PGA. In California this follows CGS SP 117A and the SCEC
  guidelines.
- Target **FS ≥ 1.0 to 1.1** under seismic load (about 1.5 static).
- Where pseudo-static fails, a **displacement (Newmark) analysis**
  estimates how far the slope moves.

### ASCE 7-22 tie-in

- §11.8.2 requires the report to evaluate **slope instability**.
- §12.13.9: **long-runout landslides must be mitigated**, not designed for.

### Mitigation

- **Regrade:** flatten the slope or unload the top.
- **Reinforce the soil** (e.g. soil nails). Nails must extend **past the
  failure surface** and anchor into stable soil beyond it; a nail that
  stops inside the sliding mass does nothing.
- **Retaining structures** (e.g. a cantilever wall). The wall and footing
  must sit **below and through** the failure surface, so the wall isn't
  carried along with the slide.

### What to check on the drawings / calcs

- Where the building is near a slope or bluff, the report gives the
  seismic slope stability result and any setback or mitigation.
- Soil nails or tiebacks shown on the drawings extend beyond the failure
  surface the report identifies.
- Retaining walls used for slope mitigation have footings keyed below the
  failure surface.
- The structural setback from the slope matches the report.

## Cantilever retaining walls

### Static design

- Materials: concrete, masonry, or steel and timber.
- The wall resists **active earth pressure**, distributed like
  hydrostatic pressure (triangular, zero at top, maximum at base). The
  static resultant **P_a** acts at **H/3** above the base.
- **Stability checks:** overturning, sliding, and soil bearing (on a
  shallow foundation). The **stem and footing** are then designed
  structurally as reinforced concrete (or masonry) members — see
  `concrete.md` and `masonry.md`.

### Seismic pressure

- An earthquake adds a **seismic increment** on top of the static active
  pressure. The soil wedge behind the wall gets a horizontal inertia force
  **a_h(W/g)** and a vertical force **a_v(W/g)**, in addition to its weight
  W and the static P_a.
- **ASCE 7-22 §11.8.3 item 1** (SDC D–F): the geotech report must provide
  the dynamic seismic lateral earth pressures on basement and retaining
  walls, for **design earthquake** motions.
- **Mononobe-Okabe (M-O):** gives the seismic active coefficient **K_AE**
  for cohesionless soils. Classic M-O puts the total thrust at H/3
  (verify: practice).
- **Point of application of the increment** (verify: practice):
  - the Seed-Whitman split places the seismic **increment** at about
    **0.6H**; the increment's resultant is commonly taken between **H/2
    and 2H/3**;
  - where the report simplifies the increment to an **equivalent uniform
    pressure**, its resultant acts at **H/2**.
- **Newer practice** (verify: practice): more recent research (e.g. Al Atik
  & Sitar, 2010) found M-O **overestimates** the increment for yielding
  cantilever walls. Many current reports give **smaller** increments,
  sometimes as an **inverted triangle** or **uniform** pressure.
- **Restrained walls** (basement walls braced by floors) are a different
  case and get **higher** pressures (e.g. the Wood method). Don't design
  them with yielding-wall active pressures (verify: practice).
- **Rule:** use the **pressure, distribution, and point of application the
  geotech report gives**, and confirm the structural calc matches it.

### Stability factors of safety and the 0.7E basis

(verify: IBC/CBC §1807.2.3 — confirm current wording)

- **FS = resisting moment (or force) ÷ driving moment (or force).**
- **FS ≥ 1.5** against sliding and overturning (static).
- **FS ≥ 1.1** where earthquake loads are included.
- For these stability checks the **IBC §1605 load combinations don't
  apply.** Use:
  - **0.7 × the nominal earthquake load** (converts strength-level E to
    service level so FS is on nominal loads);
  - **1.0 × the other nominal loads** (e.g. soil pressure H);
  - one or more **variable loads set to zero**, whichever governs. A
    surcharge or live load on the heel can *help* resist overturning, so
    removing it can be the worst case.
- **Structural design** of the stem and footing still uses the normal
  §1605 / ASCE 7 strength combinations. The 0.7E / FS approach is for
  stability only.
- **Load factors** (verify: practice): in strength design the seismic
  increment is usually treated as part of **E** (factor 1.0) and the static
  pressure as **H** (factor 1.6). The calcs should state the combination
  used.

### What to check on the drawings / calcs

- For SDC D–F, the report gives dynamic wall pressures (§11.8.3 item 1);
  in IBC/CBC terms, for walls retaining more than 6 ft of backfill
  (verify: IBC/CBC §1803.5.12).
- The seismic increment, its distribution, and its point of application
  in the calc **match the report** (not a default M-O or H/3 assumption
  when the report says otherwise).
- Stability: FS ≥ 1.5 static and ≥ 1.1 seismic for both sliding and
  overturning (verify: IBC/CBC §1807.2.3).
- Stability check uses 0.7E + 1.0H with variable loads zeroed where that
  governs, not the §1605 strength combinations (verify: IBC/CBC
  §1807.2.3).
- Stem and footing strength design uses the strength combinations, with
  the factors on static and seismic pressures stated (verify: practice).
- Basement walls braced by floors are designed for restrained-wall
  pressures, not active pressures (verify: practice).
- Sliding resistance (friction, passive) uses the report's values.

## Common findings

- **No geotech report** for an SDC C–F structure, or a report missing a
  §11.8.2 hazard or a §11.8.3 item (dynamic wall pressures, PGA_M
  evaluation, consequences, mitigation).
- **7-16-style report on a 7-22 project:** PGA_M computed as F_PGA × PGA.
  Report must be updated or reconciled.
- PGA_M taken for a **different site class** than the structural design
  uses, or a site-specific PGA_M **below 80%** of the geodatabase value.
- Liquefaction magnitude not stated.
- SDC E/F structure with **no statement** on fault rupture potential;
  California site with no A-P zone statement (verify: Alquist-Priolo Act).
- Liquefiable site with **only** the liquefied case or **only** the normal
  seismic case designed, not both (§12.13.9).
- Shallow foundations used where report displacement exceeds **Table
  12.13-2** (e.g. > 4 in. for RC IV).
- Displacement > 3 in. but **no footing ties** at 0.5μP_u, or slab thinner
  than 5 in. / ρ below 0.0025 each way.
- Pile **confinement stops at** (or above) the bottom of the liquefiable
  layer instead of extending 7× the pile dimension below the deepest one.
- **Downdrag** omitted, or not factored as seismic load.
- Lateral spreading identified but **no nonlinear pile analysis**.
- Flow failure or long-runout landslide identified but "designed for"
  instead of mitigated.
- Retaining-wall seismic increment applied at a **different height** or
  distribution than the report gives.
- Wall stability checked with **§1605 strength combinations** instead of
  0.7E + 1.0H, or seismic FS below 1.1 (verify: IBC/CBC §1807.2.3).
- **Restrained basement wall** designed with active (yielding-wall)
  pressures (verify: practice).
- Soil nails that **don't extend past** the failure surface; slope wall
  footing not keyed below it.
- Ground improvement called for in the report with **no verification
  criteria** in the structural notes or specs (verify: practice).
- Soil values on the general notes (bearing, friction, passive, wall
  pressures) **don't match** the geotech report.
