# gate-optimization

This repository explores pulse-parameter optimization using the Qiskit Dynamics Python library.
The focus is on optimizing the width of a GaussianSquare pulse to implement an X gate.

## What I Learned

- The basics of the Qiskit Dynamics library and the pulse-optimization workflow.
- How to define and optimize custom pulse envelopes for single-qubit gates.
- How to integrate JAX with quantum dynamics for efficient gradient-based optimization.

## Main Challenges

- Choosing appropriate optimization methods and understanding why certain methods work better than others.
- Understanding why optimization of parameters such as sigma (and beta for the raised Gaussian) did not converge as reliably as width.
- Implementing a ScalableSymbolicPulse version of the raised Gaussian pulse.

## What I Found Most Interesting

- Learning to use Qiskit Dynamics for pulse optimization and seeing clear progress over a relatively short time. Going from limited knowledge of the library to defining and optimizing my own pulse parameters was especially rewarding.
- Discovering how much freedom there is in pulse optimization: in principle almost any pulse shape can be defined and optimized, with many possible optimization methods. Implementing the raised cosine pulse was particularly beneficial for learning how to work with parametrized pulse envelopes.
- Observing how different optimization methods behave in practice, especially why some converge reliably while others fail. I still do not know the full answer to this question, but it strongly motivated me to learn more about optimization theory.

## Future Improvements

- Extending the qubit model to include higher energy levels to capture more realistic dynamics and increased sensitivity to pulse parameters. In this regime, amplitude would become an interesting optimization parameter, and pulse fidelity would depend more strongly on properties such as smoothness, not just width.
- Expanding pulse customization by adding more pulse shapes (i.e., defining functions that generate ScalableSymbolicPulses for specific envelopes)
- improve how the code handles different optimization methods.
- Improve my understanding of different optimization methods in order to select the most appropriate approach for a specific control problem.
- Extending the code to to support optimization of other single-qubit gates.
  
## Installation Instructions

This notebook requires the following Python libraries:

- **[Qiskit Dynamics](https://qiskit.org/documentation/dynamics/)** 
- **[SciPy](https://scipy.org/)** 
- **[JAX](https://github.com/google/jax)**
- **[Qiskit](https://quantum.cloud.ibm.com/docs/en/guides)**
- **[NumPy](https://numpy.org/)**

Install libraries with `pip` as:
```bash
pip install qiskit_dynamics scipy jax qiskit numpy
```
The notebook was developed and tested with:

Python: 3.12.5
NumPy: 2.4.2
Qiskit: 1.3.0
SciPy: 1.17.0
Qiskit_dynamics 0.6.0
