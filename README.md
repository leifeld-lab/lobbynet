# Temporal Network Infrastructure for Parliamentary Lobbying Data

This repository explores the design of a **reproducible data infrastructure** for constructing temporal relational data on legislators, lobby organisations, and related actors using publicly available parliamentary sources.

The focus is on **data acquisition, linkage, and representation**, rather than on substantive analysis or hypothesis testing.

This repository currently serves as an entry point for a **research challenge** associated with the Leifeld Lab.
 

## Scope and motivation

Parliamentary lobbying data are published across multiple heterogeneous sources, often with limited documentation and inconsistent identifiers. Constructing inferentially meaningful network data therefore requires explicit design choices about:

- how entities (legislators, organisations, clients) are identified and linked;
- how time is represented (events, intervals, updates);
- how updates and revisions are handled;
- and how resulting data structures support downstream network analysis.

This repository focuses on these **infrastructural and methodological questions**, using data from the German Bundestag as a primary case.

## Data sources

Primary data sources include:

- Legislator biography pages published by the German Bundestag  
  https://www.bundestag.de/abgeordnete/biografien

- The German Lobby Register (JSON format)  
  https://www.lobbyregister.bundestag.de/

An initial, incomplete manual data collection effort is available in `data/dataset_attempt.xlsx`. This file is provided only to illustrate relevant variables and structure; the expectation is that data will be collected programmatically.

## Current challenge focus

The current challenge is to design and prototype a **replicable pipeline** that:

1. acquires legislator biography data programmatically;
2. links legislators to organisations and entities in the lobby register;
3. represents the resulting relations as temporal relational data;
4. supports regular updates and transparent documentation of assumptions.

The challenge is modular. Contributions may focus on **one component only** (e.g. scraping, entity resolution, temporal modelling, or data storage).

Contributions are expected to be scoped to what is reasonable for an individual contributor; no fixed timeline or completion expectation is implied.

Work on this challenge is typically coordinated through GitHub issues and pull requests.

## Open design questions

Open questions include, but are not limited to:

- Which entity resolution strategies are robust given name variation and partial identifiers?
- How should lobbying relations be represented temporally (events vs intervals)?
- What data model best supports downstream network analysis and updating?
- What are the trade-offs between flat files, relational databases, and graph databases for this use case?

These questions are intentionally not fully specified.

## What would count as a contribution?

Examples of useful contributions include:

- a documented scraping pipeline for legislator biographies;
- reproducible entity matching between biographies and lobby register entries;
- a proposed data model with justification and examples;
- code for updating and validating data over time;
- benchmarks or comparisons of alternative storage backends.

Partial contributions are welcome. No single contributor is expected to address all aspects.

## Relation to further work

Downstream analyses (e.g., institutional effects, discourse network analysis, or cross-national comparison) are possible but not required for this challenge.

Successful engagement may lead to closer collaboration on applied or methodological work, depending on mutual interest and available opportunities.

A longer project description developed for a previous funding application is available in `project_proposal/`.
