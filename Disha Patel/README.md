![BeyondQuantum Banner for Research Projects](../BeyondQuantum_Banner_Research_Projects_2025.png)

# Hybrid Secure Messaging using BB84 Quantum Key Distribution and Post-Quantum Cryptography


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

Can a hybrid cryptographic model combining Quantum Key Distribution (QKD) and Post-Quantum Cryptography (PQC) provide enhanced security against both classical and quantum adversaries?

The research question investigates the potential of a hybrid cryptographic framework that integrates Quantum Key Distribution (QKD) with Post-Quantum Cryptography (PQC) to create a robust security model capable of defending against both classical adversaries and quantum adversaries. This question addresses the need to protect system against the evolving threat where quantum computers could potentially break widely used classical cryptographic algorithms like RSA, ECC, etc.

## Motivation
1. Implementation: Develop a prototype that combines QKD (BB84) for generating a shared secret key and PQC (Kyber512) for quantum-resistant key encapsulation, resulting in a hybrid AES key for secure encryption and authentication.
2. Security Analysis: a. Verify QKD’s unconditional security for key distribution, ensuring protection against eavesdropping through quantum principles.
                      b. Confirm PQC’s resistance to quantum attacks, such as those enabled by Shor’s or Grover’s algorithms.
                      c. Evaluate the hybrid model’s resilience to classical attacks, including brute-force, side-channel, and cryptanalytic threats.
3. Performance Evaluation: Assess the efficiency of key generation, computational overhead, and compatibility with existing cryptographic systems.
4. Validation: Ensure the hybrid system supports secure encryption, decryption, and message authentication, as demonstrated through successful HMAC verification.


## Method and Implementation
Methodology
The system operates in the following steps:
1. BB84 Quantum Key Distribution:
•	Simulates a quantum protocol where Alice and Bob use random bases (Z/X) to encode and measure qubits.
•	They retain only bits where their measurement bases match, forming a sifted key.
•	Implemented using Qiskit's AerSimulator (no real quantum hardware required).
2. Kyber512 Post-Quantum Key Encapsulation:
•	Uses Kyber512, a lattice-based algorithm resistant to quantum attacks.
•	Bob generates a key pair; Alice encapsulates a shared secret.
•	Bob decapsulates the ciphertext to retrieve the same secret.
3. Hybrid Key Derivation:
•	BB84 key (128-bit) XORed with the first 16 bytes of Kyber512’s secret.
•	The result is hashed (SHA-256), and the first 16 bytes are used as the AES key.
4. AES-GCM Encryption + HMAC:
•	AES-GCM encrypts the message and ensures integrity via a tag.
•	HMAC-SHA256 provides an additional authentication layer.
•	Receiver decrypts and verifies both HMAC and tag to ensure security.
5. Verification:
•	Confirms the decrypted message matches the original and passes integrity checks.

  	
Implementation Details
•	Libraries and Dependencies:
o	qiskit and qiskit-aer: Used for simulating the BB84 protocol with quantum circuits and the AerSimulator backend.
o	liboqs-python: Provides the Kyber512 implementation for post-quantum key encapsulation.
o	pycryptodome: Supplies AES-GCM encryption and HMAC-SHA256 for secure message handling.
o	Additional dependencies include numpy, scipy, and others installed via pip and apt-get for building the environment.

•	Code Structure:
o	Installation: The notebook begins by installing required packages (qiskit, qiskit-aer, pycryptodome, liboqs-python) and their dependencies in a Colab environment.
o	BB84 Simulation: The bb84_key_exchange function simulates the QKD process, generating a sifted key of approximately 100-150 bits from 300 initial bits due to basis matching.
o	Key Conversion: The bits_to_bytes function converts the sifted key into bytes for compatibility with cryptographic operations.
o	Kyber512 Integration: The oqs.KeyEncapsulation class is used to perform key encapsulation and decapsulation, producing a shared secret.
o	Hybrid Key Generation: The BB84 and Kyber512 keys are combined via XOR, and SHA-256 derives a 16-byte AES key.
o	Encryption and Verification: AES-GCM encrypts the message, and HMAC-SHA256 ensures authenticity. The decryption and verification steps confirm successful communication.

## Result
The results demonstrate the successful integration of BB84 and Kyber512 to create a secure hybrid key, effectively used for AES-GCM encryption and HMAC authentication. The smaller BB84 key size, combined with Kyber512's robust post-quantum security, ensures both efficiency and future-proofing against quantum threats. The sifting process in BB84 reduces key length but maintains security, while the hybrid approach leverages the strengths of each method, as reflected in the component distribution. This implementation provides a practical proof-of-concept for secure communication in a quantum-threatened future.
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

