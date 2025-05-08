# surroVision3D - CCS Reservoir Modeling with Deep Learning

This repository contains implementations and experiments of several deep learning models for predicting **Pressure Buildup (PBU)** and **Gas Saturation** in carbon capture and storage (CCS) reservoir simulations. The models were evaluated on various 2D/3D datasets with differing spatial and temporal resolutions.

## Notebooks Available

* `UFNO.ipynb` – U-FNO model using Fourier Neural Operators.
* `Vanilla_UNet.ipynb` – Experiments on 1500-sample PBU dataset using U-Net and ResNet.
* `CNN.ipynb` – Lightweight CNN architecture for PBU.
* `GNN.ipynb` – Graph Neural Network implemented to estimate gas saturation.

## Models Implemented

* **Convolutional U-Net**
  A deep encoder–decoder architecture with skip connections for learning multiscale spatial–temporal features.

* **U-FNO (Fourier Neural Operator)**
  Captures global spatial dependencies through spectral convolutions (FFT-based), especially effective for smooth geophysical fields like PBU.

* **Graph Neural Network (GNN)**
  Treats the reservoir as a graph of connected cells, learning from node features and neighbor relationships. Uses dynamic EdgeConv layers with residual connections for local spatial interactions.

* **ResNet**
  A residual convolutional network adapted for temporal prediction with limited data.

* **CNN**
  A lightweight convolutional network baseline for pressure buildup prediction.

## Pretrained Models & Outputs

You can access all models, results, and visualizations through this OneDrive folder:

🔗 [Model & Output Files (OneDrive)](https://imperiallondon-my.sharepoint.com/:f:/g/personal/kps24_ic_ac_uk/EtgQF8kGmINKt9voqcrK1T4BSSR_7W08w4e352vq-2ZOjw?e=kRYtFD)

## Evaluation Metrics

The models are compared using the following metrics:

* **R² Score**: Coefficient of determination (goodness of fit)
* **MAE**: Mean Absolute Error
* **Size**: Model memory footprint

| Model                   | # Training Samples | R² (PBU) | R² (Gas) | MAE (PBU) | MAE (Gas) |    Size |
| ----------------------- | -----------------: | -------: | -------: | --------: | --------: | ------: |
| **CNN**                 |              1,000 |     0.65 |      N/A |      7.25 |       N/A | 2.42 MB |
| **Convolutional U-Net** |              2,500 |     0.96 |     0.87 |      1.31 |      0.02 |  180 MB |
| **U-FNO**               |              1,500 |     0.97 |     0.86 |      1.20 |      0.03 |    3 GB |
| **ResNet**              |                150 |     0.77 |      N/A |     10.78 |       N/A | 45.6 MB |
| **Graph Neural Net**    |              3,500 |     0.89 |     0.91 |      2.65 |      0.01 |    2 MB |

## Requirements

To set up the environment, use the provided `environment.yml` file:

```bash
conda env create -f environment.yml
```

### Core Dependencies

* Python 3.8+
* PyTorch
* TorchVision
* Torch‑Geometric
* NumPy
* Matplotlib
* Scikit‑Learn

---
