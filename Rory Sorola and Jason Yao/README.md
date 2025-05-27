![BeyondQuantum Banner for Research Projects](../BeyondQuantum_Banner_Research_Projects_2025.png)

# VQE - The Effect of Varying Ansatze on the Variational Quantum Linear Solver Algorithm (VQLS)

The group members for this project are Jason Yao and Rory Sorola, mentored by Mr. Ansari. In this project, we investigate how different ansatze affect the performance of the VQLS (variational quantum linear solver) algorithm.

## Introduction

The variational quantum eigensolver (VQE) is a quantum algorithm used to quantum simulation and optimization problems, often to find the ground state of some Hamiltonian. It relies on the variational principle, which states that the expectation value of the Hamiltonian is always greater than or equal to the ground state energy, so, by minimizing what observed value from the Hamiltonian, we should eventually converge on the ground state. The algorithm starts with a parameterized ansatz, or guess for the solution's wavefunction, and finds the expectation value with respect to the Hamiltonian. Then, a classical optimizer is used to adjust those parameters and minimize the obtained expectation value and improve the guess. We can see that this algorithm thus combines quantum processing for computation and a classical optimizer.

The variational quantum linear solver (VQLS) is an algorithm similar to the VQE, but is designed for solver linear systems. This algorithm arises naturally from how we view quantum systems and quantum circuits, with the quantum state represented as a vector and gates as a linear operator, or matrix. Thus, applying some unitary operator A on a quantum state x (Ax) in a circuit is equivalent to multiplying the matrix with the vector. To apply the VQLS algorithm to solve some linear system Ax=b, we should thus model x as our initial parameterized ansatz (x($\theta$)). The quantum process done with each iteration should be in applying the A operator to the quantum state x($\theta$). We want to maximize how close Ax($\theta$) and b are, so we can define our cost function as 1-fidelity, and from there use a classical optimizer to adjust the parameters. The final output, with a minimized cost function, should have x($\theta$) be some scale factor of the true x vector.

## Research Question

Our research question is how different ansatze for the initial parameterized guess affects the performance when executing the variational quantum linear solver (VQLS) algorithm, an extension of the variational quantum eigensolver (VQE).

## Motivation

The variational quantum linear solver is a relatively novel approach of finding (or approximating) solutions to a linear system of equations, based on the idea of the variational quantum eigensolver for ground state energies. An efficient execution of the VQLS could be a relatively simple way of demonstrating the idea of quantum advantage, so by finding how our choice of ansatz affects the performance of the algorithm, we can optimize our execution of it. In our experiment, we also conduct other trials to test the limits of this algorithm, in hopes to see both how we can improve on it and how noise and other factors of modern, limited quantum computers restrict the algorithm’s usage.


## Methodology

We use Qiskit's framework for quantum circuits, and Qiskit's circuit library to import the ansatze implemented in the code (EfficientSU2, TwoLocal, PauliTwoDesign, RealAmplitudes). We implement the VQLS algorithm as outlined above, finding the cost function to be minimized as 1 - the fidelity between the Ax($\theta$) and b states, found by saving both as statevectors on the Aer simulator. The cost function is then minimized using the COBYLA optimizer. We generate several graphs of the cost function being minimized as a function of time for the different ansatze with controlled values for the A matrix, b vector, and $\theta$ parameters. We also run the algorithm and compare how the the algorithm performs as the ansatz scales up, by increasing the size of the system (number of qubits), as well as the reps of the ansatz. 

## Outline of the Jupyter Notebooks

The first notebook, titled "vqls_experiment.ipynb", contains most of the raw code for and executions of the algorithm with different specifications. 
Outline:
- Defining the basic functions for the execution of the algorithm
  - Running the algorithm for two-qubit systems, for complex coefficients with three ansatze EfficientSU2, TwoLocal, and PauliTwoDesign
  - Running the algorithm for four-qubit systems, for complex coefficients with the same three ansatze
- Implementing the algorithm for the RealAmplitudes ansatz, using matrices/vectors with real coefficients
- Analysis of the algorithm for increased circuit depth
  - Drawing the circuits and finding the # of parameters as a function of the number of qubits and reps, for each of the four ansatze
  - Running the VQLS algorithm for varying reps of the ansatz (1-8
    - For two-qubit systems
    - For four-qubit systems
    - Direct comparison between EfficientSU2 and TwoLocal ansatze, as reps increase
- Extension of the VQLS for more general linear systems
  - For more general vectors (not necessarily normalized)
  - For systems of arbitrary size

The second notebook runs the algorithm many times for each ansatze and examines only the final outputs for each trial. For each of the tested ansatz, the algorithm is run 100 times normally and 100 times with a constant noise model. The final fidelities, total iterations until convergence, and total time taken were recorded for each trial and plotted. The ansatze tested were: EfficientSU2, PauliTwoDesign (with 2 reps), PauliTwoDesign (with 5 reps), TwoLocal, and RealAmplitudes. Two-qubit systems were tested for all trials. The plots made were scatter plots for final fidelity vs. number of iterations and time taken vs. number of iterations for each ansatz, both for no-noise and noisy trials.


## Future Work

Our work, so far, only implements the algorithm using the Aer simulator to "evaluate" the quantum circuit and find the statevectors for Ax($\theta$); future work should be done to actually implement this on quantum hardware, such as by using IBM Qiskit's backends with SamplerV2 or EstimatorV2. Further, though we extend the VQLS algorithm farther than simply linear operators in quantum systems and quantum states, we do not address how the algorithm could function for a non-unitary matrix A, which, in the future, could be accomplished using techniques like block encoding. 

## References

List all your references here. Remember to put links into markdown. For example:

1.  Einstein, A. (1905). *On the Electrodynamics of Moving Bodies*. Annalen der Physik, 17, 891-921. [Internet Archive](https://archive.org/details/einstein-1905-relativity)

**Tip**: *If you have you references in BibTex, Google Scholar or Zotero*
1. Create/copy a list into ChatGPT
2. Ask it to turn it into an unsorted list in markdown

---

> The research poster for this project can be found in the [BeyondQuantum Proceedings 2025](https://thinkingbeyond.education/beyondquantum_proceedings_2025/).

