---
title: BasicSwap
description: API reference for qiskit.transpiler.passes.BasicSwap
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.BasicSwap
---

<span id="qiskit-transpiler-passes-basicswap" />

# qiskit.transpiler.passes.BasicSwap

<span id="qiskit.transpiler.passes.BasicSwap" />

`BasicSwap(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.16/qiskit/transpiler/passes/routing/basic_swap.py "view source code")

Map (with minimum effort) a DAGCircuit onto a coupling\_map adding swap gates.

The basic mapper is a minimum effort to insert swap gates to map the DAG onto a coupling map. When a cx is not in the coupling map possibilities, it inserts one or more swaps in front to make it compatible.

BasicSwap initializer.

**Parameters**

**coupling\_map** ([*CouplingMap*](qiskit.transpiler.CouplingMap "qiskit.transpiler.CouplingMap")) – Directed graph represented a coupling map.

### \_\_init\_\_

<span id="qiskit.transpiler.passes.BasicSwap.__init__" />

`__init__(coupling_map)`

BasicSwap initializer.

**Parameters**

**coupling\_map** ([*CouplingMap*](qiskit.transpiler.CouplingMap "qiskit.transpiler.CouplingMap")) – Directed graph represented a coupling map.

## Methods

|                                                                                                                         |                                |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------ |
| [`__init__`](#qiskit.transpiler.passes.BasicSwap.__init__ "qiskit.transpiler.passes.BasicSwap.__init__")(coupling\_map) | BasicSwap initializer.         |
| [`name`](#qiskit.transpiler.passes.BasicSwap.name "qiskit.transpiler.passes.BasicSwap.name")()                          | Return the name of the pass.   |
| [`run`](#qiskit.transpiler.passes.BasicSwap.run "qiskit.transpiler.passes.BasicSwap.run")(dag)                          | Run the BasicSwap pass on dag. |

## Attributes

|                                                                                                                                                    |                                             |
| -------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [`is_analysis_pass`](#qiskit.transpiler.passes.BasicSwap.is_analysis_pass "qiskit.transpiler.passes.BasicSwap.is_analysis_pass")                   | Check if the pass is an analysis pass.      |
| [`is_transformation_pass`](#qiskit.transpiler.passes.BasicSwap.is_transformation_pass "qiskit.transpiler.passes.BasicSwap.is_transformation_pass") | Check if the pass is a transformation pass. |

### is\_analysis\_pass

<span id="qiskit.transpiler.passes.BasicSwap.is_analysis_pass" />

`property is_analysis_pass`

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

### is\_transformation\_pass

<span id="qiskit.transpiler.passes.BasicSwap.is_transformation_pass" />

`property is_transformation_pass`

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

### name

<span id="qiskit.transpiler.passes.BasicSwap.name" />

`name()`

Return the name of the pass.

### run

<span id="qiskit.transpiler.passes.BasicSwap.run" />

`run(dag)`

Run the BasicSwap pass on dag.

**Parameters**

**dag** ([*DAGCircuit*](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")) – DAG to map.

**Returns**

A mapped DAG.

**Return type**

[DAGCircuit](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")

**Raises**

*   [**TranspilerError**](qiskit.transpiler.TranspilerError "qiskit.transpiler.TranspilerError") – if the coupling map or the layout are not
*   **compatible with the DAG.** –

