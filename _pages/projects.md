---
layout: single
title: "Projects"
permalink: /projects/
author_profile: true
---

## setup_core_db

The core Xspatula framework. Defines the JSON-driven process execution engine, PostgreSQL database integration, and the Jupyter notebook interface.

- **Documentation**: [xspatula.github.io/setup_core_db_docs](https://xspatula.github.io/setup_core_db_docs)
- **Source**: [github.com/xspatula/setup_core_db](https://github.com/xspatula/setup_core_db)

### What it covers

- **Scheme files** — top-level configuration defining which processes belong to a project
- **Job files** — ordered list of processes to run in a session
- **Pilot files** — parameter sets that drive individual processes
- **Process files** — atomic definitions of what a process does and what database tables it touches
- **Database security** — six user categories (`user_cat_0` through `user_cat_5`) with graduated PostgreSQL privileges

---

## seed_ai4sh_db

The AI4SoilHealth database project. Uses the `setup_core_db` framework to define, populate, and import data into a comprehensive soil observation database built for the EU Horizon-funded [AI4SoilHealth](https://ai4soilhealth.eu) project.

- **Documentation**: [xspatula.github.io/seed_ai4sh_db_docs](https://xspatula.github.io/seed_ai4sh_db_docs)
- **Source**: [github.com/xspatula/seed_ai4sh_db](https://github.com/xspatula/seed_ai4sh_db)

### Setup AI4SH DB

Defines and creates the full AI4SH PostgreSQL database structure across 9 schemas.

- **Documentation**: [seed_ai4sh_db_docs/setup_db](https://xspatula.github.io/seed_ai4sh_db_docs/setup_db/)

Covers:

- **Schemas** — 9 schemas: utility, community, process, observation_utility, observation, landscape, eDNA, and their utility sub-schemas
- **Tables** — all reference catalogues, entity tables, and observation tables with foreign key dependencies
- **Execution order** — the pilot file ordering required to satisfy foreign key constraints at creation time

### Setup AI4SH Processes

Registers the full AI4SH process catalogue in the database so the framework can dispatch calls by `root_process_id` and `process_id`.

- **Documentation**: [seed_ai4sh_db_docs/setup_process](https://xspatula.github.io/seed_ai4sh_db_docs/setup_process/)

Covers:

- **Root processes** — `manage_table_data` and `translate_data` process families
- **Translate** — processes for converting tabular data to JSON process files
- **Community, utility, observation utility, observation, eDNA** — domain-specific process registrations

### Import AI4SH Data

Step-by-step guide to importing actual soil observation data into a running AI4SH database using the two-step translate-then-manage pattern.

- **Documentation**: [seed_ai4sh_db_docs/import_data](https://xspatula.github.io/seed_ai4sh_db_docs/import_data/)

Covers:

- **Tabular source data** — Excel file layout and column conventions for all catalogue and observation tables
- **JSON data structure** — how the translate step converts Excel rows to JSON process files and pilot files
- **Import utility data** — translating the full set of observation utility catalogues (quantities, units, methods, providers, provisions, and more)
- **Manage utility data** — inserting utility catalogues into the database
- **Import observation data** — translating dataset metadata: data sources, persons, datasets, campaigns, and sampling logs
- **Manage observation data** — inserting dataset metadata into the database
- **Foreign key handling** — dependency trees, correct insertion order, and error recovery

---

## Related work

Xspatula is developed alongside [Xspectre](https://xspectre.com), a pocket-sized spectral laboratory for in-field soil analysis. The database framework is designed to store and process spectral measurements and integrate them with Earth Observation data.
