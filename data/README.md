# Data Provenance

This directory contains the three analysis-ready inputs required by the notebook.

| File | Role in the analysis | Source context |
| --- | --- | --- |
| `world_happiness.csv` | 2015 happiness score and explanatory contribution columns | [World Happiness Report 2015](https://worldhappiness.report/ed/2015/) |
| `world_happiness_allyears.csv` | Country happiness index and rank for available observations from 2013 and 2015-2023 | [World Happiness Report data-sharing page](https://worldhappiness.report/data-sharing/) |
| `who_physical_activity.csv` | Country demographics, income group, and inactivity indicators | [WHO Global Status Report on Physical Activity 2022: Country Profiles](https://www.who.int/publications/i/item/9789240064119) |

Country names are harmonized and numeric fields are cleaned inside the notebook. The generated merged and cluster-labelled CSV files are intentionally excluded from Git because they can be rebuilt from these inputs.

These files are included for reproducibility. They remain third-party data and are not covered by the repository's MIT code license. Reuse must follow the terms of the original providers.
