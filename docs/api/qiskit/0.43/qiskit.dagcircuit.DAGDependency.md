---
title: DAGDependency
description: API reference for qiskit.dagcircuit.DAGDependency
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.dagcircuit.DAGDependency
---

# DAGDependency

<span id="qiskit.dagcircuit.DAGDependency" />

`DAGDependency`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/dagcircuit/dagdependency.py "view source code")

Bases: `object`

Object to represent a quantum circuit as a directed acyclic graph via operation dependencies (i.e. lack of commutation).

The nodes in the graph are operations represented by quantum gates. The edges correspond to non-commutation between two operations (i.e. a dependency). A directed edge from node A to node B means that operation A does not commute with operation B. The object’s methods allow circuits to be constructed.

The nodes in the graph have the following attributes: ‘operation’, ‘successors’, ‘predecessors’.

**Example:**

Bell circuit with no measurement.

```python
      ┌───┐
qr_0: ┤ H ├──■──
      └───┘┌─┴─┐
qr_1: ─────┤ X ├
           └───┘
```

The dependency DAG for the above circuit is represented by two nodes. The first one corresponds to Hadamard gate, the second one to the CNOT gate as the gates do not commute there is an edge between the two nodes.

**Reference:**

\[1] Iten, R., Moyard, R., Metger, T., Sutter, D. and Woerner, S., 2020. Exact and practical pattern matching for quantum circuit optimization. [arXiv:1909.05270](https://arxiv.org/abs/1909.05270)

Create an empty DAGDependency.

## Methods

<span id="qiskit-dagcircuit-dagdependency-add-clbits" />

### add\_clbits

<span id="qiskit.dagcircuit.DAGDependency.add_clbits" />

`DAGDependency.add_clbits(clbits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/dagcircuit/dagdependency.py "view source code")

Add individual clbit wires.

<span id="qiskit-dagcircuit-dagdependency-add-creg" />

### add\_creg

<span id="qiskit.dagcircuit.DAGDependency.add_creg" />

`DAGDependency.add_creg(creg)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/dagcircuit/dagdependency.py "view source code")

Add clbits in a classical register.

<span id="qiskit-dagcircuit-dagdependency-add-op-node" />

### add\_op\_node

<span id="qiskit.dagcircuit.DAGDependency.add_op_node" />

`DAGDependency.add_op_node(operation, qargs, cargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/dagcircuit/dagdependency.py "view source code")

Add a DAGDepNode to the graph and update the edges.

**Parameters**

*   **operation** ([*qiskit.circuit.Operation*](qiskit.circuit.Operation "qiskit.circuit.Operation")) – operation as a quantum gate
*   **qargs** (*list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of qubits on which the operation acts
*   **cargs** (*list\[*[*Clbit*](qiskit.circuit.Clbit "qiskit.circuit.Clbit")*]*) – list of classical wires to attach to

<span id="qiskit-dagcircuit-dagdependency-add-qreg" />

### add\_qreg

<span id="qiskit.dagcircuit.DAGDependency.add_qreg" />

`DAGDependency.add_qreg(qreg)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/dagcircuit/dagdependency.py "view source code")

Add qubits in a quantum register.

<span id="qiskit-dagcircuit-dagdependency-add-qubits" />

### add\_qubits

<span id="qiskit.dagcircuit.DAGDependency.add_qubits" />

`DAGDependency.add_qubits(qubits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/dagcircuit/dagdependency.py "view source code")

Add individual qubit wires.

<span id="qiskit-dagcircuit-dagdependency-copy" />

### copy

<span id="qiskit.dagcircuit.DAGDependency.copy" />

`DAGDependency.copy()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/dagcircuit/dagdependency.py "view source code")

Function to copy a DAGDependency object. :returns: a copy of a DAGDependency object. :rtype: DAGDependency

<span id="qiskit-dagcircuit-dagdependency-depth" />

### depth

<span id="qiskit.dagcircuit.DAGDependency.depth" />

`DAGDependency.depth()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/dagcircuit/dagdependency.py "view source code")

Return the circuit depth. :returns: the circuit depth :rtype: int

<span id="qiskit-dagcircuit-dagdependency-direct-predecessors" />

### direct\_predecessors

<span id="qiskit.dagcircuit.DAGDependency.direct_predecessors" />

`DAGDependency.direct_predecessors(node_id)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/dagcircuit/dagdependency.py "view source code")

