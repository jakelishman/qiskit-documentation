---
title: HoareOptimizer
description: API reference for qiskit.transpiler.passes.HoareOptimizer
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.HoareOptimizer
---

# HoareOptimizer

<span id="qiskit.transpiler.passes.HoareOptimizer" />

`qiskit.transpiler.passes.HoareOptimizer(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.25/qiskit/transpiler/passes/optimization/hoare_opt.py "view source code")

Bases: [`TransformationPass`](qiskit.transpiler.TransformationPass "qiskit.transpiler.basepasses.TransformationPass")

This is a transpiler pass using Hoare logic circuit optimization. The inner workings of this are detailed in: [https://arxiv.org/abs/1810.00375](https://arxiv.org/abs/1810.00375)

**Parameters**

**size** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – size of gate cache, in number of gates

**Raises**

[**MissingOptionalLibraryError**](exceptions#qiskit.exceptions.MissingOptionalLibraryError "qiskit.exceptions.MissingOptionalLibraryError") – if unable to import z3 solver

## Attributes

<span id="qiskit.transpiler.passes.HoareOptimizer.is_analysis_pass" />

### is\_analysis\_pass

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

<span id="qiskit.transpiler.passes.HoareOptimizer.is_transformation_pass" />

### is\_transformation\_pass

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

## Methods

### name

<span id="qiskit.transpiler.passes.HoareOptimizer.name" />

`name()`

Return the name of the pass.

### run

<span id="qiskit.transpiler.passes.HoareOptimizer.run" />

`run(dag)`

**Parameters**

**dag** ([*DAGCircuit*](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")) – the directed acyclic graph to run on.

**Returns**

Transformed DAG.

**Return type**

[DAGCircuit](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")

