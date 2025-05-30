![BeyondQuantum Banner for Research Projects](../BeyondQuantum_Banner_Research_Projects_2025.png)

# QUANTUM INFORMATION THEORY AND COMPLEXEITY

## Research Question
*How does the entanglement entropy scale with the number of qubits in Grover’s algorithm[^1], and how does this scaling influence the classical simulation cost using matrix product states (MPS)?*


## Project Introduction
*Our project, **"Entanglement Scaling in Grover's Algorithm: Implications for Matrix Product State Simulation,"** conducted by Lucas Rhode and Kishan Bhowal under Manuel Rudolph's mentorship, investigates entanglement in Grover's search algorithm to assess its classical simulation using Matrix Product States (MPS). We simulated Grover's algorithm for 4 to 12 qubits, measuring bipartite entanglement entropy and bond dimension. Findings show low entanglement (below 1 ebit) and a constant bond dimension of 2, enabling efficient MPS simulations compared to high-entanglement algorithms like QAOA or Ising models.* 

## Project Motivation
*The motivation for our project stemmed from **our combined interest in exploring quantum entanglement and its implications for quantum algorithms.** After discussions with our mentor, Manuel Rudolph, **we selected Grover's search algorithm as the focus of our study, recognizing it as a feasible topic to investigate within the limited time available.** By analyzing entanglement scaling in Grover's algorithm, we aimed to understand its impact on the efficiency of classical simulations using Matrix Product States (MPS), providing insights into the resources required for simulating quantum algorithms.*

## Methodology and Approach
To investigate entanglement scaling in Grover's algorithm and its implications for Matrix Product State (MPS) simulations, we employed a systematic approach combining theoretical analysis with numerical simulations. Below is a concise explanation of the method and approach, based on the provided document:

1. **Algorithm Selection and Setup**:
   - We focused on Grover's search algorithm, which finds a marked item in an unsorted database of N items using a quadratic speedup, achieved through repeated applications of an Oracle (phase flip of the target state) and a Diffusion Operator (amplitude amplification).
   - The marked state was chosen as the all-zeros state $(|0⟩^{\otimes n})$ for simplicity and consistency.
   - Simulations were conducted for systems with $n = 4, 6, 8, 10,$ and $12$ qubits to observe trends across different system sizes.
   - The optimal number of Grover iterations was calculated as R = ${round(\frac{\pi}{4} \cdot √(2^n))}$, ensuring high probability of finding the marked state.

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

## Results
This approach allowed us to rigorously quantify entanglement scaling in Grover’s algorithm and confirm that its low entanglement ($S_{peak} < 1 ebit, \chi_{max} = 2)$ enables highly efficient MPS simulations, providing valuable insights for classical simulation strategies in quantum computing.
Our results, as presented in the document, reveal the entanglement characteristics of Grover's algorithm and their implications for Matrix Product State (MPS) simulations:

1. **Peak Entanglement Entropy $(S_{peak})$**: The bipartite entanglement entropy for a half-cut of the system grew mildly with qubit number, from $0.425$ ebits ($4$ qubits) to $0.956$ ebits ($12$ qubits), staying below 1 ebit. This indicates Grover's algorithm generates surprisingly low entanglement compared to algorithms like $QAOA$ $(~2.8 ebits for p=1 Max-Cut)$ or Ising model dynamics (linear entanglement growth).<img width="995" alt="Screenshot 2025-05-27 at 1 49 46 PM" src="https://github.com/user-attachments/assets/7939c17d-ff0a-4086-b92e-087de07afcfb" />

2. **Maximum Bond Dimension $(χ_{max})$**: The actual peak bond dimension, extracted from MPS simulations, remained constant at 2 across all tested qubit counts (4 to 12). The theoretical $χ_{max}$, calculated as $\( 2^{S_\text{peak}} \)$, ranged from ~1.3 (4 qubits) to $~1.9$ ($12$ qubits). This low and stable bond dimension underscores the efficiency of MPS for simulating Grover's algorithm.<img width="995" alt="Screenshot 2025-05-27 at 3 03 01 PM" src="https://github.com/user-attachments/assets/c0095d05-6595-4e96-ba49-5de4a52204ac" />


