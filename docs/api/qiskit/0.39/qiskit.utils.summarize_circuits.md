---
title: summarize_circuits
description: API reference for qiskit.utils.summarize_circuits
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.utils.summarize_circuits
---

# qiskit.utils.summarize\_circuits

<span id="qiskit.utils.summarize_circuits" />

`summarize_circuits(circuits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/utils/circuit_utils.py "view source code")

## Summarize circuits based on QuantumCircuit, and five metrics are summarized.

*   Number of qubits
*   Number of classical bits
*   Number of operations
*   Depth of circuits
*   Counts of different gate operations

The average statistic of the first four is provided if multiple circuits are provided.

**Parameters**

**circuits** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit") *or \[*[*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")*]*) – the to-be-summarized circuits

**Returns**

a formatted string records the summary

**Return type**

str

