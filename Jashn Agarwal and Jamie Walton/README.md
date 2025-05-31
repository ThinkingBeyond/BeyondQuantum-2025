![BeyondQuantum Banner for Research Projects](../BeyondQuantum_Banner_Research_Projects_2025.png)

# Can the Stochastic Schrodinger Equation be Used to Model Decoherence in Continuous Weak Position Measurement?

## Motivation

This investigation was motivated by the experiment “Position measurement of levitating nanoparticles using interference with its mirror image” by researchers at the University of Oxford. The researchers were trying to do continuous weak measurement (without collapse) of the position of the nanoparticle as part of a quantum cooling scheme. We wanted to see if this kind of weak measurement is modelled well using a stochastic Schrodinger equation.

## Method of Investigation
We decided to simulate continuous weak measurement in two ways. The first was by using the stochastic process in QuTiP, in which trajectories are averaged over to form the density matrix of the system, and then finding the purity and plotting purity with time. The second was using a quantum circuit in Qiskit with a noise model to simulate the same. We did an exponential fit to see how the results matched.

## Results and conclusion

We see that the simulations matched closely which led us to conclude that the stochastic model could model continuous measurement well. 

## Future Work

Upon this work we could amend the circuit and simulation so that they fit more closely with the experiment conducted by the Oxford researchers. This could then be used to have a deeper dive into decoherence and its effects in these more niche but still cutting-edge scenarios.

## Credits
Authored by Jashn Agarwal and Jamie Walton
Mentored by Dr Filip Bar

## References


- L. Dania, K Heidigger et al, “Position Measurement of a Levitated Nanoparticle via Interference with Its Mirror Image” (DOI: [10.1103/PhysRevLett.129.013601](https://doi.org/10.1103/PhysRevLett.129.013601))
- Kurt Jacobs and Daniel Steck, “A Straightforward Introduction to Continuous Quantum Measurement” (arXiv: [quant-ph/0611067](https://arxiv.org/abs/quant-ph/0611067))
- QuTiP 4.7 Documentation, “Stochastic solver” (QuTiP Documentation)(https://qutip.org/docs/4.7/guide/dynamics/dynamics-stochastic.html))


**Tip**: *If you have you references in BibTex, Google Scholar or Zotero*
1. Create/copy a list into ChatGPT
2. Ask it to turn it into an unsorted list in markdown

---

> The research poster for this project can be found in the [BeyondQuantum Proceedings 2025](https://thinkingbeyond.education/beyondquantum_proceedings_2025/).

