# ancilla-free-hamming-weight

# Ancilla-Free Hamming Weight Quantum Circuit (Qiskit)

This repository contains a Qiskit-based implementation of an ancilla-efficient quantum circuit for computing the **Hamming weight** of a binary input string. The implementation follows the shallow quantum circuit framework proposed by Zi et al., which encodes the Hamming weight into the **phase of quantum states** and retrieves the result using the **Inverse Quantum Fourier Transform (QFT†)**.

The project demonstrates how quantum algorithms can reduce the **ancillary qubit overhead** present in classical-style quantum circuit designs.

---

## Overview

Quantum circuit design in the **Noisy Intermediate-Scale Quantum (NISQ)** era is constrained by:

- Limited number of available qubits
- Circuit depth limitations
- Noise and decoherence

Classical reversible circuit implementations (such as ripple-carry adders or encoders) often require a significant number of **ancillary qubits** to store intermediate results. This quickly becomes impractical on current hardware.

This project explores a more efficient approach by implementing an **ancilla-free Hamming weight algorithm**, where:

1. The Hamming weight of the input string is encoded into the **phase of counting qubits**
2. The encoded phase information is converted into a measurable binary output using the **Inverse Quantum Fourier Transform**

This approach significantly reduces the number of helper qubits required, making it more suitable for near-term quantum devices.

---

## Algorithm Summary

The algorithm follows two primary stages:

### 1. Phase Encoding

The Hamming weight of an input string \( |x| \) is encoded into the phase of a control qubit using a specialized controlled phase gate:

\[
(\alpha|0\rangle + \beta|1\rangle)\otimes|x\rangle
\rightarrow
(\alpha|0\rangle + \beta e^{i\theta(n-2|x|)}|1\rangle)\otimes|x\rangle
\]

This phase accumulation effectively stores the value of the Hamming weight across the counting qubits.

### 2. Phase Decoding

After encoding the phase information, an **Inverse Quantum Fourier Transform (QFT†)** is applied to the counting qubits. This converts the phase information into a **binary representation of the Hamming weight**, which can be measured directly.

For an input of size **n**, the algorithm requires:

\[
m = \lceil \log_2(n+1) \rceil
\]

ancillary counting qubits.


## Implemented Circuits

In addition to the main Hamming weight algorithm, foundational quantum circuits were explored to understand the limitations of classical circuit translation in quantum computing:

- Full Adder
- 2×4 Decoder
- Symmetric Boolean Function Circuit

These circuits illustrate how ancillary qubits scale with problem size and motivate the need for more efficient algorithms.



Libraries used:

- **Qiskit** – Quantum circuit design and simulation
- **NumPy** – Numerical computations
- **Matplotlib** – Visualization of simulation results


## References

1. Zi, W., Nie, Y., & Sun, X.  
   *Shallow Quantum Circuit Implementation of Symmetric Functions With Limited Ancillary Qubits.*

2. Nielsen, M. A., & Chuang, I. L.  
   *Quantum Computation and Quantum Information.*

3. IBM Quantum  
   Qiskit Documentation  
   https://qiskit.org


## Author

Pranav Surapuraju
India

