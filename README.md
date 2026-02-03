# gate-optimization

This repository explores pulse-parameter optimization using the Qiskit Dynamics Python library.
The focus is on optimizing the width of a GaussianSquare pulse to implement an X gate.

## What I Learned

- The basics of the Qiskit Dynamics library and the pulse-optimization workflow.
- How to define and optimize custom pulse envelopes for single-qubit gates.
- How to integrate JAX with quantum dynamics for efficient gradient-based optimization.

## Main Challenges

- Choosing appropriate optimization methods and understanding why certain methods work better than others.
- Figuring out why optimization of parameters such as sigma (and beta for the raised Gaussian) did not converge as reliably as width for our system.
- Learning how to implement arbitrary pulse envelopes compatible with JAX, starting from their mathematical definitions

## What I Found Most Interesting

- Discovering how much freedom there is in pulse optimization: in principle almost any pulse shape can be defined and optimized, with many possible optimization methods. 
- Observing how different optimization methods behave in practice, especially why some converge reliably while others fail. It motivates me to learn more about optimization theory.
- Overall, learning how to work with Qiskit dynamics


## Future Improvements

- Extending the qubit model to include higher energy levels to capture more realistic dynamics and increased sensitivity to pulse parameters. In this regime, amplitude would become an interesting optimization parameter, and pulse fidelity would depend more strongly on parameters such as sigma, not just width.
- Improve how the code handles different optimization methods. Currently it uses the code aimed for gradient-based optimization also for the Nelder-Mead method that does not utilize gradients.
- Extending the code to to support optimization of other single-qubit gates.
- Expanding pulse customization by adding more supported pulse shapes (i.e., defining functions that generate ScalableSymbolicPulses for specific envelopes)

  
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
