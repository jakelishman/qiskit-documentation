---
title: random_density_matrix
description: API reference for qiskit.quantum_info.random_density_matrix
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.quantum_info.random_density_matrix
---

# random\_density\_matrix

<span id="qiskit.quantum_info.random_density_matrix" />

`random_density_matrix(dims, rank=None, method='Hilbert-Schmidt', seed=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/states/random.py "view source code")

Generator a random DensityMatrix.

**Parameters**

*   **dims** (*int or tuple*) – the dimensions of the DensityMatrix.
*   **rank** (*int or None*) – Optional, the rank of the density matrix. The default value is full-rank.
*   **method** (*string*) – Optional. The method to use. ‘Hilbert-Schmidt’: (Default) sample from the Hilbert-Schmidt metric. ‘Bures’: sample from the Bures metric.
*   **seed** (*int or np.random.Generator*) – Optional. Set a fixed seed or generator for RNG.

**Returns**

the random density matrix.

**Return type**

[DensityMatrix](qiskit.quantum_info.DensityMatrix "qiskit.quantum_info.DensityMatrix")

**Raises**

**QiskitError** – if the method is not valid.

