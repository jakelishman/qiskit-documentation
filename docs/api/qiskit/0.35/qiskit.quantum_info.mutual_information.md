---
title: mutual_information
description: API reference for qiskit.quantum_info.mutual_information
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.quantum_info.mutual_information
---

# qiskit.quantum\_info.mutual\_information

<span id="qiskit.quantum_info.mutual_information" />

`mutual_information(state, base=2)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/quantum_info/states/measures.py "view source code")

Calculate the mutual information of a bipartite state.

The mutual information $I$ is given by:

$$
I(\rho_{AB}) = S(\rho_A) + S(\rho_B) - S(\rho_{AB})
$$

where $\rho_A=Tr_B[\rho_{AB}], \rho_B=Tr_A[\rho_{AB}]$, are the reduced density matrices of the bipartite state $\rho_{AB}$.

**Parameters**

*   **state** ([*Statevector*](qiskit.quantum_info.Statevector "qiskit.quantum_info.Statevector")  *or*[*DensityMatrix*](qiskit.quantum_info.DensityMatrix "qiskit.quantum_info.DensityMatrix")) – a bipartite state.
*   **base** (*int*) – the base of the logarithm \[Default: 2].

**Returns**

The mutual information $I(\rho_{AB})$.

**Return type**

float

**Raises**

*   **QiskitError** – if the input state is not a valid QuantumState.
*   **QiskitError** – if input is not a bipartite QuantumState.

