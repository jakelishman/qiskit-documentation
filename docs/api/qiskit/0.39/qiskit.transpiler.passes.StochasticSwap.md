---
title: StochasticSwap
description: API reference for qiskit.transpiler.passes.StochasticSwap
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.StochasticSwap
---

# StochasticSwap

<span id="qiskit.transpiler.passes.StochasticSwap" />

`StochasticSwap(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/transpiler/passes/routing/stochastic_swap.py "view source code")

Bases: [`qiskit.transpiler.basepasses.TransformationPass`](qiskit.transpiler.TransformationPass "qiskit.transpiler.basepasses.TransformationPass")

Map a DAGCircuit onto a coupling\_map adding swap gates.

Uses a randomized algorithm.

## Notes

1.  Measurements may occur and be followed by swaps that result in repeated measurement of the same qubit. Near-term experiments cannot implement these circuits, so some care is required when using this mapper with experimental backend targets.
2.  We do not use the fact that the input state is zero to simplify the circuit.

StochasticSwap initializer.

The coupling map is a connected graph

If these are not satisfied, the behavior is undefined.

**Parameters**

*   **coupling\_map** ([*CouplingMap*](qiskit.transpiler.CouplingMap "qiskit.transpiler.CouplingMap")) – Directed graph representing a coupling map.
*   **trials** (*int*) – maximum number of iterations to attempt
*   **seed** (*int*) – seed for random number generator
*   **fake\_run** (*bool*) – if true, it only pretend to do routing, i.e., no swap is effectively added.
*   **initial\_layout** ([*Layout*](qiskit.transpiler.Layout "qiskit.transpiler.Layout")) – starting layout at beginning of pass.

## Methods

### name

<span id="qiskit.transpiler.passes.StochasticSwap.name" />

`StochasticSwap.name()`

Return the name of the pass.

### run

<span id="qiskit.transpiler.passes.StochasticSwap.run" />

`StochasticSwap.run(dag)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/transpiler/passes/routing/stochastic_swap.py "view source code")

Run the StochasticSwap pass on dag.

**Parameters**

**dag** ([*DAGCircuit*](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")) – DAG to map.

**Returns**

A mapped DAG.

**Return type**

[DAGCircuit](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")

**Raises**

*   [**TranspilerError**](qiskit.transpiler.TranspilerError "qiskit.transpiler.TranspilerError") – if the coupling map or the layout are not
*   **compatible with the DAG** –

## Attributes

<span id="qiskit.transpiler.passes.StochasticSwap.is_analysis_pass" />

### is\_analysis\_pass

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

<span id="qiskit.transpiler.passes.StochasticSwap.is_transformation_pass" />

### is\_transformation\_pass

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

