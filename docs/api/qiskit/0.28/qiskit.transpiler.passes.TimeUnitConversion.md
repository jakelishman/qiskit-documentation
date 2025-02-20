---
title: TimeUnitConversion
description: API reference for qiskit.transpiler.passes.TimeUnitConversion
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.TimeUnitConversion
---

# qiskit.transpiler.passes.TimeUnitConversion

<span id="qiskit.transpiler.passes.TimeUnitConversion" />

`TimeUnitConversion(inst_durations)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/transpiler/passes/scheduling/time_unit_conversion.py "view source code")

Choose a time unit to be used in the following time-aware passes, and make all circuit time units consistent with that.

This pass will add a .duration metadata to each op whose duration is known, which will be used by subsequent scheduling passes for scheduling.

If dt (dt in seconds) is known to transpiler, the unit ‘dt’ is chosen. Otherwise, the unit to be selected depends on what units are used in delays and instruction durations: \* ‘s’: if they are all in SI units. \* ‘dt’: if they are all in the unit ‘dt’. \* raise error: if they are a mix of SI units and ‘dt’.

TimeUnitAnalysis initializer.

**Parameters**

**inst\_durations** ([*InstructionDurations*](qiskit.transpiler.InstructionDurations "qiskit.transpiler.InstructionDurations")) – A dictionary of durations of instructions.

### \_\_init\_\_

<span id="qiskit.transpiler.passes.TimeUnitConversion.__init__" />

`__init__(inst_durations)`

TimeUnitAnalysis initializer.

**Parameters**

**inst\_durations** ([*InstructionDurations*](qiskit.transpiler.InstructionDurations "qiskit.transpiler.InstructionDurations")) – A dictionary of durations of instructions.

## Methods

|                                                                                                                                             |                                       |
| ------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------- |
| [`__init__`](#qiskit.transpiler.passes.TimeUnitConversion.__init__ "qiskit.transpiler.passes.TimeUnitConversion.__init__")(inst\_durations) | TimeUnitAnalysis initializer.         |
| [`name`](#qiskit.transpiler.passes.TimeUnitConversion.name "qiskit.transpiler.passes.TimeUnitConversion.name")()                            | Return the name of the pass.          |
| [`run`](#qiskit.transpiler.passes.TimeUnitConversion.run "qiskit.transpiler.passes.TimeUnitConversion.run")(dag)                            | Run the TimeUnitAnalysis pass on dag. |

## Attributes

|                                                                                                                                                                      |                                             |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [`is_analysis_pass`](#qiskit.transpiler.passes.TimeUnitConversion.is_analysis_pass "qiskit.transpiler.passes.TimeUnitConversion.is_analysis_pass")                   | Check if the pass is an analysis pass.      |
| [`is_transformation_pass`](#qiskit.transpiler.passes.TimeUnitConversion.is_transformation_pass "qiskit.transpiler.passes.TimeUnitConversion.is_transformation_pass") | Check if the pass is a transformation pass. |

### is\_analysis\_pass

<span id="qiskit.transpiler.passes.TimeUnitConversion.is_analysis_pass" />

`property is_analysis_pass`

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

### is\_transformation\_pass

<span id="qiskit.transpiler.passes.TimeUnitConversion.is_transformation_pass" />

`property is_transformation_pass`

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

### name

<span id="qiskit.transpiler.passes.TimeUnitConversion.name" />

`name()`

Return the name of the pass.

### run

<span id="qiskit.transpiler.passes.TimeUnitConversion.run" />

`run(dag)`

Run the TimeUnitAnalysis pass on dag.

**Parameters**

**dag** ([*DAGCircuit*](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")) – DAG to be checked.

**Returns**

DAG with consistent timing and op nodes annotated with duration.

**Return type**

[DAGCircuit](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")

**Raises**

[**TranspilerError**](qiskit.transpiler.TranspilerError "qiskit.transpiler.TranspilerError") – if the units are not unifiable

