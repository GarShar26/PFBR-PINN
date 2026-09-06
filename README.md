# Physics-Informed Neural Network for Core Neutronics

## Overview

This repository contains the implementation of a **Physics-Informed Neural Network (PINN)** developed for modeling core neutronics behavior in the context of the **Prototype Fast Breeder Reactor (PFBR) Operator Training Simulator**.

The project was undertaken as part of an **AI/ML internship at the Indira Gandhi Centre for Atomic Research (IGCAR)**.

The objective was to investigate the application of deep learning and physics-informed learning techniques for approximating the behavior of reactor neutronics variables while incorporating governing physical relationships into the model training process.

---

## Objectives

The primary objectives of the project were:

* Develop a neural network model for reactor core neutronics variables.
* Investigate the application of **Physics-Informed Neural Networks (PINNs)** to the problem.
* Incorporate physical constraints into the neural network loss function.
* Preprocess and normalize simulation data for model training.
* Experiment with different neural network architectures.
* Evaluate model predictions against available simulation data.
* Explore model deployment considerations for integration with a simulator environment.

---

## Problem Statement

Traditional numerical simulations can require significant computational resources when repeatedly solving complex physical models.

This project explores whether a neural-network-based surrogate model can learn the underlying dynamics of core neutronics while respecting known physical relationships.

A PINN combines conventional data-driven learning with physics-based constraints by incorporating the governing equations into the training objective.

The general loss function used in this project can be represented as:

$$
L_{total} =
\lambda_1 L_{data}
+
\lambda_2 L_{physics}
+
\lambda_3 L_{IC}
$$

where:

* $L_{data}$ represents the error between predicted and simulation data.
* $L_{physics}$ represents the physics-based constraint.
* $L_{IC}$ represents the initial-condition constraint.
* $\lambda_1$, $\lambda_2$, and $\lambda_3$ are weighting coefficients.

---

## Dataset

The model was trained using simulation data containing time-dependent reactor variables.

The dataset includes variables such as:

| Variable  | Description                               |
| --------- | ----------------------------------------- |
| `time`    | Time variable                             |
| `rho`     | Reactivity-related input                  |
| `p`       | Reactor power-related variable            |
| `C1`–`C6` | Neutron precursor-related state variables |

The primary model inputs are:

```text
time
rho
```

and the model predicts:

```text
p
C1
C2
C3
C4
C5
C6
```

Before training, the data was preprocessed and normalized to improve neural-network training stability.

> **Note:** The repository does not contain any confidential, proprietary, or restricted IGCAR data.

---

## Methodology

The overall workflow followed in the project was:

```text
Simulation Data
       ↓
Data Preprocessing
       ↓
Normalization / Scaling
       ↓
Train-Test Preparation
       ↓
Neural Network
       ↓
Physics-Informed Loss
       ↓
Model Training
       ↓
Validation
       ↓
Prediction & Evaluation
```

The PINN training process combines the available data with physics-based information so that the model is encouraged to satisfy both the observed data and the underlying physical relationships.

---

## Model Development

Different neural-network approaches were investigated during the project, including:

* Feedforward Neural Networks
* Long Short-Term Memory (LSTM) networks
* Convolutional Neural Networks (CNN)
* Physics-Informed Neural Networks (PINNs)

The primary implementation in this repository focuses on the **PINN approach**.

The implementation uses deep-learning frameworks including:

* TensorFlow
* Keras
* PyTorch

The trained model was also explored for conversion and deployment considerations in a C/C++ simulator environment.

---

## Technologies Used

### Programming Language

* Python

### Machine Learning / Deep Learning

* TensorFlow
* Keras
* PyTorch
* NumPy
* Pandas

### Data Visualization

* Matplotlib

### Development Environment

* Jupyter Notebook
* Anaconda

---

## Repository Structure

```text
IGCAR-PINN/
│
├── pinn_test31.ipynb
├── README.md
│
└── results/
    └── ...
```

The primary notebook is:

```text
pinn_test31.ipynb
```

It contains the main implementation, including data preprocessing, model development, training, and evaluation.

---

## How to Run

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd IGCAR-PINN
```

### 2. Create a Python environment

Using Conda:

```bash
conda create -n pinn_env python=3.11
conda activate pinn_env
```

### 3. Install dependencies

```bash
pip install numpy pandas matplotlib tensorflow keras torch jupyter
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open:

```text
pinn_test31.ipynb
```

and execute the notebook cells sequentially.

> **Important:** The original training dataset is not included in this public repository if it contains restricted or institute-specific information. Users should provide an equivalent dataset with the required input/output structure to reproduce the workflow.

---

## Results

The project involved experimentation with neural-network architectures, preprocessing strategies, training configurations, and physics-informed loss components.

The resulting models were evaluated by comparing predicted state variables with the corresponding simulation values.

Representative evaluation plots and metrics can be added to this repository as the project documentation is expanded.

---

## Future Work

Potential directions for further development include:

* Improving the formulation and weighting of physics-based loss terms.
* Hyperparameter optimization for improved convergence.
* More extensive comparison between conventional neural networks and PINNs.
* Evaluation on larger and more diverse simulation datasets.
* Improved handling of temporal dependencies using recurrent architectures.
* Optimization of inference speed for simulator integration.
* Further investigation of Python-to-C/C++ model deployment.

---

## Project Context

**Organization:** Indira Gandhi Centre for Atomic Research (IGCAR)
**Project:** Development of Physics-Informed Neural Network Model for Core Neutronics in the Context of PFBR Operator Training Simulator
**Role:** AI/ML Engineering Intern
**Duration:** June 2026 – August 2026

This repository presents the non-confidential technical aspects of the work carried out during the internship.

---

## Disclaimer

This repository is intended for educational and portfolio purposes.

The implementation and documentation provided here do not contain confidential, proprietary, or restricted information belonging to IGCAR or any associated organization.

---

## Author

Gargi Sharma

B.Tech Computer Science and Engineering
ABES Institute of Technology
