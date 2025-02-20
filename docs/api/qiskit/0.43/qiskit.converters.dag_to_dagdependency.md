---
title: dag_to_dagdependency
description: API reference for qiskit.converters.dag_to_dagdependency
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.converters.dag_to_dagdependency
---

<span id="qiskit-converters-dag-to-dagdependency" />

# qiskit.converters.dag\_to\_dagdependency

<span id="qiskit.converters.dag_to_dagdependency" />

`dag_to_dagdependency(dag, create_preds_and_succs=True)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/converters/dag_to_dagdependency.py "view source code")

Build a `DAGDependency` object from a `DAGCircuit`.

**Parameters**

*   **dag** ([*DAGCircuit*](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")) – the input dag.
*   **create\_preds\_and\_succs** (*bool*) – whether to construct lists of predecessors and successors for every node.

**Returns**

the DAG representing the input circuit as a dag dependency.

**Return type**

[DAGDependency](qiskit.dagcircuit.DAGDependency "qiskit.dagcircuit.DAGDependency")

