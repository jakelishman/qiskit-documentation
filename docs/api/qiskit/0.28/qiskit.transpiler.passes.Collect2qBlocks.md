---
title: Collect2qBlocks
description: API reference for qiskit.transpiler.passes.Collect2qBlocks
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.Collect2qBlocks
---

# qiskit.transpiler.passes.Collect2qBlocks

<span id="qiskit.transpiler.passes.Collect2qBlocks" />

`Collect2qBlocks(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/transpiler/passes/optimization/collect_2q_blocks.py "view source code")

Collect sequences of uninterrupted gates acting on 2 qubits.

Traverse the DAG and find blocks of gates that act consecutively on pairs of qubits. Write the blocks to property\_set as a dictionary of the form:

```python
{(q0, q1): [[g0, g1, g2], [g5]],
 (q0, q2): [[g3, g4]]
 ..
 .
}
```

Based on implementation by Andrew Cross.

### \_\_init\_\_

<span id="qiskit.transpiler.passes.Collect2qBlocks.__init__" />

`__init__()`

Initialize self. See help(type(self)) for accurate signature.

## Methods

|                                                                                                                        |                                      |
| ---------------------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| [`__init__`](#qiskit.transpiler.passes.Collect2qBlocks.__init__ "qiskit.transpiler.passes.Collect2qBlocks.__init__")() | Initialize self.                     |
| [`name`](#qiskit.transpiler.passes.Collect2qBlocks.name "qiskit.transpiler.passes.Collect2qBlocks.name")()             | Return the name of the pass.         |
| [`run`](#qiskit.transpiler.passes.Collect2qBlocks.run "qiskit.transpiler.passes.Collect2qBlocks.run")(dag)             | Run the Collect2qBlocks pass on dag. |

## Attributes

|                                                                                                                                                                |                                             |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [`is_analysis_pass`](#qiskit.transpiler.passes.Collect2qBlocks.is_analysis_pass "qiskit.transpiler.passes.Collect2qBlocks.is_analysis_pass")                   | Check if the pass is an analysis pass.      |
| [`is_transformation_pass`](#qiskit.transpiler.passes.Collect2qBlocks.is_transformation_pass "qiskit.transpiler.passes.Collect2qBlocks.is_transformation_pass") | Check if the pass is a transformation pass. |

### is\_analysis\_pass

<span id="qiskit.transpiler.passes.Collect2qBlocks.is_analysis_pass" />

`property is_analysis_pass`

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

### is\_transformation\_pass

<span id="qiskit.transpiler.passes.Collect2qBlocks.is_transformation_pass" />

`property is_transformation_pass`

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

### name

<span id="qiskit.transpiler.passes.Collect2qBlocks.name" />

`name()`

Return the name of the pass.

### run

<span id="qiskit.transpiler.passes.Collect2qBlocks.run" />

`run(dag)`

Run the Collect2qBlocks pass on dag.

The blocks contain “op” nodes in topological sort order such that all gates in a block act on the same pair of qubits and are adjacent in the circuit. the blocks are built by examining predecessors and successors of 2q gates in the circuit.

After the execution, `property_set['block_list']` is set to a list of tuples of “op” node labels.

