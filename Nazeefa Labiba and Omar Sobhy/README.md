![BeyondQuantum Banner for Research Projects](../BeyondQuantum_Banner_Research_Projects_2025.png)

### Evaluating QSVM's Scalability: A Comparative Analysis with Classical Support Vector Machines

### Introduction
SVMs are really useful machine learning algorithm. One of the main drawbacks of this algorithm is that it doesnot work for large scale data . Quantum Machine Learning gives us the advantage of computing large scale data with better efficiency using Kenrnel method. 

## Research Question

Does QSVM solve the scalability issues of classical SVM ?

## Motivation
Solving the scalability issues of SVM can open the doors towards solving bigger real life classification problems. It will give useful insights in the real life bigger datas. It will also become a very important application of Quantum Computation 

## Our Experiment:

To compare the scalability of SVM and QSVM we implemented both classical and quantum SVM in the same dataset. We conducted some thorough literature review to understand the current state of this research

The basic understanding of QSVM code was taken form this link:
- [Implementation of QSVM in Qiskit](https://github.com/Qiskit/platypus/blob/main/notebooks/summer-school/2021/resources/lab-notebooks/lab-3.ipynb )

### Table of comparison of different factors from literature review

| Paper Title | Approach | Data Size | Features | Feature Map | Scaling Performance | Other Results |
|-------------|----------|-----------|----------|-------------|---------------------|---------------|
| Quantum Support Vector Machine for Classification and Regression Problems | Hybrid | 1,000 samples | 10-12 (PCA reduced) | Angle Embedding (RX/RY) | Classical better | Better classification metrics |
| Quantum Support Vector Machine for Big Data Classification | Hybrid | <500 samples | N/A | Not specified | Classical better | No QSVM advantages |
| An Enhanced Approach for Predicting Air Pollution Using Quantum Support Vector Machine | Hybrid | 500-2,000 | Multiple indicators | Custom quantum map | Not compared | Better prediction accuracy |
| Quantum Machine Learning for Finance: Short-Term Stock Price Prediction | Hybrid | Large scale | 20+ | Hardware-efficient | QSVM scaled better | Quantum advantage (>50 qubits) |
## Future investigations:
In our study , we saw that classical SVM had better scaling in case of small scale data. Incase of middle and large scale data , the prediction of QSVMs were better. In one of the cases for a very large scale data, QSVM showed better scaling. More experiments on real life very large data datasets should be done for reaching a conclusion in this matter . We used only hybrid approaches in our study. Fully Quantum approaches can give different results


## References

- [Quantum Support Vector Machine for Classification and Regression Problems](https://arxiv.org/pdf/2407.09930)  
- [Quantum Support Vector Machine for Big Data Classification](https://or.niscpr.res.in/index.php/IJPAP/article/view/2306/613)  
- [An Enhanced Approach for Predicting Air Pollution Using Quantum Support Vector Machine](https://www.researchgate.net/publication/383427878_An_enhanced_approach_for_predicting_air_pollution_using_quantum_support_vector_machine)  
- [Quantum Machine Learning for Finance: Short-Term Stock Price Prediction](https://arxiv.org/abs/2306.00881)  

---

> The research poster for this project can be found in the [BeyondQuantum Proceedings 2025](https://thinkingbeyond.education/beyondquantum_proceedings_2025/).

