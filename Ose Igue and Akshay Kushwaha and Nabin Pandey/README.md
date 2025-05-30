![BeyondQuantum Banner for Research Projects](../BeyondQuantum_Banner_Research_Projects_2025.png)

# Solving Traveling Salesman Problem using VQE

***Provide a description of your project including*** 

1. motivating your research question
2. stating your research question
3. explaining your method and implementation
4. Briefly mention and discuss your results
5. Draw your conclusions
6. State what future investigations 
7. State your references 

### Further Guidance: Formating
- Structure this readme using subsections
- Your job is to 
    - keep it clear
    - provide sufficient detail, so what you did is understandable to the reader. This way other researchers and future cohorts of BeyondQuantum will be able to build on your research
    - List all your references at the end
- utilise markdown like *italics*, **bold**, numbered and unnumbered lists to make your document easier to read
- if you refer to links use the respective markdown for links, e.g. `[ThinkingBeyond](https://thinkingbeyond.education/)`
- If you have graphs and pictures you want to embed in your file use `![name](your_graphic.png)`
- If you want to present your results in a table use
    | Header 1            | Header 2  |
    |---------------------|-----------|
    | Lorem Ipsum         | 12345     |

**Tip:** Use tools to create markdown tables. For example, Obsidian has a table plugin, that makes creating tables much easier than doing it by hand.

## Research Question

<p align="center">
  <img src="Research%20Stage%20Graphs%20and%20Visuals/Konigsberg_visual.jpg" alt="Image" width="500"/>
</p>

In order to reinforce the foundations of fundamental Graph Theory, let's briefly introduce the Königsberg Bridge Problem posed by Leonard Euler in mid-1700s in the bustling city of Königsberg, Prussia. Euler posed an interesting investigation in regard to the wide array of bridges in Königsberg connecting the main central island to the rest of the city above water canals. Euler's investigation revolves around the interesting general question regarding the possibility of a pedestrian crossing all bridges only once to reach a desired destination. Through methodically deriving the connection between the amount of Bridges (Edges) and the amount of Regions (Nodes), Euler was able to mathematically prove that it is impossible for a pedestrian to cross all bridges in Königsberg only once. Euler's investigation into the Königsberg's Bridge Problem cascaded into the development of a vast mathematical field which Euler called at the time Geometry of Positions, but in the current times, it is known as Graph Theory. 

To connect the Königsberg's Bridge Problem to the Traveling Salesmen Problem, we can imagine a pedestrian competing in a marathon who is very self-conscious about his marathon time through the race. During this race, the pedestrian will have to cross a variety of bridges and islands and must cross through all islands in order to complete successfully complete the Marathon. The Pedestrian realizes that in order to complete the Marathon in the least amount of time, he will need to figure out the shortest paths between each Island and figure out the ideal configuration of paths so he visits all of the islands and finishes the race in the least amount of time. This is known as the Traveling Salesmen Problem and this is known as a NP-Complete Problem proving its difficulty to solve given Algorithmic Runtime Models. Our aim in regard to the Traveling Salesmen Problem would be to apply Variational Quantum Eigensolvers (VQEs) to more optimally resolve this problem.

## Motivation

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

Graph Visualization using NetworkX and MatplotLib

- The library utilized in the codebase to generate the graph is used to visually represent the cities (nodes) and the distances (edges) in the Traveling Salesman Problem
    - Each node represents a city, and each edge represents the path (or distance) between two cities.
    - The colors argument allows you to specify custom colors for nodes (useful when highlighting visited cities or paths).
    - pos is the position layout dictionary that determines where each node appears on the plot.
    - The weights of the edges (distances) are also shown as labels on the graph for clarity.
 
In order to have a guideline to compare the Quantum Implementation and determine its effectiveness, we have implemented the Classical Approach to the Traveling Salesmen Problem using Dynamic Programming to cover and explore all different permutations and routes.

**Brute Force Solution to the Traveling Salesman Problem**

- For our implementation of the Classical Approach to the Traveling Salesmen Problem, we utilized a function to resolve the different permutations with the steps below.
    - brute_force_tsp(w, N) takes the adjacency matrix w and number of nodes N and tries all possible permutations of cities (excluding the start node 0) to find the optimal route.
    - For each permutation:
    - It calculates the total distance traveled if the salesman follows that path and returns to the starting node.
    - If this distance is less than the previously best-known distance, it updates the best solution and prints it.
    - Finally, it returns the best distance and corresponding order of nodes visited.

## Future Work

Future work can explore improved ansatz designs to enhance circuit expressibility and convergence. Testing noise mitigation techniques will be crucial as we scale to larger TSP instances on NISQ devices. Hybrid quantum-classical methods could also offer better scalability by combining quantum optimization with classical heuristics. Additionally, benchmarking VQE against algorithms like QAOA and analyzing different initialization strategies can provide deeper insights and improve generalizability across diverse TSP problems.

## References

Here’s your list of references reformatted into the requested markdown style:

1. Farhi, E., Goldstone, J., & Gutmann, S. (2014). *A Quantum Approximate Optimization Algorithm*. [arXiv:1411.4028](https://arxiv.org/abs/1411.4028)

2. Peruzzo, A., McClean, J., Shadbolt, P., Yung, M. H., Zhou, X. Q., Love, P. J., ... & O'Brien, J. L. (2014). *A variational eigenvalue solver on a photonic quantum processor*. *Nature Communications*, 5, 4213. [Nature](https://www.nature.com/articles/ncomms5213)

3. Zhou, L., Wang, S. T., Choi, S., Pichler, H., & Lukin, M. D. (2020). *Quantum Approximate Optimization Algorithm: Performance, Mechanism, and Implementation on Near-Term Devices*. *Physical Review X*, 10(2), 021067. [APS](https://journals.aps.org/prx/abstract/10.1103/PhysRevX.10.021067)

4. Lucas, A. (2014). *Ising formulations of many NP problems*. *Frontiers in Physics*, 2, 5. [Frontiers](https://www.frontiersin.org/articles/10.3389/fphy.2014.00005/full)

5. Gilliam, A., Shaydulin, R., Alexeev, Y., & Dumitrescu, E. F. (2021). *Optimizing Quantum Circuits for Combinatorial Problems on NISQ Architectures*. *Quantum Information Processing*, 20(3), 1–27. [Springer](https://link.springer.com/article/10.1007/s11128-020-02961-1)

---

> The research poster for this project can be found in the [BeyondQuantum Proceedings 2025](https://thinkingbeyond.education/beyondquantum_proceedings_2025/).

