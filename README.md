# Experimental Verification of Bell State Entanglement on Superconducting Quantum Architecture

**Author:** Jenovic Lumu  
**Framework:** Qiskit v1.x | IBM Quantum Cloud  

## Abstract
This project investigates the generation and measurement of maximally entangled bipartite states (EPR pairs) using IBM's superconducting quantum processors. Utilizing the Qiskit SDK, a quantum circuit was designed to achieve the $|\Phi^+\rangle$ Bell State via the sequential application of Hadamard and Controlled-NOT (CNOT) gates. The circuit was initially verified via a noiseless local simulator (`AerSimulator`) to confirm an ideal probability distribution across the $|00\rangle$ and $|11\rangle$ basis states.

## Methodology
To observe the effects of quantum decoherence and gate infidelities on physical hardware, the circuit was transpiled and optimized for the `ibm_fez` quantum backend. Execution was handled via the modern Qiskit Runtime `SamplerV2` primitive, ensuring the code adheres to current industry-standard quantum execution models.

## Hardware Observation & Analysis
The circuit was executed on the `ibm_fez` physical backend for 1,024 shots. The resulting measurement yielded the entangled states $|00\rangle$ (486 counts) and $|11\rangle$ (458 counts), confirming successful baseline entanglement.

Notably, the physical hardware also recorded non-entangled states of $|01\rangle$ (32 counts) and $|10\rangle$ (48 counts). These anomalous readings represent an approximate 7.8% error rate, successfully demonstrating the practical effects of quantum decoherence, thermal noise, and gate infidelity inherent in Noisy Intermediate-Scale Quantum (NISQ) architecture.

---

## Technical Specifications

### Dependencies
To replicate this experiment, the following environment is required:
* Python 3.10+
* `qiskit` (v1.0+)
* `qiskit-ibm-runtime`
* `qiskit-aer`
* `matplotlib` (for histogram visualization)

### Execution
1. Clone this repository to your local environment.
2. Ensure you have an active API token from the [IBM Quantum Platform](https://quantum.ibm.com/).
3. Run the `lab_check.ipynb` Jupyter Notebook to execute the circuit locally via `AerSimulator` or push the job to an active IBM cloud node.

## Future Work
Subsequent iterations of this project will explore error mitigation techniques, specifically focusing on dynamical decoupling and readout error mitigation to suppress the ~7.8% noise observed on current hardware topologies.
