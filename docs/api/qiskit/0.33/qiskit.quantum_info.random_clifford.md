---
title: random_clifford
description: API reference for qiskit.quantum_info.random_clifford
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.quantum_info.random_clifford
---

# qiskit.quantum\_info.random\_clifford

<span id="qiskit.quantum_info.random_clifford" />

`random_clifford(num_qubits, seed=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/quantum_info/operators/symplectic/random.py "view source code")

Return a random Clifford operator.

The Clifford is sampled using the method of Reference \[1].

**Parameters**

*   **num\_qubits** (*int*) – the number of qubits for the Clifford
*   **seed** (*int or np.random.Generator*) – Optional. Set a fixed seed or generator for RNG.

**Returns**

a random Clifford operator.

**Return type**

[Clifford](qiskit.quantum_info.Clifford "qiskit.quantum_info.Clifford")

## Reference:

1.  S. Bravyi and D. Maslov, *Hadamard-free circuits expose the structure of the Clifford group*. [arXiv:2003.09412 \[quant-ph\]](https://arxiv.org/abs/2003.09412)

