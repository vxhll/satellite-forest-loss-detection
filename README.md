# Satellite-Based Vegetation Change Detection and Forest-Loss Screening

A remote-sensing project that compares satellite imagery from 2021 and 2025 to identify potential vegetation decline and investigate possible forest loss using independent tree-cover data.

## Overview

This project uses HLS Sentinel-2 surface-reflectance imagery, the Normalized Difference Vegetation Index (NDVI), and Hansen Global Forest Change data to screen for areas that warrant further investigation.

## Tech Stack

- Python
- NumPy, Matplotlib and SciPy
- Rasterio and PyProj
- Google Colab
- HLS Sentinel-2 satellite data
- Hansen Global Forest Change

## Workflow

1. Load satellite red and near-infrared bands.
2. Apply cloud and cloud-shadow quality masks.
3. Calculate NDVI for March 2021 and March 2025.
4. Compare pixels with valid observations in both years.
5. Identify candidate vegetation decline using an NDVI-change threshold of -0.15.
6. Group connected candidate pixels into regions.
7. Cross-check candidates against historical tree-canopy cover and recorded tree-cover loss.
8. Export georeferenced GeoTIFFs and visualization maps.

## Preliminary Results

- **212 pixels** flagged for NDVI decline, approximately 19.08 hectares.
- **70 pixels** in the largest candidate cluster, approximately 6.30 hectares.
- **68 pixels** in that cluster met the historical canopy-cover threshold of 30% in 2000.
- **56 pixels** overlapped Hansen-recorded tree-cover loss during 2021–2025.
- **54 pixels**, approximately 4.86 hectares, met both screening criteria.

Recorded tree-cover loss within the largest candidate cluster occurred in 2023, 2024, and 2025.

## Outputs

- Final combined candidate map
- NDVI-change GeoTIFF
- Combined candidate-class GeoTIFF
- Hansen loss-year GeoTIFF

## Limitations

This project performs preliminary vegetation-change and forest-loss screening; it does not confirm deforestation.

Only 14.11% of the study-area crop had valid observations in both selected satellite scenes. The historical canopy-cover layer represents 2000, and recorded tree-cover loss does not necessarily indicate permanent deforestation.

Additional clear satellite observations, a more recent forest-cover baseline, and independent validation are required before drawing definitive conclusions.

## Future Improvements

- Analyze multiple satellite observations to reduce cloud-related gaps.
- Improve forest-cover classification and validation.
- Evaluate candidate areas against independent reference data.
- Develop an interactive map for exploring detected changes.

## Author

**Vishal J**

- GitHub: https://github.com/vxhll
- LinkedIn: https://www.linkedin.com/in/vishal-j-btech
