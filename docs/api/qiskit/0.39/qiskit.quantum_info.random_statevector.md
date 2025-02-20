---
title: random_statevector
description: API reference for qiskit.quantum_info.random_statevector
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.quantum_info.random_statevector
---

# qiskit.quantum\_info.random\_statevector

<span id="qiskit.quantum_info.random_statevector" />

`random_statevector(dims, seed=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/quantum_info/states/random.py "view source code")

Generator a random Statevector.

The statevector is sampled from the uniform (Haar) measure.

**Parameters**

*   **dims** (*int or tuple*) – the dimensions of the state.
*   **seed** (*int or np.random.Generator*) – Optional. Set a fixed seed or generator for RNG.

**Returns**

the random statevector.

**Return type**

[Statevector](qiskit.quantum_info.Statevector "qiskit.quantum_info.Statevector")

