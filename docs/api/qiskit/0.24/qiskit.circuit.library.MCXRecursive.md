---
title: MCXRecursive
description: API reference for qiskit.circuit.library.MCXRecursive
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.MCXRecursive
---

<span id="qiskit-circuit-library-mcxrecursive" />

# qiskit.circuit.library.MCXRecursive

<span id="qiskit.circuit.library.MCXRecursive" />

`MCXRecursive(num_ctrl_qubits=None, label=None, ctrl_state=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.16/qiskit/circuit/library/standard_gates/x.py "view source code")

Implement the multi-controlled X gate using recursion.

Using a single ancilla qubit, the multi-controlled X gate is recursively split onto four sub-registers. This is done until we reach the 3- or 4-controlled X gate since for these we have a concrete implementation that do not require ancillas.

Create new MCX gate.

### \_\_init\_\_

<span id="qiskit.circuit.library.MCXRecursive.__init__" />

`__init__(num_ctrl_qubits, label=None, ctrl_state=None)`

Create new MCX gate.

## Methods

|                                                                                                                                                                                  |                                                                          |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| [`__init__`](#qiskit.circuit.library.MCXRecursive.__init__ "qiskit.circuit.library.MCXRecursive.__init__")(num\_ctrl\_qubits\[, label, ctrl\_state])                             | Create new MCX gate.                                                     |
| [`add_decomposition`](#qiskit.circuit.library.MCXRecursive.add_decomposition "qiskit.circuit.library.MCXRecursive.add_decomposition")(decomposition)                             | Add a decomposition of the instruction to the SessionEquivalenceLibrary. |
| [`assemble`](#qiskit.circuit.library.MCXRecursive.assemble "qiskit.circuit.library.MCXRecursive.assemble")()                                                                     | Assemble a QasmQobjInstruction                                           |
| [`broadcast_arguments`](#qiskit.circuit.library.MCXRecursive.broadcast_arguments "qiskit.circuit.library.MCXRecursive.broadcast_arguments")(qargs, cargs)                        | Validation and handling of the arguments and its relationship.           |
| [`c_if`](#qiskit.circuit.library.MCXRecursive.c_if "qiskit.circuit.library.MCXRecursive.c_if")(classical, val)                                                                   | Add classical condition on register classical and value val.             |
| [`control`](#qiskit.circuit.library.MCXRecursive.control "qiskit.circuit.library.MCXRecursive.control")(\[num\_ctrl\_qubits, label, ctrl\_state])                                | Return a multi-controlled-X gate with more control lines.                |
| [`copy`](#qiskit.circuit.library.MCXRecursive.copy "qiskit.circuit.library.MCXRecursive.copy")(\[name])                                                                          | Copy of the instruction.                                                 |
| [`get_num_ancilla_qubits`](#qiskit.circuit.library.MCXRecursive.get_num_ancilla_qubits "qiskit.circuit.library.MCXRecursive.get_num_ancilla_qubits")(num\_ctrl\_qubits\[, mode]) | Get the number of required ancilla qubits.                               |
| [`inverse`](#qiskit.circuit.library.MCXRecursive.inverse "qiskit.circuit.library.MCXRecursive.inverse")()                                                                        | Invert this gate.                                                        |
| [`is_parameterized`](#qiskit.circuit.library.MCXRecursive.is_parameterized "qiskit.circuit.library.MCXRecursive.is_parameterized")()                                             | Return True .IFF.                                                        |
| [`mirror`](#qiskit.circuit.library.MCXRecursive.mirror "qiskit.circuit.library.MCXRecursive.mirror")()                                                                           | DEPRECATED: use instruction.reverse\_ops().                              |
| [`power`](#qiskit.circuit.library.MCXRecursive.power "qiskit.circuit.library.MCXRecursive.power")(exponent)                                                                      | Creates a unitary gate as gate^exponent.                                 |
| [`qasm`](#qiskit.circuit.library.MCXRecursive.qasm "qiskit.circuit.library.MCXRecursive.qasm")()                                                                                 | Return a default OpenQASM string for the instruction.                    |
| [`repeat`](#qiskit.circuit.library.MCXRecursive.repeat "qiskit.circuit.library.MCXRecursive.repeat")(n)                                                                          | Creates an instruction with gate repeated n amount of times.             |
| [`reverse_ops`](#qiskit.circuit.library.MCXRecursive.reverse_ops "qiskit.circuit.library.MCXRecursive.reverse_ops")()                                                            | For a composite instruction, reverse the order of sub-instructions.      |
| [`to_matrix`](#qiskit.circuit.library.MCXRecursive.to_matrix "qiskit.circuit.library.MCXRecursive.to_matrix")()                                                                  | Return a Numpy.array for the gate unitary matrix.                        |
| [`validate_parameter`](#qiskit.circuit.library.MCXRecursive.validate_parameter "qiskit.circuit.library.MCXRecursive.validate_parameter")(parameter)                              | Gate parameters should be int, float, or ParameterExpression             |

## Attributes

|                                                                                                                                          |                                                                               |
| ---------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| [`ctrl_state`](#qiskit.circuit.library.MCXRecursive.ctrl_state "qiskit.circuit.library.MCXRecursive.ctrl_state")                         | Return the control state of the gate as a decimal integer.                    |
| [`decompositions`](#qiskit.circuit.library.MCXRecursive.decompositions "qiskit.circuit.library.MCXRecursive.decompositions")             | Get the decompositions of the instruction from the SessionEquivalenceLibrary. |
| [`definition`](#qiskit.circuit.library.MCXRecursive.definition "qiskit.circuit.library.MCXRecursive.definition")                         | Return definition in terms of other basic gates.                              |
| [`duration`](#qiskit.circuit.library.MCXRecursive.duration "qiskit.circuit.library.MCXRecursive.duration")                               | Get the duration.                                                             |
| [`label`](#qiskit.circuit.library.MCXRecursive.label "qiskit.circuit.library.MCXRecursive.label")                                        | Return gate label                                                             |
| [`num_ancilla_qubits`](#qiskit.circuit.library.MCXRecursive.num_ancilla_qubits "qiskit.circuit.library.MCXRecursive.num_ancilla_qubits") | The number of ancilla qubits.                                                 |
| [`num_ctrl_qubits`](#qiskit.circuit.library.MCXRecursive.num_ctrl_qubits "qiskit.circuit.library.MCXRecursive.num_ctrl_qubits")          | Get number of control qubits.                                                 |
| [`params`](#qiskit.circuit.library.MCXRecursive.params "qiskit.circuit.library.MCXRecursive.params")                                     | Get parameters from base\_gate.                                               |
| [`unit`](#qiskit.circuit.library.MCXRecursive.unit "qiskit.circuit.library.MCXRecursive.unit")                                           | Get the time unit of duration.                                                |

### add\_decomposition

<span id="qiskit.circuit.library.MCXRecursive.add_decomposition" />

`add_decomposition(decomposition)`

Add a decomposition of the instruction to the SessionEquivalenceLibrary.

### assemble

<span id="qiskit.circuit.library.MCXRecursive.assemble" />

`assemble()`

Assemble a QasmQobjInstruction

**Return type**

`Instruction`

### broadcast\_arguments

<span id="qiskit.circuit.library.MCXRecursive.broadcast_arguments" />

`broadcast_arguments(qargs, cargs)`

Validation and handling of the arguments and its relationship.

For example, `cx([q[0],q[1]], q[2])` means `cx(q[0], q[2]); cx(q[1], q[2])`. This method yields the arguments in the right grouping. In the given example:

```python
in: [[q[0],q[1]], q[2]],[]
outs: [q[0], q[2]], []
      [q[1], q[2]], []