Direct predecessors id of a given node as sorted list.

**Parameters**

**node\_id** (*int*) – label of considered node.

**Returns**

direct predecessors id as a sorted list

**Return type**

List

<span id="qiskit-dagcircuit-dagdependency-direct-successors" />

### direct\_successors

<span id="qiskit.dagcircuit.DAGDependency.direct_successors" />

`DAGDependency.direct_successors(node_id)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/dagcircuit/dagdependency.py "view source code")

Direct successors id of a given node as sorted list.

**Parameters**

**node\_id** (*int*) – label of considered node.

**Returns**

direct successors id as a sorted list

**Return type**

List

<span id="qiskit-dagcircuit-dagdependency-draw" />

### draw

<span id="qiskit.dagcircuit.DAGDependency.draw" />

`DAGDependency.draw(scale=0.7, filename=None, style='color')`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/dagcircuit/dagdependency.py "view source code")

Draws the DAGDependency graph.

This function needs pydot \<[https://github.com/erocarrera/pydot](https://github.com/erocarrera/pydot)>, which in turn needs Graphviz \<[https://www.graphviz.org/](https://www.graphviz.org/)>\` to be installed.

**Parameters**

*   **scale** (*float*) – scaling factor
*   **filename** (*str*) – file path to save image to (format inferred from name)
*   **style** (*str*) – ‘plain’: B\&W graph ‘color’ (default): color input/output/op nodes

**Returns**

**if in Jupyter notebook and not saving to file,**

otherwise None.

**Return type**

Ipython.display.Image

<span id="qiskit-dagcircuit-dagdependency-get-all-edges" />

### get\_all\_edges

<span id="qiskit.dagcircuit.DAGDependency.get_all_edges" />

`DAGDependency.get_all_edges()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/dagcircuit/dagdependency.py "view source code")

Enumeration of all edges.

**Returns**

corresponding to the label.

**Return type**

List

<span id="qiskit-dagcircuit-dagdependency-get-edges" />

### get\_edges

<span id="qiskit.dagcircuit.DAGDependency.get_edges" />

`DAGDependency.get_edges(src_id, dest_id)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/dagcircuit/dagdependency.py "view source code")

Edge enumeration between two nodes through method get\_all\_edge\_data.

**Parameters**

*   **src\_id** (*int*) – label of the first node.
*   **dest\_id** (*int*) – label of the second node.

**Returns**

corresponding to all edges between the two nodes.

**Return type**

List

<span id="qiskit-dagcircuit-dagdependency-get-in-edges" />

### get\_in\_edges

<span id="qiskit.dagcircuit.DAGDependency.get_in_edges" />

`DAGDependency.get_in_edges(node_id)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/dagcircuit/dagdependency.py "view source code")

Enumeration of all incoming edges for a given node.

**Parameters**

**node\_id** (*int*) – label of considered node.

**Returns**

corresponding incoming edges data.

**Return type**

List

<span id="qiskit-dagcircuit-dagdependency-get-node" />

### get\_node

<span id="qiskit.dagcircuit.DAGDependency.get_node" />

`DAGDependency.get_node(node_id)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/dagcircuit/dagdependency.py "view source code")

**Parameters**

**node\_id** (*int*) – label of considered node.

**Returns**

corresponding to the label.

**Return type**

node

<span id="qiskit-dagcircuit-dagdependency-get-nodes" />

### get\_nodes

<span id="qiskit.dagcircuit.DAGDependency.get_nodes" />

`DAGDependency.get_nodes()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/dagcircuit/dagdependency.py "view source code")

**Returns**

iterator over all the nodes.

**Return type**

generator(dict)

<span id="qiskit-dagcircuit-dagdependency-get-out-edges" />

### get\_out\_edges

<span id="qiskit.dagcircuit.DAGDependency.get_out_edges" />

`DAGDependency.get_out_edges(node_id)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/dagcircuit/dagdependency.py "view source code")

Enumeration of all outgoing edges for a given node.

**Parameters**

**node\_id** (*int*) – label of considered node.

**Returns**

corresponding outgoing edges data.

**Return type**

List

<span id="qiskit-dagcircuit-dagdependency-predecessors" />

### predecessors

<span id="qiskit.dagcircuit.DAGDependency.predecessors" />

`DAGDependency.predecessors(node_id)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/dagcircuit/dagdependency.py "view source code")

Predecessors id of a given node as sorted list.

