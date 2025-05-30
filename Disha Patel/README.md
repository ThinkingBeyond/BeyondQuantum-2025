
![BeyondQuantum Banner for Research Projects](../BeyondQuantum_Banner_Research_Projects_2025.png)

# Hybrid Secure Messaging using BB84 Quantum Key Distribution and Post-Quantum Cryptography


## Research Question

Design a hybrid **QKD-PQC** cryptographic system to ensure scalable, quantum-resistant security against evolving threats.

Given the vulnerability of traditional cryptography to quantum attacks like Shor's algorithm, the practical limitations of QKD (e.g., distance, noise), and the potential risks of PQC to future cryptanalytic advances, a hybrid QKD-PQC approach is needed to combine QKD's information-theoretic security with PQC's quantum resistance for scalable, long-term protection against evolving quantum and classical threats.

## Motivation
1. Implementation: Develop a prototype that combines QKD (BB84) for generating a shared secret key and PQC (Kyber512) for quantum-resistant key encapsulation, resulting in a **hybrid AES** key for secure encryption and authentication.
2. Security Analysis:
   a. Verify QKD’s unconditional security for key distribution, ensuring protection against eavesdropping through quantum principles.
   
   b. Confirm PQC’s resistance to quantum attacks, such as those enabled by Shor’s or Grover’s algorithms.
   
   c. Evaluate the hybrid model’s resilience to classical attacks, including brute-force, side-channel, and cryptanalytic threats.
4. Performance Evaluation: Assess the efficiency of key generation, computational overhead, and compatibility with existing cryptographic systems.
5. Validation: Ensure the hybrid system supports secure encryption, decryption, and message authentication, as demonstrated through successful **HMAC verification**.


## Method and Implementation
Methodology


1. BB84 Quantum Key Distribution:
   
Simulates a quantum protocol where Alice and Bob use random bases (Z/X) to encode and measure qubits.

They retain only bits where their measurement bases match, forming a sifted key.

Implemented using Qiskit's AerSimulator (no real quantum hardware required).

2. Kyber512 Post-Quantum Key Encapsulation:
   
Uses Kyber512, a **lattice-based algorithm** resistant to quantum attacks.

Bob generates a key pair; Alice encapsulates a shared secret.

Bob decapsulates the ciphertext to retrieve the same secret.

3. Hybrid Key Derivation:
   
BB84 key (128-bit) **XORed** with the first 16 bytes of Kyber512’s secret.

The result is hashed (SHA-256), and the first 16 bytes are used as the AES key.

4. AES-GCM Encryption + HMAC:
   
AES-GCM encrypts the message and ensures integrity via a tag.

**HMAC-SHA256** provides an additional authentication layer.

Receiver decrypts and verifies both HMAC and tag to ensure security.

5. Verification:

Confirms the decrypted message matches the original and passes integrity checks.

Implementation Details


• Libraries and Dependencies

qiskit and qiskit-aer: Used for simulating the BB84 protocol with quantum circuits and the **AerSimulator backend**.

liboqs-python: Provides the Kyber512 implementation for post-quantum key encapsulation.

pycryptodome: Supplies AES-GCM encryption and HMAC-SHA256 for secure message handling.

Additional dependencies include numpy, scipy, and others installed via pip and apt-get for building the environment.

• Code Structure

Installation: The notebook begins by installing required packages (qiskit, qiskit-aer, pycryptodome, liboqs-python) and their dependencies in a Colab environment.

BB84 Simulation: The bb84_key_exchange function simulates the QKD process, generating a sifted key of approximately 100–150 bits from 300 initial bits due to basis matching.

Key Conversion: The bits_to_bytes function converts the sifted key into bytes for compatibility with cryptographic operations.

Kyber512 Integration: The oqs.KeyEncapsulation class is used to perform key encapsulation and decapsulation, producing a shared secret.

Hybrid Key Generation: The BB84 and Kyber512 keys are combined via XOR, and SHA-256 derives a 16-byte AES key.

Encryption and Verification: AES-GCM encrypts the message, and HMAC-SHA256 ensures authenticity. The decryption and verification steps confirm successful communication.
  	

## Result

The results demonstrate the successful integration of BB84 and Kyber512 to create a secure hybrid key, effectively used for AES-GCM encryption and HMAC authentication. The smaller BB84 key size, combined with Kyber512's robust post-quantum security, ensures both efficiency and future-proofing against quantum threats. The sifting process in BB84 reduces key length but maintains security, while the hybrid approach leverages the strengths of each method, as reflected in the component distribution. This implementation provides a practical proof-of-concept for secure communication in a quantum-threatened future.
Continue working through the points listed above with the help of sensibly named subsections. 


![Graph 2](https://github.com/ThinkingBeyond/BeyondQuantum-2025/blob/main/Disha%20Patel/graphs/security_analysis.png)

![Graph 1](https://github.com/ThinkingBeyond/BeyondQuantum-2025/blob/main/Disha%20Patel/graphs/key_length.png)

![Graph 1](https://github.com/ThinkingBeyond/BeyondQuantum-2025/blob/main/Disha%20Patel/graphs/framework.png)

## Conclusion

This project successfully demonstrates a hybrid cryptographic system that integrates the BB84 Quantum Key Distribution (QKD) protocol with the Kyber512 post-quantum key encapsulation mechanism (KEM) to create a secure, future-proof communication framework. By combining BB84’s information-theoretic security with Kyber512’s resilience against quantum attacks, the system derives a 128-bit AES key used for AES-GCM encryption and HMAC-SHA256 authentication. The results, illustrated through key size comparisons, key length transitions, and component distribution, highlight the efficiency and balanced design of the hybrid model. BB84’s sifted key and Kyber512’s robust 6400-bit key together ensure both compactness and security, while the framework’s composition reflects a strategic blend of quantum, post-quantum, and classical techniques. This implementation provides a practical proof-of-concept for secure communication, effectively bridging current cryptographic practices with the demands of a quantum-threatened future.

## Future Work

This hybrid QKD-PQC system lays a solid foundation for secure communication, but there are several opportunities for improvement. First, replacing the simulated BB84 protocol with real quantum hardware (e.g., IBM Quantum) can address practical challenges like noise and photon loss. Adding eavesdropping detection and quantum error correction would enhance security and reliability. Optimizing Kyber512’s large 6400-bit key size or exploring lighter post-quantum algorithms  could improve performance and scalability. Extending the framework to quantum networks, such as quantum repeaters or satellite-based QKD, would enable long-distance secure communication. More advanced key derivation methods, beyond simple XOR, and integration of additional quantum-resistant algorithms could further strengthen security. Finally, aligning with NIST post-quantum standards and deploying the system in real-world applications like secure messaging or financial transactions will ensure practical adoption and interoperability. These advancements can make the system more robust and ready for the quantum era.

## References

Pei Zeng et al. (2024). “Practical Hybrid PQC-QKD Protocols with Enhanced Security and Performance” – arXiv preprint arXiv:2411.01086

G. Garg, A. Garg (2024). “Post-Quantum Cryptography and Quantum Key Distribution: An In-Depth Survey” – SSRN Electronic Journal

Quantum Cryptography Review (2015). “Quantum Cryptography: Key Distribution and Beyond” – Springer


> The research poster for this project can be found in the [BeyondQuantum Proceedings 2025](https://thinkingbeyond.education/beyondquantum_proceedings_2025/).

