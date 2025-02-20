---
title: euler_angles_1q
description: API reference for qiskit.quantum_info.euler_angles_1q
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.quantum_info.euler_angles_1q
---

<span id="qiskit-quantum-info-euler-angles-1q" />

# qiskit.quantum\_info.euler\_angles\_1q

<span id="qiskit.quantum_info.euler_angles_1q" />

`euler_angles_1q(unitary_matrix)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.16/qiskit/quantum_info/synthesis/two_qubit_decompose.py "view source code")

DEPRECATED: Compute Euler angles for a single-qubit gate.

Find angles (theta, phi, lambda) such that unitary\_matrix = phase \* Rz(phi) \* Ry(theta) \* Rz(lambda)

**Parameters**

**unitary\_matrix** (*ndarray*) – 2x2 unitary matrix

**Returns**

(theta, phi, lambda) Euler angles of SU(2)

**Return type**

tuple

**Raises**

**QiskitError** – if unitary\_matrix not 2x2, or failure