**Parameters**

**node\_id** (*int*) – label of considered node.

**Returns**

all predecessors id as a sorted list

**Return type**

List

<span id="qiskit-dagcircuit-dagdependency-replace-block-with-op" />

### replace\_block\_with\_op

<span id="qiskit.dagcircuit.DAGDependency.replace_block_with_op" />

`DAGDependency.replace_block_with_op(node_block, op, wire_pos_map, cycle_check=True)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/dagcircuit/dagdependency.py "view source code")

Replace a block of nodes with a single node.

This is used to consolidate a block of DAGDepNodes into a single operation. A typical example is a block of CX and SWAP gates consolidated into a LinearFunction. This function is an adaptation of a similar function from DAGCircuit.

It is important that such consolidation preserves commutativity assumptions present in DAGDependency. As an example, suppose that every node in a block \[A, B, C, D] commutes with another node E. Let F be the consolidated node, F = A o B o C o D. Then F also commutes with E, and thus the result of replacing \[A, B, C, D] by F results in a valid DAGDependency. That is, any deduction about commutativity in consolidated DAGDependency is correct. On the other hand, suppose that at least one of the nodes, say B, does not commute with E. Then the consolidated DAGDependency would imply that F does not commute with E. Even though F and E may actually commute, it is still safe to assume that they do not. That is, the current implementation of consolidation may lead to suboptimal but not to incorrect results.

**Parameters**

*   **node\_block** (*List\[*[*DAGDepNode*](qiskit.dagcircuit.DAGDepNode "qiskit.dagcircuit.DAGDepNode")*]*) – A list of dag nodes that represents the node block to be replaced
*   **op** ([*qiskit.circuit.Operation*](qiskit.circuit.Operation "qiskit.circuit.Operation")) – The operation to replace the block with
*   **wire\_pos\_map** (*Dict\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*, int]*) – The dictionary mapping the qarg to the position. This is necessary to reconstruct the qarg order over multiple gates in the combined single op node.
*   **cycle\_check** (*bool*) – When set to True this method will check that replacing the provided `node_block` with a single node would introduce a cycle (which would invalidate the `DAGDependency`) and will raise a `DAGDependencyError` if a cycle would be introduced. This checking comes with a run time penalty. If you can guarantee that your input `node_block` is a contiguous block and won’t introduce a cycle when it’s contracted to a single node, this can be set to `False` to improve the runtime performance of this method.

**Raises**

**DAGDependencyError** – if `cycle_check` is set to `True` and replacing the specified block introduces a cycle or if `node_block` is empty.

<span id="qiskit-dagcircuit-dagdependency-size" />

### size

<span id="qiskit.dagcircuit.DAGDependency.size" />

`DAGDependency.size()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/dagcircuit/dagdependency.py "view source code")

Returns the number of gates in the circuit

<span id="qiskit-dagcircuit-dagdependency-successors" />

### successors

<span id="qiskit.dagcircuit.DAGDependency.successors" />

`DAGDependency.successors(node_id)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/dagcircuit/dagdependency.py "view source code")

Successors id of a given node as sorted list.

**Parameters**

**node\_id** (*int*) – label of considered node.

**Returns**

all successors id as a sorted list

**Return type**

List

<span id="qiskit-dagcircuit-dagdependency-to-retworkx" />

### to\_retworkx

<span id="qiskit.dagcircuit.DAGDependency.to_retworkx" />

`DAGDependency.to_retworkx()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/dagcircuit/dagdependency.py "view source code")

Returns the DAGDependency in retworkx format.

<span id="qiskit-dagcircuit-dagdependency-topological-nodes" />

### topological\_nodes

<span id="qiskit.dagcircuit.DAGDependency.topological_nodes" />

`DAGDependency.topological_nodes()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/dagcircuit/dagdependency.py "view source code")

Yield nodes in topological order.

**Returns**

node in topological order.

**Return type**

generator([DAGNode](qiskit.dagcircuit.DAGNode "qiskit.dagcircuit.DAGNode"))

## Attributes

<span id="qiskit.dagcircuit.DAGDependency.calibrations" />

### calibrations

Return calibration dictionary.

**The custom pulse definition of a given gate is of the form**

\{‘gate\_name’: \{(qubits, params): schedule}}

<span id="qiskit.dagcircuit.DAGDependency.global_phase" />

### global\_phase

Return the global phase of the circuit.

