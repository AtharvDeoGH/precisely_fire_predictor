# Wildfire Risk Analysis — Carson City, NV (K-Means)

End-to-end geospatial clustering to classify property-level wildfire risk in Carson City, Nevada. The project blends cleaned property attributes with external wildfire incident data to produce actionable risk segments for underwriting, pricing, and mitigation planning.

## Overview
We address the challenge of pricing wildfire exposure more accurately by combining deduplicated property records with nearby wildfire history. Using distance to past incidents, incident frequency, and building attributes, we cluster properties into distinct risk groups and translate those groups into business guidance.

## Data
- **Precisely property dataset (deduped):** `data/Precisely_Data_Deduped.xlsx`
- **External wildfire incidents:** `data/Fire_External_Data.xlsx`
- **Merged modeling table:** `data/Main_Dataset.xlsx`
- **(Optional) Intermediate clustering table:** `data/PIF_Data_Clustering.xlsx`
- **Project report (PDF):** `reports/Wildfire_Risk_Analysis_Report.pdf`

> File names above are repo-friendly versions of your originals: “Precisely Data Duplicates Removed.xlsx”, “Fire External Data.xlsx”, “Main Dataset.xlsx”, “PIF Data CLustering.xlsx”, and “Group 3_ Wildfire Risk Analysis Report.docx-3.pdf”.

## Methodology
### 1) Data prep
- Remove duplicate addresses/units; standardize identifiers.
- Validate coordinates; keep address/ID fields for labeling only.
- Join external wildfire incidents to properties (e.g., nearest-event lookup) to derive proximity/frequency features.

### 2) Feature engineering
- **Distance from nearest fire (km)** and **historical incident frequency** near each property.
- Building/parcel attributes (e.g., bedrooms, building type) as potential risk correlates.
- Scale numeric features (z-score) for distance-based clustering.

### 3) Clustering & validation
- Primary algorithm: **K-Means**.
- Choose *k* using elbow & silhouette heuristics; run stability checks across random seeds.
- Post-hoc profiling: per-cluster feature means, z-score heatmaps, and top differentiators.

## Results (at a glance)
- Distinct, interpretable **risk segments** emerge with clear differences across:
  - Proximity to prior wildfires and local incident frequency
  - Housing/structure characteristics that correlate with exposure
- The analysis provides a basis for **premium differentiation**, **inspection prioritization**, and **targeted mitigation**.

