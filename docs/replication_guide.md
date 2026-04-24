# Replication Guide

This guide provides step-by-step instructions to replicate the analysis for the thesis on retirement, volunteering, and health.

## Prerequisites

- R version 4.3 or later
- Access to SOEP v41 data (see data_raw/README_data_access.txt)
- Required R packages (see README.md for the complete list)

## Step-by-Step Replication

### 1. Setup

1. Clone this repository
2. Open the project in RStudio
3. Place SOEP data files in the `data_raw/` directory
4. Update the root data path in the scripts

### 2. Install Dependencies

```r
install.packages("renv")
renv::restore()
```

### 3. Run Analysis Scripts in Order

#### Script 1: Dataset Builder
```r
source("code/01_dataset_builder.R")
```
This script:
- Loads raw SOEP data
- Constructs analysis variables
- Creates the analysis sample
- Saves the processed dataset

#### Script 2: Descriptives
```r
source("code/02_descriptives.R")
```
This script:
- Produces summary statistics
- Creates descriptive tables
- Generates sample composition visualizations

#### Script 3: Empirical Strategy
```r
source("code/03_empirical_strategy.R")
```
This script:
- Estimates regression models
- Tests the moderation hypothesis
- Produces tables of results

#### Script 4: Conceptual Diagram
```r
source("code/04_conceptual_diagram.R")
```
This script:
- Creates the conceptual model diagram
- Generates visualization of key relationships

### 4. Output

All results are saved in the `output/` directory:
- `output/figures/` - Generated plots and diagrams
- `output/tables/` - Summary tables and model results
- `output/models/` - Model objects and detailed results

## Troubleshooting

- Ensure all file paths are correctly specified for your system
- Check that all required packages are installed
- Verify SOEP data files are in the correct format

## Contact

For questions about replication or data access, refer to the main README.md file.