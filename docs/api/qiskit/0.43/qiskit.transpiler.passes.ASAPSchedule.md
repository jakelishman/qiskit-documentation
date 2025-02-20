---
title: ASAPSchedule
description: API reference for qiskit.transpiler.passes.ASAPSchedule
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.ASAPSchedule
---

# ASAPSchedule

<span id="qiskit.transpiler.passes.ASAPSchedule" />

`ASAPSchedule(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/transpiler/passes/scheduling/asap.py "view source code")

Bases: `BaseSchedulerTransform`

ASAP Scheduling pass, which schedules the start time of instructions as early as possible..

See `BaseSchedulerTransform` for the detailed behavior of the control flow operation, i.e. `c_if`.

<Admonition title="Note" type="note">
  This base class has been superseded by [`ASAPScheduleAnalysis`](qiskit.transpiler.passes.ASAPScheduleAnalysis "qiskit.transpiler.passes.ASAPScheduleAnalysis") and the new scheduling workflow. It will be deprecated and subsequently removed in a future release.
</Admonition>

<Admonition title="Deprecated since version 0.21.0_pending" type="danger">
  The class `qiskit.transpiler.passes.scheduling.asap.ASAPSchedule` is pending deprecation as of qiskit-terra 0.21.0. It will be marked deprecated in a future release, and then removed no earlier than 3 months after the release date. Instead, use [`ASAPScheduleAnalysis`](qiskit.transpiler.passes.ASAPScheduleAnalysis "qiskit.transpiler.passes.ASAPScheduleAnalysis"), which is an analysis pass that requires a padding pass to later modify the circuit.
</Admonition>

## Methods

<span id="qiskit-transpiler-passes-asapschedule-name" />

### name

<span id="qiskit.transpiler.passes.ASAPSchedule.name" />

`ASAPSchedule.name()`

Return the name of the pass.

<span id="qiskit-transpiler-passes-asapschedule-run" />

### run

<span id="qiskit.transpiler.passes.ASAPSchedule.run" />

`ASAPSchedule.run(dag)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/transpiler/passes/scheduling/asap.py "view source code")

Run the ASAPSchedule pass on dag.

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

<span id="qiskit.transpiler.passes.ASAPSchedule.CONDITIONAL_SUPPORTED" />

### CONDITIONAL\_SUPPORTED

`= (, )`

<span id="qiskit.transpiler.passes.ASAPSchedule.is_analysis_pass" />

### is\_analysis\_pass

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

<span id="qiskit.transpiler.passes.ASAPSchedule.is_transformation_pass" />

### is\_transformation\_pass

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

