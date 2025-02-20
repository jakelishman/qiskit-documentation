---
title: DenseLayout
description: API reference for qiskit.transpiler.passes.DenseLayout
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.DenseLayout
---

# qiskit.transpiler.passes.DenseLayout

<span id="qiskit.transpiler.passes.DenseLayout" />

`DenseLayout(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/transpiler/passes/layout/dense_layout.py "view source code")

Choose a Layout by finding the most connected subset of qubits.

This pass associates a physical qubit (int) to each virtual qubit of the circuit (Qubit).

<Admonition title="Note" type="note">
  Even though a ‘layout’ is not strictly a property of the DAG, in the transpiler architecture it is best passed around between passes by being set in property\_set.
</Admonition>

DenseLayout initializer.

**Parameters**

*   **coupling\_map** (*Coupling*) – directed graph representing a coupling map.
*   **backend\_prop** ([*BackendProperties*](qiskit.providers.models.BackendProperties "qiskit.providers.models.BackendProperties")) – backend properties object

### \_\_init\_\_

<span id="qiskit.transpiler.passes.DenseLayout.__init__" />

`__init__(coupling_map, backend_prop=None)`

DenseLayout initializer.

**Parameters**

*   **coupling\_map** (*Coupling*) – directed graph representing a coupling map.
*   **backend\_prop** ([*BackendProperties*](qiskit.providers.models.BackendProperties "qiskit.providers.models.BackendProperties")) – backend properties object

## Methods

|                                                                                                                                               |                                  |
| --------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------- |
| [`__init__`](#qiskit.transpiler.passes.DenseLayout.__init__ "qiskit.transpiler.passes.DenseLayout.__init__")(coupling\_map\[, backend\_prop]) | DenseLayout initializer.         |
| [`name`](#qiskit.transpiler.passes.DenseLayout.name "qiskit.transpiler.passes.DenseLayout.name")()                                            | Return the name of the pass.     |
| [`run`](#qiskit.transpiler.passes.DenseLayout.run "qiskit.transpiler.passes.DenseLayout.run")(dag)                                            | Run the DenseLayout pass on dag. |

## Attributes

|                                                                                                                                                        |                                             |
| ------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------- |
| [`is_analysis_pass`](#qiskit.transpiler.passes.DenseLayout.is_analysis_pass "qiskit.transpiler.passes.DenseLayout.is_analysis_pass")                   | Check if the pass is an analysis pass.      |
| [`is_transformation_pass`](#qiskit.transpiler.passes.DenseLayout.is_transformation_pass "qiskit.transpiler.passes.DenseLayout.is_transformation_pass") | Check if the pass is a transformation pass. |

### is\_analysis\_pass

<span id="qiskit.transpiler.passes.DenseLayout.is_analysis_pass" />

`property is_analysis_pass`

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

### is\_transformation\_pass

<span id="qiskit.transpiler.passes.DenseLayout.is_transformation_pass" />

`property is_transformation_pass`

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

### name

<span id="qiskit.transpiler.passes.DenseLayout.name" />

`name()`

Return the name of the pass.

### run

<span id="qiskit.transpiler.passes.DenseLayout.run" />

`run(dag)`

Run the DenseLayout pass on dag.

Pick a convenient layout depending on the best matching qubit connectivity, and set the property layout.

**Parameters**

**dag** ([*DAGCircuit*](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")) – DAG to find layout for.

**Raises**

[**TranspilerError**](qiskit.transpiler.TranspilerError "qiskit.transpiler.TranspilerError") – if dag wider than self.coupling\_map

