![BeyondQuantum Banner for Research Projects](../BeyondQuantum_Banner_Research_Projects_2025.png)

# Solving Traveling Salesman Problem using VQE

## Repository Hierachy

```bash
.
└── BeyondQuantum-2025/
    └── Ose Igue and Akshay Kushwaha and Nabin Pandey/
        ├── README.md                                 
        ├── Research Stage Graphs and Visuals/        
        │   ├── Konigsberg_visual.jpg                 
        │   ├── bitStrings.png                        
        │   ├── graphNetwork.png                     
        │   └── relativeErrrorChart.png               
        └── TSP Research Stage/                       
            ├── Classsical Approach to TSP/          
            │   ├── Classical approach - insights.docx     
            │   ├── TSP Iterative - Classical Implementation.ipynb   
            │   ├── TSP Recursive - Classical Implementation.ipynb   
            │   └── TSP___Classical_Approach.pdf      
            └── Quantum Approach to TSP/              
                ├── Hard Code QUBO Implementation/
                │   ├── QUBO_Implementation_of_Traveling_Salesman_Problem_Using_Variational_Quantum_Eigensolvers_documentation.pdf  
                │   └── QUBO_Implementation_of_Traveling_Salesmen_Problem_Final.ipynb   
                └── QUBO Implementation with Libraries/
                    ├── Map_to_Ising.ipynb            
                    └── Map_to_Ising_Second_Iteration.ipynb  
```



## Research Question

<p align="center">
  <img src="Research%20Stage%20Graphs%20and%20Visuals/Konigsberg_visual.jpg" alt="Image" width="500"/>
</p>

In order to reinforce the foundations of fundamental Graph Theory, let's briefly introduce the Königsberg Bridge Problem posed by Leonard Euler in mid-1700s in the bustling city of Königsberg, Prussia. Euler posed an interesting investigation in regard to the wide array of bridges in Königsberg connecting the main central island to the rest of the city above water canals. Euler's investigation revolves around the interesting general question regarding the possibility of a pedestrian crossing all bridges only once to reach a desired destination. Through methodically deriving the connection between the amount of Bridges (Edges) and the amount of Regions (Nodes), Euler was able to mathematically prove that it is impossible for a pedestrian to cross all bridges in Königsberg only once. Euler's investigation into the Königsberg's Bridge Problem cascaded into the development of a vast mathematical field which Euler called at the time Geometry of Positions, but in the current times, it is known as Graph Theory. 

To connect the Königsberg's Bridge Problem to the Traveling Salesmen Problem, we can imagine a pedestrian competing in a marathon who is very self-conscious about his marathon time through the race. During this race, the pedestrian will have to cross a variety of bridges and islands and must cross through all islands in order to complete successfully complete the Marathon. The Pedestrian realizes that in order to complete the Marathon in the least amount of time, he will need to figure out the shortest paths between each Island and figure out the ideal configuration of paths so he visits all of the islands and finishes the race in the least amount of time. This is known as the Traveling Salesmen Problem and this is known as a NP-Complete Problem proving its difficulty to solve given Algorithmic Runtime Models. Our aim in regard to the Traveling Salesmen Problem would be to apply Variational Quantum Eigensolvers (VQEs) to more optimally resolve this problem.

## Motivation for the Project Implementation

The Traveling Salesman Problem (TSP) stands as a quintessential example of a combinatorial optimization problem whose exact solution becomes prohibitively expensive for classical computers as the number of cities increases. Classical algorithms designed to find the optimal tour, such as Dynamic Programming, suffer from exponential time complexity, rendering them impractical for instances involving more than a few dozen cities. This computational bottleneck necessitates the exploration of alternative paradigms.

Quantum computing has emerged as a promising avenue for potentially accelerating the solution of certain computational problems, including optimization. Various quantum algorithms and heuristics are being developed and investigated for their applicability to NP-hard problems like TSP. The approach outlined in [10], which proposes encoding TSP distances into the phases of quantum states and utilizing the Quantum Phase Estimation algorithm to extract path costs, represents a specific technique leveraging fundamental quantum properties.

While theoretical analyses often suggest potential quantum speedups, the practical performance of these algorithms on current and near-term quantum hardware or simulators is not always immediately apparent due to factors such as qubit count limitations, noise, circuit depth constraints, and simulation overheads. Dynamic Programming, despite its unfavorable theoretical worst-case complexity for large N, is a well-understood and often efficient exact method for small to moderately sized TSP instances on classical hardware.

