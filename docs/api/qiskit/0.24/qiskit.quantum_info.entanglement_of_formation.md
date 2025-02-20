---
title: entanglement_of_formation
description: API reference for qiskit.quantum_info.entanglement_of_formation
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.quantum_info.entanglement_of_formation
---

<span id="qiskit-quantum-info-entanglement-of-formation" />

# qiskit.quantum\_info.entanglement\_of\_formation

<span id="qiskit.quantum_info.entanglement_of_formation" />

`entanglement_of_formation(state)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.16/qiskit/quantum_info/states/measures.py "view source code")

Calculate the entanglement of formation of quantum state.

The input quantum state must be either a bipartite state vector, or a 2-qubit density matrix.

**Parameters**

**state** ([*Statevector*](qiskit.quantum_info.Statevector "qiskit.quantum_info.Statevector")  *or*[*DensityMatrix*](qiskit.quantum_info.DensityMatrix "qiskit.quantum_info.DensityMatrix")) – a 2-qubit quantum state.

**Returns**

The entanglement of formation.

**Return type**

float

**Raises**

*   **QiskitError** – if the input state is not a valid QuantumState.
*   **QiskitError** – if input is not a bipartite QuantumState.
*   **QiskitError** – if density matrix input is not a 2-qubit state.

