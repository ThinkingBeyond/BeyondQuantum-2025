![BeyondQuantum Banner for Research Projects](../BeyondQuantum_Banner_Research_Projects_2025.png)

# Utilizing Quantum Entanglement for Fluid Dynamics Simulations

## Project Description 
Our project presents a study on quantum fluid dynamics simulations by modeling fluid flow around a circular obstacle on a 2D spatial grid. The quantum simulation leverages quantum entanglement and superposition to encode fluid behavior using qubits, with each fluid cell represented as a quantum state. The classical counterpart employs conventional numerical methods to simulate flow and velocity fields.
Both simulations are executed on an N×N grid, incorporating identical domain boundaries, obstacle masking, and flow source placement. The quantum simulation uses gates like Hadamard, CNOT, and Ry(π/6) to simulate directionally biased fluid movement and entanglement between neighboring qubits. Post-processing involves collecting measurements from 4096 quantum circuit executions, normalizing the velocity data, and applying Gaussian filters to smooth the result.
The outcome demonstrates that quantum circuits can successfully capture key fluid dynamics characteristics such as flow diversion around obstacles, symmetry in the velocity field, and smoothed gradients. Comparative centerline velocity profiles show qualitative agreement between the quantum and classical results, validating the quantum approach’s effectiveness in simplified fluid flow modeling.

## MOTIVATION
Classical fluid dynamics simulations have become increasingly complex and computationally expensive, especially when modeling large or highly detailed systems. This project was motivated by the potential for quantum computing, particularly quantum entanglement and superposition, to offer an alternative that may reduce computational load while maintaining physical accuracy. By investigating how fluid properties can be encoded into quantum states and simulated through qubit interactions, we aim to explore the feasibility of quantum computing for simulating fluid flow and computational fluid dynamics. 

## Research Question 
Can quantum computing, using principles such as superposition and entanglement, simulate fluid dynamics on a 2D grid, and how does its performance compare to Classical Methods?

## Implementation

***Phase 1: Domain Setup***
- Define an N×N grid as the spatial domain.
- Create a circular obstacle mask
- Define the fluid region by excluding the obstacle.
- Select inflow source points
  
***Phase 2: Quantum Circuit Construction***
- Initialize a circuit with N² qubits.
- Apply Hadamard gates to source qubits to inject amplitude.
- Use CNOT gates to entangle fluid neighbors 
- Apply Ry(π/6) rotations to fluid qubits for directional flow.
  
***Phase 3: Simulation & Data Processing***
- Simulate the circuit on qasm_simulator.
- Run 4096 shots; collect measurement outcomes.
- Map results to 2D grid positions and normalize by max fluid value.
  
***Phase 4: Visualization***
- Smooth data with filters
- Visualize using nearest and bicubic interpolation 

***Quantum Computational Fluid Dynamics Implementation***
- Notebook: [`QCFD.ipynb`](https://github.com/ThinkingBeyond/BeyondQuantum-2025/blob/75d5e6e019b686684e43b6bcd524f2da2c5d65cf/Vamsi%20Krishna%20Charugundla%20and%20Nivaan%20Kaushal/QCFD.ipynb)

***Classic Computational Fluid Dynamics Implementation***
- Notebook: [`CCFD.ipynb`](https://github.com/ThinkingBeyond/BeyondQuantum-2025/blob/75d5e6e019b686684e43b6bcd524f2da2c5d65cf/Vamsi%20Krishna%20Charugundla%20and%20Nivaan%20Kaushal/QCFD.ipynb)

## Results


This below results are of Quantum CFD for ***adjacent Neighbours*** in the grid .
![Adjacent Neighbours](https://github.com/ThinkingBeyond/BeyondQuantum-2025/blob/fbfa48a74b8fad7e07071f49c0bdaeb1111e8c2f/Vamsi%20Krishna%20Charugundla%20and%20Nivaan%20Kaushal/adjacent_neighbours.png)


For ***Adjacent neighbours and Diagonal Neighbours***
![Adjacent Neighbours and Diagonal Neighbours ](https://github.com/ThinkingBeyond/BeyondQuantum-2025/blob/4a398fda03b3c2b2ffa646478347565fbb2794b9/Vamsi%20Krishna%20Charugundla%20and%20Nivaan%20Kaushal/adjacent%2Bdiagonal_neighbours.png)



This is a comparative result on Quantum CFD and classical CFD on one factor i.e velocity

![comparison Q and C ](https://github.com/ThinkingBeyond/BeyondQuantum-2025/blob/4a398fda03b3c2b2ffa646478347565fbb2794b9/Vamsi%20Krishna%20Charugundla%20and%20Nivaan%20Kaushal/comparison.png)


## Conclusions
In this project, we developed and compared quantum and classical circuit-based frameworks for simulating fluid flow on a 2D grid. The quantum approach successfully replicated general flow behavior and demonstrated the feasibility of simulating fluid interactions using quantum states. However, while the quantum model showed potential for scalability in representing complex interactions, it incurred significantly longer computation times than the classical method. These results suggest that although quantum CFD holds theoretical promise, practical implementation will require improvements in quantum hardware and optimization techniques to achieve competitive performance.

## Future Improvements
    1. Extending the simulation to 3 dimensions.
    2. Including more mesh types like shapes and airfoils.
    3. Displaying time step evolution or animations.
    4. Implementing more quantities such as pressure, density to provide more complete results.
    5. Increasing the gridsize for more accurate and insightful results, currently limited by compute power of Quantum Computing.
    
## References
1. Meng, Z., et al. (2024)."Simulating unsteady fluid flows on a superconducting quantum processor." (https://arxiv.org/abs/2404.15878)
2. Sanavio, C., & Succi, S. (2024)."Quantum Computing for Simulation of Fluid Dynamics." (https://arxiv.org/abs/2404.01302)
3. Qiskit Tutorials. (https://qiskit.github.io/qiskit-aer/tutorials/index.html)
4. Sauro Succi et al. (2024). ‘Classical and quantum computational methods for fluid flow simulation: A comparative study.’ (https://www.sciencedirect.com/science/article/abs/pii/S0045793023003730)

---

> The research poster for this project can be found in the [BeyondQuantum Proceedings 2025](https://thinkingbeyond.education/beyondquantum_proceedings_2025/).

