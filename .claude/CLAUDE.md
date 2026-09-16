# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Purpose

`xspatual.github.io` is the documentation landing site for the xspatula database-integrated python framework. The documentation site written in Markdown using the Jekyll theme Minimal Mistakes (https://mmistakes.github.io/minimal-mistakes/).

The Xspatula framework is written in Python and uses JSON files to define all executions and processes. These JSON files are called from Jupyter notebooks.

The basic framework is available:
- As a sibling directory at relative path `../xspatula_core`
- On GitHub at https://github.com/xspatula/xspatula_core

A private fully developed framework is available:
- As a sibling directory at relative path `../xspatula_ai4sh`
- On GitHub at https://github.com/xspatula/xspatula_ai4sh

An open excerpt of the fully developed framework is available:
- As a sibling directory at relative path `../xspatula_lucas`
- On GitHub at https://github.com/xspatula/xspatula_lucas


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
| `Framework` | https://xspatula.github.io/xspatula_core_docs/framework/ | Framework introduction, app requirements and command file hierarchy | no action required |
| `Database setup` | https://xspatula.github.io/xspatula_core_docs/setup_db/ | Step-by-step database setup guide | no action required |
| `setup_processes` | https://xspatula.github.io/xspatula_core_docs/setup_processes/ | Step-by-step guide for setting up a process example (the example covers the processes for translating and adding tabular data to the database - used in the next row)| no action required |
| `user_data` | https://xspatula.github.io/xspatula_core_docs/user_data/ | Step-by-step guide for adding user specific tabular (excel) data via JSON conversion | no action required |
| `auditing` | https://xspatula.github.io/xspatula_core_docs/auditing/ | Guide for the audit system tracking who added, changed, or removed a database record and when | no action required |
| `community` | https://xspatula.github.io/xspatula_core_docs/community/ | Guide for adding manually inspected organisations and users, with hash-crypted passwords emailed to new users | no action required |
| `building` | https://xspatula.github.io/xspatula_core_docs/building/ | Guide for building your own Xspatula framework project end to end | no action required |
| `xspatula_lucas / LUCAS 2009` | https://xspatula.github.io/xspatula_lucas_docs/lucas_2009/ | Two-section pipeline for seeding and modelling the LUCAS 2009 soil survey (open excerpt of AI4SoilHealth) | no action required |
| `Open Source` | https://github.com/xspatula/xspatula_core | Link to GitHub repo | no action required |

## Licenses

- **Data**: Creative Commons Attribution (CC-BY)
- **Code**: MIT License

## Related Repositories

| Repo | Relationship |
|---|---|
| `xspatula/xspatula_core_docs` | Generic framework documentation and step-by-step setup and seeding of basic data |
| `xspatula/xspatula_lucas_docs/` | Setting up database, seeding it, adding data and building a model environment for the open LUCAS 2009 soil survey excerpt of AI4SoilHealth |
| `mmistakes/minimal-mistakes` | Jekyll theme used for the site |
