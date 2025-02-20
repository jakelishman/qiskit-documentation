---
title: TransformationPass
description: API reference for qiskit.transpiler.TransformationPass
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.TransformationPass
---

# qiskit.transpiler.TransformationPass

<span id="qiskit.transpiler.TransformationPass" />

`TransformationPass(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.17/qiskit/transpiler/basepasses.py "view source code")

A transformation pass: change DAG, not property set.

### \_\_init\_\_

<span id="qiskit.transpiler.TransformationPass.__init__" />

`__init__()`

Initialize self. See help(type(self)) for accurate signature.

## Methods

|                                                                                                                |                               |
| -------------------------------------------------------------------------------------------------------------- | ----------------------------- |
| [`__init__`](#qiskit.transpiler.TransformationPass.__init__ "qiskit.transpiler.TransformationPass.__init__")() | Initialize self.              |
| [`name`](#qiskit.transpiler.TransformationPass.name "qiskit.transpiler.TransformationPass.name")()             | Return the name of the pass.  |
| [`run`](#qiskit.transpiler.TransformationPass.run "qiskit.transpiler.TransformationPass.run")(dag)             | Run a pass on the DAGCircuit. |

## Attributes

|                                                                                                                                                        |                                             |
| ------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------- |
| [`is_analysis_pass`](#qiskit.transpiler.TransformationPass.is_analysis_pass "qiskit.transpiler.TransformationPass.is_analysis_pass")                   | Check if the pass is an analysis pass.      |
| [`is_transformation_pass`](#qiskit.transpiler.TransformationPass.is_transformation_pass "qiskit.transpiler.TransformationPass.is_transformation_pass") | Check if the pass is a transformation pass. |

### is\_analysis\_pass

<span id="qiskit.transpiler.TransformationPass.is_analysis_pass" />

`property is_analysis_pass`

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

### is\_transformation\_pass

<span id="qiskit.transpiler.TransformationPass.is_transformation_pass" />

`property is_transformation_pass`

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

### name

<span id="qiskit.transpiler.TransformationPass.name" />

`name()`

Return the name of the pass.

### run

<span id="qiskit.transpiler.TransformationPass.run" />

`abstract run(dag)`

Run a pass on the DAGCircuit. This is implemented by the pass developer.

**Parameters**

**dag** ([*DAGCircuit*](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")) – the dag on which the pass is run.

**Raises**

**NotImplementedError** – when this is left unimplemented for a pass.

