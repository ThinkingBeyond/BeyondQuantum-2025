![BeyondQuantum Banner for Research Projects](../BeyondQuantum_Banner_Research_Projects_2025.png)

# QUANTUM INFORMATION THEORY AND COMPLEXEITY

### Project Introduction
***Our project, "Entanglement Scaling in Grover's Algorithm: Implications for Matrix Product State Simulation," conducted by Lucas Rhode and Kishan Bhowal under Manuel Rudolph's mentorship, investigates entanglement in Grover's search algorithm to assess its classical simulation using Matrix Product States (MPS). We simulated Grover's algorithm for 4 to 12 qubits, measuring bipartite entanglement entropy and bond dimension. Findings show low entanglement (below 1 ebit) and a constant bond dimension of 2, enabling efficient MPS simulations compared to high-entanglement algorithms like QAOA or Ising models.*** 

### Project Motivation
***The motivation for our project stemmed from our combined interest in exploring quantum entanglement and its implications for quantum algorithms. After discussions with our mentor, Manuel Rudolph, we selected Grover's search algorithm as the focus of our study, recognizing it as a feasible topic to investigate within the limited time available. By analyzing entanglement scaling in Grover's algorithm, we aimed to understand its impact on the efficiency of classical simulations using Matrix Product States (MPS), providing insights into the resources required for simulating quantum algorithms.***

### Methodology and Approach
To investigate entanglement scaling in Grover's algorithm and its implications for Matrix Product State (MPS) simulations, we employed a systematic approach combining theoretical analysis with numerical simulations. Below is a concise explanation of the method and approach, based on the provided document:

1. **Algorithm Selection and Setup**:
   - We focused on Grover's search algorithm, which finds a marked item in an unsorted database of N items using a quadratic speedup, achieved through repeated applications of an Oracle (phase flip of the target state) and a Diffusion Operator (amplitude amplification).
   - The marked state was chosen as the all-zeros state $(|0⟩^{\otimes n})$ for simplicity and consistency.
   - Simulations were conducted for systems with $n = 4, 6, 8, 10,$ and $12$ qubits to observe trends across different system sizes.
   - The optimal number of Grover iterations was calculated as R = ${round(\frac{\pi}{4} * √(2^n))}$, ensuring high probability of finding the marked state.

2. **Simulation Framework**:
   - We used Qiskit, an open-source quantum computing framework, and Qiskit Aer’s simulator for both statevector and MPS simulations.
   - Statevector simulations provided exact quantum states to compute entanglement metrics, while MPS simulations were used to assess simulation efficiency and extract bond dimension data.

3. **Entanglement and Bond Dimension Metrics**:
   - **Bipartite Entanglement Entropy ($S_1/2$)**: After each Grover iteration, we conceptually divided the n-qubit system into two equal halves and calculated the von Neumann entropy between them to quantify entanglement.
   - **Peak Entanglement Entropy ($S_{peak}$)**: For each $n$, we identified the maximum $S_1/2$ across all iterations.
   - **Peak Bond Dimension ($χ_{max}$)**:
     - **Actual $χ_{max}$**: Extracted from MPS simulation metadata using Qiskit Aer’s $SaveMatrixProductState$ feature, reflecting the bond dimension required by the simulator.
     - **Theoretical $χ_{max}$**: Estimated as $2^{S_{peak}}$, linking entanglement entropy to the bond dimension.
   - **MPS Simulation Time**: Measured as the wall-clock time for MPS simulations to complete, indicating computational cost.

4. **Data Analysis and Comparison**:
   - Results were compiled into tables and graphs (as referenced in the poster) to analyze how $S_{peak}$ and $χ_{max}$ scale with $n$.
   - We compared Grover’s algorithm entanglement characteristics with other algorithms (e.g., $QAOA$ for $p=1$ Max-Cut and Ising model dynamics) to contextualize its low entanglement and MPS efficiency.

5. **Approach Rationale**:
   - The choice of MPS was motivated by its efficiency in simulating quantum states with low entanglement, where the bond dimension $(χ)$ governs computational cost (time ~ $O(nχ^k)$, $k=2$ or $3$, and memory ~ $χ$).
   - By quantifying entanglement and bond dimension, we aimed to determine the feasibility and efficiency of MPS for simulating Grover’s algorithm compared to other quantum algorithms with higher entanglement.

### Results
This approach allowed us to rigorously quantify entanglement scaling in Grover’s algorithm and confirm that its low entanglement ($S_{peak} < 1 ebit, \chi_{max} = 2)$ enables highly efficient MPS simulations, providing valuable insights for classical simulation strategies in quantum computing.
Our results, as presented in the document, reveal the entanglement characteristics of Grover's algorithm and their implications for Matrix Product State (MPS) simulations:

1. **Peak Entanglement Entropy (S_peak)**: The bipartite entanglement entropy for a half-cut of the system grew mildly with qubit number, from $0.425$ ebits ($4$ qubits) to $0.956$ ebits ($12$ qubits), staying below 1 ebit. This indicates Grover's algorithm generates surprisingly low entanglement compared to algorithms like $QAOA$ $(~2.8 ebits for p=1 Max-Cut)$ or Ising model dynamics (linear entanglement growth).

2. **Maximum Bond Dimension (χ_max)**: The actual peak bond dimension, extracted from MPS simulations, remained constant at 2 across all tested qubit counts (4 to 12). The theoretical $χ_{max}$, calculated as $\( 2^{S_\text{peak}} \)$, ranged from ~1.3 (4 qubits) to $~1.9$ ($12$ qubits). This low and stable bond dimension underscores the efficiency of MPS for simulating Grover's algorithm.

3. **MPS Simulation Time**: Simulation time increased from $0.0135$ seconds ($4$ qubits) to $49$ seconds ($12$ qubits), reflecting manageable scaling due to the low, constant $χ_{max}$.

**Discussion**: The low entanglement $(S_{peak} < 1 ebit)$ and constant $χ_{max} = 2$ highlight that Grover's algorithm is highly amenable to MPS simulations, unlike algorithms with higher entanglement that require exponentially larger bond dimensions. This efficiency makes MPS a powerful tool for simulating Grover’s circuits, offering insights into resource requirements for classical simulation of quantum algorithms.


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

State your research question here and elaborate on it.

## Motivation

Explain your motivation for your chosen research question here.

## Your next subsection

Continue working through the points listed above with the help of sensibly named subsections. 

If you want to see some good examples of README files check out:
- [Example 1](https://github.com/ThinkingBeyond/BeyondAI-2024/blob/main/warenya-loulia/README.md)
- [Example 2](https://github.com/ThinkingBeyond/BeyondAI-2024/blob/main/shaana-karuna/README.md)

[ ... ]

## Future Work

State and explain what follow-up research could be conducted based on your work.

## References

List all your references here. Remember to put links into markdown. For example:

1.  Einstein, A. (1905). *On the Electrodynamics of Moving Bodies*. Annalen der Physik, 17, 891-921. [Internet Archive](https://archive.org/details/einstein-1905-relativity)

**Tip**: *If you have you references in BibTex, Google Scholar or Zotero*
1. Create/copy a list into ChatGPT
2. Ask it to turn it into an unsorted list in markdown

---

> The research poster for this project can be found in the [BeyondQuantum Proceedings 2025](https://thinkingbeyond.education/beyondquantum_proceedings_2025/).

