---
title: get_ghz_simple
description: API reference for qiskit.ignis.verification.get_ghz_simple
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.ignis.verification.get_ghz_simple
---

<span id="qiskit-ignis-verification-get-ghz-simple" />

# qiskit.ignis.verification.get\_ghz\_simple

<span id="qiskit.ignis.verification.get_ghz_simple" />

`get_ghz_simple(n, measure=True, full_measurement=True)`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.5/qiskit/ignis/verification/entanglement/linear.py "view source code")

Creates a linear GHZ state with the option of measurement

**Parameters**

*   **n** (`int`) – number of qubits
*   **measure** (`bool`) – Whether to add measurement gates
*   **full\_measurement** (`bool`) – Whether to append full measurement, or only on the first qubit. Relevant only for measure=True

**Return type**

`QuantumCircuit`

**Returns**

A linear GHZ Circuit

