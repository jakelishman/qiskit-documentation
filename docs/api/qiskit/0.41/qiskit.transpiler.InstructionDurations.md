---
title: InstructionDurations
description: API reference for qiskit.transpiler.InstructionDurations
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.InstructionDurations
---

# InstructionDurations

<span id="qiskit.transpiler.InstructionDurations" />

`InstructionDurations(instruction_durations=None, dt=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/transpiler/instruction_durations.py "view source code")

Bases: `object`

Helper class to provide durations of instructions for scheduling.

It stores durations (gate lengths) and dt to be used at the scheduling stage of transpiling. It can be constructed from `backend` or `instruction_durations`, which is an argument of `transpile()`. The duration of an instruction depends on the instruction (given by name), the qubits, and optionally the parameters of the instruction. Note that these fields are used as keys in dictionaries that are used to retrieve the instruction durations. Therefore, users must use the exact same parameter value to retrieve an instruction duration as the value with which it was added.

## Methods

### from\_backend

<span id="qiskit.transpiler.InstructionDurations.from_backend" />

`classmethod InstructionDurations.from_backend(backend)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/transpiler/instruction_durations.py "view source code")

Construct an [`InstructionDurations`](qiskit.transpiler.InstructionDurations "qiskit.transpiler.InstructionDurations") object from the backend.

**Parameters**

**backend** ([`Backend`](qiskit.providers.Backend "qiskit.providers.backend.Backend")) – backend from which durations (gate lengths) and dt are extracted.

**Returns**

The InstructionDurations constructed from backend.

**Return type**

[InstructionDurations](qiskit.transpiler.InstructionDurations "qiskit.transpiler.InstructionDurations")

**Raises**

[**TranspilerError**](qiskit.transpiler.TranspilerError "qiskit.transpiler.TranspilerError") – If dt and dtm is different in the backend.

### get

<span id="qiskit.transpiler.InstructionDurations.get" />

`InstructionDurations.get(inst, qubits, unit='dt', parameters=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/transpiler/instruction_durations.py "view source code")

Get the duration of the instruction with the name, qubits, and parameters.

Some instructions may have a parameter dependent duration.

**Parameters**

*   **inst** (`Union`\[`str`, [`Instruction`](qiskit.circuit.Instruction "qiskit.circuit.instruction.Instruction")]) – An instruction or its name to be queried.
*   **qubits** (`Union`\[`int`, `List`\[`int`], [`Qubit`](qiskit.circuit.Qubit "qiskit.circuit.quantumregister.Qubit"), `List`\[[`Qubit`](qiskit.circuit.Qubit "qiskit.circuit.quantumregister.Qubit")]]) – Qubits or its indices that the instruction acts on.
*   **unit** (`str`) – The unit of duration to be returned. It must be ‘s’ or ‘dt’.
*   **parameters** (`Optional`\[`List`\[`float`]]) – The value of the parameters of the desired instruction.

**Returns**

The duration of the instruction on the qubits.

**Return type**

float|int

**Raises**

[**TranspilerError**](qiskit.transpiler.TranspilerError "qiskit.transpiler.TranspilerError") – No duration is defined for the instruction.

### units\_used

<span id="qiskit.transpiler.InstructionDurations.units_used" />

`InstructionDurations.units_used()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/transpiler/instruction_durations.py "view source code")

Get the set of all units used in this instruction durations.

**Return type**

`Set`\[`str`]

**Returns**

Set of units used in this instruction durations.

### update

<span id="qiskit.transpiler.InstructionDurations.update" />

`InstructionDurations.update(inst_durations, dt=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/transpiler/instruction_durations.py "view source code")

Update self with inst\_durations (inst\_durations overwrite self).

**Parameters**

*   **inst\_durations** (`Optional`\[`Union`\[`List`\[`Tuple`\[`str`, `Optional`\[`Iterable`\[`int`]], `float`, `Optional`\[`Iterable`\[`float`]], `str`]], `List`\[`Tuple`\[`str`, `Optional`\[`Iterable`\[`int`]], `float`, `Optional`\[`Iterable`\[`float`]]]], `List`\[`Tuple`\[`str`, `Optional`\[`Iterable`\[`int`]], `float`, `str`]], `List`\[`Tuple`\[`str`, `Optional`\[`Iterable`\[`int`]], `float`]], [`InstructionDurations`](qiskit.transpiler.InstructionDurations "qiskit.transpiler.instruction_durations.InstructionDurations")]]) – Instruction durations to be merged into self (overwriting self).
*   **dt** (`Optional`\[`float`]) – Sampling duration in seconds of the target backend.

**Returns**

The updated InstructionDurations.

**Return type**

[InstructionDurations](qiskit.transpiler.InstructionDurations "qiskit.transpiler.InstructionDurations")

**Raises**

[**TranspilerError**](qiskit.transpiler.TranspilerError "qiskit.transpiler.TranspilerError") – If the format of instruction\_durations is invalid.

