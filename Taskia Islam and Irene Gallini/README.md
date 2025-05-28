![BeyondQuantum Banner for Research Projects](../BeyondQuantum_Banner_Research_Projects_2025.png)

# Noise Effects on Measurement-Device-Independent Quantum Key Distribution

## Introduction
Have you ever wondered whether a credential information you send to another person actually remains secure between the two parties? Are there any potential ways you could determine whether some tried decrypting it? That’s where Quantum Cryptography comes to play! By encoding bits into polarized photon states, quantum cryptography utilizes quantum mechanical principles to ensure that your information remains secure. 

Our research focused on dividing deep into understanding a limitation of the quantum key distribution’s BB84 protocol: the impacts on the secure key by the vulnerable measurement device. We learned that one of the most effective ways to remove this limitation and make quantum cryptography more practical is by implementing the Measurement-Device-Independent quantum key distribution (MDI QKD): in this protocol, the key never gets impacted by the measurement device. The bonus? The protocol may involve untrustable third parties. We implemented the protocol on Qiskit to visualize the way it works.

That’s not it- our research further dived deep into the noise effects compared to the Quantum Bit Error Rate (QBER) on MDI-QKD compared to other QKD protocols to deduce conclusions as to the possible limitations of MDI-QKD. The reason for this is that we want to make sure that this protocol is completely applicable and the main concerns are considered. We simulated the BB84, B92 and E91 protocols on Qiskit, implemented noise effects and QBER for all three protocols as well as for the MDI-QKD protocol. Further research could be implemented on concluding the most effective methodology to improve the model discussed in our research.

## Research Question

Our research question had two main parts: the first one focuses on the MDI-QKD protocol and the second question considers the limitations. As mentioned previously, the purpose of having two parts was to make sure we not only explain how this particular protocol is promising but also look at it from a practical and applicable perspective.

Research question:
1. How can we remove the vulnerabilities of measurement devices in Quantum Key Distribution?
2. How are noise effects a limitation of removing these vulnerabilities? 


## Motivation

Quantum Key Distribution (QKD) promises theoretically unbreakable encryption based on the laws of quantum mechanics. However, many practical implementations, including the well-known BB84 protocol, are vulnerable to attacks that exploit weaknesses in the measurement devices. These side-channel attacks compromise the security of the key, undermining the core advantage of QKD. While Measurement-Device-Independent QKD (MDI-QKD) was proposed to solve this issue, it introduces its own set of practical challenges, especially under noisy conditions. Therefore, our motivation for this research project was to investigate the effectiveness of MDI-QKD in the presence of noise and compare it to other QKD protocols, with the goal of understanding its limitations and potential for real world applications.

## Key Difference between MDI-QKD and BB84
The goal of quantum cryptography is to ensure the secure information gets transmitted to the recipient safely without having it decrypted by an eavesdropper. In classical cryptography, a key is encrypted using complex mathematical problems such as integer multiplication. In modern computers, these can be decrypted much faster, and the sender and recipient would not notice the change in the keys. Therefore, quantum cryptography uses quantum mechanical principles to ensure the key is transmitted securely, and the sender + recipient would notice if an eavesdropper tried decrypting it. 

How is that? Quantum cryptography uses polarized photon states. Photons can oscillate, and polarized photons can oscillate only in one direction, either horizontal, vertical, diagonal or anti-diagonal. The most common protocol in quantum cryptography is BB84. In the BB84 protocol, we have two different parties: a sender of the key and a recipient. Here are the steps in BB84:
1. The sender (referred to as Alice in quantum cryptography) would encode the message in bits
2. For each bit, Alice would choose a specific basis: vertical, horizontal, diagonal, or anti-diagonal.
3. Alice will send now send the polarized photon states to the recipient (Bob) through an optical fibre which is a primary medium for photon transmission
4. Bob would choose a random basis and measure the photon. Bob will record each of the results
5. After steps 1-4 are completed, Alice and Bob will publicly share their basis. Because the basis does not contain the key information themselves, publicly sharing the basis will not help anyone else decrypting it.

Why is this effective?
Superposition in quantum mechanics plays a huge role in understanding why QKD works better than classical cryptography. That’s because once the states are measured, if they are measured incorrectly, then the state would collapse into one state, indicating an error that can be noticed by Alice and Bob later on. This is where the Heisenberg Uncertainty Principle comes in.
Eve does not actually know whether she is right or wrong with the measurements because she has to randomly choose a basis just like Bob, keeping the probability of getting all the bits correct very low. Additionally, due to the no-cloning theorem, photon states can not exactly be copied by the eavesdropper later on.

