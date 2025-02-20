---
title: DAGCircuit
description: API reference for qiskit.dagcircuit.DAGCircuit
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.dagcircuit.DAGCircuit
---

# DAGCircuit

<span id="qiskit.dagcircuit.DAGCircuit" />

`DAGCircuit`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Bases: `object`

Quantum circuit as a directed acyclic graph.

There are 3 types of nodes in the graph: inputs, outputs, and operations. The nodes are connected by directed edges that correspond to qubits and bits.

Create an empty circuit.

## Methods

### add\_calibration

<span id="qiskit.dagcircuit.DAGCircuit.add_calibration" />

`DAGCircuit.add_calibration(gate, qubits, schedule, params=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Register a low-level, custom pulse definition for the given gate.

**Parameters**

*   **gate** (*Union\[*[*Gate*](qiskit.circuit.Gate "qiskit.circuit.Gate")*, str]*) – Gate information.
*   **qubits** (*Union\[int, Tuple\[int]]*) – List of qubits to be measured.
*   **schedule** ([*Schedule*](qiskit.pulse.Schedule "qiskit.pulse.Schedule")) – Schedule information.
*   **params** (*Optional\[List\[Union\[float,* [*Parameter*](qiskit.circuit.Parameter "qiskit.circuit.Parameter")*]]]*) – A list of parameters.

**Raises**

**Exception** – if the gate is of type string and params is None.

### add\_clbits

<span id="qiskit.dagcircuit.DAGCircuit.add_clbits" />

`DAGCircuit.add_clbits(clbits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Add individual clbit wires.

### add\_creg

<span id="qiskit.dagcircuit.DAGCircuit.add_creg" />

`DAGCircuit.add_creg(creg)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Add all wires in a classical register.

### add\_qreg

<span id="qiskit.dagcircuit.DAGCircuit.add_qreg" />

`DAGCircuit.add_qreg(qreg)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Add all wires in a quantum register.

### add\_qubits

<span id="qiskit.dagcircuit.DAGCircuit.add_qubits" />

`DAGCircuit.add_qubits(qubits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Add individual qubit wires.

### ancestors

<span id="qiskit.dagcircuit.DAGCircuit.ancestors" />

`DAGCircuit.ancestors(node)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Returns set of the ancestors of a node as DAGNodes.

### apply\_operation\_back

<span id="qiskit.dagcircuit.DAGCircuit.apply_operation_back" />

`DAGCircuit.apply_operation_back(op, qargs=None, cargs=None, condition=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Apply an operation to the output of the circuit.

**Parameters**

*   **op** ([*qiskit.circuit.Instruction*](qiskit.circuit.Instruction "qiskit.circuit.Instruction")) – the operation associated with the DAG node
*   **qargs** (*list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – qubits that op will be applied to
*   **cargs** (*list\[*[*Clbit*](qiskit.circuit.Clbit "qiskit.circuit.Clbit")*]*) – cbits that op will be applied to
*   **condition** (*tuple or None*) – DEPRECATED optional condition (ClassicalRegister, int)

**Returns**

the current max node

**Return type**

[DAGNode](qiskit.dagcircuit.DAGNode "qiskit.dagcircuit.DAGNode")

**Raises**

[**DAGCircuitError**](qiskit.dagcircuit.DAGCircuitError "qiskit.dagcircuit.DAGCircuitError") – if a leaf node is connected to multiple outputs

### apply\_operation\_front

<span id="qiskit.dagcircuit.DAGCircuit.apply_operation_front" />

`DAGCircuit.apply_operation_front(op, qargs, cargs, condition=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Apply an operation to the input of the circuit.

**Parameters**

*   **op** ([*qiskit.circuit.Instruction*](qiskit.circuit.Instruction "qiskit.circuit.Instruction")) – the operation associated with the DAG node
*   **qargs** (*list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – qubits that op will be applied to
*   **cargs** (*list\[*[*Clbit*](qiskit.circuit.Clbit "qiskit.circuit.Clbit")*]*) – cbits that op will be applied to
*   **condition** (*tuple or None*) – DEPRECATED optional condition (ClassicalRegister, int)

**Returns**

the current max node

**Return type**

[DAGNode](qiskit.dagcircuit.DAGNode "qiskit.dagcircuit.DAGNode")

**Raises**

[**DAGCircuitError**](qiskit.dagcircuit.DAGCircuitError "qiskit.dagcircuit.DAGCircuitError") – if initial nodes connected to multiple out edges

### bfs\_successors

<span id="qiskit.dagcircuit.DAGCircuit.bfs_successors" />

`DAGCircuit.bfs_successors(node)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Returns an iterator of tuples of (DAGNode, \[DAGNodes]) where the DAGNode is the current node and \[DAGNode] is its successors in BFS order.

### collect\_1q\_runs

<span id="qiskit.dagcircuit.DAGCircuit.collect_1q_runs" />

`DAGCircuit.collect_1q_runs()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Return a set of non-conditional runs of 1q “op” nodes.

### collect\_runs

<span id="qiskit.dagcircuit.DAGCircuit.collect_runs" />

`DAGCircuit.collect_runs(namelist)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Return a set of non-conditional runs of “op” nodes with the given names.

For example, “… h q\[0]; cx q\[0],q\[1]; cx q\[0],q\[1]; h q\[1]; ..” would produce the tuple of cx nodes as an element of the set returned from a call to collect\_runs(\[“cx”]). If instead the cx nodes were “cx q\[0],q\[1]; cx q\[1],q\[0];”, the method would still return the pair in a tuple. The namelist can contain names that are not in the circuit’s basis.

Nodes must have only one successor to continue the run.

### compose

<span id="qiskit.dagcircuit.DAGCircuit.compose" />

`DAGCircuit.compose(other, edge_map=None, qubits=None, clbits=None, front=False, inplace=True)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Compose the `other` circuit onto the output of this circuit.

A subset of input wires of `other` are mapped to a subset of output wires of this circuit.

`other` can be narrower or of equal width to `self`.

**Parameters**

*   **other** ([*DAGCircuit*](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")) – circuit to compose with self
*   **edge\_map** (*dict*) – DEPRECATED - a \{Bit: Bit} map from input wires of other to output wires of self (i.e. rhs->lhs). The key, value pairs can be either Qubit or Clbit mappings.
*   **qubits** (*list\[Qubit|int]*) – qubits of self to compose onto.
*   **clbits** (*list\[Clbit|int]*) – clbits of self to compose onto.
*   **front** (*bool*) – If True, front composition will be performed (not implemented yet)
*   **inplace** (*bool*) – If True, modify the object. Otherwise return composed circuit.

**Returns**

the composed dag (returns None if inplace==True).

**Return type**

[DAGCircuit](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")

**Raises**

[**DAGCircuitError**](qiskit.dagcircuit.DAGCircuitError "qiskit.dagcircuit.DAGCircuitError") – if `other` is wider or there are duplicate edge mappings.

### compose\_back

<span id="qiskit.dagcircuit.DAGCircuit.compose_back" />

`DAGCircuit.compose_back(input_circuit, edge_map=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

DEPRECATED: use DAGCircuit.compose() instead.

### count\_ops

<span id="qiskit.dagcircuit.DAGCircuit.count_ops" />

`DAGCircuit.count_ops()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Count the occurrences of operation names.

Returns a dictionary of counts keyed on the operation name.

### count\_ops\_longest\_path

<span id="qiskit.dagcircuit.DAGCircuit.count_ops_longest_path" />

`DAGCircuit.count_ops_longest_path()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Count the occurrences of operation names on the longest path.

Returns a dictionary of counts keyed on the operation name.

### depth

<span id="qiskit.dagcircuit.DAGCircuit.depth" />

`DAGCircuit.depth()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Return the circuit depth. :returns: the circuit depth :rtype: int

**Raises**

[**DAGCircuitError**](qiskit.dagcircuit.DAGCircuitError "qiskit.dagcircuit.DAGCircuitError") – if not a directed acyclic graph

### descendants

<span id="qiskit.dagcircuit.DAGCircuit.descendants" />

`DAGCircuit.descendants(node)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Returns set of the descendants of a node as DAGNodes.

### draw

<span id="qiskit.dagcircuit.DAGCircuit.draw" />

`DAGCircuit.draw(scale=0.7, filename=None, style='color')`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Draws the dag circuit.

This function needs [pydot](https://github.com/erocarrera/pydot), which in turn needs [Graphviz](https://www.graphviz.org/) to be installed.

**Parameters**

*   **scale** (*float*) – scaling factor
*   **filename** (*str*) – file path to save image to (format inferred from name)
*   **style** (*str*) – ‘plain’: B\&W graph; ‘color’ (default): color input/output/op nodes

**Returns**

if in Jupyter notebook and not saving to file, otherwise None.

**Return type**

Ipython.display.Image

### edges

<span id="qiskit.dagcircuit.DAGCircuit.edges" />

`DAGCircuit.edges(nodes=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Iterator for edge values and source and dest node

This works by returning the output edges from the specified nodes. If no nodes are specified all edges from the graph are returned.

#### Parameters

**nodes** (*DAGNode|list(*[*DAGNode*](qiskit.dagcircuit.DAGNode "qiskit.dagcircuit.DAGNode")) – Either a list of nodes or a single input node. If none is specified all edges are returned from the graph.

#### Yields

*edge* –

#### the edge in the same format as out\_edges the tuple

(source node, destination node, edge data)

### extend\_back

<span id="qiskit.dagcircuit.DAGCircuit.extend_back" />

`DAGCircuit.extend_back(dag, edge_map=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

DEPRECATED: Add dag at the end of self, using edge\_map.

### from\_networkx

<span id="qiskit.dagcircuit.DAGCircuit.from_networkx" />

`classmethod DAGCircuit.from_networkx(graph)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Take a networkx MultiDigraph and create a new DAGCircuit.

**Parameters**

**graph** (*networkx.MultiDiGraph*) – The graph to create a DAGCircuit object from. The format of this MultiDiGraph format must be in the same format as returned by to\_networkx.

**Returns**

**The dagcircuit object created from the networkx**

MultiDiGraph.

**Return type**

[DAGCircuit](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")

**Raises**

*   [**MissingOptionalLibraryError**](qiskit.aqua.MissingOptionalLibraryError "qiskit.aqua.MissingOptionalLibraryError") – If networkx is not installed
*   [**DAGCircuitError**](qiskit.dagcircuit.DAGCircuitError "qiskit.dagcircuit.DAGCircuitError") – If input networkx graph is malformed

### front\_layer

<span id="qiskit.dagcircuit.DAGCircuit.front_layer" />

`DAGCircuit.front_layer()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Return a list of op nodes in the first layer of this dag.

### gate\_nodes

<span id="qiskit.dagcircuit.DAGCircuit.gate_nodes" />

`DAGCircuit.gate_nodes()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Get the list of gate nodes in the dag.

**Returns**

the list of DAGNodes that represent gates.

**Return type**

list\[[DAGNode](qiskit.dagcircuit.DAGNode "qiskit.dagcircuit.DAGNode")]

### has\_calibration\_for

<span id="qiskit.dagcircuit.DAGCircuit.has_calibration_for" />

`DAGCircuit.has_calibration_for(node)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Return True if the dag has a calibration defined for the node operation. In this case, the operation does not need to be translated to the device basis.

### idle\_wires

<span id="qiskit.dagcircuit.DAGCircuit.idle_wires" />

`DAGCircuit.idle_wires(ignore=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Return idle wires.

**Parameters**

**ignore** (*list(str)*) – List of node names to ignore. Default: \[]

**Yields**

*Bit* – Bit in idle wire.

### is\_predecessor

<span id="qiskit.dagcircuit.DAGCircuit.is_predecessor" />

`DAGCircuit.is_predecessor(node, node_pred)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Checks if a second node is in the predecessors of node.

### is\_successor

<span id="qiskit.dagcircuit.DAGCircuit.is_successor" />

`DAGCircuit.is_successor(node, node_succ)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Checks if a second node is in the successors of node.

### layers

<span id="qiskit.dagcircuit.DAGCircuit.layers" />

`DAGCircuit.layers()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Yield a shallow view on a layer of this DAGCircuit for all d layers of this circuit.

A layer is a circuit whose gates act on disjoint qubits, i.e., a layer has depth 1. The total number of layers equals the circuit depth d. The layers are indexed from 0 to d-1 with the earliest layer at index 0. The layers are constructed using a greedy algorithm. Each returned layer is a dict containing \{“graph”: circuit graph, “partition”: list of qubit lists}.

The returned layer contains new (but semantically equivalent) DAGNodes. These are not the same as nodes of the original dag, but are equivalent via DAGNode.semantic\_eq(node1, node2).

TODO: Gates that use the same cbits will end up in different layers as this is currently implemented. This may not be the desired behavior.

### longest\_path

<span id="qiskit.dagcircuit.DAGCircuit.longest_path" />

`DAGCircuit.longest_path()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Returns the longest path in the dag as a list of DAGNodes.

### multi\_qubit\_ops

<span id="qiskit.dagcircuit.DAGCircuit.multi_qubit_ops" />

`DAGCircuit.multi_qubit_ops()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Get list of 3+ qubit operations. Ignore directives like snapshot and barrier.

### multigraph\_layers

<span id="qiskit.dagcircuit.DAGCircuit.multigraph_layers" />

`DAGCircuit.multigraph_layers()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Yield layers of the multigraph.

### named\_nodes

<span id="qiskit.dagcircuit.DAGCircuit.named_nodes" />

`DAGCircuit.named_nodes(*names)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Get the set of “op” nodes with the given name.

### node

<span id="qiskit.dagcircuit.DAGCircuit.node" />

`DAGCircuit.node(node_id)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Get the node in the dag.

**Parameters**

**node\_id** (*int*) – Node identifier.

**Returns**

the node.

**Return type**

node

### nodes

<span id="qiskit.dagcircuit.DAGCircuit.nodes" />

`DAGCircuit.nodes()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Iterator for node values.

**Yields**

*node* – the node.

### nodes\_on\_wire

<span id="qiskit.dagcircuit.DAGCircuit.nodes_on_wire" />

`DAGCircuit.nodes_on_wire(wire, only_ops=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Iterator for nodes that affect a given wire.

**Parameters**

*   **wire** (*Bit*) – the wire to be looked at.
*   **only\_ops** (*bool*) – True if only the ops nodes are wanted; otherwise, all nodes are returned.

**Yields**

*DAGNode* – the successive ops on the given wire

**Raises**

[**DAGCircuitError**](qiskit.dagcircuit.DAGCircuitError "qiskit.dagcircuit.DAGCircuitError") – if the given wire doesn’t exist in the DAG

### num\_clbits

<span id="qiskit.dagcircuit.DAGCircuit.num_clbits" />

`DAGCircuit.num_clbits()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Return the total number of classical bits used by the circuit.

### num\_qubits

<span id="qiskit.dagcircuit.DAGCircuit.num_qubits" />

`DAGCircuit.num_qubits()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Return the total number of qubits used by the circuit. num\_qubits() replaces former use of width(). DAGCircuit.width() now returns qubits + clbits for consistency with Circuit.width() \[qiskit-terra #2564].

### num\_tensor\_factors

<span id="qiskit.dagcircuit.DAGCircuit.num_tensor_factors" />

`DAGCircuit.num_tensor_factors()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Compute how many components the circuit can decompose into.

### op\_nodes

<span id="qiskit.dagcircuit.DAGCircuit.op_nodes" />

`DAGCircuit.op_nodes(op=None, include_directives=True)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Get the list of “op” nodes in the dag.

**Parameters**

*   **op** (*Type*) – [`qiskit.circuit.Instruction`](qiskit.circuit.Instruction "qiskit.circuit.Instruction") subclass op nodes to return. If None, return all op nodes.
*   **include\_directives** (*bool*) – include barrier, snapshot etc.

**Returns**

the list of node ids containing the given op.

**Return type**

list\[[DAGNode](qiskit.dagcircuit.DAGNode "qiskit.dagcircuit.DAGNode")]

### predecessors

<span id="qiskit.dagcircuit.DAGCircuit.predecessors" />

`DAGCircuit.predecessors(node)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Returns iterator of the predecessors of a node as DAGNodes.

### properties

<span id="qiskit.dagcircuit.DAGCircuit.properties" />

`DAGCircuit.properties()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Return a dictionary of circuit properties.

### quantum\_predecessors

<span id="qiskit.dagcircuit.DAGCircuit.quantum_predecessors" />

`DAGCircuit.quantum_predecessors(node)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Returns iterator of the predecessors of a node that are connected by a quantum edge as DAGNodes.

### quantum\_successors

<span id="qiskit.dagcircuit.DAGCircuit.quantum_successors" />

`DAGCircuit.quantum_successors(node)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Returns iterator of the successors of a node that are connected by a quantum edge as DAGNodes.

### remove\_all\_ops\_named

<span id="qiskit.dagcircuit.DAGCircuit.remove_all_ops_named" />

`DAGCircuit.remove_all_ops_named(opname)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Remove all operation nodes with the given name.

### remove\_ancestors\_of

<span id="qiskit.dagcircuit.DAGCircuit.remove_ancestors_of" />

`DAGCircuit.remove_ancestors_of(node)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Remove all of the ancestor operation nodes of node.

### remove\_descendants\_of

<span id="qiskit.dagcircuit.DAGCircuit.remove_descendants_of" />

`DAGCircuit.remove_descendants_of(node)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Remove all of the descendant operation nodes of node.

### remove\_nonancestors\_of

<span id="qiskit.dagcircuit.DAGCircuit.remove_nonancestors_of" />

`DAGCircuit.remove_nonancestors_of(node)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Remove all of the non-ancestors operation nodes of node.

### remove\_nondescendants\_of

<span id="qiskit.dagcircuit.DAGCircuit.remove_nondescendants_of" />

`DAGCircuit.remove_nondescendants_of(node)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Remove all of the non-descendants operation nodes of node.

### remove\_op\_node

<span id="qiskit.dagcircuit.DAGCircuit.remove_op_node" />

`DAGCircuit.remove_op_node(node)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Remove an operation node n.

Add edges from predecessors to successors.

### reverse\_ops

<span id="qiskit.dagcircuit.DAGCircuit.reverse_ops" />

`DAGCircuit.reverse_ops()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Reverse the operations in the `self` circuit.

**Returns**

the reversed dag.

**Return type**

[DAGCircuit](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")

### serial\_layers

<span id="qiskit.dagcircuit.DAGCircuit.serial_layers" />

`DAGCircuit.serial_layers()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Yield a layer for all gates of this circuit.

A serial layer is a circuit with one gate. The layers have the same structure as in layers().

### size

<span id="qiskit.dagcircuit.DAGCircuit.size" />

`DAGCircuit.size()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Return the number of operations.

### substitute\_node

<span id="qiskit.dagcircuit.DAGCircuit.substitute_node" />

`DAGCircuit.substitute_node(node, op, inplace=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Replace a DAGNode with a single instruction. qargs, cargs and conditions for the new instruction will be inferred from the node to be replaced. The new instruction will be checked to match the shape of the replaced instruction.

**Parameters**

*   **node** ([*DAGNode*](qiskit.dagcircuit.DAGNode "qiskit.dagcircuit.DAGNode")) – Node to be replaced
*   **op** ([*qiskit.circuit.Instruction*](qiskit.circuit.Instruction "qiskit.circuit.Instruction")) – The [`qiskit.circuit.Instruction`](qiskit.circuit.Instruction "qiskit.circuit.Instruction") instance to be added to the DAG
*   **inplace** (*bool*) – Optional, default False. If True, existing DAG node will be modified to include op. Otherwise, a new DAG node will be used.

**Returns**

the new node containing the added instruction.

**Return type**

[DAGNode](qiskit.dagcircuit.DAGNode "qiskit.dagcircuit.DAGNode")

**Raises**

*   [**DAGCircuitError**](qiskit.dagcircuit.DAGCircuitError "qiskit.dagcircuit.DAGCircuitError") – If replacement instruction was incompatible with
*   **location of target node.** –

### substitute\_node\_with\_dag

<span id="qiskit.dagcircuit.DAGCircuit.substitute_node_with_dag" />

`DAGCircuit.substitute_node_with_dag(node, input_dag, wires=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Replace one node with dag.

**Parameters**

*   **node** ([*DAGNode*](qiskit.dagcircuit.DAGNode "qiskit.dagcircuit.DAGNode")) – node to substitute
*   **input\_dag** ([*DAGCircuit*](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")) – circuit that will substitute the node
*   **wires** (*list\[Bit]*) – gives an order for (qu)bits in the input circuit. This order gets matched to the node wires by qargs first, then cargs, then conditions.

**Raises**

[**DAGCircuitError**](qiskit.dagcircuit.DAGCircuitError "qiskit.dagcircuit.DAGCircuitError") – if met with unexpected predecessor/successors

### successors

<span id="qiskit.dagcircuit.DAGCircuit.successors" />

`DAGCircuit.successors(node)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Returns iterator of the successors of a node as DAGNodes.

### threeQ\_or\_more\_gates

<span id="qiskit.dagcircuit.DAGCircuit.threeQ_or_more_gates" />

`DAGCircuit.threeQ_or_more_gates()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Get list of 3-or-more-qubit gates: (id, data).

### to\_networkx

<span id="qiskit.dagcircuit.DAGCircuit.to_networkx" />

`DAGCircuit.to_networkx()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Returns a copy of the DAGCircuit in networkx format.

### topological\_nodes

<span id="qiskit.dagcircuit.DAGCircuit.topological_nodes" />

`DAGCircuit.topological_nodes()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Yield nodes in topological order.

**Returns**

node in topological order

**Return type**

generator([DAGNode](qiskit.dagcircuit.DAGNode "qiskit.dagcircuit.DAGNode"))

### topological\_op\_nodes

<span id="qiskit.dagcircuit.DAGCircuit.topological_op_nodes" />

`DAGCircuit.topological_op_nodes()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Yield op nodes in topological order.

**Returns**

op node in topological order

**Return type**

generator([DAGNode](qiskit.dagcircuit.DAGNode "qiskit.dagcircuit.DAGNode"))

### twoQ\_gates

<span id="qiskit.dagcircuit.DAGCircuit.twoQ_gates" />

`DAGCircuit.twoQ_gates()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Get list of 2-qubit gates. Ignore snapshot, barriers, and the like.

### two\_qubit\_ops

<span id="qiskit.dagcircuit.DAGCircuit.two_qubit_ops" />

`DAGCircuit.two_qubit_ops()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Get list of 2 qubit operations. Ignore directives like snapshot and barrier.

### width

<span id="qiskit.dagcircuit.DAGCircuit.width" />

`DAGCircuit.width()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/dagcircuit/dagcircuit.py "view source code")

Return the total number of qubits + clbits used by the circuit. This function formerly returned the number of qubits by the calculation return len(self.\_wires) - self.num\_clbits() but was changed by issue #2564 to return number of qubits + clbits with the new function DAGCircuit.num\_qubits replacing the former semantic of DAGCircuit.width().

## Attributes

<span id="qiskit.dagcircuit.DAGCircuit.calibrations" />

### calibrations

Return calibration dictionary.

**The custom pulse definition of a given gate is of the form**

\{‘gate\_name’: \{(qubits, params): schedule}}

<span id="qiskit.dagcircuit.DAGCircuit.global_phase" />

### global\_phase

Return the global phase of the circuit.

<span id="qiskit.dagcircuit.DAGCircuit.node_counter" />

### node\_counter

Returns the number of nodes in the dag.

<span id="qiskit.dagcircuit.DAGCircuit.wires" />

### wires

Return a list of the wires in order.

