---
title: entropy
description: API reference for qiskit.quantum_info.entropy
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.quantum_info.entropy
---

# entropy

<span id="qiskit.quantum_info.entropy" />

`entropy(state, base=2)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/states/measures.py "view source code")

Calculate the von-Neumann entropy of a quantum state.

The entropy $S$ is given by

**Parameters**

*   **state** ([*Statevector*](qiskit.quantum_info.Statevector "qiskit.quantum_info.Statevector")  *or*[*DensityMatrix*](qiskit.quantum_info.DensityMatrix "qiskit.quantum_info.DensityMatrix")) – a quantum state.
*   **base** (*int*) – the base of the logarithm \[Default: 2].

**Returns**

The von-Neumann entropy S(rho).

**Return type**

float

**Raises**

**QiskitError** – if the input state is not a valid QuantumState.

