---
title: RZXCalibrationBuilderNoEcho
description: API reference for qiskit.transpiler.passes.RZXCalibrationBuilderNoEcho
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.RZXCalibrationBuilderNoEcho
---

# RZXCalibrationBuilderNoEcho

<span id="qiskit.transpiler.passes.RZXCalibrationBuilderNoEcho" />

`RZXCalibrationBuilderNoEcho(instruction_schedule_map=None, qubit_channel_mapping=None, verbose=True)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/transpiler/passes/calibration/rzx_builder.py "view source code")

Bases: [`qiskit.transpiler.passes.calibration.rzx_builder.RZXCalibrationBuilder`](qiskit.transpiler.passes.RZXCalibrationBuilder "qiskit.transpiler.passes.calibration.rzx_builder.RZXCalibrationBuilder")

Creates calibrations for RZXGate(theta) by stretching and compressing Gaussian square pulses in the CX gate.

The `RZXCalibrationBuilderNoEcho` is a variation of the [`RZXCalibrationBuilder`](qiskit.transpiler.passes.RZXCalibrationBuilder "qiskit.transpiler.passes.RZXCalibrationBuilder") pass that creates calibrations for the cross-resonance pulses without inserting the echo pulses in the pulse schedule. This enables exposing the echo in the cross-resonance sequence as gates so that the transpiler can simplify them. The `RZXCalibrationBuilderNoEcho` only supports the hardware-native direction of the CX gate.

Initializes a RZXGate calibration builder.

**Parameters**

*   **instruction\_schedule\_map** (`Optional`\[[`InstructionScheduleMap`](qiskit.pulse.InstructionScheduleMap "qiskit.pulse.instruction_schedule_map.InstructionScheduleMap")]) – The `InstructionScheduleMap` object representing the default pulse calibrations for the target backend
*   **qubit\_channel\_mapping** (`Optional`\[`List`\[`List`\[`str`]]]) – The list mapping qubit indices to the list of channel names that apply on that qubit.
*   **verbose** (`bool`) – Set True to raise a user warning when RZX schedule cannot be built.

**Raises**

**QiskitError** – Instruction schedule map is not provided.

## Methods

### get\_calibration

<span id="qiskit.transpiler.passes.RZXCalibrationBuilderNoEcho.get_calibration" />

`RZXCalibrationBuilderNoEcho.get_calibration(node_op, qubits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/transpiler/passes/calibration/rzx_builder.py "view source code")

Builds the calibration schedule for the RZXGate(theta) without echos.

**Parameters**

*   **node\_op** ([`Instruction`](qiskit.circuit.Instruction "qiskit.circuit.instruction.Instruction")) – Instruction of the RZXGate(theta). I.e. params\[0] is theta.
*   **qubits** (`List`) – List of qubits for which to get the schedules. The first qubit is the control and the second is the target.

**Returns**

The calibration schedule for the RZXGate(theta).

**Return type**

schedule

**Raises**

*   **QiskitError** – if rotation angle is not assigned.
*   **QiskitError** – If the control and target qubits cannot be identified, or the backend does not natively support the specified direction of the cx.
*   **CalibrationNotAvailable** – RZX schedule cannot be built for input node.

### name

<span id="qiskit.transpiler.passes.RZXCalibrationBuilderNoEcho.name" />

`RZXCalibrationBuilderNoEcho.name()`

Return the name of the pass.

### rescale\_cr\_inst

<span id="qiskit.transpiler.passes.RZXCalibrationBuilderNoEcho.rescale_cr_inst" />

`static RZXCalibrationBuilderNoEcho.rescale_cr_inst(instruction, theta, sample_mult=16)`

**Parameters**

*   **instruction** ([`Play`](qiskit.pulse.instructions.Play "qiskit.pulse.instructions.play.Play")) – The instruction from which to create a new shortened or lengthened pulse.
*   **theta** (`float`) – desired angle, pi/2 is assumed to be the angle that the pulse in the given play instruction implements.
*   **sample\_mult** (`int`) – All pulses must be a multiple of sample\_mult.

**Returns**

**The play instruction with the stretched compressed**

GaussianSquare pulse.

**Return type**

qiskit.pulse.Play

**Raises**

**QiskitError** – if rotation angle is not assigned.

### run

<span id="qiskit.transpiler.passes.RZXCalibrationBuilderNoEcho.run" />

`RZXCalibrationBuilderNoEcho.run(dag)`

Run the calibration adder pass on dag.

**Parameters**

**dag** ([`DAGCircuit`](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.dagcircuit.DAGCircuit")) – DAG to schedule.

**Return type**

[`DAGCircuit`](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.dagcircuit.DAGCircuit")

**Returns**

A DAG with calibrations added to it.

### supported

<span id="qiskit.transpiler.passes.RZXCalibrationBuilderNoEcho.supported" />

`RZXCalibrationBuilderNoEcho.supported(node_op, qubits)`

Determine if a given node supports the calibration.

**Parameters**

*   **node\_op** ([`Instruction`](qiskit.circuit.Instruction "qiskit.circuit.instruction.Instruction")) – Target instruction object.
*   **qubits** (`List`) – Integer qubit indices to check.

**Return type**

`bool`

**Returns**

Return `True` is calibration can be provided.

## Attributes

<span id="qiskit.transpiler.passes.RZXCalibrationBuilderNoEcho.is_analysis_pass" />

### is\_analysis\_pass

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

<span id="qiskit.transpiler.passes.RZXCalibrationBuilderNoEcho.is_transformation_pass" />

### is\_transformation\_pass

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

