---
title: pauli_basis
description: API reference for qiskit.quantum_info.pauli_basis
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.quantum_info.pauli_basis
---

<span id="qiskit-quantum-info-pauli-basis" />

# qiskit.quantum\_info.pauli\_basis

<span id="qiskit.quantum_info.pauli_basis" />

`qiskit.quantum_info.pauli_basis(num_qubits, weight=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/quantum_info/operators/symplectic/pauli_utils.py "view source code")

Return the ordered PauliList for the n-qubit Pauli basis.

**Parameters**

*   **num\_qubits** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – number of qubits
*   **weight** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – if True optionally return the basis sorted by Pauli weight rather than lexicographic order (Default: False)

**Returns**

the Paulis for the basis

**Return type**

[PauliList](qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList")