However, the big issue we face in the BB84 protocol is that the key relies upon a measurement device. This measurement device can be weak and vulnerable, making it susceptible to errors. To solve this problem, we dived deep into the Measurement-Device-Independent Quantum Key Distribution protocol which ensures that the key itself is not altered by the measurement device. The way MDI-QKD works is simple:
1. Both Alice and Bob encode choose phase-randomized weak coherent light pulses
2. They then encode their own random bits into each pulse using the same states from BB84. These are the same basis from the BB84 protocol
3. They implement the decoy state and modulate each pulse using an optical intensity modulator to prevent photon-number-splitting attacks
4. Both Alice and Bob send the photon pulses to Charlie, who is a central third party and can be untrusted
5. Charlie performs partial Bell State Measurements to see which photon pulses have entanglement-like correlations. Charlie does not have any information about the key itself which is why he can be untrusted.
6. Charlie sends the successful partial Bell State Measurements to Alice and Bob. Alice and Bob publicly share their basis and discard the wrong measurements
7. Alice and Bob uses QBER to check for errors that Charlie may have made

## Methodology and Implementation

The ultimate goal for implementation was to ensure that we considered all the 3 main types of quantum key distribution protocols (which are BB84, B92 and E91) as well as the MDI-QKD protocol, and develop a noise simulation for all of them. With the help of Qiskit on Google Colab, we successfully implemented the prototype and simulation for all of these protocols for easier visualization on the data.

*Insert BB84 protocol and noise simulation*
*Insert B92 protocol and noise simulation*
*Insert E91 protocol and noise simulation*

## Results
To measure how noise affects the MDI protocol we used Quantum Bit Error Rate (QBER), a performance metric which represents the percentage of incorrect qubits in a secret key. Receiving incorrect bits can allow an eavesdropper to go undetected, so QBER reflects a QKD’s vulnerability. Depolarizing noise, which randomly alters a qubit’s state, simulates realistic channel imperfections. We plotted the effect of increasing depolarizing noise on QBER for MDI, BB84, E91, and B92.

## Conclusions
- The measurement-device-independent quantum key distribution protocol is one of the most promising ways to remove side-detection channels which can be weak and vulnerable. This is a cutting-edge protocol because it makes quantum key distribution much safer and more applicable in the light of cryptography.
- In our result for the noise effects on MDI-QKD compared to other protocols, MDI shows a nonlinear QBER trend with sharp fluctuations, similar to entanglement-based protocols like E91 and B92. In contrast, BB84 exhibits a linear increase in QBER as depolarizing noise rises. BB84 involves only Alice and Bob, and depolarizing noise affects qubits uniformly. This allows straightforward error correction methods, such as increasing redundancy based on the measured QBER.
- MDI, however, introduces a third party measurement and relies on photon indistinguishability. Depolarizing noise disrupts interference visibility, making QBER highly sensitive and unpredictable. Therefore, MDI requires adaptive, block-based error correction strategies that respond to local QBER variations.

## Future Work

Our research highlighted the potential of MDI-QKD in addressing measurement device vulnerabilities, but also revealed its sensitivity to depolarizing noise and the resulting non linear behavior of the Quantum Bit Error Rate (QBER) in QKD protocols that rely on third party measurement, such as the  MDI-QKD or entanglement such as the B92 and E91 protocls. These findings open several directions for further research.

One promising area is the implementation and testing of adaptive error correction strategies tailored to MDI-QKD, such as evaluating the performance of the Cascade protocol or other block based methods under varying noise conditions. These could help stabilize QBER fluctuations and improve protocol robustness.

Additionally, future work could explore the effect of different types of quantum noise, such as phase damping or amplitude damping, and how they compare to depolarizing noise in terms of their impact on secure key generation. Investigating how key generation rates change under these different noise models could also provide insights into the efficiency and scalability of MDI-QKD in practical applications.

We also recommend a deeper analysis of the non linear QBER peaks observed in MDI and entanglement based protocols like E91 and B92. Understanding the pattern and cause of these fluctuations could lead to more resilient and predictable protocol designs.

Further studies could involve simulating potential eavesdropping attacks, such as photon number splitting or Trojan horse attacks, to assess the protocol's security beyond idealized noise models. Finally, expanding the comparison to additional QKD protocols and integrating them into larger quantum communication frameworks could provide a broader understanding of the strengths and trade offs involved in each approach.


## References

List all your references here. Remember to put links into markdown. For example:

1.  Einstein, A. (1905). *On the Electrodynamics of Moving Bodies*. Annalen der Physik, 17, 891-921. [Internet Archive](https://archive.org/details/einstein-1905-relativity)

**Tip**: *If you have you references in BibTex, Google Scholar or Zotero*
1. Create/copy a list into ChatGPT
2. Ask it to turn it into an unsorted list in markdown

---

> The research poster for this project can be found in the [BeyondQuantum Proceedings 2025](https://thinkingbeyond.education/beyondquantum_proceedings_2025/).

