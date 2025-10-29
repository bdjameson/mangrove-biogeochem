# 🌿 Mangrove Microprofile Data Processing

[![R ≥ 4.3](https://img.shields.io/badge/R-≥4.3-blue.svg)](https://www.r-project.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Manuscript Status](https://img.shields.io/badge/Status-Under%20Review%20at%20GRL-orange.svg)]()

This repository provides all code, data, and documentation for processing and modeling **mangrove sediment microprofile data** collected before and after a hurricane disturbance in Bermuda.  
The workflows support **sensor drift correction**, **calibration**, and **PROFILE model input generation** for quantifying microscale redox zonation and biogeochemical fluxes.

> 🧾 **Citation:** Jameson, B. D., Moran, T. H., Hendrikx, C., Sawall, Y., & Grundle, D. S.(2025). *Hurricane disturbance alters surface sediment redox chemistry and stimulates N₂O consumption in a subtropical mangrove stand.* Manuscript submitted for review in *Geophysical Research Letters.*

---

## 📁 Repository Structure

    ├── compiled-data/                # Combined datasets (microprofiles, metadata, calibration, porosity)
    ├── corrected-profiles/           # Drift-corrected and calibrated profiles
    ├── hobo-data/                    # HOBO logger temperature and light data
    │
    ├── 01_microprofile_processing.Rmd      # Drift correction, calibration, export
    ├── 01_microprofile_processing.html     # Knitted HTML report
    ├── 02_generate_PROFILE_inputs.Rmd      # Generation of PROFILE input .txt files
    │
    └── README.md

---

## ⚙️ Workflow Overview

### 1. Microprofile Data Processing (`01_microprofile_processing.Rmd`)
- Imports compiled datasets and metadata.  
- Applies signal drift correction using a time-dependent model.  
- Calibrates sensor output using experiment-specific coefficients.  
- Adjusts profiles to baseline and exports cleaned datasets.  
- Produces quality-control and diagnostic plots for all analytes.

### 2. PROFILE Model Input Generation (`02_generate_PROFILE_inputs.Rmd`)
- Loads corrected and calibrated profiles.  
- Formats data into `.txt` files following PROFILE model conventions.  
- Exports analyte-specific input files for redox reaction modeling.

---

## 📊 Data Overview

| Folder | Description |
|---------|-------------|
| **compiled-data** | Contains microprofile data, calibration coefficients, porosity measurements, and experimental metadata. |
| **corrected-profiles** | Final drift-corrected and calibrated profiles used for modeling. |
| **hobo-data** | HOBO temperature and light logger data associated with incubation experiments. |

---

## 🚀 Quick Start

1. **Clone this repository:**
   ```bash
   git clone https://github.com/bdjameson/mangrove-biogeochem.git
   cd mangrove-biogeochem