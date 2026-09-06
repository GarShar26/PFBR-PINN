# Models

This folder is intended for trained model files generated during the PINN experiments.

## Model

The project includes experiments with neural-network-based models for predicting core neutronics variables using time and reactivity as inputs.

The trained model was exported in Keras/HDF5 format for potential integration and deployment.

## Model Outputs

The model predicts the following quantities:

- Power (`p`)
- Precursor concentrations (`C1`–`C6`)

## Note

Trained model files are not included in the repository at this stage because they may be large and/or dependent on restricted project data.

The notebook `pinn_test31.ipynb` contains the model architecture and training implementation.
