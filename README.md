# Congo Basin Mining Concession Analysis

A Python/GeoPandas and QGIS project exploring mining-concession records across the
Congo Basin. It combines resource-label standardization, country-level area summaries
and map outputs. It reflects an environmental-economics application of data analysis.

![Tenke Fungurume map](Tenke%20Fungurume%20Mine.png)

## Evidence in this repository

- `Basin.ipynb`: source-field selection, label normalization, exploratory energy-transition
  mineral classification, country summaries, maps and GeoPackage export.
- `Tenke Fungurume Mine.png`, `Kamoto Copper Company.png`, `DRC_ETM_MINING_2.png`: existing QGIS map outputs.
- `requirements.txt`: compatible dependency ranges for setting up the notebook.

## Data access and reproduction

**The source GeoPackage is not included.** The original notebook referenced a shared
research drive. This update removes that hardcoded path and requires an authorized
local dataset; it does not make restricted research data public.

```bash
pip install -r requirements.txt
# Linux/macOS:
export MINING_GPKG=/your/authorized/Congo_Basin_Mining_Concessions.gpkg
# Windows PowerShell:
# $env:MINING_GPKG='C:\data\Congo_Basin_Mining_Concessions.gpkg'
jupyter lab Basin.ipynb
```

Required fields: `COUNTRY_NAME`, `OPERATOR`, `CONC_TYPE`, `RESOURCE`, `PRIMARY_SOURCE`,
`AREA_KM2`, and geometry. In Colab, mount your own authorized Drive first and set
`MINING_GPKG` to that file. Output defaults to `outputs/Congo_Basin_Data.gpkg`;
`MINING_OUTPUT` can override it.

## October 2026 improvements

Input/output paths are configurable. Missing values are filled only in categorical
columns, preserving numeric areas and geometry. The original resource text is kept
in `RESOURCE_ORIGINAL` so substitutions can be audited. Notebook execution outputs
were cleared because the restricted source was unavailable for a fresh run. Existing
map images remain historical artifacts, not newly generated results.

## Interpretation and limitations

Concession boundaries do **not** establish the area actively mined, deforested or
otherwise damaged. Summed concession areas can double-count overlapping polygons;
unique spatial footprint would require geometry union and an appropriate projected
coordinate system. The current notebook sums the provided `AREA_KM2` field.

Resource mappings and the ETM list are exploratory and require domain review. Some
labels group ores or commodities rather than chemical elements; do not treat the
mapping as a validated mineral taxonomy. Geographic associations alone do not show
causation or a regulatory violation.

The original source description cites collaborative environmental monitoring and
acknowledges [Earth Insight](https://www.earth-insight.org/). Dataset licensing and
access permission must be confirmed with its owner. Historical README references
included [dragoooooooooon34/Spatial_Python_Project](https://github.com/dragoooooooooon34/Spatial_Python_Project);
that reference is retained here for provenance. Preview images now load locally.

[Portfolio](https://jirehandre23.github.io/Portfolio/)
