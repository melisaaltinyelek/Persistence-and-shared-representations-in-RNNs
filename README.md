# Persistence and Shared Representations in Recurrent Neural Networks

**Research Project | Cognitive Science – Artificial Intelligence & Neuroscience | Universität Osnabrück**

**Tech Stack:** Python · TensorFlow · Keras · LSTM · NumPy · Pandas · SciPy · Statsmodels · Matplotlib

## Overview

This project investigates the relationship between **representation persistence, shared neural representations, and task-switching interference** in recurrent neural networks.

In cognitive science, task switching describes the ability to transition between different tasks or cognitive processes. When multiple tasks rely on shared internal representations, information retained from a previous task may interfere with subsequent processing.

Building on the research of Musslick and Cohen (2019), which investigated these mechanisms using feedforward neural networks, this project explores how persistence and shared representations can be studied using an **LSTM-based recurrent neural network**.

The project combines deep learning, computational cognitive modeling, experimental data generation, and statistical analysis.

## Research Objectives

The project investigates four central questions:

1. **Representation Persistence:** How can recurrent neural networks model the persistence of information over time?
2. **Shared Representations:** How might overlapping task representations contribute to interference between tasks?
3. **Task Switching:** How does the timing of task-related information affect network performance when switching tasks?
4. **Learning and Evaluation:** How can model accuracy across experimental conditions help characterize task-switching behavior?

## Model Architecture

The neural network is implemented using TensorFlow and Keras, with a Long Short-Term Memory (LSTM) architecture.

The implementation includes:

- An `LSTM` layer for sequential information processing.
- A fully connected output layer with nine neurons and `softmax` activation.
- The Adam optimizer.
- Mean Squared Error (MSE) as the training loss.
- Accuracy as an evaluation metric.

LSTMs are particularly relevant to this research because their recurrent structure enables information to be maintained and updated across time steps.

The model is trained on generated task sequences and evaluated under different task-switching conditions.

## Methodology

### 1. Experimental Data Generation

Training and evaluation samples are generated programmatically to represent task sequences and task-switching scenarios.

The experimental setup includes:

- Multiple task combinations.
- Sequential input and output representations.
- Task-switching conditions.
- Variation in task-cue positions.
- Separate training and evaluation datasets.

These controlled conditions allow the relationship between task-switching behavior and model performance to be investigated.

### 2. Model Training

The LSTM is trained on generated input-output sequences using TensorFlow/Keras.

The implementation includes:

- Configurable LSTM units, learning rates, and batch sizes.
- Training with the Adam optimizer.
- Tracking training loss and accuracy.
- A configurable MSE-based stopping criterion.
- Custom Keras callbacks for evaluating performance during training.

The repository also contains a saved model in HDF5 format.

### 3. Task-Switching Evaluation

Model performance is evaluated across two experimental task combinations:

- **Condition A&B**
- **Condition A&C**

The evaluation examines accuracy across different cue positions, allowing performance to be compared under different temporal conditions.

The implementation tracks:

- Accuracy for individual cue positions.
- Accuracy across experimental conditions.
- Changes in performance over training epochs.
- Training loss and accuracy.

### 4. Statistical Analysis

The analysis uses Python-based statistical methods to examine differences in model performance.

The analysis code includes:

- Two-way ANOVA with interaction terms.
- Welch's independent-samples t-test.
- Accuracy comparisons across experimental conditions.
- Mean and standard deviation calculations.
- Visualization of training and evaluation metrics.

The statistical analysis helps investigate whether task conditions and cue timing are associated with differences in network accuracy.

## Repository Structure

| File | Description |
|---|---|
| `LSTM_model.py` | LSTM implementation, training, callbacks, and evaluation |
| `CreateTrainingTestingSamples_switchTASKnotSTIMULI.py` | Generation of experimental training and evaluation samples |
| `Analysis.py` | Statistical analysis and visualization |
| `df_training_samples_for_conditioning.csv` | Training dataset |
| `df_validation_samples_for_evaluation.csv` | Evaluation dataset |
| `df_AB_all_accuracies_run1.csv` | Accuracy results for condition A&B |
| `df_AC_all_accuracies_run1.csv` | Accuracy results for condition A&C |
| `loss_df_run1.csv` | Recorded training loss and accuracy |
| `frozen_model.h5` | Saved neural network model |
| `requirements.txt` | Python dependencies |

## Technologies

**Deep Learning**
- TensorFlow and Keras
- Long Short-Term Memory (LSTM) networks
- Recurrent neural networks

**Data Processing**
- Python
- NumPy
- Pandas

**Statistical Analysis**
- SciPy
- Statsmodels
- ANOVA
- Welch's t-test

**Visualization**
- Matplotlib
- Accuracy and loss curves
- Comparative performance visualizations

## Installation

Clone the repository:

`git clone https://github.com/melisaaltinyelek/Persistence-and-shared-representations-in-RNNs.git`

Navigate to the project directory:

`cd Persistence-and-shared-representations-in-RNNs`

Install dependencies:

`pip install -r requirements.txt`

The repository contains separate scripts for experimental data generation, LSTM training, and statistical analysis.

Some dataset paths and configurations may need adjustment before reproducing the original experiments.

## Research Scope

This project was developed as a collaborative research project in Cognitive Science at the Universität Osnabrück.

Its primary objective is to investigate computational mechanisms of representation persistence and task-switching interference using recurrent neural networks.

The repository demonstrates practical experience in:

- Designing and implementing LSTM architectures with TensorFlow/Keras.
- Generating controlled experimental datasets.
- Training and evaluating recurrent neural networks.
- Implementing custom model evaluation procedures.
- Analyzing model performance across experimental conditions.
- Applying statistical hypothesis-testing methods to machine learning results.
- Connecting deep learning methods with cognitive science research.

The project focuses on computational experimentation and scientific analysis rather than production deployment.

## Research References

1. Musslick, S., & Cohen, J. D. (2019). *A mechanistic account of constraints on control-dependent processing: Shared representation, conflict and persistence.* pp. 849–855.

2. Musslick, S., Saxe, A. M., Dey, B., Henselman, G., & Cohen, J. D. (2017). *Multitasking capability versus learning efficiency in neural network architectures.* pp. 829–834.

## Contributors

- **Melisa Altinyelek** — [GitHub](https://github.com/melisaaltinyelek)
- **Jenny Arndt** — [GitHub](https://github.com/jearndt)
