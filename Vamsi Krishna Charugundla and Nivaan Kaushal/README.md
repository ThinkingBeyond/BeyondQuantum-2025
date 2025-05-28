![BeyondQuantum Banner for Research Projects](../BeyondQuantum_Banner_Research_Projects_2025.png)

# Leveraging Quantum Entanglement for Fluid Dynamics Simulations

## Project Description 
our project presents a  study on quantum fluid dynamics simulations by modeling fluid flow around a circular obstacle on a 2D spatial grid. The quantum simulation leverages quantum entanglement and superposition to encode fluid behavior using qubits, with each fluid cell represented as a quantum state. The classical counterpart employs conventional numerical methods to simulate flow and velocity fields.
Both simulations are executed on an N×N grid, incorporating identical domain boundaries, obstacle masking, and flow source placement. The quantum simulation uses gates like Hadamard, CNOT, and Ry(π/6) to simulate directionally biased fluid movement and entanglement between neighboring qubits. Post-processing involves collecting measurements from 4096 quantum circuit executions, normalizing the velocity data, and applying Gaussian filters to smooth the result.
The outcome demonstrates that quantum circuits can successfully capture key fluid dynamics characteristics such as flow diversion around obstacles, symmetry in the velocity field, and smoothed gradients. Comparative centerline velocity profiles show qualitative agreement between the quantum and classical results, validating the quantum approach’s effectiveness in simplified fluid flow modeling.
we had done a compartive on quantum fluid dynamics simulation and classical fulid dynamics simulation.

## MOTIVATION
We aimed to explore whether quantum computing especially the use of quantum entanglement and superposition could provide a scalable alternative. By encoding fluid properties into quantum states and constructing a lattice grid through qubit interactions, we hypothesized that quantum simulations could reproduce realistic flow patterns with fewer computational resources.where this motivated us by the increasing computational cost and complexity of classical fluid dynamics simulations, particularly when modeling flow around obstacles or within irregular geometries. Traditional methods require solving complex partial differential equations and often become inefficient as spatial resolution increases.

## Research Question 
Classical fluid dynamics simulations are computationally intensive, especially when modeling complex interactions near obstacles. This project explores a quantum circuit based framework to simulate simplified fluid behavior using quantum entanglement and superposition on a 2D lattice grid.

## Implementation
***Quantum computational fulid dynamics***
To implementing code we need to  all required packages .here below is the package file to install all packages at once .
- packages file :['requriment.txt']()
after above step completed then implementing this below colab notebook for Quantum CFD
In this notebook we did all setup to quantum circuit framework for quantum cfd
- Notebook: [`QCFD.ipynb`](https://github.com/ThinkingBeyond/BeyondQuantum-2025/blob/75d5e6e019b686684e43b6bcd524f2da2c5d65cf/Vamsi%20Krishna%20Charugundla%20and%20Nivaan%20Kaushal/QCFD.ipynb)
  next we implement this  below classical CFD colab notebook
  In this below notebook we setup a framework for  classical cfd .
- Notebook: [`CCFD.ipynb`](https://github.com/ThinkingBeyond/BeyondQuantum-2025/blob/75d5e6e019b686684e43b6bcd524f2da2c5d65cf/Vamsi%20Krishna%20Charugundla%20and%20Nivaan%20Kaushal/QCFD.ipynb)

## Results 


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