```

The general broadcasting rules are:

> *   If len(qargs) == 1:
>
>     ```python
>     [q[0], q[1]] -> [q[0]],[q[1]]
>     ```
>
> *   If len(qargs) == 2:
>
>     ```python
>     [[q[0], q[1]], [r[0], r[1]]] -> [q[0], r[0]], [q[1], r[1]]
>     [[q[0]], [r[0], r[1]]]       -> [q[0], r[0]], [q[0], r[1]]
>     [[q[0], q[1]], [r[0]]]       -> [q[0], r[0]], [q[1], r[0]]
>     ```
>
> *   If len(qargs) >= 3:
>
>     ```python
>     [q[0], q[1]], [r[0], r[1]],  ...] -> [q[0], r[0], ...], [q[1], r[1], ...]
>     ```

**Parameters**

*   **qargs** (`List`) – List of quantum bit arguments.
*   **cargs** (`List`) – List of classical bit arguments.

**Return type**

`Tuple`\[`List`, `List`]

**Returns**

A tuple with single arguments.

**Raises**

**CircuitError** – If the input is not valid. For example, the number of arguments does not match the gate expectation.

### c\_if

<span id="qiskit.circuit.library.MCXRecursive.c_if" />

`c_if(classical, val)`

Add classical condition on register classical and value val.

### control

<span id="qiskit.circuit.library.MCXRecursive.control" />

`control(num_ctrl_qubits=1, label=None, ctrl_state=None)`

Return a multi-controlled-X gate with more control lines.

**Parameters**

*   **num\_ctrl\_qubits** (*int*) – number of control qubits.
*   **label** (*str or None*) – An optional label for the gate \[Default: None]
*   **ctrl\_state** (*int or str or None*) – control state expressed as integer, string (e.g. ‘110’), or None. If None, use all 1s.

**Returns**

controlled version of this gate.

**Return type**

[ControlledGate](qiskit.circuit.ControlledGate "qiskit.circuit.ControlledGate")

### copy

<span id="qiskit.circuit.library.MCXRecursive.copy" />

`copy(name=None)`

Copy of the instruction.

**Parameters**

**name** (*str*) – name to be given to the copied circuit, if None then the name stays the same.

**Returns**

**a copy of the current instruction, with the name**

updated if it was provided

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

### ctrl\_state

<span id="qiskit.circuit.library.MCXRecursive.ctrl_state" />

`property ctrl_state`

Return the control state of the gate as a decimal integer.

**Return type**

`int`

### decompositions

<span id="qiskit.circuit.library.MCXRecursive.decompositions" />

`property decompositions`

Get the decompositions of the instruction from the SessionEquivalenceLibrary.

### definition

<span id="qiskit.circuit.library.MCXRecursive.definition" />

`property definition`

Return definition in terms of other basic gates. If the gate has open controls, as determined from self.ctrl\_state, the returned definition is conjugated with X without changing the internal \_definition.

**Return type**

`List`

### duration

<span id="qiskit.circuit.library.MCXRecursive.duration" />

`property duration`

Get the duration.

### get\_num\_ancilla\_qubits

<span id="qiskit.circuit.library.MCXRecursive.get_num_ancilla_qubits" />

`static get_num_ancilla_qubits(num_ctrl_qubits, mode='recursion')`

Get the number of required ancilla qubits.

### inverse

<span id="qiskit.circuit.library.MCXRecursive.inverse" />

`inverse()`

Invert this gate. The MCX is its own inverse.

### is\_parameterized

<span id="qiskit.circuit.library.MCXRecursive.is_parameterized" />

`is_parameterized()`

Return True .IFF. instruction is parameterized else False

### label

<span id="qiskit.circuit.library.MCXRecursive.label" />

`property label`

Return gate label

**Return type**

`str`

### mirror

<span id="qiskit.circuit.library.MCXRecursive.mirror" />

`mirror()`

DEPRECATED: use instruction.reverse\_ops().

**Returns**

**a new instruction with sub-instructions**

reversed.

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

### num\_ancilla\_qubits

<span id="qiskit.circuit.library.MCXRecursive.num_ancilla_qubits" />

`property num_ancilla_qubits`

The number of ancilla qubits.

### num\_ctrl\_qubits

<span id="qiskit.circuit.library.MCXRecursive.num_ctrl_qubits" />

`property num_ctrl_qubits`

Get number of control qubits.

**Returns**

The number of control qubits for the gate.

**Return type**

int

### params

<span id="qiskit.circuit.library.MCXRecursive.params" />

`property params`

Get parameters from base\_gate.

**Returns**

List of gate parameters.

**Return type**

list

**Raises**

**CircuitError** – Controlled gate does not define a base gate

### power

<span id="qiskit.circuit.library.MCXRecursive.power" />

`power(exponent)`

Creates a unitary gate as gate^exponent.

**Parameters**

**exponent** (*float*) – Gate^exponent

**Returns**

To which to\_matrix is self.to\_matrix^exponent.

**Return type**

[qiskit.extensions.UnitaryGate](qiskit.extensions.UnitaryGate "qiskit.extensions.UnitaryGate")

**Raises**

**CircuitError** – If Gate is not unitary

### qasm

<span id="qiskit.circuit.library.MCXRecursive.qasm" />

`qasm()`

Return a default OpenQASM string for the instruction.

Derived instructions may override this to print in a different format (e.g. measure q\[0] -> c\[0];).

### repeat

<span id="qiskit.circuit.library.MCXRecursive.repeat" />

`repeat(n)`

Creates an instruction with gate repeated n amount of times.

**Parameters**

**n** (*int*) – Number of times to repeat the instruction

**Returns**

Containing the definition.

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

**Raises**

**CircuitError** – If n \< 1.

### reverse\_ops

<span id="qiskit.circuit.library.MCXRecursive.reverse_ops" />

`reverse_ops()`

For a composite instruction, reverse the order of sub-instructions.

This is done by recursively reversing all sub-instructions. It does not invert any gate.

**Returns**

**a new instruction with**

sub-instructions reversed.

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

### to\_matrix

<span id="qiskit.circuit.library.MCXRecursive.to_matrix" />

`to_matrix()`

Return a Numpy.array for the gate unitary matrix.

**Raises**

**CircuitError** – If a Gate subclass does not implement this method an exception will be raised when this base class method is called.

**Return type**

`ndarray`

### unit

<span id="qiskit.circuit.library.MCXRecursive.unit" />

`property unit`

Get the time unit of duration.

### validate\_parameter

<span id="qiskit.circuit.library.MCXRecursive.validate_parameter" />

`validate_parameter(parameter)`

Gate parameters should be int, float, or ParameterExpression

