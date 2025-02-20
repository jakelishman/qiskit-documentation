---
title: pauli_group
description: API reference for qiskit.quantum_info.pauli_group
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.quantum_info.pauli_group
---

# qiskit.quantum\_info.pauli\_group

<span id="qiskit.quantum_info.pauli_group" />

`pauli_group(number_of_qubits, case='weight')`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/quantum_info/operators/pauli.py "view source code")

DEPRECATED: Return the Pauli group with 4^n elements.

This function is deprecated. Use [`pauli_basis()`](qiskit.quantum_info.pauli_basis "qiskit.quantum_info.pauli_basis") for equivalent functionality.

The phases have been removed. case ‘weight’ is ordered by Pauli weights and case ‘tensor’ is ordered by I,X,Y,Z counting lowest qubit fastest.

**Parameters**

*   **number\_of\_qubits** (*int*) – number of qubits
*   **case** (*str*) – determines ordering of group elements (‘weight’ or ‘tensor’)

**Returns**

list of Pauli objects

**Return type**

list

**Raises**

*   **QiskitError** – case is not ‘weight’ or ‘tensor’
*   **QiskitError** – number\_of\_qubits is larger than 4

