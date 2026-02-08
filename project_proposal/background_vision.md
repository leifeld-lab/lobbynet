# Background vision

## Project aims

In this project, we want to do the following things:

1. Collect data about German [legislators' biographies](https://www.bundestag.de/abgeordnete/biografien), to link individual legislators to organisations.
2. Match the organisations and legislators with the German [lobby register](https://www.lobbyregister.bundestag.de/), which is available in JSON format, to create a merged multipartite network of legislators, lobbyists, lobby organisations, and their clients, linked up with information about electoral institutions.
3. Test if electoral institutions (list vs direct) make a difference for legislators' embeddedness in the lobbying network.
4. Conduct a discourse network analysis of lobbying and corruption regulation as a separate network layer, and find if central nodes in the lobbying network occupy central positions in the discourse network. Apply higher-order network analysis and inferential models to the entire system.
5. Repeat the same analysis with UK data (and potentially other countries), and compare findings.

The current directory contains a [full project description](project_proposal.md), which was under consideration for funding in 2025, including a shorter [summary](project_summary.md). Since the bid was unsuccessful in the final stage, we want to make progress with the data without funding for now and attempt a different funder once initial results trickle in. This can also be a basis for co-authored publications.

## Legislator and lobbying data

In 2022, a research assistant started manually collecting the required data from the legislator biographies website. The [spreadsheet in the data directory](../data/dataset_attempt.xlsx) contains the initial data collection effort. It can serve to identify the important variables. However, the data themselves are incomplete and are probably best web-scraped from scratch from the Bundestag website, perhaps for the last two or three legislation periods, in line with the timeline covered by the lobby register or longer. Scraping can be done using R or other languages or even specialised web scraping tools.

Ideally, the data should be saved in a graph database, such as neo4j or similar using the ISO GraphQL query language. As a second-best alternative, the data should be saved in a relational database, such as MariaDB or mySQL, using SQL. At a minimum, the data can be saved in CSV files, but a database would make our life easier.

The project should create a replicable pipeline that can be used to update the results later when new data trickle in. The pipeline should do the scraping, the data processing and storage, name disambiguation and matching with the lobby register JSON data, and the analysis, probably in separate steps, but they need to be replicable and well documented.

It is advisable to screen other existing datasets to avoid any duplication of existing work. For example, screen existing datasets like the [German Bundestag Election Results at Constituency Level](https://doi.org/10.7910/DVN/S1M6SA) dataset and other published datasets on the [Harvard Dataverse](https://dataverse.harvard.edu/), in the academic literature, and elsewhere.

## Discourse network analysis

As a separate strand, we want to conduct a discourse network analysis using parliamentary and/or media data. The annotation should be done using Discourse Network Analyzer and/or a machine learning pipeline with automatic annotation and validation after a suitable codebook has been manually generated and validated.

This part of the analysis is more traditional political science work and requires a qualitative understanding of the debate and codebook development.

Once coded, the discourse network dataset should be merged into the graph database, and the final step will be a joint higher-order network analysis of everything together. This part is more technical again.