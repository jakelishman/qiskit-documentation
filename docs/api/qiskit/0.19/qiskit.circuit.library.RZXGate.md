---
title: RZXGate
description: API reference for qiskit.circuit.library.RZXGate
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.RZXGate
---

# RZXGate

<span id="qiskit.circuit.library.RZXGate" />

`RZXGate(theta)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/circuit/library/standard_gates/rzx.py "view source code")

A parameteric 2-qubit $Z \otimes X$ interaction (rotation about ZX).

This gate is maximally entangling at $\theta = \pi/2$.

The cross-resonance gate (CR) for superconducting qubits implements a ZX interaction (however other terms are also present in an experiment).

**Circuit Symbol:**

```python
     ┌─────────┐
q_0: ┤0        ├
     │  Rzx(θ) │
q_1: ┤1        ├
     └─────────┘
```

**Matrix Representation:**

$$
 \begin{align}\begin{aligned}\newcommand{\th}{\frac{\theta}{2}}\\\begin{split}R_{ZX}(\theta)\ q_0, q_1 = exp(-i \frac{\theta}{2} X{\otimes}Z) =
    \begin{pmatrix}
        \cos(\th)   & 0          & -i\sin(\th)  & 0          \\
        0           & \cos(\th)  & 0            & i\sin(\th) \\
        -i\sin(\th) & 0          & \cos(\th)    & 0          \\
        0           & i\sin(\th) & 0            & \cos(\th)
    \end{pmatrix}\end{split}\end{aligned}\end{align} 
$$

<Admonition title="Note" type="note">
  In Qiskit’s convention, higher qubit indices are more significant (little endian convention). In the above example we apply the gate on (q\_0, q\_1) which results in the $X \otimes Z$ tensor order. Instead, if we apply it on (q\_1, q\_0), the matrix will be $Z \otimes X$:

  ```python
       ┌─────────┐
  q_0: ┤1        ├
       │  Rzx(θ) │
  q_1: ┤0        ├
       └─────────┘
  ```

  $$
   \begin{align}\begin{aligned}\newcommand{\th}{\frac{\theta}{2}}\\\begin{split}R_{ZX}(\theta)\ q_1, q_0 = exp(-i \frac{\theta}{2} Z{\otimes}X) =
      \begin{pmatrix}
          \cos(\th)   & -i\sin(\th) & 0           & 0          \\
          -i\sin(\th) & \cos(\th)   & 0           & 0          \\
          0           & 0           & \cos(\th)   & i\sin(\th) \\
          0           & 0           & i\sin(\th)  & \cos(\th)
      \end{pmatrix}\end{split}\end{aligned}\end{align} 
  $$

  This is a direct sum of RX rotations, so this gate is equivalent to a uniformly controlled (multiplexed) RX gate:

  $$
  \begin{split}R_{ZX}(\theta)\ q_1, q_0 =
      \begin{pmatrix}
          RX(\theta) & 0 \\
          0 & RX(-\theta)
      \end{pmatrix}\end{split}
  $$
</Admonition>

**Examples:**

> $$
> R_{ZX}(\theta = 0) = I
> $$
>
> $$
> R_{ZX}(\theta = 2\pi) = -I
> $$
>
> $$
> R_{ZX}(\theta = \pi) = -i Z \otimes X
> $$
>
> $$
> \begin{split}RZX(\theta = \frac{\pi}{2}) = \frac{1}{\sqrt{2}}
>                         \begin{pmatrix}
>                             1  & 0 & -i & 0 \\
>                             0  & 1 & 0  & i \\
>                             -i & 0 & 1  & 0 \\
>                             0  & i & 0  & 1
>                         \end{pmatrix}\end{split}
> $$

Create new RZX gate.

## Attributes

### decompositions

Get the decompositions of the instruction from the SessionEquivalenceLibrary.

### definition

Return definition in terms of other basic gates.

### label

<span id="qiskit.circuit.library.RZXGate.label" />

`str`

Return gate label

**Return type**

`str`

### params

return instruction params.

## Methods

### add\_decomposition

<span id="qiskit.circuit.library.RZXGate.add_decomposition" />

`RZXGate.add_decomposition(decomposition)`

Add a decomposition of the instruction to the SessionEquivalenceLibrary.

### assemble

<span id="qiskit.circuit.library.RZXGate.assemble" />

`RZXGate.assemble()`

Assemble a QasmQobjInstruction

**Return type**

[`Instruction`](qiskit.circuit.Instruction "qiskit.circuit.instruction.Instruction")

### broadcast\_arguments

<span id="qiskit.circuit.library.RZXGate.broadcast_arguments" />

`RZXGate.broadcast_arguments(qargs, cargs)`

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

<span id="qiskit.circuit.library.RZXGate.c_if" />

`RZXGate.c_if(classical, val)`

Add classical condition on register classical and value val.

### control

<span id="qiskit.circuit.library.RZXGate.control" />

`RZXGate.control(num_ctrl_qubits=1, label=None, ctrl_state=None)`

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

<span id="qiskit.circuit.library.RZXGate.copy" />

`RZXGate.copy(name=None)`

Copy of the instruction.

**Parameters**

**name** (*str*) – name to be given to the copied circuit, if None then the name stays the same.

**Returns**

**a copy of the current instruction, with the name**

updated if it was provided

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

### inverse

<span id="qiskit.circuit.library.RZXGate.inverse" />

`RZXGate.inverse()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/circuit/library/standard_gates/rzx.py "view source code")

Return inverse RZX gate (i.e. with the negative rotation angle).

### is\_parameterized

<span id="qiskit.circuit.library.RZXGate.is_parameterized" />

`RZXGate.is_parameterized()`

Return True .IFF. instruction is parameterized else False

### mirror

<span id="qiskit.circuit.library.RZXGate.mirror" />

`RZXGate.mirror()`

For a composite instruction, reverse the order of sub-gates.

This is done by recursively mirroring all sub-instructions. It does not invert any gate.

**Returns**

a fresh gate with sub-gates reversed

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

### power

<span id="qiskit.circuit.library.RZXGate.power" />

`RZXGate.power(exponent)`

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

<span id="qiskit.circuit.library.RZXGate.qasm" />

`RZXGate.qasm()`

Return a default OpenQASM string for the instruction.

Derived instructions may override this to print in a different format (e.g. measure q\[0] -> c\[0];).

### repeat

<span id="qiskit.circuit.library.RZXGate.repeat" />

`RZXGate.repeat(n)`

Creates an instruction with gate repeated n amount of times.

**Parameters**

**n** (*int*) – Number of times to repeat the instruction

**Returns**

Containing the definition.

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

**Raises**

**CircuitError** – If n \< 1.

### to\_matrix

<span id="qiskit.circuit.library.RZXGate.to_matrix" />

`RZXGate.to_matrix()`

Return a Numpy.array for the gate unitary matrix.

**Raises**

**CircuitError** – If a Gate subclass does not implement this method an exception will be raised when this base class method is called.

**Return type**

`ndarray`

