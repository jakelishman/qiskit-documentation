---
title: ALAPScheduleAnalysis
description: API reference for qiskit.transpiler.passes.ALAPScheduleAnalysis
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.ALAPScheduleAnalysis
---

# ALAPScheduleAnalysis

<span id="qiskit.transpiler.passes.ALAPScheduleAnalysis" />

`ALAPScheduleAnalysis(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/transpiler/passes/scheduling/scheduling/alap.py "view source code")

Bases: `BaseScheduler`

ALAP Scheduling pass, which schedules the **stop** time of instructions as late as possible.

See the [Scheduling Stage](transpiler#scheduling-stage) section in the [`qiskit.transpiler`](transpiler#module-qiskit.transpiler "qiskit.transpiler") module documentation for the detailed behavior of the control flow operation, i.e. `c_if`.

Scheduler initializer.

**Parameters**

*   **durations** – Durations of instructions to be used in scheduling
*   **target** – The [`Target`](qiskit.transpiler.Target "qiskit.transpiler.Target") representing the target backend, if both `durations` and this are specified then this argument will take precedence and `durations` will be ignored.

## Methods

<span id="qiskit-transpiler-passes-alapscheduleanalysis-name" />

### name

<span id="qiskit.transpiler.passes.ALAPScheduleAnalysis.name" />

`ALAPScheduleAnalysis.name()`

Return the name of the pass.

<span id="qiskit-transpiler-passes-alapscheduleanalysis-run" />

### run

<span id="qiskit.transpiler.passes.ALAPScheduleAnalysis.run" />

`ALAPScheduleAnalysis.run(dag)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/transpiler/passes/scheduling/scheduling/alap.py "view source code")

Run the ALAPSchedule pass on dag.

**Parameters**

**dag** ([*DAGCircuit*](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")) – DAG to schedule.

**Returns**

A scheduled DAG.

**Return type**

[DAGCircuit](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")

**Raises**

*   [**TranspilerError**](qiskit.transpiler.TranspilerError "qiskit.transpiler.TranspilerError") – if the circuit is not mapped on physical qubits.
*   [**TranspilerError**](qiskit.transpiler.TranspilerError "qiskit.transpiler.TranspilerError") – if conditional bit is added to non-supported instruction.

## Attributes

<span id="qiskit.transpiler.passes.ALAPScheduleAnalysis.CONDITIONAL_SUPPORTED" />

### CONDITIONAL\_SUPPORTED

`= (, )`

<span id="qiskit.transpiler.passes.ALAPScheduleAnalysis.is_analysis_pass" />

### is\_analysis\_pass

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

<span id="qiskit.transpiler.passes.ALAPScheduleAnalysis.is_transformation_pass" />

### is\_transformation\_pass

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

