---
title: InstructionScheduleMap
description: API reference for qiskit.pulse.InstructionScheduleMap
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.pulse.InstructionScheduleMap
---

# InstructionScheduleMap

<span id="qiskit.pulse.InstructionScheduleMap" />

`InstructionScheduleMap`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/pulse/instruction_schedule_map.py "view source code")

Bases: `object`

Mapping from [`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit") [`qiskit.circuit.Instruction`](qiskit.circuit.Instruction "qiskit.circuit.Instruction") names and qubits to [`Schedule`](qiskit.pulse.Schedule "qiskit.pulse.Schedule") s. In particular, the mapping is formatted as type:

```python
Dict[str, Dict[Tuple[int], Schedule]]
```

where the first key is the name of a circuit instruction (e.g. `'u1'`, `'measure'`), the second key is a tuple of qubit indices, and the final value is a Schedule implementing the requested instruction.

These can usually be seen as gate calibrations.

Initialize a circuit instruction to schedule mapper instance.

## Methods

<span id="qiskit-pulse-instructionschedulemap-add" />

### add

<span id="qiskit.pulse.InstructionScheduleMap.add" />

`InstructionScheduleMap.add(instruction, qubits, schedule, arguments=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/pulse/instruction_schedule_map.py "view source code")

Add a new known instruction for the given qubits and its mapping to a pulse schedule.

**Parameters**

*   **instruction** (*str |* [*Instruction*](qiskit.circuit.Instruction "qiskit.circuit.instruction.Instruction")) – The name of the instruction to add.
*   **qubits** (*int | Iterable\[int]*) – The qubits which the instruction applies to.
*   **schedule** ([*Schedule*](qiskit.pulse.Schedule "qiskit.pulse.schedule.Schedule")  *|*[*ScheduleBlock*](qiskit.pulse.ScheduleBlock "qiskit.pulse.schedule.ScheduleBlock")  *| Callable\[\[...],*[*Schedule*](qiskit.pulse.Schedule "qiskit.pulse.schedule.Schedule")  *|*[*ScheduleBlock*](qiskit.pulse.ScheduleBlock "qiskit.pulse.schedule.ScheduleBlock")*]*) – The Schedule that implements the given instruction.
*   **arguments** (*List\[str] | None*) – List of parameter names to create a parameter-bound schedule from the associated gate instruction. If [`get()`](qiskit.pulse.InstructionScheduleMap#get "qiskit.pulse.InstructionScheduleMap.get") is called with arguments rather than keyword arguments, this parameter list is used to map the input arguments to parameter objects stored in the target schedule.

**Raises**

[**PulseError**](pulse#qiskit.pulse.PulseError "qiskit.pulse.PulseError") – If the qubits are provided as an empty iterable.

<span id="qiskit-pulse-instructionschedulemap-assert-has" />

### assert\_has

<span id="qiskit.pulse.InstructionScheduleMap.assert_has" />

`InstructionScheduleMap.assert_has(instruction, qubits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/pulse/instruction_schedule_map.py "view source code")

Error if the given instruction is not defined.

**Parameters**

*   **instruction** (*str |* [*Instruction*](qiskit.circuit.Instruction "qiskit.circuit.instruction.Instruction")) – The instruction for which to look.
*   **qubits** (*int | Iterable\[int]*) – The specific qubits for the instruction.

**Raises**

[**PulseError**](pulse#qiskit.pulse.PulseError "qiskit.pulse.PulseError") – If the instruction is not defined on the qubits.

<span id="qiskit-pulse-instructionschedulemap-get" />

### get

<span id="qiskit.pulse.InstructionScheduleMap.get" />

`InstructionScheduleMap.get(instruction, qubits, *params, **kwparams)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/pulse/instruction_schedule_map.py "view source code")

Return the defined [`Schedule`](qiskit.pulse.Schedule "qiskit.pulse.Schedule") or [`ScheduleBlock`](qiskit.pulse.ScheduleBlock "qiskit.pulse.ScheduleBlock") for the given instruction on the given qubits.

If all keys are not specified this method returns schedule with unbound parameters.

**Parameters**

*   **instruction** (*str |* [*Instruction*](qiskit.circuit.Instruction "qiskit.circuit.instruction.Instruction")) – Name of the instruction or the instruction itself.
*   **qubits** (*int | Iterable\[int]*) – The qubits for the instruction.
*   **\*params** (*complex |* [*ParameterExpression*](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")) – Command parameters for generating the output schedule.
*   **\*\*kwparams** (*complex |* [*ParameterExpression*](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")) – Keyworded command parameters for generating the schedule.

**Returns**

The Schedule defined for the input.

**Return type**

[*Schedule*](qiskit.pulse.Schedule "qiskit.pulse.schedule.Schedule") | [*ScheduleBlock*](qiskit.pulse.ScheduleBlock "qiskit.pulse.schedule.ScheduleBlock")

<span id="qiskit-pulse-instructionschedulemap-get-parameters" />

### get\_parameters

<span id="qiskit.pulse.InstructionScheduleMap.get_parameters" />

`InstructionScheduleMap.get_parameters(instruction, qubits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/pulse/instruction_schedule_map.py "view source code")

Return the list of parameters taken by the given instruction on the given qubits.

**Parameters**

*   **instruction** (*str |* [*Instruction*](qiskit.circuit.Instruction "qiskit.circuit.instruction.Instruction")) – Name of the instruction.
*   **qubits** (*int | Iterable\[int]*) – The qubits for the instruction.

**Returns**

The names of the parameters required by the instruction.

**Return type**

*Tuple*\[str]

<span id="qiskit-pulse-instructionschedulemap-has" />

### has

<span id="qiskit.pulse.InstructionScheduleMap.has" />

`InstructionScheduleMap.has(instruction, qubits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/pulse/instruction_schedule_map.py "view source code")

Is the instruction defined for the given qubits?

**Parameters**

*   **instruction** (*str |* [*Instruction*](qiskit.circuit.Instruction "qiskit.circuit.instruction.Instruction")) – The instruction for which to look.
*   **qubits** (*int | Iterable\[int]*) – The specific qubits for the instruction.

**Returns**

True iff the instruction is defined.

**Return type**

bool

<span id="qiskit-pulse-instructionschedulemap-has-custom-gate" />

### has\_custom\_gate

<span id="qiskit.pulse.InstructionScheduleMap.has_custom_gate" />

`InstructionScheduleMap.has_custom_gate()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/pulse/instruction_schedule_map.py "view source code")

Return `True` if the map has user provided instruction.

**Return type**

bool

<span id="qiskit-pulse-instructionschedulemap-pop" />

### pop

<span id="qiskit.pulse.InstructionScheduleMap.pop" />

`InstructionScheduleMap.pop(instruction, qubits, *params, **kwparams)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/pulse/instruction_schedule_map.py "view source code")

Remove and return the defined schedule for the given instruction on the given qubits.

**Parameters**

*   **instruction** (*str |* [*Instruction*](qiskit.circuit.Instruction "qiskit.circuit.instruction.Instruction")) – Name of the instruction.
*   **qubits** (*int | Iterable\[int]*) – The qubits for the instruction.
*   **\*params** (*complex |* [*ParameterExpression*](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")) – Command parameters for generating the output schedule.
*   **\*\*kwparams** (*complex |* [*ParameterExpression*](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")) – Keyworded command parameters for generating the schedule.

**Returns**

The Schedule defined for the input.

**Return type**

[*Schedule*](qiskit.pulse.Schedule "qiskit.pulse.schedule.Schedule") | [*ScheduleBlock*](qiskit.pulse.ScheduleBlock "qiskit.pulse.schedule.ScheduleBlock")

<span id="qiskit-pulse-instructionschedulemap-qubit-instructions" />

### qubit\_instructions

<span id="qiskit.pulse.InstructionScheduleMap.qubit_instructions" />

`InstructionScheduleMap.qubit_instructions(qubits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/pulse/instruction_schedule_map.py "view source code")

Return a list of the instruction names that are defined by the backend for the given qubit or qubits.

**Parameters**

**qubits** (*int | Iterable\[int]*) – A qubit index, or a list or tuple of indices.

**Returns**

All the instructions which are defined on the qubits.

For 1 qubit, all the 1Q instructions defined. For multiple qubits, all the instructions which apply to that whole set of qubits (e.g. `qubits=[0, 1]` may return `['cx']`).

**Return type**

*List*\[str]

<span id="qiskit-pulse-instructionschedulemap-qubits-with-instruction" />

### qubits\_with\_instruction

<span id="qiskit.pulse.InstructionScheduleMap.qubits_with_instruction" />

`InstructionScheduleMap.qubits_with_instruction(instruction)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/pulse/instruction_schedule_map.py "view source code")

Return a list of the qubits for which the given instruction is defined. Single qubit instructions return a flat list, and multiqubit instructions return a list of ordered tuples.

**Parameters**

**instruction** (*str |* [*Instruction*](qiskit.circuit.Instruction "qiskit.circuit.instruction.Instruction")) – The name of the circuit instruction.

**Returns**

Qubit indices which have the given instruction defined. This is a list of tuples if the instruction has an arity greater than 1, or a flat list of ints otherwise.

**Raises**

[**PulseError**](pulse#qiskit.pulse.PulseError "qiskit.pulse.PulseError") – If the instruction is not found.

**Return type**

*List*\[int | *Tuple*\[int]]

<span id="qiskit-pulse-instructionschedulemap-remove" />

### remove

<span id="qiskit.pulse.InstructionScheduleMap.remove" />

`InstructionScheduleMap.remove(instruction, qubits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/pulse/instruction_schedule_map.py "view source code")

Remove the given instruction from the listing of instructions defined in self.

**Parameters**

*   **instruction** (*str |* [*Instruction*](qiskit.circuit.Instruction "qiskit.circuit.instruction.Instruction")) – The name of the instruction to add.
*   **qubits** (*int | Iterable\[int]*) – The qubits which the instruction applies to.

## Attributes

<span id="qiskit.pulse.InstructionScheduleMap.instructions" />

### instructions

Return all instructions which have definitions.

By default, these are typically the basis gates along with other instructions such as measure and reset.

**Returns**

The names of all the circuit instructions which have Schedule definitions in this.

