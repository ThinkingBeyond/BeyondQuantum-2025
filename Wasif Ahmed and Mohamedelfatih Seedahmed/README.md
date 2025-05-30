# Sparse Fourier Signal Reconstruction Using QAOA

## Research Question

How well can the Quantum Approximate Optimization Algorithm (QAOA) identify the most significant Fourier coefficients to reconstruct a sparse periodic signal using a limited number of terms?

## Motivation

Our goal was to investigate whether QAOA can approximate a sparse signal by selecting the best K Fourier coefficients out of a set of N = 20.

## Method and Implementation

1. We constructed a synthetic signal using a Fourier basis of N = 20 terms, where only 4 frequency components had non-zero amplitudes.
2. The task of selecting the best K coefficients (sparsity level) was formulated as a Quadratic Unconstrained Binary Optimization (QUBO) problem.
3. We then converted the QUBO into an Ising Hamiltonian compatible with QAOA.
4. Using Qiskit's implementation of QAOA (with p=2 layers and COBYLA optimizer), we executed the algorithm to identify the optimal subset of coefficients.
5. We repeated the process for sparsity levels K = 1 to 20 and measured reconstruction error (MSE) compared to the full signal.
6. The signal was reconstructed using only the selected coefficients, and we plotted both the real signal and reconstructed signal over time.

## Results and Discussion

* **Signal Recovery**: The reconstructed signal from QAOA-selected coefficients closely matched the original signal, even with only K=5 components.
* **MSE Analysis**: The Mean Squared Error dropped significantly as K increased, demonstrating that QAOA effectively prioritizes the most informative frequencies. Two occasional peaks in MSE appeared, likely due to suboptimal parameter convergence by the classical optimizer.
* **Insights**: Once all significant frequencies were captured, the reconstruction error approached zero. This validates the suitability of QAOA for sparse approximation tasks.

![download (3)](https://github.com/user-attachments/assets/14c95db8-d414-453b-b77d-7bcc38219445)
*Figure: Original vs QAOA-Reconstructed Signal*

![download (2)](https://github.com/user-attachments/assets/07aa2985-ca36-42e2-86e2-a7a6a6053f3c)
*Figure: MSE vs Sparsity Level and Sparsity vs K*

## Conclusion

This project demonstrates that QAOA can be successfully applied to sparse Fourier signal reconstruction problems. Even with shallow circuit depth and a small number of shots, the algorithm approximated the dominant frequency components and minimized signal error. The approach is scalable and adaptable to other forms of sparse recovery.

## Future Work

* Explore deeper QAOA circuits (larger p) and compare with classical optimization benchmarks.
* Investigate other signal models (non-Fourier, noisy, or structured sparsity).
* Test alternative classical optimizers (e.g., SPSA, Adam) or warm-start techniques to reduce MSE variance.
* Run on real quantum hardware to assess performance under noise.

## References

1. Glover, F., Kochenberger, G., & Du, Y. (2019). *A Tutorial on Formulating and Using QUBO Models*. [arXiv:1811.11538](https://arxiv.org/abs/1811.11538)
2. Ceroni, J. (2020). *Intro to QAOA*. PennyLane Demos. [Link](https://pennylane.ai/qml/demos/tutorial_qaoa_intro/)
3. Bernal, D. (2022). *Ising and QUBO Lecture Slides*. [Link](https://bernalde.github.io/QuIPML/slides/QUIP%20and%20QML%20Lecture%205%20-%20Ising%20and%20QUBO.pdf)

---

Let me know if you want this saved into a `.md` file you can upload directly to GitHub.
