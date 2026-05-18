# Harborton Frog Taxi: Predictive Modeling for Amphibopteran Migration

This repository houses the end-to-end data processing and predictive machine learning pipeline for the **Harborton Frog Taxi** (traditionally known as the Frog Shuttle). This volunteer-led conservation initiative safely transports Northern Red-Legged Frogs across Highway 30 in Portland, Oregon, protecting them from vehicular mortality during their critical seasonal breeding migrations.

The operational goal of this project is to model migration timing and direction to help coordinators predict peak volunteer staffing requirements and mitigate roadkill risks.

## Project Overview

The project workflow tackles over a decade of messy, non-standardized field logs to build a predictive framework:
**Data Ingestion & Quality Control (`frog_data_cleaner.qmd`):** Aggregates and reconciles 12 seasonal Excel workbooks spanning 2014 to 2026. It standardizes shifting schemas, eliminates metadata tabs, fixes temperature anomalies, and handles missing data.

### Biological Context: Understanding "Up" vs. "Down"
* **Total Frogs Down:** Frogs migrating *toward* the breeding wetland.
* **Total Frogs Up:** Frogs migrating *away* from the wetland, returning to their upland forest habitats.
* **Total Live Frogs:** The overall active migration volume counted by volunteers for a given night.

---

## Repository Structure

```text
├── frog_data/               # Directory containing raw seasonal Excel logs (.xlsx)
├── README.md                # Project documentation
├── requirements.txt         # Python package dependencies
└── frog_data_cleaner.qmd    # Quarto script for data wrangling and validation
```

## Getting Started
1. Clone the Repository

```
Bash
git clone [https://github.com/georgiakirkpatrick/harborton_frog_shuttle.git](https://github.com/georgiakirkpatrick/harborton_frog_shuttle.git)
cd harborton_frog_shuttle
```

2. Environment Setup

Install the necessary package dependencies utilizing pip.

Mac: `pip3 install -r requirements.txt`

Windows: `pip install -r requirements.txt`

3. Raw Data Requirements

Before executing the scripts, place your raw Excel workbooks inside the /frog_data folder.

File names must strictly follow the format: frog_log_YYYY_YY.xlsx (e.g., frog_log_2024_25.xlsx).

Individual worksheets within the files should correspond to specific months (e.g., "December 2014", "January 2015").

## Detailed Pipeline Breakdown
### Phase 1: Data Cleaning & Wrangling

The frog_data_cleaner.qmd notebook dynamically parses all historical worksheets to output a clean master dataset (combined_frog_data.csv):  

* Automatically strips out non-log reference tabs (e.g., "Legend", "Moon Phases", "Labels").  

* Skips trailing "Total" rows and structural notes dynamically by locating the final valid date indices.  

* Maps variations in volunteer logging names (e.g., merging leaders into a single captain name).  

* Uses regex patterns to recover stray dates written across text columns. It also flags temperature anomalies, converting accidental Celsius entries (0∘C to 15∘C) to Fahrenheit.

### Phase 2: Feature Engineering & Dual-Stage Modeling

To be added by teammates.