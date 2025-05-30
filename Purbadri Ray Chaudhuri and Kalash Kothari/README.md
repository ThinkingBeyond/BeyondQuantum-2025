![BeyondQuantum Banner for Research Projects](../BeyondQuantum_Banner_Research_Projects_2025.png)

# Qubit Manipulation in Quantum Circuits -  Solving Grover’s Algorithm for 2- and 3-Qubit Systems.
---
The following project is done by purbadri Ray Chaudhuri and Kalash Sanjay Kothari, Mentored by Ms. Madhurima. This project solely explores how the Qubit Manipulation works and how it can be advanced to next stages where we can use circuit Kinniting and Cuting.

---
## Introduction

Over the past few decades, quantum computing has emerged as a groundbreaking paradigm that redefines the boundaries of classical computation. At the core of this revolution lies the qubit (quantum bit), which, unlike its classical counterpart restricted to binary states (0 or 1), can exist in a superposition of both. This property, when combined with entanglement—a quantum phenomenon where the state of one qubit is intrinsically linked to another—and quantum interference, enables quantum systems to process information in ways that are fundamentally more powerful and non-intuitive than classical methods.

Quantum computation is carried out by manipulating qubits using sequences of quantum gates—reversible, unitary operations mathematically represented by matrices acting on complex Hilbert spaces. These gates serve as the essential building blocks of quantum circuits, analogous to logic gates in classical systems. However, unlike classical algorithms that follow deterministic logic paths, quantum algorithms evolve through dynamic superpositions and entangled states, demanding precise control over qubit transformations and interactions to harness their computational advantage.

---

## Research Question

**How can foundational concepts in qubit manipulation be applied to implement algorithms like Grover’s Algorithm in small quantum systems, and how can these be scaled correctly to use the concepts of circuit Knitting and Cutting with low enough noise**

---

## Motivation

As we approach the physical and theoretical limits of classical computation, quantum computing offers a fundamentally new model based on the physics of quantum mechanics. Grover’s Algorithm provides a rare example of a provable quadratic speedup for unstructured search, illustrating the potential of quantum systems to outperform classical ones. 

Despite theoretical advancements, quantum algorithms face significant implementation barriers due to:
- Short qubit coherence times
- Gate infidelity
- Limited circuit width and depth on current hardware

Thus, this project is motivated by few critical needs:
1. To *deepen conceptual understanding* of qubit-based computation and how gate operations manipulate quantum states.
2. To *bridge the gap* between theoretical algorithms and practical quantum computing by building efficient enough code algorithm.
3. To *Make a ptoper understanding* of how can be techniques such as circuit Knitting be helpful in scaling the Quantum system and Qubit Manipulation

---

## Methodology and Implementation

### 1. Qubit Representation and State Preparation
- Qubits are described using Dirac notation
- The state of a Qubit is visualized using the **Bloch Sphere**.
- Multi-qubit registers are initialized using the Kronecker product of individual qubits:  
  (|0>^n)

### 2. Quantum Gates and Implementation
- **Single-Qubit Gates**:
  - Pauli-X (NOT), Pauli-Y, Pauli-Z
  - Hadamard (H): Creates equal superpositions
  - Phase gates: S (π/2 shift), T (π/4 shift)
  - Rotation gates: Rx(θ), Ry(θ), Rz(θ)

- **Two-Qubit Gates**:
  - CNOT (Controlled-NOT): Entangling gate
  - SWAP and Toffoli gates: Used for conditional control logic

- All gates are defined using **unitary matrix transformations** over the complex vector spaces.

### 3. Grover’s Algorithm Construction
1. **Initialization**: All qubits are placed in a superposition using H gate or the Hadamard gate.
2. **Oracle Operator**: Implements a phase flip to mark the target state, This operator is unique for different states.
3. **Diffusion Operator**: Performs amplitude amplification using reflection over the mean.
4. **Grover Iteration**: Combination of oracle and diffusion operators repeated ⌊π/4√N⌋ times.
5. **Measurement**: Collapse the state and extract the marked solution with high probability.

### 4. Circuit Knitting and Cutting
- Introduced as a **resource-aware simulation strategy** for decomposing large circuits.
- Demonstrated potential for reconstructing large-scale quantum results by stitching together smaller subcircuits.
- Using these circuit to showcase advanced qubit manipulation
---

## Results and Analysis

### Simulated Grover's Algorithm on:
- **2-Qubit System (N=4)**: 1 iteration → 100% target state amplification.
- **3-Qubit System (N=8)**: 2 iterations → ~93% probability of correct solution.

### 📈 Probability Distribution Table

| Qubit Count | Database Size (N) | Grover Iterations | Target State Probability (in ideal condition) |
|-------------|-------------------|-------------------|--------------------------|
| 2 Qubits    | 4                 | 1                 | 100%                     |
| 3 Qubits    | 8                 | 2                 | ~93%                     |

Visual inspection using Qiskit’s statevector and histogram backends confirmed theoretical predictions.

---

## Conclusion

This project demonstrates that:

- **Precise qubit manipulation** through linear algebraic operations enables complex quantum logic construction.
- **Grover’s Algorithm** offers a hands-on illustration of quantum advantage for search problems.
- **Circuit knitting** presents a practical approach for working within hardware constraints and simulating higher-order algorithms in modular form.

These outcomes reinforce the importance of bridging theory with implementation as we move toward fault-tolerant, scalable quantum systems.

---

## Future Work

To build upon this research, future directions include:

1. **Extending to 4–5 Qubit Systems** using advanced circuit knitting methods.
2. **Quantum Error Correction**: Integrate with surface code to mitigate decoherence during oracle evaluation.
3. **Implementing of Circuit cutting**: Implementing Circuit cutting on real time software 

---

## References

1. Grover, L. K. (1996). *A fast quantum mechanical algorithm for database search*. [Proceedings of STOC 1996](https://doi.org/10.1145/237814.237866)
2. Qiskit Textbook. *Learn Quantum Computation using Qiskit*. [https://qiskit.org/learn](https://qiskit.org/learn)

---

> 🧾 The research poster for this project can be found in the [BeyondQuantum Proceedings 2025](https://thinkingbeyond.education/beyondquantum_proceedings_2025/)