Therefore, the primary motivation for this experiment is to conduct a direct, empirical comparison between the practical performance of a classical Dynamic Programming solver and a quantum algorithm based on phase encoding and Quantum Phase Estimation for the Traveling Salesman Problem. By executing both approaches on a range of small TSP instances using readily available codebases and simulation tools, we aim to:

Gain concrete, hands-on experience with the implementation and execution of a specific quantum optimization algorithm.
Quantify the runtime performance of the quantum simulation approach relative to an established classical method on scales where both are feasible.
Identify and highlight the practical overheads and current limitations of the quantum simulation compared to classical computation for this problem.
Provide empirical data to support discussions on the current feasibility and future potential of quantum phase-based encoding techniques for combinatorial optimization.

This comparison is crucial for bridging the gap between theoretical quantum speedup claims and the observed performance on existing or simulated quantum systems, offering valuable insight into the current state of quantum computation for practical problem-solving.

## Tutorial on How to Install the Necessary Libraries and Run the Project

- Steps to install the Libraries
    - Download the Map_to_Ising Google Collaboratory and open it within Google Chrome.
    - After Reading the initial Instruction, please **run the first cell** containing the list of libraries and tools needed for the execution of this codebase
    - Tinker and test the Quantum Approach to the Traveling Salesmen Problem

Note: Printing out the Relative error between the Energies of the Classical Approach and the Quantum Approach takes a significant amount of time.

## Implementation of the Traveling Salesmen Problem in the Quantum Setting

To begin with the implementation of the Traveling Salesmen Problem in the Quantum Setting, a weighted directed graph must be generated which could be bi-directional and uni-directional. In a normal standpoint in order to generate a graph instance, we would be utilizing an Adjacency List or an Adjacency Matrix where a index (node) maps to another index (node) with the value at that index being the weight. In our implementation of the Codebase, we utilized the NetworkX libraries which makes generating graphs quicker and simpler to deal with our Quantum Implementation code.

<p align="center">
  <img src="Research%20Stage%20Graphs%20and%20Visuals//graphNetwork.png" alt="Image" width="500"/>
</p>

<hr>


**Graph Visualization using NetworkX and MatplotLib**

- The library utilized in the codebase to generate the graph is used to visually represent the cities (nodes) and the distances (edges) in the Traveling Salesman Problem
    - Each node represents a city, and each edge represents the path (or distance) between two cities.
    - The colors argument allows you to specify custom colors for nodes (useful when highlighting visited cities or paths).
    - pos is the position layout dictionary that determines where each node appears on the plot.
    - The weights of the edges (distances) are also shown as labels on the graph for clarity.
 
In order to have a guideline to compare the Quantum Implementation and determine its effectiveness, we have implemented the Classical Approach to the Traveling Salesmen Problem using Dynamic Programming to cover and explore all different permutations and routes.


<hr>


**Brute Force Solution to the Traveling Salesman Problem**

- For our implementation of the Classical Approach to the Traveling Salesmen Problem, we utilized a function to resolve the different permutations with the steps below.
    - brute_force_tsp(w, N) takes the adjacency matrix w and number of nodes N and tries all possible permutations of cities (excluding the start node 0) to find the optimal route.
    - For each permutation:
    - It calculates the total distance traveled if the salesman follows that path and returns to the starting node.
    - If this distance is less than the previously best-known distance, it updates the best solution and prints it.
    - Finally, it returns the best distance and corresponding order of nodes visited.
 
<hr>

**QUBO Formulation and Implementation**

- Now to create the Quantum Implementation, we utilized the QUBO Formulation and formatted our Adjacency List into a Quadratic Program where the variables contain within represent:
    - Binary variables representing whether a city is visited at a specific position.
    - Objective function that encodes the total distance traveled.
    - Constraints that enforce a valid Hamiltonian cycle:
    - Each city is visited exactly once.
    - Each position in the tour is occupied by exactly one city.
 
<hr>


**Convert to Ising Model and Solve VQE**

- The Ising Model comprises of:
    - A Hamiltonian operator (qubitOp) that describes the energy landscape of the problem.
    - An offset value that accounts for constant shifts in the energy.
 
We can then use the Ising Model to compare energy landscapes in the next section and be resolved using MininiumEigenOptimizer.

<hr>

