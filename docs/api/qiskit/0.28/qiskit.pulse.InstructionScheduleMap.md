---
title: InstructionScheduleMap
description: API reference for qiskit.pulse.InstructionScheduleMap
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.pulse.InstructionScheduleMap
---

# qiskit.pulse.InstructionScheduleMap

<span id="qiskit.pulse.InstructionScheduleMap" />

`InstructionScheduleMap`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/pulse/instruction_schedule_map.py "view source code")

Mapping from [`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit") [`qiskit.circuit.Instruction`](qiskit.circuit.Instruction "qiskit.circuit.Instruction") names and qubits to [`Schedule`](qiskit.pulse.Schedule "qiskit.pulse.Schedule") s. In particular, the mapping is formatted as type:

```python
Dict[str, Dict[Tuple[int], Schedule]]
```

where the first key is the name of a circuit instruction (e.g. `'u1'`, `'measure'`), the second key is a tuple of qubit indices, and the final value is a Schedule implementing the requested instruction.

These can usually be seen as gate calibrations.

Initialize a circuit instruction to schedule mapper instance.

### \_\_init\_\_

<span id="qiskit.pulse.InstructionScheduleMap.__init__" />

`__init__()`

Initialize a circuit instruction to schedule mapper instance.

## Methods

|                                                                                                                                                                      |                                                                                                                                                                                                             |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.pulse.InstructionScheduleMap.__init__ "qiskit.pulse.InstructionScheduleMap.__init__")()                                                         | Initialize a circuit instruction to schedule mapper instance.                                                                                                                                               |
| [`add`](#qiskit.pulse.InstructionScheduleMap.add "qiskit.pulse.InstructionScheduleMap.add")(instruction, qubits, schedule\[, arguments])                             | Add a new known instruction for the given qubits and its mapping to a pulse schedule.                                                                                                                       |
| [`assert_has`](#qiskit.pulse.InstructionScheduleMap.assert_has "qiskit.pulse.InstructionScheduleMap.assert_has")(instruction, qubits)                                | Error if the given instruction is not defined.                                                                                                                                                              |
| [`get`](#qiskit.pulse.InstructionScheduleMap.get "qiskit.pulse.InstructionScheduleMap.get")(instruction, qubits, \*params, \*\*kwparams)                             | Return the defined [`Schedule`](qiskit.pulse.Schedule "qiskit.pulse.Schedule") or [`ScheduleBlock`](qiskit.pulse.ScheduleBlock "qiskit.pulse.ScheduleBlock") for the given instruction on the given qubits. |
| [`get_parameters`](#qiskit.pulse.InstructionScheduleMap.get_parameters "qiskit.pulse.InstructionScheduleMap.get_parameters")(instruction, qubits)                    | Return the list of parameters taken by the given instruction on the given qubits.                                                                                                                           |
| [`has`](#qiskit.pulse.InstructionScheduleMap.has "qiskit.pulse.InstructionScheduleMap.has")(instruction, qubits)                                                     | Is the instruction defined for the given qubits?                                                                                                                                                            |
| [`pop`](#qiskit.pulse.InstructionScheduleMap.pop "qiskit.pulse.InstructionScheduleMap.pop")(instruction, qubits, \*params, \*\*kwparams)                             | Remove and return the defined schedule for the given instruction on the given qubits.                                                                                                                       |
| [`qubit_instructions`](#qiskit.pulse.InstructionScheduleMap.qubit_instructions "qiskit.pulse.InstructionScheduleMap.qubit_instructions")(qubits)                     | Return a list of the instruction names that are defined by the backend for the given qubit or qubits.                                                                                                       |
| [`qubits_with_instruction`](#qiskit.pulse.InstructionScheduleMap.qubits_with_instruction "qiskit.pulse.InstructionScheduleMap.qubits_with_instruction")(instruction) | Return a list of the qubits for which the given instruction is defined.                                                                                                                                     |
| [`remove`](#qiskit.pulse.InstructionScheduleMap.remove "qiskit.pulse.InstructionScheduleMap.remove")(instruction, qubits)                                            | Remove the given instruction from the listing of instructions defined in self.                                                                                                                              |

## Attributes

|                                                                                                                        |                                                 |
| ---------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------- |
| [`instructions`](#qiskit.pulse.InstructionScheduleMap.instructions "qiskit.pulse.InstructionScheduleMap.instructions") | Return all instructions which have definitions. |

### add

<span id="qiskit.pulse.InstructionScheduleMap.add" />

`add(instruction, qubits, schedule, arguments=None)`

Add a new known instruction for the given qubits and its mapping to a pulse schedule.

**Parameters**

*   **instruction** (`Union`\[`str`, `Instruction`]) – The name of the instruction to add.
*   **qubits** (`Union`\[`int`, `Iterable`\[`int`]]) – The qubits which the instruction applies to.
*   **schedule** (`Union`\[`Schedule`, `ScheduleBlock`, `Callable`\[…, `Union`\[`Schedule`, `ScheduleBlock`]]]) – The Schedule that implements the given instruction.
*   **arguments** (`Optional`\[`List`\[`str`]]) – List of parameter names to create a parameter-bound schedule from the associated gate instruction. If [`get()`](#qiskit.pulse.InstructionScheduleMap.get "qiskit.pulse.InstructionScheduleMap.get") is called with arguments rather than keyword arguments, this parameter list is used to map the input arguments to parameter objects stored in the target schedule.

**Raises**

[**PulseError**](qiskit.pulse.PulseError "qiskit.pulse.PulseError") – If the qubits are provided as an empty iterable.

**Return type**

`None`

### assert\_has

<span id="qiskit.pulse.InstructionScheduleMap.assert_has" />

`assert_has(instruction, qubits)`

Error if the given instruction is not defined.

**Parameters**

*   **instruction** (`Union`\[`str`, `Instruction`]) – The instruction for which to look.
*   **qubits** (`Union`\[`int`, `Iterable`\[`int`]]) – The specific qubits for the instruction.

**Raises**

[**PulseError**](qiskit.pulse.PulseError "qiskit.pulse.PulseError") – If the instruction is not defined on the qubits.

**Return type**

`None`

### get

<span id="qiskit.pulse.InstructionScheduleMap.get" />

`get(instruction, qubits, *params, **kwparams)`

Return the defined [`Schedule`](qiskit.pulse.Schedule "qiskit.pulse.Schedule") or [`ScheduleBlock`](qiskit.pulse.ScheduleBlock "qiskit.pulse.ScheduleBlock") for the given instruction on the given qubits.

If all keys are not specified this method returns schedule with unbound parameters.

**Parameters**

*   **instruction** (`Union`\[`str`, `Instruction`]) – Name of the instruction or the instruction itself.
*   **qubits** (`Union`\[`int`, `Iterable`\[`int`]]) – The qubits for the instruction.
*   **\*params** – Command parameters for generating the output schedule.
*   **\*\*kwparams** – Keyworded command parameters for generating the schedule.

**Return type**

`Union`\[`Schedule`, `ScheduleBlock`]

**Returns**

The Schedule defined for the input.

**Raises**

[**PulseError**](qiskit.pulse.PulseError "qiskit.pulse.PulseError") – When invalid parameters are specified.

### get\_parameters

<span id="qiskit.pulse.InstructionScheduleMap.get_parameters" />

`get_parameters(instruction, qubits)`

Return the list of parameters taken by the given instruction on the given qubits.

**Parameters**

*   **instruction** (`Union`\[`str`, `Instruction`]) – Name of the instruction.
*   **qubits** (`Union`\[`int`, `Iterable`\[`int`]]) – The qubits for the instruction.

**Return type**

`Tuple`\[`str`]

**Returns**

The names of the parameters required by the instruction.

### has

<span id="qiskit.pulse.InstructionScheduleMap.has" />

`has(instruction, qubits)`

Is the instruction defined for the given qubits?

**Parameters**

*   **instruction** (`Union`\[`str`, `Instruction`]) – The instruction for which to look.
*   **qubits** (`Union`\[`int`, `Iterable`\[`int`]]) – The specific qubits for the instruction.

**Return type**

`bool`

**Returns**

True iff the instruction is defined.

### instructions

<span id="qiskit.pulse.InstructionScheduleMap.instructions" />

`property instructions`

Return all instructions which have definitions.

By default, these are typically the basis gates along with other instructions such as measure and reset.

**Return type**

`List`\[`str`]

**Returns**

The names of all the circuit instructions which have Schedule definitions in this.

### pop

<span id="qiskit.pulse.InstructionScheduleMap.pop" />

`pop(instruction, qubits, *params, **kwparams)`

Remove and return the defined schedule for the given instruction on the given qubits.

**Parameters**

*   **instruction** (`Union`\[`str`, `Instruction`]) – Name of the instruction.
*   **qubits** (`Union`\[`int`, `Iterable`\[`int`]]) – The qubits for the instruction.
*   **\*params** – Command parameters for generating the output schedule.
*   **\*\*kwparams** – Keyworded command parameters for generating the schedule.

**Return type**

`Union`\[`Schedule`, `ScheduleBlock`]

**Returns**

The Schedule defined for the input.

### qubit\_instructions

<span id="qiskit.pulse.InstructionScheduleMap.qubit_instructions" />

`qubit_instructions(qubits)`

Return a list of the instruction names that are defined by the backend for the given qubit or qubits.

**Parameters**

**qubits** (`Union`\[`int`, `Iterable`\[`int`]]) – A qubit index, or a list or tuple of indices.

**Return type**

`List`\[`str`]

**Returns**

All the instructions which are defined on the qubits.

For 1 qubit, all the 1Q instructions defined. For multiple qubits, all the instructions which apply to that whole set of qubits (e.g. `qubits=[0, 1]` may return `['cx']`).

### qubits\_with\_instruction

<span id="qiskit.pulse.InstructionScheduleMap.qubits_with_instruction" />

`qubits_with_instruction(instruction)`

Return a list of the qubits for which the given instruction is defined. Single qubit instructions return a flat list, and multiqubit instructions return a list of ordered tuples.

**Parameters**

**instruction** (`Union`\[`str`, `Instruction`]) – The name of the circuit instruction.

**Return type**

`List`\[`Union`\[`int`, `Tuple`\[`int`]]]

**Returns**

Qubit indices which have the given instruction defined. This is a list of tuples if the instruction has an arity greater than 1, or a flat list of ints otherwise.

**Raises**

[**PulseError**](qiskit.pulse.PulseError "qiskit.pulse.PulseError") – If the instruction is not found.

### remove

<span id="qiskit.pulse.InstructionScheduleMap.remove" />

`remove(instruction, qubits)`

Remove the given instruction from the listing of instructions defined in self.

**Parameters**

*   **instruction** (`Union`\[`str`, `Instruction`]) – The name of the instruction to add.
*   **qubits** (`Union`\[`int`, `Iterable`\[`int`]]) – The qubits which the instruction applies to.

**Return type**

`None`

