---
title: GatesInBasis
description: API reference for qiskit.transpiler.passes.GatesInBasis
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.GatesInBasis
---

# GatesInBasis

<span id="qiskit.transpiler.passes.GatesInBasis" />

`GatesInBasis(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/transpiler/passes/utils/gates_basis.py "view source code")

Bases: `qiskit.transpiler.basepasses.AnalysisPass`

Check if all gates in a DAG are in a given set of gates

Initialize the GatesInBasis pass.

**Parameters**

*   **basis\_gates** (*list*) – The list of strings representing the set of basis gates.
*   **target** ([*Target*](qiskit.transpiler.Target "qiskit.transpiler.Target")) – The target representing the backend. If specified this will be used instead of the `basis_gates` parameter

**Raises**

[**TranspilerError**](qiskit.transpiler.TranspilerError "qiskit.transpiler.TranspilerError") – If neither basis\_gates or target is set.

## Methods

### name

<span id="qiskit.transpiler.passes.GatesInBasis.name" />

`GatesInBasis.name()`

Return the name of the pass.

### run

<span id="qiskit.transpiler.passes.GatesInBasis.run" />

`GatesInBasis.run(dag)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/transpiler/passes/utils/gates_basis.py "view source code")

Run the GatesInBasis pass on dag.

## Attributes

<span id="qiskit.transpiler.passes.GatesInBasis.is_analysis_pass" />

### is\_analysis\_pass

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

<span id="qiskit.transpiler.passes.GatesInBasis.is_transformation_pass" />

### is\_transformation\_pass

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

