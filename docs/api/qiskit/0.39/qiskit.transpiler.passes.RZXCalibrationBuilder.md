---
title: RZXCalibrationBuilder
description: API reference for qiskit.transpiler.passes.RZXCalibrationBuilder
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.RZXCalibrationBuilder
---

# RZXCalibrationBuilder

<span id="qiskit.transpiler.passes.RZXCalibrationBuilder" />

`RZXCalibrationBuilder(instruction_schedule_map=None, qubit_channel_mapping=None, verbose=True)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/transpiler/passes/calibration/rzx_builder.py "view source code")

Bases: `qiskit.transpiler.passes.calibration.base_builder.CalibrationBuilder`

Creates calibrations for RZXGate(theta) by stretching and compressing Gaussian square pulses in the CX gate. This is done by retrieving (for a given pair of qubits) the CX schedule in the instruction schedule map of the backend defaults. The CX schedule must be an echoed cross-resonance gate optionally with rotary tones. The cross-resonance drive tones and rotary pulses must be Gaussian square pulses. The width of the Gaussian square pulse is adjusted so as to match the desired rotation angle. If the rotation angle is small such that the width disappears then the amplitude of the zero width Gaussian square pulse (i.e. a Gaussian) is reduced to reach the target rotation angle. Additional details can be found in [https://arxiv.org/abs/2012.11660](https://arxiv.org/abs/2012.11660).

Initializes a RZXGate calibration builder.

**Parameters**

*   **instruction\_schedule\_map** (`Optional`\[[`InstructionScheduleMap`](qiskit.pulse.InstructionScheduleMap "qiskit.pulse.instruction_schedule_map.InstructionScheduleMap")]) – The `InstructionScheduleMap` object representing the default pulse calibrations for the target backend
*   **qubit\_channel\_mapping** (`Optional`\[`List`\[`List`\[`str`]]]) – The list mapping qubit indices to the list of channel names that apply on that qubit.
*   **verbose** (`bool`) – Set True to raise a user warning when RZX schedule cannot be built.

**Raises**

**QiskitError** – Instruction schedule map is not provided.

## Methods

### get\_calibration

<span id="qiskit.transpiler.passes.RZXCalibrationBuilder.get_calibration" />

`RZXCalibrationBuilder.get_calibration(node_op, qubits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/transpiler/passes/calibration/rzx_builder.py "view source code")

Builds the calibration schedule for the RZXGate(theta) with echos.

**Parameters**

*   **node\_op** ([`Instruction`](qiskit.circuit.Instruction "qiskit.circuit.instruction.Instruction")) – Instruction of the RZXGate(theta). I.e. params\[0] is theta.
*   **qubits** (`List`) – List of qubits for which to get the schedules. The first qubit is the control and the second is the target.

**Returns**

The calibration schedule for the RZXGate(theta).

**Return type**

schedule

**Raises**

*   **QiskitError** – if rotation angle is not assigned.
*   **QiskitError** – If the control and target qubits cannot be identified.
*   **CalibrationNotAvailable** – RZX schedule cannot be built for input node.

### name

<span id="qiskit.transpiler.passes.RZXCalibrationBuilder.name" />

`RZXCalibrationBuilder.name()`

Return the name of the pass.

### rescale\_cr\_inst

<span id="qiskit.transpiler.passes.RZXCalibrationBuilder.rescale_cr_inst" />

`static RZXCalibrationBuilder.rescale_cr_inst(instruction, theta, sample_mult=16)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/transpiler/passes/calibration/rzx_builder.py "view source code")

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

<span id="qiskit.transpiler.passes.RZXCalibrationBuilder.run" />

`RZXCalibrationBuilder.run(dag)`

Run the calibration adder pass on dag.

**Parameters**

**dag** ([`DAGCircuit`](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.dagcircuit.DAGCircuit")) – DAG to schedule.

**Return type**

[`DAGCircuit`](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.dagcircuit.DAGCircuit")

**Returns**

A DAG with calibrations added to it.

### supported

<span id="qiskit.transpiler.passes.RZXCalibrationBuilder.supported" />

`RZXCalibrationBuilder.supported(node_op, qubits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/transpiler/passes/calibration/rzx_builder.py "view source code")

Determine if a given node supports the calibration.

**Parameters**

*   **node\_op** ([`Instruction`](qiskit.circuit.Instruction "qiskit.circuit.instruction.Instruction")) – Target instruction object.
*   **qubits** (`List`) – Integer qubit indices to check.

**Return type**

`bool`

**Returns**

Return `True` is calibration can be provided.

## Attributes

<span id="qiskit.transpiler.passes.RZXCalibrationBuilder.is_analysis_pass" />

### is\_analysis\_pass

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

<span id="qiskit.transpiler.passes.RZXCalibrationBuilder.is_transformation_pass" />

### is\_transformation\_pass

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

