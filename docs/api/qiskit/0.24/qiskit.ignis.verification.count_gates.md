---
title: count_gates
description: API reference for qiskit.ignis.verification.count_gates
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.ignis.verification.count_gates
---

<span id="qiskit-ignis-verification-count-gates" />

# qiskit.ignis.verification.count\_gates

<span id="qiskit.ignis.verification.count_gates" />

`count_gates(qobj, basis, qubits)`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.5/qiskit/ignis/verification/randomized_benchmarking/rb_utils.py "view source code")

Take a compiled qobj and output the number of gates in each circuit.

**Parameters**

*   **qobj** (*QasmQObj*) – compiled qobj.
*   **basis** (*list*) – gates basis for the qobj.
*   **qubits** (*list*) – qubits to count over.

**Returns**

n x l x m list of number of gates.

> *   n: number of circuits,
> *   l: number of qubits,
> *   m: number of gates in basis.

**Return type**

list

## Additional Information:

nQ gates are counted in each qubit’s set of gates.

