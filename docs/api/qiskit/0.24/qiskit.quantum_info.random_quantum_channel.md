---
title: random_quantum_channel
description: API reference for qiskit.quantum_info.random_quantum_channel
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.quantum_info.random_quantum_channel
---

<span id="qiskit-quantum-info-random-quantum-channel" />

# qiskit.quantum\_info.random\_quantum\_channel

<span id="qiskit.quantum_info.random_quantum_channel" />

`random_quantum_channel(input_dims=None, output_dims=None, rank=None, seed=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.16/qiskit/quantum_info/operators/random.py "view source code")

Return a random CPTP quantum channel.

This constructs the Stinespring operator for the quantum channel by sampling a random isometry from the unitary Haar measure.

**Parameters**

*   **input\_dims** (*int or tuple*) – the input dimension of the channel.
*   **output\_dims** (*int or tuple*) – the input dimension of the channel.
*   **rank** (*int*) – Optional. The rank of the quantum channel Choi-matrix.
*   **seed** (*int or np.random.Generator*) – Optional. Set a fixed seed or generator for RNG.

**Returns**

a quantum channel operator.

**Return type**

[Stinespring](qiskit.quantum_info.Stinespring "qiskit.quantum_info.Stinespring")

**Raises**

**QiskitError** – if rank or dimensions are invalid.

