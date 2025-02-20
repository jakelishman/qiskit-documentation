---
title: DAGOpNode
description: API reference for qiskit.dagcircuit.DAGOpNode
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.dagcircuit.DAGOpNode
---

# DAGOpNode

<span id="qiskit.dagcircuit.DAGOpNode" />

`qiskit.dagcircuit.DAGOpNode(op, qargs=(), cargs=())`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.25/qiskit/dagcircuit/dagnode.py "view source code")

Bases: [`DAGNode`](qiskit.dagcircuit.DAGNode "qiskit.dagcircuit.dagnode.DAGNode")

Object to represent an Instruction at a node in the DAGCircuit.

Create an Instruction node

## Attributes

<span id="qiskit.dagcircuit.DAGOpNode.op" />

### op

<span id="qiskit.dagcircuit.DAGOpNode.qargs" />

### qargs

<span id="qiskit.dagcircuit.DAGOpNode.cargs" />

### cargs

<span id="qiskit.dagcircuit.DAGOpNode.sort_key" />

### sort\_key

<span id="qiskit.dagcircuit.DAGOpNode.name" />

### name

Returns the Instruction name corresponding to the op for this node

## Methods

### semantic\_eq

<span id="qiskit.dagcircuit.DAGOpNode.semantic_eq" />

`static semantic_eq(node1, node2, bit_indices1, bit_indices2)`

Check if DAG nodes are considered equivalent, e.g., as a node\_match for [`rustworkx.is_isomorphic_node_match()`](https://qiskit.org/ecosystem/rustworkx/apiref/rustworkx.is_isomorphic_node_match.html#rustworkx.is_isomorphic_node_match "(in rustworkx v0.13.2)").

**Parameters**

*   **node1** ([*DAGOpNode*](#qiskit.dagcircuit.DAGOpNode "qiskit.dagcircuit.DAGOpNode")*,* [*DAGInNode*](qiskit.dagcircuit.DAGInNode "qiskit.dagcircuit.DAGInNode")*,* [*DAGOutNode*](qiskit.dagcircuit.DAGOutNode "qiskit.dagcircuit.DAGOutNode")) – A node to compare.
*   **node2** ([*DAGOpNode*](#qiskit.dagcircuit.DAGOpNode "qiskit.dagcircuit.DAGOpNode")*,* [*DAGInNode*](qiskit.dagcircuit.DAGInNode "qiskit.dagcircuit.DAGInNode")*,* [*DAGOutNode*](qiskit.dagcircuit.DAGOutNode "qiskit.dagcircuit.DAGOutNode")) – The other node to compare.
*   **bit\_indices1** ([*dict*](https://docs.python.org/3/library/stdtypes.html#dict "(in Python v3.12)")) – Dictionary mapping Bit instances to their index within the circuit containing node1
*   **bit\_indices2** ([*dict*](https://docs.python.org/3/library/stdtypes.html#dict "(in Python v3.12)")) – Dictionary mapping Bit instances to their index within the circuit containing node2

**Returns**

If node1 == node2

**Return type**

[Bool](circuit_classical#qiskit.circuit.classical.types.Bool "qiskit.circuit.classical.types.Bool")

