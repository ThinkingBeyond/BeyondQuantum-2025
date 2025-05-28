![BeyondQuantum Banner for Research Projects](../BeyondQuantum_Banner_Research_Projects_2025.png)

# Noise Effects on Measurement-Device-Independent Quantum Key Distribution

***Provide a description of your project including*** 

1. motivating your research question
2. stating your research question
3. explaining your method and implementation
4. Briefly mention and discuss your results
5. Draw your conclusions
6. State what future investigations 
7. State your references 

# Introduction
Have you ever wondered whether a credential information you send to another person actually remains secure between the two parties? Are there any potential ways you could determine whether some tried decrypting it? That’s where Quantum Cryptography comes to play! By encoding bits into polarized photon states, quantum cryptography utilizes quantum mechanical principles to ensure that your information remains secure. 

Our research focused on dividing deep into understanding a limitation of the quantum key distribution’s BB84 protocol: the impacts on the secure key by the vulnerable measurement device. We learned that one of the most effective ways to remove this limitation and make quantum cryptography more practical is by implementing the Measurement-Device-Independent quantum key distribution (MDI QKD): in this protocol, the key never gets impacted by the measurement device. The bonus? The protocol may involve untrustable third parties. We implemented the protocol on Qiskit to visualize the way it works.

That’s not it- our research further dived deep into the noise effects compared to the Quantum Bit Error Rate (QBER) on MDI-QKD compared to other QKD protocols to deduce conclusions as to the possible limitations of MDI-QKD. The reason for this is that we want to make sure that this protocol is completely applicable and the main concerns are considered. We simulated the BB84, B92 and E91 protocols on Qiskit, implemented noise effects and QBER for all three protocols as well as for the MDI-QKD protocol. Further research could be implemented on concluding the most effective methodology to improve the model discussed in our research.


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

