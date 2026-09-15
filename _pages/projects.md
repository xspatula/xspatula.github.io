---
layout: single
title: "Projects"
permalink: /projects/
author_profile: true
---

## xspatula_core

The core Xspatula framework. Defines the JSON-driven process execution engine, PostgreSQL database integration, and the Jupyter notebook interface.

- **Documentation**: [xspatula.github.io/xspatula_core_docs](https://xspatula.github.io/xspatula_core_docs)
- **Source**: [github.com/xspatula/xspatula_core](https://github.com/xspatula/xspatula_core)

### What it covers

- **Scheme files** — top-level configuration defining which processes belong to a project
- **Job files** — ordered list of processes to run in a session
- **Pilot files** — parameter sets that drive individual processes
- **Process files** — atomic definitions of what a process does and what database tables it touches
- **Database security** — six user categories (`user_cat_0` through `user_cat_5`) with graduated PostgreSQL privileges

### Setup processes

Register the translate-and-manage process catalogue in the database. This is the prerequisite step for the user-data workflow: before any user data can be imported, the framework needs the relevant process definitions present in the database.

- **Documentation**: [xspatula_core_docs/setup_processes](https://xspatula.github.io/xspatula_core_docs/setup_processes/)

Covers:

- **Translate processes** — process definitions that convert tabular (Excel) rows into JSON process and pilot files
- **Manage processes** — process definitions that insert JSON-converted data into the database
- **Process registration order** — which root processes and process IDs must be present before user-data import can run

### User data

Step-by-step guide for adding your own tabular (Excel) data to the database using the registered translate-and-manage processes from the previous step.

- **Documentation**: [xspatula_core_docs/user_data](https://xspatula.github.io/xspatula_core_docs/user_data/)

Covers:

- **Excel file layout** — column conventions required for the translate step to parse correctly
- **Translate** — converting Excel rows to JSON process files and pilot files
- **Manage** — inserting the converted data into the database via the registered process catalogue
- **Verification** — querying the database to confirm the imported records

---

## xspatula_lucas

An open excerpt of the private `xspatula_ai4sh` project, containing only the publicly releasable LUCAS 2009 soil survey records. Uses the `xspatula_core` framework to define, populate, and import this data into a soil observation database built for the EU Horizon-funded [AI4SoilHealth](https://ai4soilhealth.eu) project.

- **Documentation**: [xspatula.github.io/xspatula_lucas_docs](https://xspatula.github.io/xspatula_lucas_docs)
- **Source**: [github.com/xspatula/xspatula_lucas](https://github.com/xspatula/xspatula_lucas)

### Setup LUCAS DB

Defines and creates the LUCAS PostgreSQL database structure.

- **Documentation**: [xspatula_lucas_docs/setup_db](https://xspatula.github.io/xspatula_lucas_docs/setup_db/)

Covers:

- **Schemas** — utility, community, process, observation_utility, observation, and landscape, and their utility sub-schemas
- **Tables** — all reference catalogues, entity tables, and observation tables with foreign key dependencies
- **Execution order** — the pilot file ordering required to satisfy foreign key constraints at creation time

### Setup LUCAS Processes

Registers the LUCAS process catalogue in the database so the framework can dispatch calls by `root_process_id` and `process_id`.

- **Documentation**: [xspatula_lucas_docs/setup_process](https://xspatula.github.io/xspatula_lucas_docs/setup_process/)

Covers:

- **Root processes** — `manage_table_data` and `translate_data` process families
- **Translate** — processes for converting tabular data to JSON process files
- **Community, utility, observation utility, observation** — domain-specific process registrations

### Import LUCAS Data

Step-by-step guide to importing the LUCAS 2009 soil observation data into a running database using the two-step translate-then-manage pattern.

- **Documentation**: [xspatula_lucas_docs/import_data](https://xspatula.github.io/xspatula_lucas_docs/import_data/)

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
