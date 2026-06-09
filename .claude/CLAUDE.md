# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Purpose

`xspatual.github.io` is the documentation landing site for the xspatula database-integrated python framework. The documentation site written in Markdown using the Jekyll theme Minimal Mistakes (https://mmistakes.github.io/minimal-mistakes/).

The Xspatula framework is written in Python and uses JSON files to define all executions and processes. These JSON files are called from Jupyter notebooks.

The basic framework is available:
- As a sibling directory at relative path `../setup_core_db`
- On GitHub at https://github.com/xspatula/setup_core_db

A fully developed framework is available:
- As a sibling directory at relative path `../load_ai4sh_db`
- On GitHub at https://github.com/xspatula/load_ai4sh_db

## Site Architecture

**Theme**: Minimal Mistakes Jekyll theme, version 4.27.3 (local install, not remote)
**URL (production)**: `https://xspatula.github.io` (url + baseurl from `_config.yml`)
**Search**: Lunr (client-side, full content)

### Key Directories

- `_data/` — `navigation.yml` (site nav) and `ui-text.yml` (theme UI strings)
- `assets/media/` — logos and schema diagram images
- `_site/` — generated output

## Configuration Files

- `_config.yml` — production config; sets site title, URL, collections, plugins
- `_config_local.yml` — local dev override; sets empty URL/baseurl for local serving
- `Gemfile` — single gem dependency: `minimal-mistakes-jekyll 4.27.3`

To serve locally: `bundle exec jekyll serve --config _config.yml,_config_local.yml`

## Content Conventions

- All documentation pages use Jekyll front matter with at minimum: `layout`, `title`, `categories`, `tags`
- Sidebar navigation is set via `sidebar: { nav: "<nav_key>" }` in front matter
- Internal links use Jekyll's `{{ site.baseurl }}` or relative paths
- Code examples are fenced with language identifiers (python, json, sql, bash)
- Database schema diagrams are stored in `assets/media/` and referenced in markdown

## Content Scope

The documentation covers:
1. **Front page** — general overview and tabulated description of project sites/collections that introduces how to build a framework
2. **Projects** — An expansion of the tabulated project descriptions with links to sites/collections

### Project links

| Project | target page | purpose | action |
|---|---|---|---|
| `Framework` | https://xspatula.github.io/setup_core_db_docs/framework/ | Framework introduction, app requirements and command file hierarchy | no action required |
| `Database setup` | https://xspatula.github.io/setup_core_db_docs/setup_db/ | Step-by-step database setup guide | no action required |
| `setup_processes` | https://xspatula.github.io/setup_core_db_docs/setup_processes/ | Step-by-step guide for setting up a process example (the example covers the processes for translating and adding tabular data to the database - used in the next row)| create project summary in landing page and under project |
| `user_data` | https://xspatula.github.io/setup_core_db_docs/user_data/ | Step-by-step guide for adding user specific tabular (excel) data via JSON conversion | create project summary in landing page and under project |
| `AI4SoilHealth database` | https://xspatula.github.io/seed_ai4sh_db_docs/setup_db/ | Step-by-step guide for setting up the a soil analysis and modelling database (AI4SoilHealth)| no action required |
| `AI4SoilHealth processes` | https://xspatula.github.io/seed_ai4sh_db_docs/setup_process/ | Step-by-step guide for setting up the a soil analysis and modelling processes (AI4SoilHealth)| no action required |
| `AI4SoilHealth data import` | https://xspatula.github.io/seed_ai4sh_db_docs/import_data/ | Step-by-step guide for importing data to the soil analysis and modelling framework (AI4SoilHealth)| no action required |
| `Open Source` | https://github.com/xspatula/setup_core_db | Link to GitHub repo | no action required |

## Licenses

- **Data**: Creative Commons Attribution (CC-BY)
- **Code**: MIT License

## Related Repositories

| Repo | Relationship |
|---|---|
| `xspatula/setup_core_db_docs` | Generic framework documentation and step-by-step setup and seeding of basic data |
| `xspatula/seed_ai4sh_db_docs/` | Setting up and seeding a project database and model environment for the project AI4Soilhealth |
| `mmistakes/minimal-mistakes` | Jekyll theme used for the site |
