![BeyondQuantum Banner for Research Projects](../BeyondQuantum_Banner_Research_Projects_2025.png)

# Solving the Travelling Salesman Problem using the Quantum Approximate Optimisation Algorithm

## Project Description
The Travelling Salesman Problem (TSP) is an NP-hard combinatorial optimisation problem which asks, "Given a set of cities and the paths connecting different cities together, what is the shortest possible tour that visits each city exactly once and returns to the starting city?" It was found that approximate solutions to this problem can be obtained using the Quantum Approximate Optimisation Algorithm (QAOA), a specific case of the Variational Quantum Eigensolver. For our research project, we applied the QAOA to a case of the TSP to see if it is able to give us accurate approximate solutions.

## Motivation
The Travelling Salesman Problem (TSP) is a well-known NP-hard combinatorial optimisation problem. Classical algorithms struggle to solve large instances of TSP efficiently due to its computational complexity. Quantum computing, particularly variational algorithms like the Quantum Approximate Optimisation Algorithm (QAOA), offers a promising alternative by potentially providing speedup over classical methods for certain problem sizes. This is very important as the TSP has many real-world uses, which makes the ability to solve this problem quickly and give optimal solutions very important. The TSP is commonly used in route planning, manufacturing and even DNA sequencing.

## Method and Implementation
Before using QAOA to solve the TSP, we needed to learn how to convert the TSP into a Quadratic Unconstrained Binary Optimisation (QUBO) problem. We learnt about the QUBO formulation, converted the TSP into binary variables and used penalty terms to factor in the constraints, each city must be visited exactly once and each position in the tour must be filled by exactly one city. Then, we used the Ising model to convert our QUBO cost function into a cost Hamiltonian which can be applied to a quantum circuit as a unitary operator. After learning about how QAOA works and the quantum circuit structure, we used the QAOA to solve an asymmetric case of the TSP with 3 cities.

## Results and Conclusion
In the end, the QAOA outputted the optimal solution to the TSP, which was confirmed when we gave a classical algorithm the same problem to solve and they both had identical solutions. So, we can conclude that the QAOA can solve the TSP effectively and give accurate approximate solutions to it.

## Future Work
We only tested the QAOA on one specific case of the TSP so a future idea would be to apply it to more cases and see how the performance changes as the number of cities increases. Also, in the QAOA strucutre itself there are many different possible parameters you could change and investigate the effect of that on the accuracy of the solutions. For example, the number of iterations of the cost and mixer layers you apply, changing the initial state of the qubits or comparing different classical optimisation algorithms, which are used to change the parameters for the cost and mixer layers. QAOA can be applied to any combinatorial optimisation problem which can be converted into a QUBO formulation, so there are many different problems which can be tackled and researched into to see if QAOA can solve them.

## Credits
**Student Researchers**: Mariam Khaled, Ehan Sajjad
**Mentor**: Vanessa Dehn

## References

