---
title: TrivialLayout
description: API reference for qiskit.transpiler.passes.TrivialLayout
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.TrivialLayout
---

# TrivialLayout

<span id="qiskit.transpiler.passes.TrivialLayout" />

`TrivialLayout(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/transpiler/passes/layout/trivial_layout.py "view source code")

Bases: [`qiskit.transpiler.basepasses.AnalysisPass`](qiskit.transpiler.AnalysisPass "qiskit.transpiler.basepasses.AnalysisPass")

Choose a Layout by assigning `n` circuit qubits to device qubits `0, .., n-1`.

A pass for choosing a Layout of a circuit onto a Coupling graph, using a simple round-robin order.

This pass associates a physical qubit (int) to each virtual qubit of the circuit (Qubit) in increasing order.

Does not assume any ancilla.

TrivialLayout initializer.

**Parameters**

**coupling\_map** (*Coupling*) – directed graph representing a coupling map.

**Raises**

[**TranspilerError**](qiskit.transpiler.TranspilerError "qiskit.transpiler.TranspilerError") – if invalid options

## Methods

### name

<span id="qiskit.transpiler.passes.TrivialLayout.name" />

`TrivialLayout.name()`

Return the name of the pass.

### run

<span id="qiskit.transpiler.passes.TrivialLayout.run" />

`TrivialLayout.run(dag)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/transpiler/passes/layout/trivial_layout.py "view source code")

Run the TrivialLayout pass on dag.

**Parameters**

**dag** ([*DAGCircuit*](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")) – DAG to find layout for.

**Raises**

[**TranspilerError**](qiskit.transpiler.TranspilerError "qiskit.transpiler.TranspilerError") – if dag wider than self.coupling\_map

## Attributes

<span id="qiskit.transpiler.passes.TrivialLayout.is_analysis_pass" />

### is\_analysis\_pass

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

<span id="qiskit.transpiler.passes.TrivialLayout.is_transformation_pass" />

### is\_transformation\_pass

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

