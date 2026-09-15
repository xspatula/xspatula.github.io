---
layout: splash
title: "Xspatula"
excerpt: "Database-integrated Python modelling framework — script your own environment."
header:
  overlay_color: "#333"
  actions:
    - label: "Get started"
      url: "https://xspatula.github.io/xspatula_core_docs"
    - label: "GitHub"
      url: "https://github.com/xspatula"
feature_row:
  - title: "Framework"
    excerpt: "JSON-driven process definitions called from Jupyter notebooks. No code changes needed to reconfigure workflows — edit a JSON file and re-run."
    url: "https://xspatula.github.io/xspatula_core_docs/framework/"
    btn_label: "Read more"
    btn_class: "btn--primary"
  - title: "Database setup"
    excerpt: "Step-by-step guide to installing PostgreSQL, creating an Anaconda environment, and defining schemas and tables using Xspatula from a Jupyter notebook."
    url: "https://xspatula.github.io/xspatula_core_docs/setup_db/"
    btn_label: "Read more"
    btn_class: "btn--primary"
  - title: "Setup processes"
    excerpt: "Register the translate-and-manage process catalogue in the database — these process definitions are the prerequisite for the user-data import workflow."
    url: "https://xspatula.github.io/xspatula_core_docs/setup_processes/"
    btn_label: "Read more"
    btn_class: "btn--primary"
  - title: "User data"
    excerpt: "Add your own tabular (Excel) data to the database: the translate step converts rows to JSON process files; the manage step inserts them using the registered processes."
    url: "https://xspatula.github.io/xspatula_core_docs/user_data/"
    btn_label: "Read more"
    btn_class: "btn--primary"
  - title: "LUCAS soil database"
    excerpt: "Step-by-step guide to seeding the LUCAS 2009 soil survey PostgreSQL database — an open excerpt of the AI4SoilHealth (AI4SH) database, covering the publicly releasable soil observation data — using the Xspatula framework."
    url: "https://xspatula.github.io/xspatula_lucas_docs/setup_db/"
    btn_label: "Read more"
    btn_class: "btn--primary"
  - title: "LUCAS processes"
    excerpt: "Register the LUCAS process catalogue in the database — root processes, translate, community, utility, observation utility, and observation process families."
    url: "https://xspatula.github.io/xspatula_lucas_docs/setup_process/"
    btn_label: "Read more"
    btn_class: "btn--primary"
  - title: "LUCAS data import"
    excerpt: "Two-step translate-then-manage workflow for importing LUCAS 2009 soil survey data: utility catalogues, dataset metadata, campaigns, sampling logs, and measurements."
    url: "https://xspatula.github.io/xspatula_lucas_docs/import_data/"
    btn_label: "Read more"
    btn_class: "btn--primary"
  - title: "Open source"
    excerpt: "Code under MIT License, data under CC-BY. Clone the framework from GitHub and adapt it to your own domain."
    url: "https://github.com/xspatula/xspatula_core"
    btn_label: "View on GitHub"
    btn_class: "btn--inverse"
---

{% include feature_row %}

## What is Xspatula?

Xspatula is a Python framework for building database-integrated modelling workflows. The core idea is simple: **all execution logic lives in JSON files**, not in code. You define schemes, jobs, pilots, and processes in JSON; a Jupyter notebook calls the framework; the framework reads the JSON and runs the pipeline.

This separation makes it straightforward to:

- swap datasets without touching Python
- version-control your experimental configurations separately from the codebase
- hand workflows to non-programmers who edit JSON rather than code

The framework uses **PostgreSQL** as its backbone. Every result, parameter set, and process definition is stored in the database, which gives you full audit trails and makes it easy to query what ran, when, and with what inputs.

## Documentation

The full documentation is at **[xspatula.github.io/xspatula_core_docs](https://xspatula.github.io/xspatula_core_docs)** and covers:

- [Framework architecture](https://xspatula.github.io/xspatula_core_docs/framework/) — scheme files, job files, pilot files, process files, notebook interface
- [Database setup](https://xspatula.github.io/xspatula_core_docs/setup_db/) — PostgreSQL, Anaconda, `.netrc` credentials, schemas and tables
- [Setup processes](https://xspatula.github.io/xspatula_core_docs/setup_processes/) — register the translate-and-manage process catalogue; prerequisite for the user-data workflow
- [User data](https://xspatula.github.io/xspatula_core_docs/user_data/) — translate Excel rows to JSON process files, then manage them into the database

### LUCAS 2009 soil survey case study

**[xspatula.github.io/xspatula_lucas_docs](https://xspatula.github.io/xspatula_lucas_docs)** documents seeding a soil database with the LUCAS 2009 survey data using the Xspatula framework. `xspatula_lucas` is an open excerpt of the private `xspatula_ai4sh` project — built for the EU Horizon-funded [AI4SoilHealth](https://ai4soilhealth.eu) project — containing only the publicly releasable LUCAS 2009 records:

- [Setup DB](https://xspatula.github.io/xspatula_lucas_docs/setup_db/) — defines the schemas and tables (utility, community, process, landscape, observation and their utility schemas)
- [Setup processes](https://xspatula.github.io/xspatula_lucas_docs/setup_process/) — registers all framework processes in the database
- [Import data](https://xspatula.github.io/xspatula_lucas_docs/import_data/) — translate-then-manage workflow for importing utility catalogues, dataset metadata, and LUCAS soil observation records

## Licenses

- **Code**: [MIT License](https://github.com/xspatula/xspatula_core/blob/main/LICENSE)
- **Data**: [Creative Commons Attribution (CC-BY)](https://creativecommons.org/licenses/by/4.0/)