3. **MPS Simulation Time**: Simulation time increased from $0.0135$ seconds ($4$ qubits) to $49$ seconds ($12$ qubits), reflecting manageable scaling due to the low, constant $χ_{max}$.<img width="998" alt="Screenshot 2025-05-28 at 7 01 55 AM" src="https://github.com/user-attachments/assets/80460fe5-eb68-4f7a-a451-c4e81e6dec82" />

# Table

| n-Qubits            | Iterations $S_{max}$|(ebits) $χ_{max}$     | (actual) $χ_{max}$  |   Theory $(2^S)$  |   MPS time  $(s)$    |
|---------------------|-----------|------------- |------------|-------------|-----------------|
|         4           |     3     |    0.4250    |    2.0     |     1.3     |     0.1353      | 
|         6           |     6     |    0.6905    |    2.0     |     1.6     |     0.6882      |
|         8           |     13    |    0.8337    |    2.0     |     1.8     |     5.3440      |
|         10          |     25    |    0.9124    |    2.0     |     1.9     |    22.0588      |
|         12          |     50    |    0.9558    |    2.0     |     1.9     |   151.3528      |
    

    
**Discussion**: The low entanglement $(S_{peak} < 1 ebit)$ and constant $χ_{max} = 2$ highlight that Grover's algorithm is highly amenable to MPS simulations, unlike algorithms with higher entanglement that require exponentially larger bond dimensions. This efficiency makes MPS a powerful tool for simulating Grover’s circuits, offering insights into resource requirements for classical simulation of quantum algorithms.

## Conclusions

Our study on "Entanglement Scaling in Grover's Algorithm: Implications for Matrix Product State Simulation" leads to the following conclusions:

1. **Low Entanglement in Grover's Algorithm**: Grover's algorithm exhibits remarkably low bipartite entanglement, with peak entanglement entropy $(S_{peak})$ remaining below 1 ebit for systems up to $12$ qubits (ranging from $0.425$ ebits for $4$ qubits to $0.956$ ebits for $12$ qubits). This is significantly lower than other quantum algorithms like $QAOA$ (~2.8 ebits for $p=1$ Max-Cut) or Ising model dynamics (linear entanglement growth).

2. **Efficient MPS Simulations**: The low entanglement translates to a consistently low bond dimension $(χ_{max} = 2)$ across all tested qubit counts ($4$ to $12$), as observed in MPS simulations. The theoretical $χ_{max} (2^{S_{peak}})$ also remained small (~1.3 to 1.9). This enables highly efficient MPS simulations, with simulation times scaling manageably ($0.0135$ seconds for $4$ qubits to $49$ seconds for $12$ qubits).

3. **Practical Implications**: The minimal entanglement and stable bond dimension indicate that MPS is an exceptionally effective method for classically simulating Grover's algorithm, particularly when compared to algorithms requiring larger bond dimensions due to higher entanglement. This efficiency is valuable for benchmarking quantum algorithms and understanding classical simulation resource requirements.

4. **Theoretical Insight**: The findings enhance our understanding of entanglement scaling in Grover’s algorithm, highlighting its unique characteristic of maintaining low entanglement, which is advantageous for classical simulation strategies.

In summary, Grover's algorithm’s low entanglement makes it ideally suited for MPS-based classical simulations, offering both practical and theoretical insights into optimizing quantum algorithm simulations.

## Future Work

We can follow up this research work with tests for different algorithms other than Grover's . This can help us understand the effeiciency or the real quantum advantage achieved in different quantum algorithms and it will substantiate the benefits quantum computers can provide at large. The cost of operating a Quantum algorithm must be significantly less than that of its classical counter-part , this project can help us realise if quantum computers are all hype or they do have some substantial benefits and what they are.

## References

[^1] : *Quantum Computation and Quantum Information* , By Michael A. Nielsen, Isaac L. Chuang https://www.google.co.in/books/edition/Quantum_Computation_and_Quantum_Informat/65FqEKQOfP8C?hl=en

2. *Quantum Entanglement* Ryszard Horodecki , Pawel Horodecki , Michal Horodecki and Karol Horodecki
   https://arxiv.org/abs/quant-ph/0702225v2

3. *IBM Quantum Learning* https://learning.quantum.ibm.com/


---

> The research poster for this project can be found in the [BeyondQuantum Proceedings 2025](https://thinkingbeyond.education/beyondquantum_proceedings_2025/).[View only poster on Canva](https://www.canva.com/design/DAGoNhExnn8/urFVDI1sOlgAeHoil7k9Yw/edit)
