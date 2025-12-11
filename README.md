# Feature Selection using PSO for Breast Cancer Classification

## Overview
This project implements a **feature selection method using Particle Swarm Optimization (PSO)** combined with a **Decision Tree Classifier** to classify breast cancer data. The main goal is to select the most informative features from the dataset while maintaining high classification accuracy. This task is part of the **Bio-Mathematics coursework**.

---

## Dataset
- **Source:** `sklearn.datasets.load_breast_cancer()`
- **Features:** 30 numeric features describing cell nuclei properties.
- **Target:** Binary classification (malignant or benign).
- **Data Split:** 80% training, 20% testing.

---

## Methodology

### 1. Particle Swarm Optimization (PSO)
- PSO is used to optimize feature selection.
- Each particle represents a potential subset of features with values between 0 and 1.
- Features with a particle position > 0.5 are selected.
- Fitness function combines:
  - Classification error using cross-validated Decision Tree.
  - Fraction of selected features to penalize large feature sets.

### 2. Decision Tree Classifier
- Used to evaluate the predictive power of selected features.
- Accuracy is measured using cross-validation during PSO optimization and final testing.

### 3. PSO Parameters
- Number of particles: 3
- Maximum iterations: 10
- Inertia weight (w): 0.7
- Personal and global coefficients (c1, c2): 2.0
- Random factors (r1, r2): 0.5, 0.3

---

## Implementation Steps
1. Import necessary libraries.
2. Load and prepare the breast cancer dataset.
3. Initialize particles and velocities.
4. Evaluate particles using the fitness function.
5. Update personal bests and global best iteratively.
6. Determine the final selected features.
7. Train Decision Tree on selected features and evaluate on test data.
8. Compare with a model trained on all features.

---

## Results
- Number of selected features: *[dynamic based on PSO run]*
- Selected features: *[dynamic based on PSO run]*
- Accuracy with selected features: *[dynamic based on test evaluation]*
- Accuracy with all features: *[dynamic based on test evaluation]*

**Observation:** Feature selection reduces the dataset dimensionality while maintaining or improving classification performance.

---

## Usage
1. Clone the repository:
```bash
git clone https://github.com/your-username/repo-name.git
