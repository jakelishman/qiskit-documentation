---
title: get_ghz_po_para
description: API reference for qiskit.ignis.verification.get_ghz_po_para
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.ignis.verification.get_ghz_po_para
---

<span id="qiskit-ignis-verification-get-ghz-po-para" />

# qiskit.ignis.verification.get\_ghz\_po\_para

<span id="qiskit.ignis.verification.get_ghz_po_para" />

`get_ghz_po_para(n)`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.5/qiskit/ignis/verification/entanglement/linear.py "view source code")

This function creates a Parity Oscillation circuit with n qubits, where the middle superposition rotation around

the x and y axes is by delta

**Parameters**

**n** (`int`) – number of qubits

**Return type**

`Tuple`\[`QuantumCircuit`, `List`\[`Parameter`]]

**Returns**

The parity oscillation circuit and its Delta/minus-delta parameters

