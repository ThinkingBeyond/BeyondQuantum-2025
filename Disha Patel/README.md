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
1.	BB84 Quantum Key Exchange:
    o	The BB84 protocol is simulated to generate a shared secret key between two parties, Alice and Bob.
    o	Random bits and bases (Z or X) are chosen by Alice to encode quantum states, which are then measured by Bob using randomly chosen bases.
    o	Qubits are prepared in the computational basis (Z) or Hadamard basis (X) based on Alice's choices, and Bob measures them in either basis.
    o	After measurement, Alice and Bob compare their basis choices over a public channel and retain bits where their bases match, forming a sifted key.
    o	The simulation uses Qiskit's AerSimulator to emulate quantum behavior, as real quantum hardware is not required for this proof-of-concept.
2.	Kyber512 Key Encapsulation:
    o	The Kyber512 algorithm, a lattice-based post-quantum KEM, is used to generate an additional shared secret.
    o	The server (Bob) generates a public-private key pair using oqs.KeyEncapsulation.
    o	The client (Alice) encapsulates a shared secret using the server's public key, producing a ciphertext.
    o	The server decapsulates the ciphertext to retrieve the same shared secret, ensuring both parties share an identical key.
    o	Kyber512 is chosen for its security against quantum attacks, complementing the quantum-based BB84 protocol.
3.	Hybrid Key Derivation:
    o	The sifted key from BB84 (truncated to 128 bits and converted to bytes) is combined with the first 16 bytes of the Kyber512 shared secret using a bitwise XOR operation.
    o	The resulting hybrid key is hashed using SHA-256, and the first 16 bytes of the hash are used as the AES key for encryption.
    o	This hybrid approach enhances security by leveraging the information-theoretic security of QKD and the computational security of post-quantum cryptography.
4.	AES-GCM Encryption and Authentication:
    o	The derived AES key is used with AES in GCM mode (Crypto.Cipher.AES) to encrypt a plaintext message, producing a ciphertext, nonce, and authentication tag.
    o	An HMAC-SHA256 is computed over the plaintext using the same AES key to provide message authentication.
    o	The receiver decrypts the ciphertext using the AES key, nonce, and tag, and verifies the HMAC to ensure the message's integrity and authenticity.
5.	Verification:
    o	The decrypted message is compared with the original plaintext, and the HMAC is recomputed to verify authenticity.
    o	Successful decryption and HMAC verification confirm the integrity and correctness of the secure communication.
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

