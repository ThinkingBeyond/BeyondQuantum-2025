![BeyondQuantum Banner for Research Projects](../BeyondQuantum_Banner_Research_Projects_2025.png)

# Quantum Machine Learning to Model Credit Portfolio Losses

## Research Question

To what extent can **Quantum Boltzmann Machines** surpass their classical counterparts at modelling **credit portfolio losses**?

**Quantum Boltzmann Machines** are the Quantum version of the classical Boltzmann machines, aiming to include **quantum entanglement** and **coherences** in the modelled **probability distribution**. However, there are many **computational issues** when implementing the theoretical model, therefore I focussed on a **classical-quantum hybrid model**. Here are the main objectives of our research project:

1. Implement the basic classical **RBM** and tune the **hyperparameters** in order to best improve the **training rate** using the code in the paper - (G.Genovese et al, 2022)
2. Implement the **hybrid model** for our dataset by using the **pennylane library** - based on the **pseudocode** given in the paper (Ya.S. Lakhyova et al, 2021)
3. Develop a **comprehensive understanding** of the dataset we are using and the **possible uses** for an improved model
4. Benchmark all of our models, and come to a **conclusion** about the performance of our models whilst providing a **theoretical discussion**

## Motivation

Modelling **credit portfolio losses** is an important stage for **risk analysts** at any company, aiming to **invest** or take out **loans**. A **default** is what occurs when an obligor is unable to meet the **legal requirements** of the loan, and **default rates** across sectors are highly correlated and provide substantial information about the current **economic environment**. Therefore, any improvement in our ability to model the default distributions would substantially improve how we manage risk within a **credit portfolio**.

More specifically, our **Hybrid Boltzmann Machine**, if successful, would provide better approximations for default rates, and could help with stress testing, through the addition of macroeconomic variables into the hidden layer, such as the **GDP**, **Inflation**, **Unemployment**, to predict future defaults under various economic scenarios. Therefore, any improvement to a classical model would have significant uses and implications within industry.

## Methods and Implementation

The classical **Restricted Boltzmann Machine**, from (G.Genovese et al, 2022), works through **parameterising** the **Gibbs sampling** procedure, and then using the **Adam optimiser** to train our model on the dataset. The Gibbs sampling procedure functions through **two linear combinations**, the **positive phase** (calculating the hidden nodes from the visible nodes) and the **negative phase** (calculating the visible nodes from the hidden nodes), which are repeated according to the number of **Gibbs steps**. Furthermore, the Adam optimiser is used alongside the **Contrastive Divergence** protocol which functions very similar to **gradient descent** but uses a Gibbs approximation instead of an exact evaluation of the result. The hybrid model works very similarly, however on the positive phase it embeds the results of the **linear combination** into an **angle embedding** followed by an **entangling quantum circuit**. The quantum circuit is the strongly entangling template circuit from the **pennylane documentation**, which we can compute the **expected values** of to calculate the negative phase.

Our implementation follows this logic, controlled by several hyperparameters which are as follows:

### Classical Hyperparameters

- Number of Visible Nodes: **30**
- Number of Hidden Nodes: **5, 10, 15, 20,**
- Training Routine: **Persistent CD**
- Learning Rate: **7e-3**
- Learning Rate Scheduler: **Linear**
- Batch Size: **1000**
- Number of Epochs: **2000**
- Benchmark: **Reconstruction Error**
- Number of Gibbs Sampling Steps: **2**

### Quantum Hyperparameters

- Number of Visible Nodes: **30**
- Number of Hidden Nodes: **5, 10, 15, 20**
- Training Routine: **CD**
- Learning Rate: **1e-3**
- Learning Rate Scheduler: **Exponential - 0.99**
- Batch Size: **300**
- Number of Epochs: **100**
- Benchmark: **Reconstruction Error**
- Number of Gibbs Sampling Steps: **10**

## Results 

![5 Nodes](./Graphs/5%20Nodes%20Comparison.png)
![10 Nodes](./Graphs/10%20Nodes%20Comparison.png)
![15 Nodes](./Graphs/15%20Nodes%20Comparison.png)
![20 Nodes](./Graphs/20%20Nodes%20Comparison.png)
![Quantum Nodes](./Graphs/Quantum%20Model%20Comparison.png)
![Classical Nodes](./Graphs/Classical%20Model%20Comparison.png)
## Conclusions

For **classical** models the reconstruction error converges after **20** hidden nodes, and the **hybrid** model is the lowest at **15**, suggesting that this number of nodes is sufficient for approximating how well each distribution can approximate losses in a credit portfolio. Furthermore, as shown by the graphs, the classical models with **5, 10, 15** and **20** nodes outperform their respective hybrid models when considering the **reconstruction error**. This suggests that the classical model is more suited to this use scenario than the hybrid model

However, it is important to note that **inefficiencies** will exist in both the implementations of the **classical** and **quantum** model, and I have only tracked one **benchmark** throughout training, which may measure some specific strength of the classical model, whilst covering up its **worse performances** on other models.

## Future Work

Due to **limitations** in the project timeline, the simplified **classical-quantum hybrid** could most certainly be **improved** to a full or restricted **Quantum Boltzmann Machine**. This would be significantly more complicated than the current model, however in Amin's "Quantum Boltzmann Machine" he proposed a method known as a **Bound-Based** QBM. This is a computationally-efficient method which places a trainable **upper-bound** on the accuracy and lowers this throughout the iterations, succesfully achieving the benefits of a fully quantum distribution

Another different area for **future research** involves analysing how well the models performs when modelling **distributions** with a varying number of companies. This hasn't been possible within our research project due to the **proprietary** nature of the dataset with more companies. Furthermore, the results within our code could be improved by utilising the **Persistent Contrastive Divergence** routine other the regular CD training. This routine keeps the value of the visible nodes **across parameter updates** to improve the training protocol as it provides a **better approximation** of the sampled distribution. Furthermore, we achieve multiple parameter updates with each training sample, decreasing the quantity of required data for successful training.

## References
1.  Genovese G., Nikeghbali A., Serra N., & Visentin G. (2022). Universal approximation of credit portfolio losses using Restricted Boltzmann Machines. arXiv preprint arXiv:2202.11060. Internet Archive [https://arxiv.org/abs/2202.11060]
2.  Amin, M. H., Andriyash, E., Rolfe, J., Kulchytskyy, B., & Melko, R. (2016). Quantum Boltzmann Machine. arXiv preprint arXiv:1601.02036. Internet Archive [https://arxiv.org/abs/1601.02036]
3.  Lyakhova Ya. S., Polyakov E. A., & Rubtsov A. N. (2021). Effectively Trainable Semi-Quantum Restricted Boltzmann Machine. arXiv preprint arXiv:2001.08997v4. Internet Archive [https://arxiv.org/abs/2001.08997] 
---

> The research poster for this project can be found in the [BeyondQuantum Proceedings 2025](https://thinkingbeyond.education/beyondquantum_proceedings_2025/).

