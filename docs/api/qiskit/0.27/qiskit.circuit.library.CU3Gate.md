---
title: CU3Gate
description: API reference for qiskit.circuit.library.CU3Gate
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.CU3Gate
---

# qiskit.circuit.library.CU3Gate

<span id="qiskit.circuit.library.CU3Gate" />

`CU3Gate(theta, phi, lam, label=None, ctrl_state=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.17/qiskit/circuit/library/standard_gates/u3.py "view source code")

Controlled-U3 gate (3-parameter two-qubit gate).

This is a controlled version of the U3 gate (generic single qubit rotation). It is restricted to 3 parameters, and so cannot cover generic two-qubit controlled gates).

**Circuit symbol:**

```python
q_0: ──────■──────
     ┌─────┴─────┐
q_1: ┤ U3(ϴ,φ,λ) ├
     └───────────┘
```

**Matrix representation:**

$$
 \begin{align}\begin{aligned}\newcommand{\th}{\frac{\theta}{2}}\\\begin{split}CU3(\theta, \phi, \lambda)\ q_0, q_1 =
    I \otimes |0\rangle\langle 0| +
    U3(\theta,\phi,\lambda) \otimes |1\rangle\langle 1| =
    \begin{pmatrix}
        1 & 0                   & 0 & 0 \\
        0 & \cos(\th)           & 0 & -e^{i\lambda}\sin(\th) \\
        0 & 0                   & 1 & 0 \\
        0 & e^{i\phi}\sin(\th)  & 0 & e^{i(\phi+\lambda)}\cos(\th)
    \end{pmatrix}\end{split}\end{aligned}\end{align} 
$$

<Admonition title="Note" type="note">
  In Qiskit’s convention, higher qubit indices are more significant (little endian convention). In many textbooks, controlled gates are presented with the assumption of more significant qubits as control, which in our case would be q\_1. Thus a textbook matrix for this gate will be:

  ```python
       ┌───────────┐
  q_0: ┤ U3(ϴ,φ,λ) ├
       └─────┬─────┘
  q_1: ──────■──────
  ```

  $$
  \begin{split}CU3(\theta, \phi, \lambda)\ q_1, q_0 =
      |0\rangle\langle 0| \otimes I +
      |1\rangle\langle 1| \otimes U3(\theta,\phi,\lambda) =
      \begin{pmatrix}
          1 & 0   & 0                  & 0 \\
          0 & 1   & 0                  & 0 \\
          0 & 0   & \cos(\th)          & -e^{i\lambda}\sin(\th) \\
          0 & 0   & e^{i\phi}\sin(\th) & e^{i(\phi+\lambda)}\cos(\th)
      \end{pmatrix}\end{split}
  $$
</Admonition>

Create new CU3 gate.

### \_\_init\_\_

<span id="qiskit.circuit.library.CU3Gate.__init__" />

`__init__(theta, phi, lam, label=None, ctrl_state=None)`

Create new CU3 gate.

## Methods

|                                                                                                                                                 |                                                                          |
| ----------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| [`__init__`](#qiskit.circuit.library.CU3Gate.__init__ "qiskit.circuit.library.CU3Gate.__init__")(theta, phi, lam\[, label, ctrl\_state])        | Create new CU3 gate.                                                     |
| [`add_decomposition`](#qiskit.circuit.library.CU3Gate.add_decomposition "qiskit.circuit.library.CU3Gate.add_decomposition")(decomposition)      | Add a decomposition of the instruction to the SessionEquivalenceLibrary. |
| [`assemble`](#qiskit.circuit.library.CU3Gate.assemble "qiskit.circuit.library.CU3Gate.assemble")()                                              | Assemble a QasmQobjInstruction                                           |
| [`broadcast_arguments`](#qiskit.circuit.library.CU3Gate.broadcast_arguments "qiskit.circuit.library.CU3Gate.broadcast_arguments")(qargs, cargs) | Validation and handling of the arguments and its relationship.           |
| [`c_if`](#qiskit.circuit.library.CU3Gate.c_if "qiskit.circuit.library.CU3Gate.c_if")(classical, val)                                            | Add classical condition on register classical and value val.             |
| [`control`](#qiskit.circuit.library.CU3Gate.control "qiskit.circuit.library.CU3Gate.control")(\[num\_ctrl\_qubits, label, ctrl\_state])         | Return controlled version of gate.                                       |
| [`copy`](#qiskit.circuit.library.CU3Gate.copy "qiskit.circuit.library.CU3Gate.copy")(\[name])                                                   | Copy of the instruction.                                                 |
| [`inverse`](#qiskit.circuit.library.CU3Gate.inverse "qiskit.circuit.library.CU3Gate.inverse")()                                                 | Return inverted CU3 gate.                                                |
| [`is_parameterized`](#qiskit.circuit.library.CU3Gate.is_parameterized "qiskit.circuit.library.CU3Gate.is_parameterized")()                      | Return True .IFF.                                                        |
| [`mirror`](#qiskit.circuit.library.CU3Gate.mirror "qiskit.circuit.library.CU3Gate.mirror")()                                                    | DEPRECATED: use instruction.reverse\_ops().                              |
| [`power`](#qiskit.circuit.library.CU3Gate.power "qiskit.circuit.library.CU3Gate.power")(exponent)                                               | Creates a unitary gate as gate^exponent.                                 |
| [`qasm`](#qiskit.circuit.library.CU3Gate.qasm "qiskit.circuit.library.CU3Gate.qasm")()                                                          | Return a default OpenQASM string for the instruction.                    |
| [`repeat`](#qiskit.circuit.library.CU3Gate.repeat "qiskit.circuit.library.CU3Gate.repeat")(n)                                                   | Creates an instruction with gate repeated n amount of times.             |
| [`reverse_ops`](#qiskit.circuit.library.CU3Gate.reverse_ops "qiskit.circuit.library.CU3Gate.reverse_ops")()                                     | For a composite instruction, reverse the order of sub-instructions.      |
| [`soft_compare`](#qiskit.circuit.library.CU3Gate.soft_compare "qiskit.circuit.library.CU3Gate.soft_compare")(other)                             | Soft comparison between gates.                                           |
| [`to_matrix`](#qiskit.circuit.library.CU3Gate.to_matrix "qiskit.circuit.library.CU3Gate.to_matrix")()                                           | Return a Numpy.array for the gate unitary matrix.                        |
| [`validate_parameter`](#qiskit.circuit.library.CU3Gate.validate_parameter "qiskit.circuit.library.CU3Gate.validate_parameter")(parameter)       | Gate parameters should be int, float, or ParameterExpression             |

## Attributes

|                                                                                                                       |                                                                               |
| --------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| [`ctrl_state`](#qiskit.circuit.library.CU3Gate.ctrl_state "qiskit.circuit.library.CU3Gate.ctrl_state")                | Return the control state of the gate as a decimal integer.                    |
| [`decompositions`](#qiskit.circuit.library.CU3Gate.decompositions "qiskit.circuit.library.CU3Gate.decompositions")    | Get the decompositions of the instruction from the SessionEquivalenceLibrary. |
| [`definition`](#qiskit.circuit.library.CU3Gate.definition "qiskit.circuit.library.CU3Gate.definition")                | Return definition in terms of other basic gates.                              |
| [`duration`](#qiskit.circuit.library.CU3Gate.duration "qiskit.circuit.library.CU3Gate.duration")                      | Get the duration.                                                             |
| [`label`](#qiskit.circuit.library.CU3Gate.label "qiskit.circuit.library.CU3Gate.label")                               | Return gate label                                                             |
| [`name`](#qiskit.circuit.library.CU3Gate.name "qiskit.circuit.library.CU3Gate.name")                                  | Get name of gate.                                                             |
| [`num_ctrl_qubits`](#qiskit.circuit.library.CU3Gate.num_ctrl_qubits "qiskit.circuit.library.CU3Gate.num_ctrl_qubits") | Get number of control qubits.                                                 |
| [`params`](#qiskit.circuit.library.CU3Gate.params "qiskit.circuit.library.CU3Gate.params")                            | Get parameters from base\_gate.                                               |
| [`unit`](#qiskit.circuit.library.CU3Gate.unit "qiskit.circuit.library.CU3Gate.unit")                                  | Get the time unit of duration.                                                |

### add\_decomposition

<span id="qiskit.circuit.library.CU3Gate.add_decomposition" />

`add_decomposition(decomposition)`

Add a decomposition of the instruction to the SessionEquivalenceLibrary.

### assemble

<span id="qiskit.circuit.library.CU3Gate.assemble" />

`assemble()`

Assemble a QasmQobjInstruction

**Return type**

`Instruction`

### broadcast\_arguments

<span id="qiskit.circuit.library.CU3Gate.broadcast_arguments" />

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

<span id="qiskit.circuit.library.CU3Gate.c_if" />

`c_if(classical, val)`

Add classical condition on register classical and value val.

### control

<span id="qiskit.circuit.library.CU3Gate.control" />

`control(num_ctrl_qubits=1, label=None, ctrl_state=None)`

Return controlled version of gate. See [`ControlledGate`](qiskit.circuit.ControlledGate "qiskit.circuit.ControlledGate") for usage.

**Parameters**

*   **num\_ctrl\_qubits** (`Optional`\[`int`]) – number of controls to add to gate (default=1)
*   **label** (`Optional`\[`str`]) – optional gate label
*   **ctrl\_state** (`Union`\[`int`, `str`, `None`]) – The control state in decimal or as a bitstring (e.g. ‘111’). If None, use 2\*\*num\_ctrl\_qubits-1.

**Returns**

Controlled version of gate. This default algorithm uses num\_ctrl\_qubits-1 ancillae qubits so returns a gate of size num\_qubits + 2\*num\_ctrl\_qubits - 1.

**Return type**

[qiskit.circuit.ControlledGate](qiskit.circuit.ControlledGate "qiskit.circuit.ControlledGate")

**Raises**

**QiskitError** – unrecognized mode or invalid ctrl\_state

### copy

<span id="qiskit.circuit.library.CU3Gate.copy" />

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

<span id="qiskit.circuit.library.CU3Gate.ctrl_state" />

`property ctrl_state`

Return the control state of the gate as a decimal integer.

**Return type**

`int`

### decompositions

<span id="qiskit.circuit.library.CU3Gate.decompositions" />

`property decompositions`

Get the decompositions of the instruction from the SessionEquivalenceLibrary.

### definition

<span id="qiskit.circuit.library.CU3Gate.definition" />

`property definition`

Return definition in terms of other basic gates. If the gate has open controls, as determined from self.ctrl\_state, the returned definition is conjugated with X without changing the internal \_definition.

**Return type**

`List`

### duration

<span id="qiskit.circuit.library.CU3Gate.duration" />

`property duration`

Get the duration.

### inverse

<span id="qiskit.circuit.library.CU3Gate.inverse" />

`inverse()`

Return inverted CU3 gate.

$CU3(\theta,\phi,\lambda)^{\dagger} =CU3(-\theta,-\phi,-\lambda)$)

### is\_parameterized

<span id="qiskit.circuit.library.CU3Gate.is_parameterized" />

`is_parameterized()`

Return True .IFF. instruction is parameterized else False

### label

<span id="qiskit.circuit.library.CU3Gate.label" />

`property label`

Return gate label

**Return type**

`str`

### mirror

<span id="qiskit.circuit.library.CU3Gate.mirror" />

`mirror()`

DEPRECATED: use instruction.reverse\_ops().

**Returns**

**a new instruction with sub-instructions**

reversed.

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

### name

<span id="qiskit.circuit.library.CU3Gate.name" />

`property name`

Get name of gate. If the gate has open controls the gate name will become:

> \<original\_name\_o\<ctrl\_state>

where \<original\_name> is the gate name for the default case of closed control qubits and \<ctrl\_state> is the integer value of the control state for the gate.

**Return type**

`str`

### num\_ctrl\_qubits

<span id="qiskit.circuit.library.CU3Gate.num_ctrl_qubits" />

`property num_ctrl_qubits`

Get number of control qubits.

**Returns**

The number of control qubits for the gate.

**Return type**

int

### params

<span id="qiskit.circuit.library.CU3Gate.params" />

`property params`

Get parameters from base\_gate.

**Returns**

List of gate parameters.

**Return type**

list

**Raises**

**CircuitError** – Controlled gate does not define a base gate

### power

<span id="qiskit.circuit.library.CU3Gate.power" />

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

<span id="qiskit.circuit.library.CU3Gate.qasm" />

`qasm()`

Return a default OpenQASM string for the instruction.

Derived instructions may override this to print in a different format (e.g. measure q\[0] -> c\[0];).

### repeat

<span id="qiskit.circuit.library.CU3Gate.repeat" />

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

<span id="qiskit.circuit.library.CU3Gate.reverse_ops" />

`reverse_ops()`

For a composite instruction, reverse the order of sub-instructions.

This is done by recursively reversing all sub-instructions. It does not invert any gate.

**Returns**

**a new instruction with**

sub-instructions reversed.

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

### soft\_compare

<span id="qiskit.circuit.library.CU3Gate.soft_compare" />

`soft_compare(other)`

Soft comparison between gates. Their names, number of qubits, and classical bit numbers must match. The number of parameters must match. Each parameter is compared. If one is a ParameterExpression then it is not taken into account.

**Parameters**

**other** (*instruction*) – other instruction.

**Returns**

are self and other equal up to parameter expressions.

**Return type**

bool

### to\_matrix

<span id="qiskit.circuit.library.CU3Gate.to_matrix" />

`to_matrix()`

Return a Numpy.array for the gate unitary matrix.

**Returns**

if the Gate subclass has a matrix definition.

**Return type**

np.ndarray

**Raises**

**CircuitError** – If a Gate subclass does not implement this method an exception will be raised when this base class method is called.

### unit

<span id="qiskit.circuit.library.CU3Gate.unit" />

`property unit`

Get the time unit of duration.

### validate\_parameter

<span id="qiskit.circuit.library.CU3Gate.validate_parameter" />

`validate_parameter(parameter)`

Gate parameters should be int, float, or ParameterExpression

