---
title: CU1Gate
description: API reference for qiskit.circuit.library.CU1Gate
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.CU1Gate
---

<span id="qiskit-circuit-library-cu1gate" />

# qiskit.circuit.library.CU1Gate

<span id="qiskit.circuit.library.CU1Gate" />

`CU1Gate(theta, label=None, ctrl_state=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.16/qiskit/circuit/library/standard_gates/u1.py "view source code")

Controlled-U1 gate.

This is a diagonal and symmetric gate that induces a phase on the state of the target qubit, depending on the control state.

**Circuit symbol:**

```python
q_0: ─■──
      │λ
q_1: ─■──
```

**Matrix representation:**

$$
\begin{split}CU1 =
    |0\rangle\langle 0| \otimes I + |1\rangle\langle 1| \otimes U1 =
    \begin{pmatrix}
        1 & 0 & 0 & 0 \\
        0 & 1 & 0 & 0 \\
        0 & 0 & 1 & 0 \\
        0 & 0 & 0 & e^{i\lambda}
    \end{pmatrix}\end{split}
$$

<Admonition title="See also" type="note">
  `CRZGate`: Due to the global phase difference in the matrix definitions of U1 and RZ, CU1 and CRZ are different gates with a relative phase difference.
</Admonition>

Create new CU1 gate.

### \_\_init\_\_

<span id="qiskit.circuit.library.CU1Gate.__init__" />

`__init__(theta, label=None, ctrl_state=None)`

Create new CU1 gate.

## Methods

|                                                                                                                                                 |                                                                          |
| ----------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| [`__init__`](#qiskit.circuit.library.CU1Gate.__init__ "qiskit.circuit.library.CU1Gate.__init__")(theta\[, label, ctrl\_state])                  | Create new CU1 gate.                                                     |
| [`add_decomposition`](#qiskit.circuit.library.CU1Gate.add_decomposition "qiskit.circuit.library.CU1Gate.add_decomposition")(decomposition)      | Add a decomposition of the instruction to the SessionEquivalenceLibrary. |
| [`assemble`](#qiskit.circuit.library.CU1Gate.assemble "qiskit.circuit.library.CU1Gate.assemble")()                                              | Assemble a QasmQobjInstruction                                           |
| [`broadcast_arguments`](#qiskit.circuit.library.CU1Gate.broadcast_arguments "qiskit.circuit.library.CU1Gate.broadcast_arguments")(qargs, cargs) | Validation and handling of the arguments and its relationship.           |
| [`c_if`](#qiskit.circuit.library.CU1Gate.c_if "qiskit.circuit.library.CU1Gate.c_if")(classical, val)                                            | Add classical condition on register classical and value val.             |
| [`control`](#qiskit.circuit.library.CU1Gate.control "qiskit.circuit.library.CU1Gate.control")(\[num\_ctrl\_qubits, label, ctrl\_state])         | Controlled version of this gate.                                         |
| [`copy`](#qiskit.circuit.library.CU1Gate.copy "qiskit.circuit.library.CU1Gate.copy")(\[name])                                                   | Copy of the instruction.                                                 |
| [`inverse`](#qiskit.circuit.library.CU1Gate.inverse "qiskit.circuit.library.CU1Gate.inverse")()                                                 | Return inverted CU1 gate ($CU1(\lambda){\dagger} = CU1(-\lambda)$)       |
| [`is_parameterized`](#qiskit.circuit.library.CU1Gate.is_parameterized "qiskit.circuit.library.CU1Gate.is_parameterized")()                      | Return True .IFF.                                                        |
| [`mirror`](#qiskit.circuit.library.CU1Gate.mirror "qiskit.circuit.library.CU1Gate.mirror")()                                                    | DEPRECATED: use instruction.reverse\_ops().                              |
| [`power`](#qiskit.circuit.library.CU1Gate.power "qiskit.circuit.library.CU1Gate.power")(exponent)                                               | Creates a unitary gate as gate^exponent.                                 |
| [`qasm`](#qiskit.circuit.library.CU1Gate.qasm "qiskit.circuit.library.CU1Gate.qasm")()                                                          | Return a default OpenQASM string for the instruction.                    |
| [`repeat`](#qiskit.circuit.library.CU1Gate.repeat "qiskit.circuit.library.CU1Gate.repeat")(n)                                                   | Creates an instruction with gate repeated n amount of times.             |
| [`reverse_ops`](#qiskit.circuit.library.CU1Gate.reverse_ops "qiskit.circuit.library.CU1Gate.reverse_ops")()                                     | For a composite instruction, reverse the order of sub-instructions.      |
| [`to_matrix`](#qiskit.circuit.library.CU1Gate.to_matrix "qiskit.circuit.library.CU1Gate.to_matrix")()                                           | Return a numpy.array for the CU1 gate.                                   |
| [`validate_parameter`](#qiskit.circuit.library.CU1Gate.validate_parameter "qiskit.circuit.library.CU1Gate.validate_parameter")(parameter)       | Gate parameters should be int, float, or ParameterExpression             |

## Attributes

|                                                                                                                       |                                                                               |
| --------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| [`ctrl_state`](#qiskit.circuit.library.CU1Gate.ctrl_state "qiskit.circuit.library.CU1Gate.ctrl_state")                | Return the control state of the gate as a decimal integer.                    |
| [`decompositions`](#qiskit.circuit.library.CU1Gate.decompositions "qiskit.circuit.library.CU1Gate.decompositions")    | Get the decompositions of the instruction from the SessionEquivalenceLibrary. |
| [`definition`](#qiskit.circuit.library.CU1Gate.definition "qiskit.circuit.library.CU1Gate.definition")                | Return definition in terms of other basic gates.                              |
| [`duration`](#qiskit.circuit.library.CU1Gate.duration "qiskit.circuit.library.CU1Gate.duration")                      | Get the duration.                                                             |
| [`label`](#qiskit.circuit.library.CU1Gate.label "qiskit.circuit.library.CU1Gate.label")                               | Return gate label                                                             |
| [`num_ctrl_qubits`](#qiskit.circuit.library.CU1Gate.num_ctrl_qubits "qiskit.circuit.library.CU1Gate.num_ctrl_qubits") | Get number of control qubits.                                                 |
| [`params`](#qiskit.circuit.library.CU1Gate.params "qiskit.circuit.library.CU1Gate.params")                            | Get parameters from base\_gate.                                               |
| [`unit`](#qiskit.circuit.library.CU1Gate.unit "qiskit.circuit.library.CU1Gate.unit")                                  | Get the time unit of duration.                                                |

### add\_decomposition

<span id="qiskit.circuit.library.CU1Gate.add_decomposition" />

`add_decomposition(decomposition)`

Add a decomposition of the instruction to the SessionEquivalenceLibrary.

### assemble

<span id="qiskit.circuit.library.CU1Gate.assemble" />

`assemble()`

Assemble a QasmQobjInstruction

**Return type**

`Instruction`

### broadcast\_arguments

<span id="qiskit.circuit.library.CU1Gate.broadcast_arguments" />

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

<span id="qiskit.circuit.library.CU1Gate.c_if" />

`c_if(classical, val)`

Add classical condition on register classical and value val.

### control

<span id="qiskit.circuit.library.CU1Gate.control" />

`control(num_ctrl_qubits=1, label=None, ctrl_state=None)`

Controlled version of this gate.

**Parameters**

*   **num\_ctrl\_qubits** (*int*) – number of control qubits.
*   **label** (*str or None*) – An optional label for the gate \[Default: None]
*   **ctrl\_state** (*int or str or None*) – control state expressed as integer, string (e.g. ‘110’), or None. If None, use all 1s.

**Returns**

controlled version of this gate.

**Return type**

[ControlledGate](qiskit.circuit.ControlledGate "qiskit.circuit.ControlledGate")

### copy

<span id="qiskit.circuit.library.CU1Gate.copy" />

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

<span id="qiskit.circuit.library.CU1Gate.ctrl_state" />

`property ctrl_state`

Return the control state of the gate as a decimal integer.

**Return type**

`int`

### decompositions

<span id="qiskit.circuit.library.CU1Gate.decompositions" />

`property decompositions`

Get the decompositions of the instruction from the SessionEquivalenceLibrary.

### definition

<span id="qiskit.circuit.library.CU1Gate.definition" />

`property definition`

Return definition in terms of other basic gates. If the gate has open controls, as determined from self.ctrl\_state, the returned definition is conjugated with X without changing the internal \_definition.

**Return type**

`List`

### duration

<span id="qiskit.circuit.library.CU1Gate.duration" />

`property duration`

Get the duration.

### inverse

<span id="qiskit.circuit.library.CU1Gate.inverse" />

`inverse()`

Return inverted CU1 gate ($CU1(\lambda){\dagger} = CU1(-\lambda)$)

### is\_parameterized

<span id="qiskit.circuit.library.CU1Gate.is_parameterized" />

`is_parameterized()`

Return True .IFF. instruction is parameterized else False

### label

<span id="qiskit.circuit.library.CU1Gate.label" />

`property label`

Return gate label

**Return type**

`str`

### mirror

<span id="qiskit.circuit.library.CU1Gate.mirror" />

`mirror()`

DEPRECATED: use instruction.reverse\_ops().

**Returns**

**a new instruction with sub-instructions**

reversed.

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

### num\_ctrl\_qubits

<span id="qiskit.circuit.library.CU1Gate.num_ctrl_qubits" />

`property num_ctrl_qubits`

Get number of control qubits.

**Returns**

The number of control qubits for the gate.

**Return type**

int

### params

<span id="qiskit.circuit.library.CU1Gate.params" />

`property params`

Get parameters from base\_gate.

**Returns**

List of gate parameters.

**Return type**

list

**Raises**

**CircuitError** – Controlled gate does not define a base gate

### power

<span id="qiskit.circuit.library.CU1Gate.power" />

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

<span id="qiskit.circuit.library.CU1Gate.qasm" />

`qasm()`

Return a default OpenQASM string for the instruction.

Derived instructions may override this to print in a different format (e.g. measure q\[0] -> c\[0];).

### repeat

<span id="qiskit.circuit.library.CU1Gate.repeat" />

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

<span id="qiskit.circuit.library.CU1Gate.reverse_ops" />

`reverse_ops()`

For a composite instruction, reverse the order of sub-instructions.

This is done by recursively reversing all sub-instructions. It does not invert any gate.

**Returns**

**a new instruction with**

sub-instructions reversed.

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

### to\_matrix

<span id="qiskit.circuit.library.CU1Gate.to_matrix" />

`to_matrix()`

Return a numpy.array for the CU1 gate.

### unit

<span id="qiskit.circuit.library.CU1Gate.unit" />

`property unit`

Get the time unit of duration.

### validate\_parameter

<span id="qiskit.circuit.library.CU1Gate.validate_parameter" />

`validate_parameter(parameter)`

Gate parameters should be int, float, or ParameterExpression

