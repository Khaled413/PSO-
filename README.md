# Feature Selection Using Particle Swarm Optimization (PSO) in Bio-Mathematics

This project demonstrates feature selection on the **Breast Cancer dataset** using **Particle Swarm Optimization (PSO)** combined with a **Decision Tree Classifier**. It is designed as part of a **Bio-Mathematics course task**.

---

## Table of Contents
- [Introduction](#introduction)
- [Dataset](#dataset)
- [Methodology](#methodology)
  - [Particle Swarm Optimization](#particle-swarm-optimization)
  - [Fitness Function](#fitness-function)
- [Implementation Steps](#implementation-steps)
- [Results](#results)
- [Dependencies](#dependencies)
- [Usage](#usage)
- [License](#license)

---

## Introduction
Feature selection is a key step in improving model performance and interpretability. This project uses PSO to automatically select the most informative features from the Breast Cancer dataset to train a Decision Tree Classifier.

---

## Dataset
The project uses the **Breast Cancer Wisconsin dataset** from `sklearn.datasets`. It consists of:

- **Number of features:** 30  
- **Number of samples:** 569  
- **Target:** Malignant (0) or Benign (1) tumors

---

## Methodology

### Particle Swarm Optimization
PSO is an optimization algorithm inspired by the social behavior of birds and fish. Particles explore the search space to find the optimal subset of features by updating their velocities and positions based on **personal best** and **global best** scores.

### Fitness Function
The fitness function evaluates the quality of a feature subset by combining:
- **Classification error** from cross-validation using a Decision Tree
- **Fraction of features selected** to penalize large subsets

The goal is to **minimize the fitness score**.

---

## Implementation Steps
1. **Import libraries**: `numpy`, `sklearn` modules
2. **Load and split dataset**: Training (80%) and Testing (20%)
3. **Initialize PSO parameters**:
   - Number of particles
   - Maximum iterations
   - Inertia weight, cognitive & social coefficients
4. **Run PSO loop**:
   - Update particle velocities and positions
   - Evaluate fitness scores
   - Update personal and global bests
5. **Select optimal features** and train a Decision Tree
6. **Evaluate model performance** on test data:
   - Compare accuracy using all features vs selected features

---

## Results
- **Number of selected features:** `X` (based on final PSO output)  
- **Selected features:** `List of features`  
- **Accuracy with selected features:** `accuracy_selected`  
- **Accuracy with all features:** `accuracy_all`  

This shows how PSO can effectively reduce dimensionality while maintaining high model accuracy.

---

## Dependencies
- Python >= 3.8  
- numpy  
- scikit-learn  

Install dependencies via pip:

```bash
pip install numpy scikit-learn
