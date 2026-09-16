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
- **Database security** — five user categories (`user_cat_1` through `user_cat_5`) with graduated PostgreSQL privileges

### Setup processes

Register the process catalogue in the database. This is the prerequisite step for the user-data workflow: before any user data can be imported, the framework needs the relevant process definitions present in the database.

- **Documentation**: [xspatula_core_docs/setup_processes](https://xspatula.github.io/xspatula_core_docs/setup_processes/)

Covers:

- **Insert processes** — process definitions that convert tabular (Excel) rows into database records in a single step
- **Translate processes** — process definitions that convert tabular (Excel) rows into JSON process and pilot files
- **Manage processes** — process definitions that insert JSON-converted data into the database
- **Process registration order** — which root processes and process IDs must be present before user-data import can run

### User data

Guide for adding your own tabular (Excel) data to the database.

- **Documentation**: [xspatula_core_docs/user_data](https://xspatula.github.io/xspatula_core_docs/user_data/)

Covers:

- **Excel file layout** — column conventions required for the translate step to parse correctly
- **Insert** — convert tabular (Excel) rows into database records in a single step
- **Translate** — converting Excel rows to JSON process files and pilot files
- **Manage** — inserting the converted data into the database via the registered process catalogue
- **Verification** — querying the database to confirm the imported records

### Auditing

Include a comprehensive audit system with your Xspatula database to keep track of when and by whom a record was added, changed, or removed.

- **Documentation**: [xspatula_core_docs/auditing](https://xspatula.github.io/xspatula_core_docs/auditing/)

Covers:

- **Audit tables** — how record-level history (who, when, what changed) is stored alongside the operational data
- **Enabling auditing** — turning on audit tracking for a schema or table
- **Querying history** — retrieving the change history for a given record

### Community

Add manually inspected organisations and users to your Xspatula project.

- **Documentation**: [xspatula_core_docs/community](https://xspatula.github.io/xspatula_core_docs/community/)

Covers:

- **Organisations and users** — registering organisations and the users that belong to them
- **Password handling** — hash-crypted passwords, automatically emailed to new users
- **User categories** — assigning graduated PostgreSQL privileges to new users

### Building

Guide to building your own Xspatula framework project from scratch.

- **Documentation**: [xspatula_core_docs/building](https://xspatula.github.io/xspatula_core_docs/building/)

Covers:

- **Notebooks** — adjusting the Jupyter notebook interface for your project
- **Database** — setting up the database for a new project
- **Users and auditing** — adding users and enabling audit tracking
- **Custom processes** — adding your own processes to the framework

---

## xspatula_lucas

An open excerpt of the private `xspatula_ai4sh` project, containing only the publicly releasable LUCAS 2009 soil survey records. Builds on the `xspatula_core` framework to seed, explore, and model a soil observation database for the EU Horizon-funded [AI4SoilHealth](https://ai4soilhealth.eu) project.

- **Documentation**: [xspatula.github.io/xspatula_lucas_docs/lucas_2009](https://xspatula.github.io/xspatula_lucas_docs/lucas_2009/)
- **Source**: [github.com/xspatula/xspatula_lucas](https://github.com/xspatula/xspatula_lucas)

The `lucas_2009` documentation covers a two-section pipeline: seeding the database, then exploring and modelling the seeded data.

### Section 1: Seeding

- [Prepare data](https://xspatula.github.io/xspatula_lucas_docs/lucas_2009/prepare_data/) — download the LUCAS 2009 data and prepare it for import
- [Insert utility data](https://xspatula.github.io/xspatula_lucas_docs/lucas_2009/insert_utility/) — insert the utility catalogues into the database
- [Insert dataset metadata](https://xspatula.github.io/xspatula_lucas_docs/lucas_2009/insert_dataset_meta/) — insert the LUCAS dataset metadata
- [Load LUCAS 2009 data](https://xspatula.github.io/xspatula_lucas_docs/lucas_2009/load_lucas_2009/) — load the LUCAS soil observation records into the database

### Section 2: Modelling

- [Explore and select data](https://xspatula.github.io/xspatula_lucas_docs/lucas_2009/machine_learning/explore_select_data/) — explore the seeded data and select the subset to model
- [Preprocess data](https://xspatula.github.io/xspatula_lucas_docs/lucas_2009/machine_learning/ml_preprocess/) — prepare the selected data for machine learning
- [Model](https://xspatula.github.io/xspatula_lucas_docs/lucas_2009/machine_learning/ml_model/) — train and evaluate machine learning models on the LUCAS soil data

---

## Related work

Xspatula is developed alongside [Xspectre](https://xspectre.com), a pocket-sized spectral laboratory for in-field soil analysis. The database framework is designed to store and process spectral measurements and integrate them with Earth Observation data.
