---
title: RYGate
description: API reference for qiskit.circuit.library.RYGate
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.RYGate
---

<span id="qiskit-circuit-library-rygate" />

# qiskit.circuit.library.RYGate

<span id="qiskit.circuit.library.RYGate" />

`RYGate(theta, label=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.16/qiskit/circuit/library/standard_gates/ry.py "view source code")

Single-qubit rotation about the Y axis.

**Circuit symbol:**

```python
     ┌───────┐
q_0: ┤ Ry(ϴ) ├
     └───────┘
```

**Matrix Representation:**

$$
 \begin{align}\begin{aligned}\newcommand{\th}{\frac{\theta}{2}}\\\begin{split}RY(\theta) = exp(-i \th Y) =
    \begin{pmatrix}
        \cos{\th} & -\sin{\th} \\
        \sin{\th} & \cos{\th}
    \end{pmatrix}\end{split}\end{aligned}\end{align} 
$$

Create new RY gate.

### \_\_init\_\_

<span id="qiskit.circuit.library.RYGate.__init__" />

`__init__(theta, label=None)`

Create new RY gate.

## Methods

|                                                                                                                                               |                                                                          |
| --------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| [`__init__`](#qiskit.circuit.library.RYGate.__init__ "qiskit.circuit.library.RYGate.__init__")(theta\[, label])                               | Create new RY gate.                                                      |
| [`add_decomposition`](#qiskit.circuit.library.RYGate.add_decomposition "qiskit.circuit.library.RYGate.add_decomposition")(decomposition)      | Add a decomposition of the instruction to the SessionEquivalenceLibrary. |
| [`assemble`](#qiskit.circuit.library.RYGate.assemble "qiskit.circuit.library.RYGate.assemble")()                                              | Assemble a QasmQobjInstruction                                           |
| [`broadcast_arguments`](#qiskit.circuit.library.RYGate.broadcast_arguments "qiskit.circuit.library.RYGate.broadcast_arguments")(qargs, cargs) | Validation and handling of the arguments and its relationship.           |
| [`c_if`](#qiskit.circuit.library.RYGate.c_if "qiskit.circuit.library.RYGate.c_if")(classical, val)                                            | Add classical condition on register classical and value val.             |
| [`control`](#qiskit.circuit.library.RYGate.control "qiskit.circuit.library.RYGate.control")(\[num\_ctrl\_qubits, label, ctrl\_state])         | Return a (mutli-)controlled-RY gate.                                     |
| [`copy`](#qiskit.circuit.library.RYGate.copy "qiskit.circuit.library.RYGate.copy")(\[name])                                                   | Copy of the instruction.                                                 |
| [`inverse`](#qiskit.circuit.library.RYGate.inverse "qiskit.circuit.library.RYGate.inverse")()                                                 | Return inverted RY gate.                                                 |
| [`is_parameterized`](#qiskit.circuit.library.RYGate.is_parameterized "qiskit.circuit.library.RYGate.is_parameterized")()                      | Return True .IFF.                                                        |
| [`mirror`](#qiskit.circuit.library.RYGate.mirror "qiskit.circuit.library.RYGate.mirror")()                                                    | DEPRECATED: use instruction.reverse\_ops().                              |
| [`power`](#qiskit.circuit.library.RYGate.power "qiskit.circuit.library.RYGate.power")(exponent)                                               | Creates a unitary gate as gate^exponent.                                 |
| [`qasm`](#qiskit.circuit.library.RYGate.qasm "qiskit.circuit.library.RYGate.qasm")()                                                          | Return a default OpenQASM string for the instruction.                    |
| [`repeat`](#qiskit.circuit.library.RYGate.repeat "qiskit.circuit.library.RYGate.repeat")(n)                                                   | Creates an instruction with gate repeated n amount of times.             |
| [`reverse_ops`](#qiskit.circuit.library.RYGate.reverse_ops "qiskit.circuit.library.RYGate.reverse_ops")()                                     | For a composite instruction, reverse the order of sub-instructions.      |
| [`to_matrix`](#qiskit.circuit.library.RYGate.to_matrix "qiskit.circuit.library.RYGate.to_matrix")()                                           | Return a numpy.array for the RY gate.                                    |
| [`validate_parameter`](#qiskit.circuit.library.RYGate.validate_parameter "qiskit.circuit.library.RYGate.validate_parameter")(parameter)       | Gate parameters should be int, float, or ParameterExpression             |

## Attributes

|                                                                                                                  |                                                                               |
| ---------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| [`decompositions`](#qiskit.circuit.library.RYGate.decompositions "qiskit.circuit.library.RYGate.decompositions") | Get the decompositions of the instruction from the SessionEquivalenceLibrary. |
| [`definition`](#qiskit.circuit.library.RYGate.definition "qiskit.circuit.library.RYGate.definition")             | Return definition in terms of other basic gates.                              |
| [`duration`](#qiskit.circuit.library.RYGate.duration "qiskit.circuit.library.RYGate.duration")                   | Get the duration.                                                             |
| [`label`](#qiskit.circuit.library.RYGate.label "qiskit.circuit.library.RYGate.label")                            | Return gate label                                                             |
| [`params`](#qiskit.circuit.library.RYGate.params "qiskit.circuit.library.RYGate.params")                         | return instruction params.                                                    |
| [`unit`](#qiskit.circuit.library.RYGate.unit "qiskit.circuit.library.RYGate.unit")                               | Get the time unit of duration.                                                |

### add\_decomposition

<span id="qiskit.circuit.library.RYGate.add_decomposition" />

`add_decomposition(decomposition)`

Add a decomposition of the instruction to the SessionEquivalenceLibrary.

### assemble

<span id="qiskit.circuit.library.RYGate.assemble" />

`assemble()`

Assemble a QasmQobjInstruction

**Return type**

`Instruction`

### broadcast\_arguments

<span id="qiskit.circuit.library.RYGate.broadcast_arguments" />

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

<span id="qiskit.circuit.library.RYGate.c_if" />

`c_if(classical, val)`

Add classical condition on register classical and value val.

### control

<span id="qiskit.circuit.library.RYGate.control" />

`control(num_ctrl_qubits=1, label=None, ctrl_state=None)`

Return a (mutli-)controlled-RY gate.

**Parameters**

*   **num\_ctrl\_qubits** (*int*) – number of control qubits.
*   **label** (*str or None*) – An optional label for the gate \[Default: None]
*   **ctrl\_state** (*int or str or None*) – control state expressed as integer, string (e.g. ‘110’), or None. If None, use all 1s.

**Returns**

controlled version of this gate.

**Return type**

[ControlledGate](qiskit.circuit.ControlledGate "qiskit.circuit.ControlledGate")

### copy

<span id="qiskit.circuit.library.RYGate.copy" />

`copy(name=None)`

Copy of the instruction.

**Parameters**

**name** (*str*) – name to be given to the copied circuit, if None then the name stays the same.

**Returns**

**a copy of the current instruction, with the name**

updated if it was provided

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

### decompositions

<span id="qiskit.circuit.library.RYGate.decompositions" />

`property decompositions`

Get the decompositions of the instruction from the SessionEquivalenceLibrary.

### definition

<span id="qiskit.circuit.library.RYGate.definition" />

`property definition`

Return definition in terms of other basic gates.

### duration

<span id="qiskit.circuit.library.RYGate.duration" />

`property duration`

Get the duration.

### inverse

<span id="qiskit.circuit.library.RYGate.inverse" />

`inverse()`

Return inverted RY gate.

$RY(\lambda){\dagger} = RY(-\lambda)$

### is\_parameterized

<span id="qiskit.circuit.library.RYGate.is_parameterized" />

`is_parameterized()`

Return True .IFF. instruction is parameterized else False

### label

<span id="qiskit.circuit.library.RYGate.label" />

`property label`

Return gate label

**Return type**

`str`

### mirror

<span id="qiskit.circuit.library.RYGate.mirror" />

`mirror()`

DEPRECATED: use instruction.reverse\_ops().

**Returns**

**a new instruction with sub-instructions**

reversed.

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

### params

<span id="qiskit.circuit.library.RYGate.params" />

`property params`

return instruction params.

### power

<span id="qiskit.circuit.library.RYGate.power" />

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

<span id="qiskit.circuit.library.RYGate.qasm" />

`qasm()`

Return a default OpenQASM string for the instruction.

Derived instructions may override this to print in a different format (e.g. measure q\[0] -> c\[0];).

### repeat

<span id="qiskit.circuit.library.RYGate.repeat" />

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

<span id="qiskit.circuit.library.RYGate.reverse_ops" />

`reverse_ops()`

For a composite instruction, reverse the order of sub-instructions.

This is done by recursively reversing all sub-instructions. It does not invert any gate.

**Returns**

**a new instruction with**

sub-instructions reversed.

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

### to\_matrix

<span id="qiskit.circuit.library.RYGate.to_matrix" />

`to_matrix()`

Return a numpy.array for the RY gate.

### unit

<span id="qiskit.circuit.library.RYGate.unit" />

`property unit`

Get the time unit of duration.

### validate\_parameter

<span id="qiskit.circuit.library.RYGate.validate_parameter" />

`validate_parameter(parameter)`

Gate parameters should be int, float, or ParameterExpression

