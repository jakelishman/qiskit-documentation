---
title: CheckMap
description: API reference for qiskit.transpiler.passes.CheckMap
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.CheckMap
---

# CheckMap

<span id="qiskit.transpiler.passes.CheckMap" />

`CheckMap(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/transpiler/passes/utils/check_map.py "view source code")

Check if a DAG circuit is already mapped to a coupling map.

Check if a DAGCircuit is mapped to coupling\_map by checking that all 2-qubit interactions are laid out to be physically close, setting the property `is_swap_mapped` to `True` or `False` accordingly.

CheckMap initializer.

**Parameters**

**coupling\_map** ([*CouplingMap*](qiskit.transpiler.CouplingMap "qiskit.transpiler.CouplingMap")) – Directed graph representing a coupling map.

## Attributes

### is\_analysis\_pass

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

### is\_transformation\_pass

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

## Methods

### name

<span id="qiskit.transpiler.passes.CheckMap.name" />

`CheckMap.name()`

Return the name of the pass.

### run

<span id="qiskit.transpiler.passes.CheckMap.run" />

`CheckMap.run(dag)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/transpiler/passes/utils/check_map.py "view source code")

Run the CheckMap pass on dag.

If dag is mapped to coupling\_map, the property is\_swap\_mapped is set to True (or to False otherwise).

**Parameters**

**dag** ([*DAGCircuit*](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")) – DAG to map.

