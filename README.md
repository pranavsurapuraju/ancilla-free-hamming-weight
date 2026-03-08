# Ancilla-Free Hamming Weight Quantum Circuit with T-Gate Reduction

This project implements an efficient quantum circuit for computing the **Hamming weight of a binary input string** using Qiskit. The circuit follows the shallow circuit framework proposed by **Zi et al.**, where the Hamming weight is encoded into quantum phase rotations and later decoded using the **Inverse Quantum Fourier Transform (QFT†)**.

The primary focus of this implementation is **reducing the number of costly T gates**, which are a major resource in fault-tolerant quantum computing. To achieve this, the circuit explores **different ancilla usage strategies**, including **hard ancilla (clean ancilla initialized to |0⟩)** and **soft/borrowed ancilla (ancilla that can start in any state but must be restored)**. These techniques help reduce circuit cost while maintaining correct computation of the Hamming weight.


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

