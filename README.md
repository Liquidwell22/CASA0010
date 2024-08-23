# Enhancing Road Safety in London: A Data-Driven Approach to Assessing and Mitigating Killed and Seriously Injured (KSI) Casualties
## Research Question
Can we develop a model that, by integrating complex variables, assesses the severity of casualties (whether KSI or not) in road traffic accidents?
## Data Source
Office for National Statistics (ONS) (2015). [Super Output Area Population (LSOA, MSOA), London](https://data.london.gov.uk/dataset/super-output-area-population-lsoa-msoa-london)

Office for National Statistics (ONS) (2024). [Statistical Geographies](https://www.ons.gov.uk/methodology/geography/ukgeographies/statisticalgeographies)

Office for National Statistics (ONS) (2021). [2021 Census: Ward and LSOA Estimates](https://data.london.gov.uk/census/2021-ward-and-lsoa-estimates)

Ministry of Housing, Communities & Local Government (MHCLG) (2019). [Indices of Deprivation](https://data.london.gov.uk/dataset/indices-of-deprivation)

OpenStreetMap Wiki, 2024. [OpenStreetMap Wiki](https://wiki.openstreetmap.org/wiki)

## Workflow Analysis
### Data Collection and Data Preprocessing
1. Download the points for shops and bus stops in London locally (see code in OSM.ipynb).
2. Clean the data tables for London accident data, IMD scores, and each LSOA's population and commuting numbers from the census, cleaning NA values (code see in Preprocess.ipynb).
3. Calculate the density using the geometry of the LSOAs and the population and commuting numbers for each LSOA from the census (code see in Preprocess.ipynb).
4. Use GIS neighborhood analysis to calculate the total number of shops and bus stops within a certain range of each London accident data point (code see in Preprocess.ipynb).
5. Merge all the above data by LSOA and casualty index (code see in Preprocess.ipynb).
6. Perform one-hot encoding on the merged categorical data (code see in Preprocess.ipynb).
### Conduct EDA on the Merged Data Table, Create Maps, Tables, and Figures (see EDA.ipynb)
1. Feature Engineering (see EDA.ipynb)
2. VIF Analysis
3. Feature Selection using Random Forest MDA (results figure see in Output.ipynb)
4. Normalization
### Modelling, Comparison, and Validation (see Models.ipynb)
1. Spatial K-fold Cross-Validation
2. Overfitting and Underfitting Steps
3. Comparison of XGB and Logistic Regression (results figure seen in Output.ipynb)
4. Validation of the optimal XGB model on unseen 2023 data (data cleaning for 2023 seen in Validation.ipynb)
5. Compare the feature importance in XGB for the two selected areas, City of London and Barking and Dagenham