- Albornoz, C., Alonso, G., Andrenkov, M., Angara, P., Asadi, A., et al. (2024). *Variational Quantum Eigensolver*. In *Pennylane Codebook*. [https://pennylane.ai/codebook/variational-quantum-algorithms/variational-quantum-eigensolver](https://pennylane.ai/codebook/variational-quantum-algorithms/variational-quantum-eigensolver)

- Ceroni, J. (2020). *Intro to QAOA*. PennyLane Demos. [https://pennylane.ai/qml/demos/tutorial_qaoa_intro/](https://pennylane.ai/qml/demos/tutorial_qaoa_intro/)

- Glover, F., Kochenberger, G., & Du, Y. (2019). *A Tutorial on Formulating and Using QUBO Models*. arXiv. [https://arxiv.org/abs/1811.11538](https://arxiv.org/abs/1811.11538)

- Hadfield, S., Wang, Z., O'Gorman, B., Rieffel, E. G., Venturelli, D., & Biswas, R. (2019). *From the Quantum Approximate Optimization Algorithm to a Quantum Alternating Operator Ansatz*. *Algorithms, 12*(2), 34. [https://www.mdpi.com/1999-4893/12/2/34](https://www.mdpi.com/1999-4893/12/2/34)

- Johnson, D. S., & Lovász, L. A. (2001). *The Traveling Salesman Problem*. In *Combinatorial Optimization* (p. 527). Springer. [https://link.springer.com/chapter/10.1007/978-3-540-71844-4_21](https://link.springer.com/chapter/10.1007/978-3-540-71844-4_21)

- Kim, T., & Kim, S. (2024). *Quantum Algorithm for Dynamic Programming and its Application to the Traveling Salesman Problem*. arXiv. [https://arxiv.org/abs/2402.14036](https://arxiv.org/abs/2402.14036)

- Kumar, A. (2021). *Complexity Classes Simplified*. Medium. [https://anujk2901.medium.com/complexity-classes-simplified-4afb8504cb2a](https://anujk2901.medium.com/complexity-classes-simplified-4afb8504cb2a)

- Lehigh University, Department of Industrial and Systems Engineering. (2023). *QUBO Formulations of Combinatorial Optimization
Problems for Quantum Computing Devices* (No. 23T-016). [https://engineering.lehigh.edu/sites/engineering.lehigh.edu/files/_DEPARTMENTS/ise/pdf/tech-papers/23/23T_016.pdf](https://engineering.lehigh.edu/sites/engineering.lehigh.edu/files/_DEPARTMENTS/ise/pdf/tech-papers/23/23T_016.pdf)

- Premkumar, K. (2020, July 8). *Traveling Salesman Problem: Dynamic programming*. IVYMobility TechBytes. [https://medium.com/ivymobility-developers/traveling-salesman-problem-9ab623c88fab](https://medium.com/ivymobility-developers/traveling-salesman-problem-9ab623c88fab)

- Qian, W., Basili, R. A. M., Eshaghian-Wilner, M., Khokhar, A., Luecke, G., & Vary, J. P. (2023). *Comparative study of variations in quantum approximate optimization algorithms for the Traveling Salesman Problem*. arXiv. [https://arxiv.org/abs/2307.07243](https://arxiv.org/abs/2307.07243)

- Qian, W., Basili, R. A. M., Eshaghian-Wilner, M. M., Khokhar, A., Luecke, G., & Vary, J. P. (2023). *Comparative Study of Variations in Quantum Approximate Optimization Algorithms for the Traveling Salesman Problem*. *Entropy, 25*(8), 1238. [https://doi.org/10.3390/e25081238](https://doi.org/10.3390/e25081238)

- Qiskit. (2021, October 5). *Lecture 5.2 - Introduction to the Quantum Approximate Optimization Algorithm and Applications* [Video]. YouTube. [https://www.youtube.com/watch?v=YpLzSQPrgSc](https://www.youtube.com/watch?v=YpLzSQPrgSc)

- QuEra. (2025). *Hamiltonian*. [https://www.quera.com/glossary/hamiltonian](https://www.quera.com/glossary/hamiltonian)

- Quantum Inspire. (2025). *Rotation Operators*. [https://www.quantum-inspire.com/kbase/rotation-operators/](https://www.quantum-inspire.com/kbase/rotation-operators/)

- ScienceDirect Topics. (2025). *Pauli Operator*. [https://www.sciencedirect.com/topics/computer-science/pauli-operator](https://www.sciencedirect.com/topics/computer-science/pauli-operator)

- The Quantastic Journal. (2023, June). *Traveling Salesman Problem Using Quantum Computing*. Medium. [https://medium.com/the-quantastic-journal/traveling-salesman-problem-using-quantum-computing-02ae6356544b](https://medium.com/the-quantastic-journal/traveling-salesman-problem-using-quantum-computing-02ae6356544b)

> The research poster for this project can be found in the [BeyondQuantum Proceedings 2025](https://thinkingbeyond.education/beyondquantum_proceedings_2025/).

