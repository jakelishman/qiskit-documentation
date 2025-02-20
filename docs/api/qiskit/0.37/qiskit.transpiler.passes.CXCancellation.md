---
title: CXCancellation
description: API reference for qiskit.transpiler.passes.CXCancellation
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.CXCancellation
---

# CXCancellation

<span id="qiskit.transpiler.passes.CXCancellation" />

`CXCancellation(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/transpiler/passes/optimization/cx_cancellation.py "view source code")

Bases: [`qiskit.transpiler.basepasses.TransformationPass`](qiskit.transpiler.TransformationPass "qiskit.transpiler.basepasses.TransformationPass")

Cancel back-to-back cx gates in dag.

## Methods

### name

<span id="qiskit.transpiler.passes.CXCancellation.name" />

`CXCancellation.name()`

Return the name of the pass.

### run

<span id="qiskit.transpiler.passes.CXCancellation.run" />

`CXCancellation.run(dag)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/transpiler/passes/optimization/cx_cancellation.py "view source code")

Run the CXCancellation pass on dag.

**Parameters**

**dag** ([*DAGCircuit*](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")) – the directed acyclic graph to run on.

**Returns**

Transformed DAG.

**Return type**

[DAGCircuit](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")

## Attributes

<span id="qiskit.transpiler.passes.CXCancellation.is_analysis_pass" />

### is\_analysis\_pass

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

<span id="qiskit.transpiler.passes.CXCancellation.is_transformation_pass" />

### is\_transformation\_pass

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

