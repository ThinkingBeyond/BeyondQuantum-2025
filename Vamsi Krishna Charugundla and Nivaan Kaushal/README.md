![BeyondQuantum Banner for Research Projects](../BeyondQuantum_Banner_Research_Projects_2025.png)

# Utilizing Quantum Entanglement for Fluid Dynamics Simulations

## Project Description 
Our project presents a study on quantum fluid dynamics simulations by modeling fluid flow around a circular obstacle on a 2D spatial grid. The quantum simulation leverages quantum entanglement and superposition to encode fluid behavior using qubits, with each fluid cell represented as a quantum state. The classical counterpart employs conventional numerical methods to simulate flow and velocity fields.
Both simulations are executed on an N×N grid, incorporating identical domain boundaries, obstacle masking, and flow source placement. The quantum simulation uses gates like Hadamard, CNOT, and Ry(π/6) to simulate directionally biased fluid movement and entanglement between neighboring qubits. Post-processing involves collecting measurements from 4096 quantum circuit executions, normalizing the velocity data, and applying Gaussian filters to smooth the result.
The outcome demonstrates that quantum circuits can successfully capture key fluid dynamics characteristics such as flow diversion around obstacles, symmetry in the velocity field, and smoothed gradients. Comparative centerline velocity profiles show qualitative agreement between the quantum and classical results, validating the quantum approach’s effectiveness in simplified fluid flow modeling.

## MOTIVATION
We aimed to explore whether quantum computing especially through the use of quantum entanglement and superposition could provide a scalable alternative. By encoding fluid properties into quantum states and constructing a lattice grid through qubit interactions, we hypothesized that quantum simulations could reproduce realistic flow patterns with fewer computational resources. This was motivated by the increasing computational cost and complexity of classical fluid dynamics simulations, particularly when modeling flow around obstacles or within irregular geometries. Traditional methods require solving complex partial differential equations and often become inefficient as spatial resolution increases.

## Research Question 
Classical fluid dynamics simulations are computationally intensive, especially when modeling complex interactions near obstacles. This project explores a quantum circuit based framework to simulate simplified fluid behavior using quantum entanglement and superposition on a 2D lattice grid.

## Implementation
***Quantum computational fluid dynamics***
- To implement code we need to install all required packages. Below is the package file to install all packages at once .
- Package file: :[requriment.txt]()
    - After above step completed then implementing this below colab notebook for Quantum CFD
    - In this notebook we did all setup to quantum circuit framework for quantum cfd
- Notebook: [`QCFD.ipynb`](https://github.com/ThinkingBeyond/BeyondQuantum-2025/blob/75d5e6e019b686684e43b6bcd524f2da2c5d65cf/Vamsi%20Krishna%20Charugundla%20and%20Nivaan%20Kaushal/QCFD.ipynb)
   ***classical computational fluid dynamics***
     - Next we implement this  below classical CFD colab notebook
     - In this below notebook we setup a framework for classical cfd .
- Notebook: [`CCFD.ipynb`](https://github.com/ThinkingBeyond/BeyondQuantum-2025/blob/75d5e6e019b686684e43b6bcd524f2da2c5d65cf/Vamsi%20Krishna%20Charugundla%20and%20Nivaan%20Kaushal/QCFD.ipynb)

## Results


This below results are of Quantum CFD for ***adjacent Neighbours*** in the grid .
![Adjacent Neighbours](https://github.com/ThinkingBeyond/BeyondQuantum-2025/blob/fbfa48a74b8fad7e07071f49c0bdaeb1111e8c2f/Vamsi%20Krishna%20Charugundla%20and%20Nivaan%20Kaushal/adjacent_neighbours.png)


For ***Adjacent neighbours and Diagonal Neighbours***
![Adjacent Neighbours and Diagonal Neighbours ](https://github.com/ThinkingBeyond/BeyondQuantum-2025/blob/4a398fda03b3c2b2ffa646478347565fbb2794b9/Vamsi%20Krishna%20Charugundla%20and%20Nivaan%20Kaushal/adjacent%2Bdiagonal_neighbours.png)



This is comparitive result on Quantum CFD and classical CFD on one factor i.e velocity

![comparison Q and C ](https://github.com/ThinkingBeyond/BeyondQuantum-2025/blob/4a398fda03b3c2b2ffa646478347565fbb2794b9/Vamsi%20Krishna%20Charugundla%20and%20Nivaan%20Kaushal/comparison.png)


## Conclusions
In this  project we demonstrates a quantum circuit-based approach for simulating fluid flow on a 2D grid. Each fluid cell is represented by a qubit, with superposition and entanglement modeling local interactions. Obstacle regions are excluded using binary masks, allowing realistic simulation of flow constraints. Quantum measurements are processed using normalization and Gaussian smoothing, revealing velocity patterns that closely match classical simulations. The results which are discussed above confirm that quantum circuits can effectively capture essential features of fluid dynamics, offering a promising alternative for future simulation tasks.

## Future Improvements
    1. Extending the simulation to 3 dimensions.
    2. Including more mesh types like shapes and airfoils.
    3. Displaying time step evolution or animations .
    4. Implementing more quantities such as pressure, density to provide more complete results.
    5. Increasing the gridsize for more accurate and insightful results, currently limited by compute power of Quantum Computing.
    
## References
1. Meng, Z., et al. (2024)."Simulating unsteady fluid flows on a superconducting quantum processor."[https://arxiv.org/abs/2404.15878 ](https://arxiv.org/abs/2404.15878)
2. Sanavio, C., & Succi, S. (2024)."Quantum Computing for Simulation of Fluid Dynamics."[https://arxiv.org/abs/2404.01302 ](https://arxiv.org/abs/2404.01302)
3. Qiskit Tutorials .[Qiskit Tutorials ](https://qiskit.github.io/qiskit-aer/tutorials/index.html)
4. Sauro Succi et al . (2024). ‘Classical and quantum computational methods for fluid flow simulation: A comparative study.’[click here](https://www.sciencedirect.com/science/article/abs/pii/S0045793023003730)

---

> The research poster for this project can be found in the [BeyondQuantum Proceedings 2025](https://thinkingbeyond.education/beyondquantum_proceedings_2025/).

