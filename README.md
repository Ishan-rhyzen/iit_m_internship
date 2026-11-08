# Satellite Chlorophyll-a Gap Filling with Hybrid Deep Learning

This repository contains two Jupyter notebooks for training and evaluating hybrid deep learning models to reconstruct missing values in satellite-derived chlorophyll-a (Chl-a) observations.

project title :- Development of hybrid machine learning models for gap-filling of satellite derived chlorophyll-a observations.

The project was conducted as part of the IASc–INSA–NASI Summer Research Fellowship Programme 2025 at IIT Madras.
## Models

Both models combine spatial and temporal features, then use a fusion MLP to predict Chl-a for a target grid cell.

| Notebook | Model | Architecture |
|---|---|---|
| `CCM3.ipynb` | CCM | CNN–CNN–MLP |
| `CMM.ipynb` | CMM | CNN–MLP–MLP |

CCM uses convolutional branches for both spatial and temporal features. CMM uses a CNN for spatial features and an MLP for temporal features. In both models, a final MLP combines the learned representations.

## Study context

The study addresses gaps in satellite-derived Chl-a observations caused by factors such as cloud cover and atmospheric interference. The report describes a regional study area around the Palk Strait–Gulf of Mannar corridor and uses daily ESA Ocean Colour Climate Change Initiative (OC-CCI) Version 6 Chl-a data for 2014–2024.

## Reported test results

On the test split, **CCM (CNN–CNN–MLP)** achieved:

- RMSE: 0.1503 mg m⁻³
- MAE: 0.0823 mg m⁻³

**CMM (CNN–MLP–MLP)** achieved:

- RMSE: 0.2105 mg m⁻³
- MAE: 0.1031 mg m⁻³

These results are reported in the project report. CCM performed more consistently across the training, validation, and test splits.
## Repository contents and scope

This repository contains the two notebooks above, which cover model training and evaluation. It does not include the source dataset or a separate inference notebook.

## Running the notebooks

1. Open a notebook in Jupyter Notebook, JupyterLab, or a compatible editor.
2. Review its import cells and install the required Python packages.
3. Update any data paths to match your local files.
4. Run the notebook cells in order.

Reproducing the reported results requires the source data and a compatible Python environment.