**Comparing Classical Approach and Quantum Approach using Relative Error Plots**

In this section, we use a Variational Quantum Eigensolver (VQE) algorithm to solve the TSP. VQE is a hybrid quantum-classical algorithm that can find the minimum eigenvalue of a Hamiltonian, which corresponds to the optimal TSP solution.

- Optimizer and Ansatz:

    - The Simultaneous Perturbation Stochastic Approximation (SPSA) optimizer is used for VQE, with a maximum of 300 iterations (maxiter=300). This optimizer helps in minimizing the energy (Hamiltonian) through a series of iterations.
The ansatz, a parameterized quantum circuit, is chosen as a TwoLocal circuit with the ry rotation and cz entanglement gates. This is repeated 5 times (reps=5), with a linear entanglement structure.
VQE Setup:

    - We initialize the VQE with the chosen optimizer (SPSA) and ansatz (ry). The quantum state is prepared by applying the parameterized ansatz, and the energy is minimized iteratively.
Compute Minimum Eigenvalue:

    - The compute_minimum_eigenvalue(qubitOp) method computes the eigenvalue of the Hamiltonian, which corresponds to the optimal TSP solution.
The energy (the minimum eigenvalue) is printed out, and the optimization time (result.optimizer_time) is also displayed.
Sampling and Interpreting the Solution:

    - The most likely state (result.eigenstate) is sampled using tsp.sample_most_likely(), and it is checked for feasibility using qubo.is_feasible(x).
The solution is interpreted using tsp.interpret(x) to retrieve the node visit order for the TSP path.

    - The optimal path is visualized using draw_tsp_solution(tsp.graph, z, colors, pos).
 
- To compare the Classical Approach and the Quantum Approach, we calculated the relative Error Plot where:

    - Larger values mean the algorithm found a less optimal solution.
    - The bar chart shows this comparison visually, highlighting which method performs best.

<p align="center">
  <img src="Research%20Stage%20Graphs%20and%20Visuals/relativeErrrorChart.png" alt="Image" width="500"/>
</p>

## Future Work and Conclusion

**Conclusion based on Calculated Results**

Based on our visualizations of the relative error plot, we can utilize that the Quantum Approach made from the QUBO Implementation and Ising Model utilizes far less energy compared to the Brute Force Approach and it showcases the sheer power that the Quantum Approach posesses in large instances of the Traveling Salesmen Problem where the Classical Approach may fail or Runtime on. In other words, the distance between the exact result shown in the bar chart and the distance of the Quantum Approach are closer than the distance between the exact result shown in our bar chart and the distance of the Classical Approach suggesting that the Quantum Approach succeeds in utilizing less energy and is far more efficient for large TSP instances.

<hr>


**Future Work on the Project**

Future work can explore improved ansatz designs to enhance circuit expressibility and convergence. Testing noise mitigation techniques will be crucial as we scale to larger TSP instances on NISQ devices. Hybrid quantum-classical methods could also offer better scalability by combining quantum optimization with classical heuristics. Additionally, benchmarking VQE against algorithms like QAOA and analyzing different initialization strategies can provide deeper insights and improve generalizability across diverse TSP problems.

## References

Here’s your list of references reformatted into the requested markdown style:

1. Tilly, J., Chen, H., Cao, S., Picozzi, D., Setia, K., Li, Y., ... & Tennyson, J. (2022). *The Variational Quantum Eigensolver: a review of methods and best practices*. arXiv preprint arXiv:2111.05176.

2. IBM Quantum. (n.d.). *Max-Cut and Traveling Salesman Problem*. Qiskit Optimization Tutorials. Retrieved from https://qiskit-community.github.io/qiskit-optimization/tutorials/06_examples_max_cut_and_tsp.html#Max-Cut-problem

3. Applegate, D. L., Bixby, R. E., Chvátal, V., & Cook, W. J. (2006). *The traveling salesman problem: A computational study*. Princeton University Press.

4. Harishaseebat92. (n.d.). *Quantum Inspired Optimization: QOSF Cohort 10 Documentation* [PDF]. GitHub. Retrieved from https://github.com/harishaseebat92/Quantum_Inspired_Optimization/blob/main/Documentation/QOSF_coh10_doc.pdf

---

> The research poster for this project can be found in the [BeyondQuantum Proceedings 2025](https://thinkingbeyond.education/beyondquantum_proceedings_2025/).

