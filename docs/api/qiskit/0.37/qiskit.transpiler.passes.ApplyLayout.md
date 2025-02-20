---
title: ApplyLayout
description: API reference for qiskit.transpiler.passes.ApplyLayout
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.ApplyLayout
---

# ApplyLayout

<span id="qiskit.transpiler.passes.ApplyLayout" />

`ApplyLayout(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/transpiler/passes/layout/apply_layout.py "view source code")

Bases: [`qiskit.transpiler.basepasses.TransformationPass`](qiskit.transpiler.TransformationPass "qiskit.transpiler.basepasses.TransformationPass")

Transform a circuit with virtual qubits into a circuit with physical qubits.

Transforms a DAGCircuit with virtual qubits into a DAGCircuit with physical qubits by applying the Layout given in property\_set. Requires either of passes to set/select Layout, e.g. SetLayout, TrivialLayout. Assumes the Layout has full physical qubits.

If a post layout pass is run and sets the `post_layout` property set field with a new layout to use after `ApplyLayout` has already run once this pass will compact the layouts so that we apply `original_virtual` -> `existing_layout` -> `new_layout` -> `new_physical` so that the output circuit and layout combination become: `original_virtual` -> `new_physical`

## Methods

### name

<span id="qiskit.transpiler.passes.ApplyLayout.name" />

`ApplyLayout.name()`

Return the name of the pass.

### run

<span id="qiskit.transpiler.passes.ApplyLayout.run" />

`ApplyLayout.run(dag)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/transpiler/passes/layout/apply_layout.py "view source code")

Run the ApplyLayout pass on dag.

**Parameters**

**dag** ([*DAGCircuit*](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")) – DAG to map.

**Returns**

A mapped DAG (with physical qubits).

**Return type**

[DAGCircuit](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")

**Raises**

[**TranspilerError**](qiskit.transpiler.TranspilerError "qiskit.transpiler.TranspilerError") – if no layout is found in property\_set or no full physical qubits.

## Attributes

<span id="qiskit.transpiler.passes.ApplyLayout.is_analysis_pass" />

### is\_analysis\_pass

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

<span id="qiskit.transpiler.passes.ApplyLayout.is_transformation_pass" />

### is\_transformation\_pass

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

