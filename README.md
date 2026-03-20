# The Ashley Nate Memorial Project (ANMP)

**A Comprehensive Civic Transparency Initiative for Canaan, New Hampshire**

Author: Charles W. Dowd Jr.  
Organization: [OpenSourcePatents](https://github.com/OpenSourcePatents)  
License: Apache License 2.0

-----

## What Is ANMP?

The Ashley Nate Memorial Project is an open-source civic transparency platform that digitizes, automates, and democratizes access to public information across every domain of municipal government in Canaan, New Hampshire.

Everything ANMP tracks is already public under New Hampshire law. The project doesn’t create new rights — it builds the infrastructure to exercise the ones that already exist. Paper annual reports become interactive dashboards. Manual records requests become automated pipelines. Informal complaints become tracked, timestamped, permanent records.

-----

## Project Structure

```
ANMP/
├── README.md
├── LICENSE                          # Apache License 2.0
│
├── concept-papers/
│   ├── ANMP_Master_Concept_Paper.md
│   ├── ANMP_Road_Watch_Concept_Paper.md
│   ├── ANMP_Budget_Watch_Concept_Paper.md
│   ├── ANMP_Police_Transparency_Concept_Paper.md
│   ├── VIGIL_Concept_Paper.md
│   ├── AEGIS_Concept_Paper.md
│   └── SENTINEL_Concept_Paper.md
│
├── demos/
│   ├── canaan-road-watch/
│   │   ├── canaan-roads.jsx         # Interactive Road Watch prototype
│   │   └── README.md
│   └── canaan-budget-watch/
│       ├── canaan-budget.jsx        # Interactive Budget Watch prototype
│       └── README.md
│
├── docs/
│   ├── legal-foundation.md          # RSA 91-A, RSA 106-L, RSA 105:13-d reference
│   ├── technical-architecture.md    # Stack overview: Next.js, Supabase, Resend, etc.
│   ├── replication-guide.md         # How to deploy ANMP for your NH municipality
│   └── data-sources.md              # Where every data point comes from
│
└── assets/
    └── (diagrams, screenshots, logos as needed)
```

-----

## Modules

### Core Modules (Concept Papers Complete, Prototypes Built)

|Module                 |What It Does                                                                                                                                                                                          |Demo          |
|-----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------|
|**Canaan Road Watch**  |Citizen road condition monitoring with GPS reporting, repair tracking, citizen verification of repair quality, and a performance-to-funding accountability framework for the Road Agent.              |[Live Demo](#)|
|**Canaan Budget Watch**|Interactive digital budget — department allocations, employee salaries, effective hourly rates, year-over-year trends, per-capita analysis. Turns the paper annual report into an accountability tool.|[Live Demo](#)|

### Core Modules (Concept Papers Complete)

|Module                                  |What It Does                                                                                                                                                                                                                                                      |
|----------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|**Automated Police Transparency System**|Daily automated RSA 91-A requests to Canaan PD. Ingests, OCRs, parses, and publishes dispatch logs, incident reports, arrest records, and use-of-force data in a searchable public archive. Tracks compliance with the 5-business-day statutory response deadline.|

### Statewide Expansion Layers

|Module      |Scope                                                                  |What It Does                                                                                                                                                                                                                                  |
|------------|-----------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|**VIGIL**   |All NH law enforcement (~160 municipal + 10 county + state)            |Seven-pillar accountability framework: automated records requests, open citizen complaints, use-of-force registry, officer transition tracking, compliance scorecards, cross-jurisdictional analytics, and citizen reporting.                 |
|**AEGIS**   |All 10 NH county attorney offices + regional prosecutorial associations|Prosecutorial accountability: charge-to-fact alignment auditing, victim rights compliance tracking (RSA 21-M:8-k), prosecutorial performance scorecards, victim reporting portal, and escalation pipeline to AG / county delegations / voters.|
|**SENTINEL**|Government-wide                                                        |Broad government corruption detection and accountability framework integrating data feeds from VIGIL, AEGIS, and ANMP modules into a unified anomaly detection and public transparency layer.                                                 |

### Planned Local Modules

|Module                     |Target                                                                                                            |
|---------------------------|------------------------------------------------------------------------------------------------------------------|
|School District Funding    |Mascoma Valley Regional School District (SAU #62) — per-pupil breakdowns, tax impact by town, enrollment trends   |
|Transfer Station Operations|Real-time status, disposal volumes, recycling rates, fee schedules, per-household cost                            |
|Water & Sewer Transparency |Rate structures, water quality data, infrastructure assessments, capital improvement schedules                    |
|Fire/Rescue/EMS Operations |Call volume by type, response times, staffing levels, apparatus inventory, per-capita cost                        |
|Government Meetings Archive|Searchable Select Board minutes, committee records, vote tracking for all 5 board members, warrant article history|
|Property Tax & Assessment  |Tax rates in context, assessment data, equalization ratios, warrant article tax impact calculator                 |

-----

## The Accountability Chain

```
Incident
  → Police Response .............. tracked by VIGIL
    → Charging Decision .......... audited by AEGIS
      → Victim Notification ...... enforced by AEGIS
        → Plea / Trial ........... monitored by AEGIS
          → Disposition ........... archived by AEGIS
            → Compliance Record ... aggregated by VIGIL + AEGIS
              → Public Archive .... published by ANMP / SENTINEL
```

-----

## Legal Foundation

Every function of ANMP and its expansion modules operates within existing New Hampshire law. No new legislation required. No government approval needed.

|Function                     |Authority                                                                          |
|-----------------------------|-----------------------------------------------------------------------------------|
|Records requests             |RSA 91-A:4 — Right-to-Know. No purpose requirement. No frequency limit. Any person.|
|Complaint filing             |RSA 106-L:18 — Conduct Review Committee receives complaints from any person.       |
|Publishing public records    |RSA 91-A records, once obtained, are public. No restriction on republication.      |
|Exculpatory Evidence Schedule|RSA 105:13-d — public record, published monthly by DOJ.                            |
|Victim rights tracking       |RSA 21-M:8-k — statutory rights with mandatory language (“are entitled to”).       |
|Compliance metrics           |Calculated from statutory deadlines already in law.                                |
|Citizen reporting & analysis |First Amendment.                                                                   |

-----

## Tech Stack

|Layer              |Technology                                                              |
|-------------------|------------------------------------------------------------------------|
|Frontend           |Next.js 14+ (React) on Vercel                                           |
|Backend / Database |Supabase (PostgreSQL, Auth, Storage, Edge Functions, Realtime)          |
|Email Automation   |Resend API for automated RSA 91-A requests and notifications            |
|Document Processing|Tesseract OCR for scanned PDFs; structured parsing for digital documents|
|AI Classification  |Anthropic API for document categorization and data extraction           |
|Mapping            |Mapbox GL JS / Leaflet for road condition and incident mapping          |
|Geospatial         |PostGIS for spatial queries and analysis                                |
|Authentication     |Supabase Auth with email verification; optional residency verification  |

**Estimated operating cost:** Under $50/month for the full platform at Canaan scale. Under $100/month for statewide law enforcement coverage (VIGIL). A statewide police transparency deployment covering all 234 NH municipalities would cost less than a single mid-level town employee.

-----

## Canaan Context

Canaan is a town of approximately 4,000 people in Grafton County, New Hampshire.

- **Operating budget:** $6.37 million (2026, up from $6.16M in 2025)
- **Police department:** 7 officers, nationally accredited, led by Chief Ryan R. Porter
- **Select Board:** Expanded from 3 to 5 members by voter approval in March 2026 (318–297)
- **School district:** Mascoma Valley Regional (SAU #62), shared with Enfield, Dorchester, Grafton, and Orange
- **Town roads:** ~70 miles maintained by the Highway Department
- **Infrastructure:** Potato Road Bridge over Indian River currently closed indefinitely

If a comprehensive civic transparency platform can work in Canaan — with its modest budget, limited staffing, and paper-based processes — it can work anywhere in the state.

-----

## Principles

1. **Citizen-operated, not government-operated.** The town does not run, fund, or control any ANMP module. This eliminates political capture and ensures the platform survives changes in leadership.
1. **Data belongs to the public.** Everything displayed is already public under NH RSA 91-A. The platform adds accessibility, not information.
1. **Open source and replicable.** Every module is Apache 2.0 licensed and designed for deployment in any NH municipality with minimal customization.
1. **Verify everything.** Every data point is tagged with its source and verification status. Estimates are clearly marked.
1. **Low cost, high impact.** Free-tier cloud services. No enterprise software. No consultants.
1. **Non-partisan, non-adversarial.** The platform reports data. It does not endorse candidates, advocate for specific budget outcomes, or target individuals. High-performing officials benefit from visibility.

-----

## Implementation Timeline

|Phase   |Deliverables                                                                  |Target      |
|--------|------------------------------------------------------------------------------|------------|
|Phase 1 |Road Watch, Budget Watch, Police Transparency concept papers published        |March 2026 ✅|
|Phase 1b|VIGIL, AEGIS, SENTINEL concept papers published                               |March 2026 ✅|
|Phase 2 |Road Watch and Budget Watch web platforms deployed with real Canaan data      |Q2 2026     |
|Phase 3 |Police Transparency automated request pipeline operational                    |Q3 2026     |
|Phase 4 |School district module; Transfer Station module                               |Q4 2026     |
|Phase 5 |Water/Sewer, Fire/EMS, Meetings Archive, Tax modules                          |Q1–Q2 2027  |
|Phase 6 |Template packaging for replication; first deployment to second NH municipality|Q3 2027     |

-----

## Related Projects

ANMP is part of the broader [OpenSourcePatents](https://github.com/OpenSourcePatents) organization. Other published projects include REVOLT (power systems), THOR (grid energy), REHD (recoil energy harvesting), Project NARC (opioid crisis geospatial intelligence), GUARDIAN (inter-agency accountability), GiveCoin (decentralized charity), Earth Pills (biome-specific seed deployment), and others.

-----

## Contributing

This project is licensed under Apache 2.0. You can use, modify, and distribute it freely under the terms of that license.

If you want to deploy ANMP for your own New Hampshire municipality, see `docs/replication-guide.md`. The legal framework (RSA 91-A) is identical across all 234 municipalities. The only things that change are department names, contact emails, and local budget numbers.

If you find errors in any data, open an issue. Accuracy matters more than speed.

-----

## License

[Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0)

Copyright 2026 Charles W. Dowd Jr. / OpenSourcePatents