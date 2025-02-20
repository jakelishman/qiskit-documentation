---
title: dagcircuit
description: API reference for qiskit.dagcircuit
in_page_toc_min_heading_level: 1
python_api_type: module
python_api_name: qiskit.dagcircuit
---

<span id="module-qiskit.dagcircuit" />

<span id="qiskit-dagcircuit" />

<span id="dag-circuits-qiskit-dagcircuit" />

# DAG Circuits

<span id="module-qiskit.dagcircuit" />

`qiskit.dagcircuit`

## Circuits as Directed Acyclic Graphs

|                                                                                                                   |                                                                                                          |
| ----------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| [`DAGCircuit`](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")()                                     | Quantum circuit as a directed acyclic graph.                                                             |
| [`DAGNode`](qiskit.dagcircuit.DAGNode "qiskit.dagcircuit.DAGNode")(\[nid])                                        | Parent class for DAGOpNode, DAGInNode, and DAGOutNode.                                                   |
| [`DAGOpNode`](qiskit.dagcircuit.DAGOpNode "qiskit.dagcircuit.DAGOpNode")(op\[, qargs, cargs, dag])                | Object to represent an Instruction at a node in the DAGCircuit.                                          |
| [`DAGInNode`](qiskit.dagcircuit.DAGInNode "qiskit.dagcircuit.DAGInNode")(wire)                                    | Object to represent an incoming wire node in the DAGCircuit.                                             |
| [`DAGOutNode`](qiskit.dagcircuit.DAGOutNode "qiskit.dagcircuit.DAGOutNode")(wire)                                 | Object to represent an outgoing wire node in the DAGCircuit.                                             |
| [`DAGDepNode`](qiskit.dagcircuit.DAGDepNode "qiskit.dagcircuit.DAGDepNode")(\[type, op, name, qargs, cargs, ...]) | Object to represent the information at a node in the DAGDependency().                                    |
| [`DAGDependency`](qiskit.dagcircuit.DAGDependency "qiskit.dagcircuit.DAGDependency")()                            | Object to represent a quantum circuit as a Directed Acyclic Graph (DAG) via operation dependencies (i.e. |

## Exceptions

<span id="qiskit.dagcircuit.DAGCircuitError" />

`qiskit.dagcircuit.DAGCircuitError(*msg)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/dagcircuit/exceptions.py "view source code")

Base class for errors raised by the DAGCircuit object.

Set the error message.

<span id="qiskit.dagcircuit.DAGDependencyError" />

`qiskit.dagcircuit.DAGDependencyError(*msg)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/dagcircuit/exceptions.py "view source code")

Base class for errors raised by the DAGDependency object.

Set the error message.

