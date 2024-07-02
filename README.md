# Trustworthy-AI-Fairness-and-Security

This repository contains Jupyter notebooks exploring key concepts in Trustworthy AI, focusing on fairness and security in machine learning models.

## Notebooks Overview

### 1. TAI_HW4_FAIRNESS.ipynb

This notebook explores fairness in machine learning, specifically addressing gender bias in a binary income prediction task.

#### Key Components:
- **Data Preprocessing**: Loads and prepares a dataset containing features including gender and income.
- **Base Model Implementation**: Uses XGBoost classifier to create an initial prediction model.
- **Fairness Metrics**: 
  - Implements Zemel fairness metric: P(Y=1 | gender=MALE) - P(Y=1 | gender=FEMALE)
  - Implements disparate impact metric: P(Y=1 | gender=FEMALE) / P(Y=1 | gender=MALE)
- **Bias Mitigation**: 
  - Implements a data transformation technique to reduce gender bias.
  - Creates a new dataset by adjusting the predictions for male and female subgroups.
- **Unbiased Model**: Trains a new XGBoost model on the transformed dataset.
- **Comparative Analysis**: Evaluates and compares the fairness metrics and classification performance of the base and unbiased models.

#### Experiment Results:
The notebook demonstrates how the bias mitigation technique reduces the difference in prediction probabilities between genders, improving fairness metrics while maintaining overall classification performance.

### 2. TAI_HW4_SECURITY.ipynb

This notebook investigates the security of deep learning models, focusing on detecting and mitigating backdoor attacks in an MNIST digit classifier.

#### Key Components:
- **Model Architecture**: Implements a convolutional neural network (CNN) for MNIST classification.
- **Trigger Reverse Engineering**:
  - Defines an optimization problem to discover potential triggers in the model.
  - Uses a mask and pattern approach to visualize potential backdoors.
- **Anomaly Detection**:
  - Calculates L1 norms of the discovered masks.
  - Uses Median Absolute Deviation (MAD) to identify anomalous (potentially infected) labels.
- **Unlearning Process**:
  - Implements a fine-tuning approach to "unlearn" the backdoor.
  - Uses a mixture of clean and triggered samples in the unlearning process.

#### Experiment Flow:
1. Loads a pre-trained (potentially poisoned) model.
2. Performs trigger reverse engineering for each possible target label.
3. Analyzes the results to identify the most likely infected label.
4. Implements an unlearning procedure to mitigate the backdoor.
5. Evaluates the attack success rate before and after unlearning.

#### Key Findings:
- Demonstrates the effectiveness of the reverse engineering approach in identifying potential triggers.
- Shows how the unlearning process can significantly reduce the success rate of the backdoor attack while maintaining overall model performance.
