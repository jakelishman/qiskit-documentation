---
title: circuit_to_dagdependency
description: API reference for qiskit.converters.circuit_to_dagdependency
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.converters.circuit_to_dagdependency
---

# qiskit.converters.circuit\_to\_dagdependency

<span id="qiskit.converters.circuit_to_dagdependency" />

`circuit_to_dagdependency(circuit, create_preds_and_succs=True)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/converters/circuit_to_dagdependency.py "view source code")

Build a `DAGDependency` object from a `QuantumCircuit`.

**Parameters**

*   **circuit** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – the input circuit.
*   **create\_preds\_and\_succs** (*bool*) – whether to construct lists of predecessors and successors for every node.

**Returns**

the DAG representing the input circuit as a dag dependency.

**Return type**

[DAGDependency](qiskit.dagcircuit.DAGDependency "qiskit.dagcircuit.DAGDependency")

