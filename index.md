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
    excerpt: "Guide to installing PostgreSQL, creating a Python environment, and defining schemas and tables using Xspatula from a Jupyter notebook."
    url: "https://xspatula.github.io/xspatula_core_docs/setup_db/"
    btn_label: "Read more"
    btn_class: "btn--primary"
  - title: "Setup processes"
    excerpt: "Register the process catalogue in the database — these process definitions are the prerequisite for the user-data import workflow and all further functions."
    url: "https://xspatula.github.io/xspatula_core_docs/setup_processes/"
    btn_label: "Read more"
    btn_class: "btn--primary"
  - title: "User data"
    excerpt: "Add your own tabular (Excel) data to the database: Xspatula translates the tables to JSON and then inserts the data - each Excel layout requires a process."
    url: "https://xspatula.github.io/xspatula_core_docs/user_data/"
    btn_label: "Read more"
    btn_class: "btn--primary"
  - title: "Audit"
    excerpt: "Include a comprehensive audit system with your Xspatula database to keep track of when and by whom a record in the database was added, changed or removed."
    url: "https://xspatula.github.io/xspatula_core_docs/auditing/"
    btn_label: "Read more"
    btn_class: "btn--primary"  
  - title: "Community"
    excerpt: "Add manually inspected organisations and users to your Xspatula project - user passwords are hash-crypted and automatically sent to new users by email."
    url: "https://xspatula.github.io/xspatula_core_docs/community/"
    btn_label: "Read more"
    btn_class: "btn--primary"
  - title: "Building"
    excerpt: "Guide to building your own Xspatula framework project - adjusting notebooks, setting up the database, adding users, auditing, adding your own processes."
    url: "https://xspatula.github.io/xspatula_core_docs/building/"
    btn_label: "Read more"
    btn_class: "btn--primary"
  - title: "Project: European soil"
    excerpt: "Building a customized framework for seeding, exploring and modeling data from the LUCAS 2009 soil survey — an open source project to learn and test how Xspatula operates."
    url: "https://xspatula.github.io/xspatula_lucas_docs/"
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
- [Setup processes](https://xspatula.github.io/xspatula_core_docs/setup_processes/) — register the process catalogue; prerequisite for the user-data workflow
- [User data](https://xspatula.github.io/xspatula_core_docs/user_data/) — translate Excel rows to database records
- [Auditing](https://xspatula.github.io/xspatula_core_docs/auditing/) — keep track of changes in the database
- [Community](https://xspatula.github.io/xspatula_core_docs/community/) — add users to your Xspatula project
- [Building](https://xspatula.github.io/xspatula_core_docs/building/) — guide for building your own Xspatula project

### LUCAS 2009 soil survey case study

**[xspatula.github.io/xspatula_lucas_docs/lucas_2009](https://xspatula.github.io/xspatula_lucas_docs/lucas_2009/)** documents a full pipeline for seeding and modelling the LUCAS 2009 soil survey using the Xspatula framework. `xspatula_lucas` is an open excerpt of the private `xspatula_ai4sh` project — built for the EU Horizon-funded [AI4SoilHealth](https://ai4soilhealth.eu) project — containing only the publicly releasable LUCAS 2009 records. The pipeline has two sections:

**Section 1: Seeding**

- [Prepare data](https://xspatula.github.io/xspatula_lucas_docs/lucas_2009/prepare_data/) — download the LUCAS 2009 data and prepare it for import
- [Insert utility data](https://xspatula.github.io/xspatula_lucas_docs/lucas_2009/insert_utility/) — insert the utility catalogues into the database
- [Insert dataset metadata](https://xspatula.github.io/xspatula_lucas_docs/lucas_2009/insert_dataset_meta/) — insert the LUCAS dataset metadata
- [Load LUCAS 2009 data](https://xspatula.github.io/xspatula_lucas_docs/lucas_2009/load_lucas_2009/) — load the LUCAS soil observation records into the database

**Section 2: Modelling**

- [Explore and select data](https://xspatula.github.io/xspatula_lucas_docs/lucas_2009/machine_learning/explore_select_data/) — explore the seeded data and select the subset to model
- [Preprocess data](https://xspatula.github.io/xspatula_lucas_docs/lucas_2009/machine_learning/ml_preprocess/) — prepare the selected data for machine learning
- [Model](https://xspatula.github.io/xspatula_lucas_docs/lucas_2009/machine_learning/ml_model/) — train and evaluate machine learning models on the LUCAS soil data

## Licenses

- **Code**: [MIT License](https://github.com/xspatula/xspatula_core/blob/main/LICENSE)
- **Data**: [Creative Commons Attribution (CC-BY)](https://creativecommons.org/licenses/by/4.0/)
