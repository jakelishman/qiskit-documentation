---
title: UnrollForLoops
description: API reference for qiskit.transpiler.passes.UnrollForLoops
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.UnrollForLoops
---

# UnrollForLoops

<span id="qiskit.transpiler.passes.UnrollForLoops" />

`qiskit.transpiler.passes.UnrollForLoops(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.25/qiskit/transpiler/passes/utils/unroll_forloops.py "view source code")

Bases: [`TransformationPass`](qiskit.transpiler.TransformationPass "qiskit.transpiler.basepasses.TransformationPass")

`UnrollForLoops` transpilation pass unrolls for-loops when possible.

Things like for x in \{0, 3, 4} \{rx(x) qr\[1];} will turn into rx(0) qr\[1]; rx(3) qr\[1]; rx(4) qr\[1];.

<Admonition title="Note" type="note">
  The `UnrollForLoops` unrolls only one level of block depth. No inner loop will be considered by `max_target_depth`.
</Admonition>

**Parameters**

**max\_target\_depth** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – Optional. Checks if the unrolled block is over a particular subcircuit depth. To disable the check, use `-1` (Default).

## Attributes

<span id="qiskit.transpiler.passes.UnrollForLoops.is_analysis_pass" />

### is\_analysis\_pass

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

<span id="qiskit.transpiler.passes.UnrollForLoops.is_transformation_pass" />

### is\_transformation\_pass

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

## Methods

### name

<span id="qiskit.transpiler.passes.UnrollForLoops.name" />

`name()`

Return the name of the pass.

### run

<span id="qiskit.transpiler.passes.UnrollForLoops.run" />

`run(dag)`

Run the UnrollForLoops pass on dag.

**Parameters**

**dag** ([*DAGCircuit*](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")) – the directed acyclic graph to run on.

**Returns**

Transformed DAG.

**Return type**

[DAGCircuit](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")

