![BeyondQuantum Banner for Research Projects](../BeyondQuantum_Banner_Research_Projects_2025.png)

# Quantum Machine Learning to Model Credit Portfolio Losses

## Research Question

To what extent can **Quantum Boltzmann Machines** surpass their classical counterparts at modelling **credit portfolio losses**?

**Quantum Boltzmann Machines** are the Quantum version of the classical Boltzmann machines, aiming to include **quantum entanglement** and **coherences** in the modelled **probability distribution**. However, there are many **computational issues** when implementing the theoretical model, therefore I focussed on a **classical-quantum hybrid model**. Here are the main objectives of our research project:

1. Implement the basic classical **RBM** and tune the **hyperparameters** in order to best improve the **training rate** using the code in the paper - (G.Genovese et al, 2023)
2. Implement the hybrid model for our dataset by using the pennylane documentation - based on the pseudocode given in the paper (Ya.S. Lakhyova et al, 2021)
3. Develop a comprehensive understanding of the dataset we are using and the possible uses for an improved model
4. Benchmark all of our models, and come to a conclusion about the performance of our models whilst providing a theoretical discussion

## Motivation

Modelling **credit portfolio losses** is an important stage for **risk analysts** at any company, aiming to **invest** or take out **loans**. A **default** is what occurs when an obligor is unable to meet the **legal requirements** of the loan, and **default rates** across sectors are highly correlated and provide substantial information about the current **economic environment**. Therefore, any improvement in our ability to model the default distributions would substantially improve how we manage risk within a **credit portfolio**.

More specifically, our **Hybrid Boltzmann Machine**, if successful, would provide better approximations for default rates, and could help with stress testing, through the addition of macroeconomic variables into the hidden layer, such as the **GDP**, **Inflation**, **Unemployment**, to predict future defaults under various economic scenarios. Therefore, any improvement to a classical model would have significant uses and implications within industry.

## Methods and Implementation

## Results

[Classical vs Quantum (5 Nodes)](Graphs/5 Nodes Comparison.png)

## Conclusions



## Future Work

Due to **limitations** in the project timeline, the simplified **classical-quantum hybrid** could most certainly be **improved** to a full or restricted **Quantum Boltzmann Machine**. This would be significantly more complicated than the current model, however in Amin's "Quantum Boltzmann Machine" he proposed a method known as a **Bound-Based** QBM. This is a computationally-efficient method which places a trainable **upper-bound** on the accuracy and lowers this throughout the iterations, succesfully achieving the benefits of a fully quantum distribution

Another different area for **future research** involves analysing how well the models performs when modelling **distributions** with a varying number of companies. This hasn't been possible within our research project due to the **proprietary** nature of the dataset with more companies. Furthermore, the results within our code could be improved by utilising the **Persistent Contrastive Divergence** routine other the regular CD training. This routine keeps the value of the visible nodes **across parameter updates** to improve the training protocol as it provides a **better approximation** of the sampled distribution. Furthermore, we achieve multiple parameter updates with each training sample, decreasing the quantity of required data for successful training

## References

List all your references here. Remember to put links into markdown. For example:

1.  Einstein, A. (1905). *On the Electrodynamics of Moving Bodies*. Annalen der Physik, 17, 891-921. [Internet Archive](https://archive.org/details/einstein-1905-relativity)

**Tip**: *If you have you references in BibTex, Google Scholar or Zotero*
1. Create/copy a list into ChatGPT
2. Ask it to turn it into an unsorted list in markdown

## Your next subsection

Continue working through the points listed above with the help of sensibly named subsections. 

If you want to see some good examples of README files check out:
- [Example 1](https://github.com/ThinkingBeyond/BeyondAI-2024/blob/main/warenya-loulia/README.md)
- [Example 2](https://github.com/ThinkingBeyond/BeyondAI-2024/blob/main/shaana-karuna/README.md)

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

[ ... ]

---

> The research poster for this project can be found in the [BeyondQuantum Proceedings 2025](https://thinkingbeyond.education/beyondquantum_proceedings_2025/).

