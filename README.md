# surroVision3D - CCS Reservoir Modeling with Deep Learning

This repository contains implementations and experiments of several deep learning models for predicting **Pressure Buildup (PBU)** and **Gas Saturation** in carbon capture and storage (CCS) reservoir simulations. The models were evaluated on various 2D/3D datasets with differing spatial and temporal resolutions.

## Notebooks Available

- `UFNO.ipynb` – U-FNO model using Fourier Neural Operators.
- `Vanilla_UNet.ipynb` – Experiments on 1500-sample PBU dataset using U-Net and ResNet.
- `CNN.ipynb` – Lightweight CNN architecture for PBU.
- `GNN.ipynb` – Graph Neural Network implemented to estimate gas saturation

## Models Implemented

- **Convolutional U-Net**  
  A deep encoder-decoder architecture with skip connections for learning multiscale spatial-temporal features.

- **U-FNO (Fourier Neural Operator)**  
  Captures global spatial dependencies through spectral convolutions, especially effective for smooth geophysical fields like PBU.

- **Graph Neural Network (GNN)**  
  Leverages structured grid information and neighborhood relations, showing excellent generalization for gas saturation prediction.

- **ResNet**  
  A residual convolutional network adapted for temporal prediction with limited data.

## Pretrained Models & Outputs

You can access all models, results, and visualizations through this OneDrive folder:

🔗 [Model & Output Files (OneDrive)](https://imperiallondon-my.sharepoint.com/:f:/g/personal/kps24_ic_ac_uk/EtgQF8kGmINKt9voqcrK1T4BSSR_7W08w4e352vq-2ZOjw?e=kRYtFD)

## Evaluation Metrics

Models are compared using:

- \( R^2 \) Score: Goodness of fit
- MAE: Mean Absolute Error
- Size: Model memory footprint (MB/GB)

## Requirements

- Python 3.8+
- `torch`, `torchvision`, `torch-geometric`
- `matplotlib`, `numpy`, `scikit-learn`


