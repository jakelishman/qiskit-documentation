---
title: CollectLinearFunctions
description: API reference for qiskit.transpiler.passes.CollectLinearFunctions
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.CollectLinearFunctions
---

# CollectLinearFunctions

<span id="qiskit.transpiler.passes.CollectLinearFunctions" />

`qiskit.transpiler.passes.CollectLinearFunctions(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.25/qiskit/transpiler/passes/optimization/collect_linear_functions.py "view source code")

Bases: `CollectAndCollapse`

Collect blocks of linear gates ([`CXGate`](qiskit.circuit.library.CXGate "qiskit.circuit.library.CXGate") and [`SwapGate`](qiskit.circuit.library.SwapGate "qiskit.circuit.library.SwapGate") gates) and replaces them by linear functions ([`LinearFunction`](qiskit.circuit.library.LinearFunction "qiskit.circuit.library.LinearFunction")).

CollectLinearFunctions initializer.

**Parameters**

*   **do\_commutative\_analysis** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – if True, exploits commutativity relations between nodes.
*   **split\_blocks** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – if True, splits collected blocks into sub-blocks over disjoint qubit subsets.
*   **min\_block\_size** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – specifies the minimum number of gates in the block for the block to be collected.
*   **split\_layers** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – if True, splits collected blocks into sub-blocks over disjoint qubit subsets.
*   **collect\_from\_back** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – specifies if blocks should be collected started from the end of the circuit.

## Attributes

<span id="qiskit.transpiler.passes.CollectLinearFunctions.is_analysis_pass" />

### is\_analysis\_pass

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

<span id="qiskit.transpiler.passes.CollectLinearFunctions.is_transformation_pass" />

### is\_transformation\_pass

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

## Methods

### name

<span id="qiskit.transpiler.passes.CollectLinearFunctions.name" />

`name()`

Return the name of the pass.

### run

<span id="qiskit.transpiler.passes.CollectLinearFunctions.run" />

`run(dag)`

Run the CollectLinearFunctions pass on dag. :param dag: the DAG to be optimized. :type dag: DAGCircuit

**Returns**

the optimized DAG.

**Return type**

[DAGCircuit](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")

