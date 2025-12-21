![BeyondQuantum Banner for Research Projects](../BeyondQuantum_Banner_Research_Projects_2025.png)

# Exoplanet Detection from Kepler Mission Data: Comparing Classical and Quantum Approaches

**Author:** Siddharth Kumar Gopal  
**Mentor:** Gerhard Hellstern  

This project compares **classical Convolutional Neural Networks (CNNs)** and **quantum / hybrid quantum–classical models** for exoplanet detection using Kepler mission data. The study evaluates performance metrics and computational feasibility using identical datasets.

---

## Research Question

**How do quantum and hybrid quantum–classical machine learning models compare with classical CNNs for exoplanet detection using Kepler mission data, in terms of F1 score, recall, precision, and runtime?**

---

## Motivation

Classical CNNs are effective for exoplanet detection but require extensive hyperparameter tuning. With growing interest in quantum machine learning, this project investigates whether **quantum approaches can achieve comparable classification performance** or offer complementary advantages when applied to real astronomical data.

---

## Dataset Description

- Source: **NASA Exoplanet Archive**
- Initial samples: ~7,300
- Original features: ~29
- After removing flags and biased indices: **12 features**
- Labels:
  - 2,743 confirmed exoplanets
  - 4,581 false positives
- Training subset:
  - 2,000 confirmed exoplanets
  - 3,500 false positives

---

## Method and Implementation

### Classical CNN

- CNN trained with systematic hyperparameter tuning
- Tuned parameters:
  - Learning rate (0.001 → 0.01)
  - Activation functions: ReLU, LeakyReLU, ELU, tanh
  - Convolutional filter counts
  - Dense layer sizes
- Best performance observed at **learning rate = 0.07**

### Quantum / Hybrid Model (VQC)

- Hybrid quantum–classical supervised learning framework
- Implemented using **PennyLane**
- Techniques used:
  - Angle encoding
  - BasicEntanglerLayers
  - Variational Quantum Classifier (VQC)
  - Gradient-free optimization using **COBYLA**
- Feature compression reduced inputs to **4 qubits** (3 rotations)

---

## Results

All values below are **directly taken from the research poster**.

| Model Type | F1 Score | Recall | Precision | Runtime |
|-----------|----------|--------|-----------|---------|
| Classical CNN | **0.814** | **0.865** | 0.814 | ~1 minute |
| Quantum VQC | 0.664 | **0.889** | 0.529 | ~40 minutes |

**Key observations:**
- CNN achieved the highest overall performance.
- Quantum model showed high recall but low precision.
- Quantum runtime made extensive parameter tuning infeasible.

---

## Conclusions

- Classical CNNs **outperform quantum models** in both accuracy and efficiency.
- Quantum models demonstrate **non-trivial learning behavior**, but are limited by:
  - Feature compression
  - Small qubit counts
  - Long execution times
- At present, quantum approaches are **not competitive** for large-scale exoplanet classification.

---

## Future Work

- Explore improved quantum encoding strategies
- Test on larger or less compressed feature sets
- Investigate hybrid pipelines where quantum models assist classical preprocessing
- Apply methods to other astronomical classification tasks

---

## References

1. Bergholm, V., Izaac, J., Schuld, M., Gogolin, C., & Killoran, N. (2018). *PennyLane: Automatic differentiation of hybrid quantum-classical computations*. arXiv preprint arXiv:1811.04968.  
   Related experimental demonstration: Havlíček, V., Córcoles, A. D., Temme, K., et al. *Nature*, 567, 209–212 (2019).

2. Bravyi, S., Gambetta, J., & Woerner, S. (2020). *Quantum Machine Learning for Exoplanet Transit Detection*. IBM Research Technical Report.

3. Martinis, B. M. S., Salgado, C. A., & Martín-Martínez, E. (2020). *Quantum Machine Learning in Astronomy*. arXiv:2004.01401.

4. González, C. E., & Arrighi, P. (2021). *Opportunities and challenges of quantum computing for large-scale astronomical surveys*. Data Mining and Knowledge Discovery, 35, 1400–1423.

---

> The research poster for this project can be found in the  
> [BeyondQuantum Proceedings 2025](https://thinkingbeyond.education/beyondquantum_proceedings_2025/).

