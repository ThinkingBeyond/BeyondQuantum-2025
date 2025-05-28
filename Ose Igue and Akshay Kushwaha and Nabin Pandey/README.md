![BeyondQuantum Banner for Research Projects](../BeyondQuantum_Banner_Research_Projects_2025.png)

# State Your Project Title Here With Capitalised Letters as Shown

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

State your research question here and elaborate on it.

## Motivation

The Traveling Salesman Problem (TSP) stands as a quintessential example of a combinatorial optimization problem whose exact solution becomes prohibitively expensive for classical computers as the number of cities increases. Classical algorithms designed to find the optimal tour, such as Dynamic Programming, suffer from exponential time complexity, rendering them impractical for instances involving more than a few dozen cities. This computational bottleneck necessitates the exploration of alternative paradigms.

Quantum computing has emerged as a promising avenue for potentially accelerating the solution of certain computational problems, including optimization. Various quantum algorithms and heuristics are being developed and investigated for their applicability to NP-hard problems like TSP. The approach outlined in [10], which proposes encoding TSP distances into the phases of quantum states and utilizing the Quantum Phase Estimation algorithm to extract path costs, represents a specific technique leveraging fundamental quantum properties.

While theoretical analyses often suggest potential quantum speedups, the practical performance of these algorithms on current and near-term quantum hardware or simulators is not always immediately apparent due to factors such as qubit count limitations, noise, circuit depth constraints, and simulation overheads. Dynamic Programming, despite its unfavorable theoretical worst-case complexity for large N, is a well-understood and often efficient exact method for small to moderately sized TSP instances on classical hardware.

Therefore, the primary motivation for this experiment is to conduct a direct, empirical comparison between the practical performance of a classical Dynamic Programming solver and a quantum algorithm based on phase encoding and Quantum Phase Estimation for the Traveling Salesman Problem. By executing both approaches on a range of small TSP instances using readily available codebases and simulation tools, we aim to:
\begin{itemize}
    \item Gain concrete, hands-on experience with the implementation and execution of a specific quantum optimization algorithm.
    \item Quantify the runtime performance of the quantum simulation approach relative to an established classical method on scales where both are feasible.
    \item Identify and highlight the practical overheads and current limitations of the quantum simulation compared to classical computation for this problem.
    \item Provide empirical data to support discussions on the current feasibility and future potential of quantum phase-based encoding techniques for combinatorial optimization.
\end{itemize}
This comparison is crucial for bridging the gap between theoretical quantum speedup claims and the observed performance on existing or simulated quantum systems, offering valuable insight into the current state of quantum computation for practical problem-solving.

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

