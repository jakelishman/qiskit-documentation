---
title: random_hermitian
description: API reference for qiskit.quantum_info.random_hermitian
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.quantum_info.random_hermitian
---

<span id="qiskit-quantum-info-random-hermitian" />

# qiskit.quantum\_info.random\_hermitian

<span id="qiskit.quantum_info.random_hermitian" />

`random_hermitian(dims, traceless=False, seed=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/quantum_info/operators/random.py "view source code")

Return a random hermitian Operator.

The operator is sampled from Gaussian Unitary Ensemble.

**Parameters**

*   **dims** (*int or tuple*) – the input dimension of the Operator.
*   **traceless** (*bool*) – Optional. If True subtract diagonal entries to return a traceless hermitian operator (Default: False).
*   **seed** (*int or np.random.Generator*) – Optional. Set a fixed seed or generator for RNG.

**Returns**

a Hermitian operator.

**Return type**

[Operator](qiskit.quantum_info.Operator "qiskit.quantum_info.Operator")

