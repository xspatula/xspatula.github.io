---
layout: splash
title: "Xspatula"
excerpt: "Database-integrated Python modelling framework — script your own environment."
header:
  overlay_color: "#333"
  actions:
    - label: "Get started"
      url: "https://xspatula.github.io/setup_core_db_docs"
    - label: "GitHub"
      url: "https://github.com/xspatula"
feature_row:
  - title: "Framework"
    excerpt: "JSON-driven process definitions called from Jupyter notebooks. No code changes needed to reconfigure workflows — edit a JSON file and re-run."
    url: "https://xspatula.github.io/setup_core_db_docs/framework/introduction/"
    btn_label: "Read more"
    btn_class: "btn--primary"
  - title: "Database setup"
    excerpt: "Step-by-step guide to installing PostgreSQL, creating an Anaconda environment, and defining schemas and tables using Xspatula."
    url: "https://xspatula.github.io/setup_core_db_docs/setup_db/introduction/"
    btn_label: "Read more"
    btn_class: "btn--primary"
  - title: "Open source"
    excerpt: "Code under MIT License, data under CC-BY. Clone the framework from GitHub and adapt it to your own domain."
    url: "https://github.com/xspatula/setup_core_db"
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

The full documentation is at **[xspatula.github.io/setup_core_db_docs](https://xspatula.github.io/setup_core_db_docs)** and covers:

- [Framework architecture](https://xspatula.github.io/setup_core_db_docs/framework/introduction/) — scheme files, job files, pilot files, process files, notebook interface
- [Database setup](https://xspatula.github.io/setup_core_db_docs/setup_db/introduction/) — PostgreSQL, Anaconda, `.netrc` credentials, schemas and tables

## Licenses

- **Code**: [MIT License](https://github.com/xspatula/setup_core_db/blob/main/LICENSE)
- **Data**: [Creative Commons Attribution (CC-BY)](https://creativecommons.org/licenses/by/4.0/)
