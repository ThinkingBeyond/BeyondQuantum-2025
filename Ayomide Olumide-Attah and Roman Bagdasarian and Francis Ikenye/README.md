![BeyondQuantum Banner for Research Projects](../BeyondQuantum_Banner_Research_Projects_2025.png)

# Quantum Methods for Modular Exponentiation in Shor's Algorithm

## Repository Structure
``` text
.
├── discrete-Fourier-transform/
│   ├── discrete-fourier-transform.ipynb     # Discrete Fourier transform modular multiplication
│   ├── metadata.txt                         # Example circuit metadata
│   └── statevector.txt                      # Example circuit statevector
├── modexp_comparison/
│   ├── modexp_comparison.ipynb              # Modular exponentiation comparison analysis
└── README.md
```

## Research Question

How to implement the quantum modular exponentiation component in Shor's algorithm for near-term quantum hardware?

This project investigates and evaluates two distinct approaches:
- **Discrete Fourier transform-based modular multiplication**
- **Toffoli gates-based modular exponentiation**

## Motivation

**Shor's algorithm** for prime factorisation delivers an *exponential* speedup over the best-known classical algorithms, fundamentally threatening current cryptographic security.

However, the **modular exponentiation operation** is the **runtime bottleneck** in practical implementations, demanding substantial quantum resources.

The motivation is to reduce the total number of qubits, lower gate complexity, and minimise circuit depth for near-term quantum hardware.

## Implementation

**Discrete Fourier transform-based modular multiplication**
- Notebook: [`discrete-fourier-transform.ipynb`](https://github.com/ThinkingBeyond/BeyondQuantum-2025/blob/main/Ayomide%20Olumide-Attah%20and%20Roman%20Bagdasarian%20and%20Francis%20Ikenye/discrete-Fourier-transform/discrete-fourier-transform.ipynb)
- Quantum circuit is entirely implemented in terms of the standard quantum circuit for the discrete Fourier transform and its variants based on a relation between the modular multiplication operator and generalizations of discrete Fourier transforms

## Results

### Performance comparison graph for Toffoli gates-based versus discrete Fourier transform-based modular multiplication

![Modular Exponentiation Comparison](https://github.com/ThinkingBeyond/BeyondQuantum-2025/blob/main/Ayomide%20Olumide-Attah%20and%20Roman%20Bagdasarian%20and%20Francis%20Ikenye/modexp_comparison/modexp_comparison.svg)

### Circuit complexity for an $L$-bit integer $L = \lceil \log_2 N \rceil$

| Implementation             | Qubits   | Modular Exponentiation       || Circuit                          ||
|----------------------------|----------|-----------------|-------------|-----------------|-----------------|
|                            |          | Gates           | Depth       | Gates           | Depth           |
| Discrete Fourier transform | $2L$     | $O(L^2)$        | $O(L^2)$    | $O(L^3)$        | $O(L^3)$        |
| Toffoli gates              | $2L + 2$ | $O(L^2 \log L)$ | $O(L^2)$    | $O(L^3 \log L)$ | $O(L^3)$        |

## Conclusions

- **Mathematical analysis**: The **discrete Fourier transform**-based modular multiplication achieves a qubit and gate complexity reduction
- **Empirical analysis**: The significant **speedup factor** depicted significant issues in the implementation of Toffoli gates-based modular exponentiation on the existing hardware
- **Scalability**: The discrete Fourier transform-based modular multiplication offers promising results

## Future Work

### Industry Applications
- Deploy implementations on **physical quantum hardware**
- Integrate fault-tolerant **error correction** schemes
- Cross-platform benchmark in **quantum software frameworks**

### Academic Extensions
- Develop an **educational article** presenting analysis and conclusions
- Extend to **integer factorisation** via Quantum Annealing or hybrid classical-quantum methods
- Evaluate resource requirements for factoring 2048-bit RSA integers on noisy qubits (Gidney, 2025)

## References

- P. W. Shor. “Algorithms for quantum computation: discrete logarithms and factoring.” In *Proceedings of the 35th Annual Symposium on Foundations of Computer Science*, Santa Fe, NM, USA: IEEE Computer Society Press, 1994, pp. 124–134. [IEEE Explore](https://ieeexplore.ieee.org/document/365700)
- P. W. Shor. “Polynomial-Time Algorithms for Prime Factorization and Discrete Logarithms on a Quantum Computer.” *SIAM Journal on Computing*, vol. 26, no. 5, pp. 1484–1509, Oct. 1997. [arXiv:quant-ph/9508027](https://arxiv.org/abs/quant-ph/9508027)
- Thomas Häner, Martin Roetteler, and Krysta M. Svore. “Factoring using 2n+2 qubits with Toffoli based modular multiplication.” *Quantum Information & Computation*, vol. 17, no. 7–8, pp. 673–684, Jun. 01, 2017. [arXiv:1611.07995](https://arxiv.org/abs/1611.07995)
- A. M. Patoary, A. Vikram, and V. Galitski. “A discrete Fourier transform based quantum circuit for modular multiplication in Shor’s algorithm.” Mar. 20, 2025. [arXiv:2503.10008](https://arxiv.org/abs/2503.10008)
- Craig Gidney. “Creating bigger controlled nots from single qubit, Toffoli, and CNOT gates, without workspace.” StackExchange Q&A, 2015. [cs.stackexchange.com](http://cs.stackexchange.com/questions/40933/)

---

> The research poster for this project can be found in the [BeyondQuantum Proceedings 2025](https://thinkingbeyond.education/beyondquantum_proceedings_2025/).

