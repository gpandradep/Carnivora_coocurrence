[![DOI](https://zenodo.org/badge/724158517.svg)](https://zenodo.org/doi/10.5281/zenodo.10211295)

# A repository for

From co-occurrence patterns to agonistic interactions. A meta-analysis of carnivore mammals camera trap research

## Links to different parts of the page

1. [Description of the repository](#description-of-the-repository)

2. [The root folder](#the-root-folder)

3. [The data folder (`./data`)](#the-data-folder-data)

4. [Files for statistical modeling](#files-for-statistical-modeling)

## Description of the repository

This repository contains the data and code used in *From co-occurrence patterns to agonistic interactions. A meta-analysis of carnivore mammals camera trap research*. The data come from a literature review of peer-reviewed articles focused on the study of spatial or temporal co-occurrence of mammals of the order Carnivora with camera traps. All data used in the modeling process are located in the `./Data/` folder. Inside the `./Data/Literature` folder you will find the information of the articles selected in the literature search. The `./Data/Model data` folder contains the files with the information used to perform the statistical modeling. The code is available online in html form for each interaction and in Quarto script format in the root folder.

[Back to table of contents ⤒](#a-repository-for)

### The root folder

The root folder contains the following files: `_quarto.yml`, `styles.css` and `.gitignore`, which are configuration files for rendering Quarto files (`\*.qmd`) and GitHub configurations respectively. The Readme file (`README.md`) contains the same information of the `index.qmd` file, which is the description of the repository. The code is in Quarto format and contains statistical modeling procedures for competitive (`C_modelling_2023.qmd`) and predator-prey (`P_modelling_2023.qmd`) interactions. Finally the `Carnivora_coocurrence.Rproj` is used to open the project in Rstudio.

The scripts are in R language but require [Quarto](https://quarto.org/) to be installed in Rstudio to run. However the corresponding `.htmls` files contain all the code information (including results) without the need to open R.

[Back to table of contents ⤒](#a-repository-for)

### The data folder (`./Data`)

This folder has 5 files and 2 sub-folders.

**`./Data/Literature/bib_database.csv`**: Database in csv format with the 314 fully scanned articles. The base columns have the following information



| Column | Description |
|--------|-------------|
| label | Identifier of each article |
| title | Complete title |
| author | List of authors |
| journal | publication journal |
| abstract | abstract of each article |
| year | year of publication |
| doi | digital object identifier |
| volume | journal volume |
| language | language of publication |
| issue | journal issue |
| Selected | Selected or not selected during the screening process |


**`./Data/Model Data/`** : This folder contains 4 files containing all the information extracted from the selected articles. `spatC_db.csv` and `tempC_db.csv` contain the information on the competitive interactions of carnivorous mammals in the spatial and temporal dimension respectively. While, `spatP_db.csv` and `tempP_db.csv` contain the information on predator-prey interactions in the spatial and temporal dimension respectively. The description of the variables of the four bases are described in the following table


| Column | Description | Source | Interaction |
|--------|-------------|--------|-------------|
| SIF | Species interaction factor derived from multi-species occupancy models; SIF<1 species avoidance, SIF:1 random pattern, SIF>1 Aggregation pattern | Each study or calculated | Both |
| SIF_ic | SIF 95% confidence intervals | Each study | Both |
| Ov_coeff | Overlapping delta coefficient: 0 indicating no overlapping in species activity patterns, 1 indicating total overlapping | Each study | Both |
| Ov_ic | Overlapping delta coefficient 95% confidence intervals | Each study | Both |
| D_competitor | Scientific name of the bigger or dominant competitor | Each study | Competitive |
| S_competitor | Scientific name of the subordinate or smaller competitor | Each study | Competitive |
| D_family | Family of the dominant competitor | Each study | Competitive |
| S_family | Family of the subordinate competitor | Each study | Competitive |
| D_genus | Genus of the dominant competitor | Each study | Competitive |
| S_genus | Genus of the subordinate competitor | Each study | Competitive |
| p_distance | Pairwise mitochondrial DNA phylogenetic distances | [@hassanin2021] | Competitive |
| mass_ratio | For competitive interactions=ln(Dominant competitor body mass (g)/ Subordinate competitor body mass (g)). For predator-prey interactions= ln(Predator body mass (g) / Prey body mass (g)) | Calculated | Both |
| D_mass | Dominant competitor body mass (g) | COMBINE data base [@soria2021] | Competitive |
| S_mass | Subordinate competitor body mass (g) | COMBINE data base [@soria2021] | Competitive |
| D_diet | Dominant competitor diet category | PHYLACINE trait database [@faurby2020] | Competitive |
| S_diet | Subordinate competitor diet category | PHYLACINE trait database [@faurby2020] | Competitive |
| diet_dist | Dominant and subordinate competitor category diets: Same if pair of competitors shares de diet category, different if not | calculated | Competitive |
| Pred_sp | Scientific name of the predator | Each study | Predator-prey |
| Prey_sp | Scientific name of the prey | Each study | Predator-prey |
| Pred_family | Family of the predator | Each study | Predator-prey |
| Prey_family | Family of the prey | Each study | Predator-prey |
| Pred_genus | Genus of the predator | Each study | Predator-prey |
| Prey_genus | Genus of the prey | Each study | Predator-prey |
| Pred_mass | Predator body mass (g) | COMBINE data base [@soria2021] | Predator-prey |
| P_hunt | Predator hunting strategy: pursuit, ambush, group hunting | [@hirt2020] and other sources | Predator-prey |
| Prey_mass | Prey body mass (g) | COMBINE data base [@soria2021] | Predator-prey |
| Label | Article identifier | Each study | Both |
| Lon | Longitude of the center of the locality or each study locality in decimal coordinates | Each study | Both |
| Lat | Latitude of the center of the locality or each study locality in decimal coordinates | Each study | Both |
| Continent | Continent in which the research is conducted | Each study | Both |
| Country | Country in which the research is carried out | Each study | Both |
| Locality | Location where the co-occurrence measurements were obtained. | Each study | Both |
| Samp_dur | Sampling duration in months | Each study | Both |
| N_stations | Number of sampling stations | Each study | Both |
| Effort | Sampling effort calculated as number of sampling stations per number of camera days | Each study | Both |
| Avg_dist | Average distance between sampling stations in km | Each study | Both |
| S_area | Sampling area in km^2 | Each study | Both |
| Pred_evidence | Direct evidence of predation | Global Interaction data base [@poelen2014] | Predator-prey |
| Hunt_source | Bibliographic source of the hunting strategy | Literature | Predator-prey |


[Back to table of contents ⤒](#a-repository-for)

### Files for statistical modeling

The `qmd` files contain the entire statistical modeling prthe respective results.


**`C_modelling_2023.qmd`** : This file contain the modeling process performed for the co-occurrence data of competing species of carnivorous mammals. It includes both the modeling of the spatial co-occurrence data and the temporal co-occurrence data. The script requires the following data files: `Data/Model data/SpatC_db.csv` and `Data/Model data/tempC_db.csv`. Can be viewed without opening R using the `C_modelling_2023.html` file and the [online page](https://gpandradep.github.io/Carnivora_coocurrence/C_modelling_2023.html).


**`P_modelling_2023.qmd`** : This file contain the modeling process performed for the co-occurrence data of Carnivora predators an their mammals preys. It includes both the modeling of the spatial co-occurrence data and the temporal co-occurrence data. The script requires the following data files: `Data/Model data/PpatC_db.csv` and `Data/Model data/tempP_db.csv`. Can be viewed without opening R using the `P_modelling_2023.html` file and the [online page](https://gpandradep.github.io/Carnivora_coocurrence/P_modelling_2023.html).

[Back to table of contents ⤒](#a-repository-for)

## References
Faurby, Søren, Rasmus Ø Pedersen, Matt Davis, Simon D. Schowanek, Scott Jarvie, Alexandre Antonelli, and Jens-Christian Svenning. 2020. MegaPast2Future/PHYLACINE_1.2: PHYLACINE Version 1.2.1. Zenodo. https://doi.org/10.5281/zenodo.3690867.
Hassanin, Alexandre, Géraldine Veron, Anne Ropiquet, Bettine Jansen van Vuuren, Alexis Lécu, Steven M. Goodman, Jibran Haider, and Trung Thanh Nguyen. 2021. “Evolutionary History of Carnivora (Mammalia, Laurasiatheria) Inferred from Mitochondrial Genomes.” PLOS ONE 16 (2): e0240770. https://doi.org/10.1371/journal.pone.0240770.
Hirt, Myriam R., Marlee Tucker, Thomas Müller, Benjamin Rosenbaum, and Ulrich Brose. 2020. “Rethinking Trophic Niches: Speed and Body Mass Colimit Prey Space of Mammalian Predators.” Ecology and Evolution 10 (14): 7094–7105. https://doi.org/10.1002/ece3.6411.
Poelen, Jorrit H., James D. Simons, and Chris J. Mungall. 2014. “Global Biotic Interactions: An Open Infrastructure to Share and Analyze Species-Interaction Datasets.” Ecological Informatics 24 (November): 148–59. https://doi.org/10.1016/j.ecoinf.2014.08.005.
Soria, Carmen D., Michela Pacifici, Moreno Di Marco, Sarah M. Stephen, and Carlo Rondinini. 2021. “COMBINE: A Coalesced Mammal Database of Intrinsic and Extrinsic Traits.” Ecology 102 (6): e03344. https://doi.org/10.1002/ecy.3344.

[Back to table of contents ⤒](#a-repository-for)