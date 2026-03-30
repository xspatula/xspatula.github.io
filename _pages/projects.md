---
layout: single
title: "Projects"
permalink: /projects/
author_profile: true
---

## setup_core_db

The core Xspatula framework. Defines the JSON-driven process execution engine, PostgreSQL database integration, and the Jupyter notebook interface.

- **Documentation**: [xspatula.github.io/setup_core_db_docs](https://xspatula.github.io/setup_core_db_docs/docs)
- **Source**: [github.com/xspatula/setup_core_db](https://github.com/xspatula/setup_core_db)

### What it covers

- **Scheme files** — top-level configuration defining which processes belong to a project
- **Job files** — ordered list of processes to run in a session
- **Pilot files** — parameter sets that drive individual processes
- **Process files** — atomic definitions of what a process does and what database tables it touches
- **Database security** — six user categories (`user_cat_0` through `user_cat_5`) with graduated PostgreSQL privileges

---

## setup_core_db_docs

The documentation site for `setup_core_db`. Written in Markdown with the Jekyll Minimal Mistakes theme.

- **Site**: [xspatula.github.io/setup_core_db_docs](https://xspatula.github.io/setup_core_db_docs/docs)
- **Source**: [github.com/xspatula/setup_core_db_docs](https://github.com/xspatula/setup_core_db_docs)

---

## Related work

Xspatula is developed alongside [Xspectre](https://xspectre.com), a pocket-sized spectral laboratory for in-field soil analysis. The database framework is designed to store and process spectral measurements and integrate them with Earth Observation data.
