---
title: MCXVChain
description: API reference for qiskit.circuit.library.MCXVChain
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.MCXVChain
---

# qiskit.circuit.library.MCXVChain

<span id="qiskit.circuit.library.MCXVChain" />

`MCXVChain(num_ctrl_qubits=None, dirty_ancillas=False, label=None, ctrl_state=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/circuit/library/standard_gates/x.py "view source code")

Implement the multi-controlled X gate using a V-chain of CX gates.

Create new MCX gate.

### \_\_init\_\_

<span id="qiskit.circuit.library.MCXVChain.__init__" />

`__init__(num_ctrl_qubits, dirty_ancillas=False, label=None, ctrl_state=None)`

Create new MCX gate.

## Methods

|                                                                                                                                                                            |                                                                          |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| [`__init__`](#qiskit.circuit.library.MCXVChain.__init__ "qiskit.circuit.library.MCXVChain.__init__")(num\_ctrl\_qubits\[, dirty\_ancillas, …])                             | Create new MCX gate.                                                     |
| [`add_decomposition`](#qiskit.circuit.library.MCXVChain.add_decomposition "qiskit.circuit.library.MCXVChain.add_decomposition")(decomposition)                             | Add a decomposition of the instruction to the SessionEquivalenceLibrary. |
| [`assemble`](#qiskit.circuit.library.MCXVChain.assemble "qiskit.circuit.library.MCXVChain.assemble")()                                                                     | Assemble a QasmQobjInstruction                                           |
| [`broadcast_arguments`](#qiskit.circuit.library.MCXVChain.broadcast_arguments "qiskit.circuit.library.MCXVChain.broadcast_arguments")(qargs, cargs)                        | Validation and handling of the arguments and its relationship.           |
| [`c_if`](#qiskit.circuit.library.MCXVChain.c_if "qiskit.circuit.library.MCXVChain.c_if")(classical, val)                                                                   | Add classical condition on register or cbit classical and value val.     |
| [`control`](#qiskit.circuit.library.MCXVChain.control "qiskit.circuit.library.MCXVChain.control")(\[num\_ctrl\_qubits, label, ctrl\_state])                                | Return a multi-controlled-X gate with more control lines.                |
| [`copy`](#qiskit.circuit.library.MCXVChain.copy "qiskit.circuit.library.MCXVChain.copy")(\[name])                                                                          | Copy of the instruction.                                                 |
| [`get_num_ancilla_qubits`](#qiskit.circuit.library.MCXVChain.get_num_ancilla_qubits "qiskit.circuit.library.MCXVChain.get_num_ancilla_qubits")(num\_ctrl\_qubits\[, mode]) | Get the number of required ancilla qubits.                               |
| [`inverse`](#qiskit.circuit.library.MCXVChain.inverse "qiskit.circuit.library.MCXVChain.inverse")()                                                                        | Invert this gate.                                                        |
| [`is_parameterized`](#qiskit.circuit.library.MCXVChain.is_parameterized "qiskit.circuit.library.MCXVChain.is_parameterized")()                                             | Return True .IFF.                                                        |
| [`mirror`](#qiskit.circuit.library.MCXVChain.mirror "qiskit.circuit.library.MCXVChain.mirror")()                                                                           | DEPRECATED: use instruction.reverse\_ops().                              |
| [`power`](#qiskit.circuit.library.MCXVChain.power "qiskit.circuit.library.MCXVChain.power")(exponent)                                                                      | Creates a unitary gate as gate^exponent.                                 |
| [`qasm`](#qiskit.circuit.library.MCXVChain.qasm "qiskit.circuit.library.MCXVChain.qasm")()                                                                                 | Return a default OpenQASM string for the instruction.                    |
| [`repeat`](#qiskit.circuit.library.MCXVChain.repeat "qiskit.circuit.library.MCXVChain.repeat")(n)                                                                          | Creates an instruction with gate repeated n amount of times.             |
| [`reverse_ops`](#qiskit.circuit.library.MCXVChain.reverse_ops "qiskit.circuit.library.MCXVChain.reverse_ops")()                                                            | For a composite instruction, reverse the order of sub-instructions.      |
| [`soft_compare`](#qiskit.circuit.library.MCXVChain.soft_compare "qiskit.circuit.library.MCXVChain.soft_compare")(other)                                                    | Soft comparison between gates.                                           |
| [`to_matrix`](#qiskit.circuit.library.MCXVChain.to_matrix "qiskit.circuit.library.MCXVChain.to_matrix")()                                                                  | Return a Numpy.array for the gate unitary matrix.                        |
| [`validate_parameter`](#qiskit.circuit.library.MCXVChain.validate_parameter "qiskit.circuit.library.MCXVChain.validate_parameter")(parameter)                              | Gate parameters should be int, float, or ParameterExpression             |

## Attributes

|                                                                                                                                    |                                                                               |
| ---------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| [`ctrl_state`](#qiskit.circuit.library.MCXVChain.ctrl_state "qiskit.circuit.library.MCXVChain.ctrl_state")                         | Return the control state of the gate as a decimal integer.                    |
| [`decompositions`](#qiskit.circuit.library.MCXVChain.decompositions "qiskit.circuit.library.MCXVChain.decompositions")             | Get the decompositions of the instruction from the SessionEquivalenceLibrary. |
| [`definition`](#qiskit.circuit.library.MCXVChain.definition "qiskit.circuit.library.MCXVChain.definition")                         | Return definition in terms of other basic gates.                              |
| [`duration`](#qiskit.circuit.library.MCXVChain.duration "qiskit.circuit.library.MCXVChain.duration")                               | Get the duration.                                                             |
| [`label`](#qiskit.circuit.library.MCXVChain.label "qiskit.circuit.library.MCXVChain.label")                                        | Return instruction label                                                      |
| [`name`](#qiskit.circuit.library.MCXVChain.name "qiskit.circuit.library.MCXVChain.name")                                           | Get name of gate.                                                             |
| [`num_ancilla_qubits`](#qiskit.circuit.library.MCXVChain.num_ancilla_qubits "qiskit.circuit.library.MCXVChain.num_ancilla_qubits") | The number of ancilla qubits.                                                 |
| [`num_ctrl_qubits`](#qiskit.circuit.library.MCXVChain.num_ctrl_qubits "qiskit.circuit.library.MCXVChain.num_ctrl_qubits")          | Get number of control qubits.                                                 |
| [`params`](#qiskit.circuit.library.MCXVChain.params "qiskit.circuit.library.MCXVChain.params")                                     | Get parameters from base\_gate.                                               |
| [`unit`](#qiskit.circuit.library.MCXVChain.unit "qiskit.circuit.library.MCXVChain.unit")                                           | Get the time unit of duration.                                                |

### add\_decomposition

<span id="qiskit.circuit.library.MCXVChain.add_decomposition" />

`add_decomposition(decomposition)`

Add a decomposition of the instruction to the SessionEquivalenceLibrary.

### assemble

<span id="qiskit.circuit.library.MCXVChain.assemble" />

`assemble()`

Assemble a QasmQobjInstruction

### broadcast\_arguments

<span id="qiskit.circuit.library.MCXVChain.broadcast_arguments" />

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

<span id="qiskit.circuit.library.MCXVChain.c_if" />

`c_if(classical, val)`

Add classical condition on register or cbit classical and value val.

### control

<span id="qiskit.circuit.library.MCXVChain.control" />

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

<span id="qiskit.circuit.library.MCXVChain.copy" />

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

<span id="qiskit.circuit.library.MCXVChain.ctrl_state" />

`property ctrl_state`

Return the control state of the gate as a decimal integer.

**Return type**

`int`

### decompositions

<span id="qiskit.circuit.library.MCXVChain.decompositions" />

`property decompositions`

Get the decompositions of the instruction from the SessionEquivalenceLibrary.

### definition

<span id="qiskit.circuit.library.MCXVChain.definition" />

`property definition`

Return definition in terms of other basic gates. If the gate has open controls, as determined from self.ctrl\_state, the returned definition is conjugated with X without changing the internal \_definition.

**Return type**

`List`

### duration

<span id="qiskit.circuit.library.MCXVChain.duration" />

`property duration`

Get the duration.

### get\_num\_ancilla\_qubits

<span id="qiskit.circuit.library.MCXVChain.get_num_ancilla_qubits" />

`static get_num_ancilla_qubits(num_ctrl_qubits, mode='v-chain')`

Get the number of required ancilla qubits.

### inverse

<span id="qiskit.circuit.library.MCXVChain.inverse" />

`inverse()`

Invert this gate. The MCX is its own inverse.

### is\_parameterized

<span id="qiskit.circuit.library.MCXVChain.is_parameterized" />

`is_parameterized()`

Return True .IFF. instruction is parameterized else False

### label

<span id="qiskit.circuit.library.MCXVChain.label" />

`property label`

Return instruction label

**Return type**

`str`

### mirror

<span id="qiskit.circuit.library.MCXVChain.mirror" />

`mirror()`

DEPRECATED: use instruction.reverse\_ops().

**Returns**

**a new instruction with sub-instructions**

reversed.

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

### name

<span id="qiskit.circuit.library.MCXVChain.name" />

`property name`

Get name of gate. If the gate has open controls the gate name will become:

> \<original\_name\_o\<ctrl\_state>

where \<original\_name> is the gate name for the default case of closed control qubits and \<ctrl\_state> is the integer value of the control state for the gate.

**Return type**

`str`

### num\_ancilla\_qubits

<span id="qiskit.circuit.library.MCXVChain.num_ancilla_qubits" />

`property num_ancilla_qubits`

The number of ancilla qubits.

### num\_ctrl\_qubits

<span id="qiskit.circuit.library.MCXVChain.num_ctrl_qubits" />

`property num_ctrl_qubits`

Get number of control qubits.

**Returns**

The number of control qubits for the gate.

**Return type**

int

### params

<span id="qiskit.circuit.library.MCXVChain.params" />

`property params`

Get parameters from base\_gate.

**Returns**

List of gate parameters.

**Return type**

list

**Raises**

**CircuitError** – Controlled gate does not define a base gate

### power

<span id="qiskit.circuit.library.MCXVChain.power" />

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

<span id="qiskit.circuit.library.MCXVChain.qasm" />

`qasm()`

Return a default OpenQASM string for the instruction.

Derived instructions may override this to print in a different format (e.g. measure q\[0] -> c\[0];).

### repeat

<span id="qiskit.circuit.library.MCXVChain.repeat" />

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

<span id="qiskit.circuit.library.MCXVChain.reverse_ops" />

`reverse_ops()`

For a composite instruction, reverse the order of sub-instructions.

This is done by recursively reversing all sub-instructions. It does not invert any gate.

**Returns**

**a new instruction with**

sub-instructions reversed.

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

### soft\_compare

<span id="qiskit.circuit.library.MCXVChain.soft_compare" />

`soft_compare(other)`

Soft comparison between gates. Their names, number of qubits, and classical bit numbers must match. The number of parameters must match. Each parameter is compared. If one is a ParameterExpression then it is not taken into account.

**Parameters**

**other** (*instruction*) – other instruction.

**Returns**

are self and other equal up to parameter expressions.

**Return type**

bool

### to\_matrix

<span id="qiskit.circuit.library.MCXVChain.to_matrix" />

`to_matrix()`

Return a Numpy.array for the gate unitary matrix.

**Returns**

if the Gate subclass has a matrix definition.

**Return type**

np.ndarray

**Raises**

**CircuitError** – If a Gate subclass does not implement this method an exception will be raised when this base class method is called.

### unit

<span id="qiskit.circuit.library.MCXVChain.unit" />

`property unit`

Get the time unit of duration.

### validate\_parameter

<span id="qiskit.circuit.library.MCXVChain.validate_parameter" />

`validate_parameter(parameter)`

Gate parameters should be int, float, or ParameterExpression

