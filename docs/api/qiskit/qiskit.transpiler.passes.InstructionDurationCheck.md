---
title: InstructionDurationCheck
description: API reference for qiskit.transpiler.passes.InstructionDurationCheck
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.InstructionDurationCheck
---

# InstructionDurationCheck

<span id="qiskit.transpiler.passes.InstructionDurationCheck" />

`qiskit.transpiler.passes.InstructionDurationCheck(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/transpiler/passes/scheduling/alignments/check_durations.py "view source code")

Bases: [`AnalysisPass`](qiskit.transpiler.AnalysisPass "qiskit.transpiler.basepasses.AnalysisPass")

Duration validation pass for reschedule.

This pass investigates the input quantum circuit and checks if the circuit requires rescheduling for execution. Note that this pass can be triggered without scheduling. This pass only checks the duration of delay instructions and user defined pulse gates, which report duration values without pre-scheduling.

This pass assumes backend supported instructions, i.e. basis gates, have no violation of the hardware alignment constraints, which is true in general.

Create new duration validation pass.

The alignment values depend on the control electronics of your quantum processor.

**Parameters**

*   **acquire\_alignment** – Integer number representing the minimum time resolution to trigger acquisition instruction in units of `dt`.
*   **pulse\_alignment** – Integer number representing the minimum time resolution to trigger gate instruction in units of `dt`.

## Attributes

<span id="qiskit.transpiler.passes.InstructionDurationCheck.is_analysis_pass" />

### is\_analysis\_pass

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

<span id="qiskit.transpiler.passes.InstructionDurationCheck.is_transformation_pass" />

### is\_transformation\_pass

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

## Methods

### execute

<span id="qiskit.transpiler.passes.InstructionDurationCheck.execute" />

`execute(passmanager_ir, state, callback=None)`

Execute optimization task for input Qiskit IR.

**Parameters**

*   **passmanager\_ir** ([*Any*](https://docs.python.org/3/library/typing.html#typing.Any "(in Python v3.12)")) – Qiskit IR to optimize.
*   **state** ([*PassManagerState*](qiskit.passmanager.PassManagerState "qiskit.passmanager.compilation_status.PassManagerState")) – State associated with workflow execution by the pass manager itself.
*   **callback** ([*Callable*](https://docs.python.org/3/library/collections.abc.html#collections.abc.Callable "(in Python v3.12)") *| None*) – A callback function which is caller per execution of optimization task.

**Returns**

Optimized Qiskit IR and state of the workflow.

**Return type**

[tuple](https://docs.python.org/3/library/stdtypes.html#tuple "(in Python v3.12)")\[[*Any*](https://docs.python.org/3/library/typing.html#typing.Any "(in Python v3.12)"), [qiskit.passmanager.compilation\_status.PassManagerState](qiskit.passmanager.PassManagerState "qiskit.passmanager.compilation_status.PassManagerState")]

### name

<span id="qiskit.transpiler.passes.InstructionDurationCheck.name" />

`name()`

Name of the pass.

**Return type**

[str](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")

### run

<span id="qiskit.transpiler.passes.InstructionDurationCheck.run" />

`run(dag)`

Run duration validation passes.

**Parameters**

**dag** ([*DAGCircuit*](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.dagcircuit.DAGCircuit")) – DAG circuit to check instruction durations.

### update\_status

<span id="qiskit.transpiler.passes.InstructionDurationCheck.update_status" />

`update_status(state, run_state)`

Update workflow status.

**Parameters**

*   **state** ([*PassManagerState*](qiskit.passmanager.PassManagerState "qiskit.passmanager.compilation_status.PassManagerState")) – Pass manager state to update.
*   **run\_state** (*RunState*) – Completion status of current task.

**Returns**

Updated pass manager state.

**Return type**

[*PassManagerState*](qiskit.passmanager.PassManagerState "qiskit.passmanager.compilation_status.PassManagerState")

