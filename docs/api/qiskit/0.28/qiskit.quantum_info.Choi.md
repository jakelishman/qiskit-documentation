---
title: Choi
description: API reference for qiskit.quantum_info.Choi
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.quantum_info.Choi
---

# qiskit.quantum\_info.Choi

<span id="qiskit.quantum_info.Choi" />

`Choi(data, input_dims=None, output_dims=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/quantum_info/operators/channel/choi.py "view source code")

Choi-matrix representation of a Quantum Channel.

The Choi-matrix representation of a quantum channel $\mathcal{E}$ is a matrix

$$
\Lambda = \sum_{i,j} |i\rangle\!\langle j|\otimes
            \mathcal{E}\left(|i\rangle\!\langle j|\right)
$$

Evolution of a [`DensityMatrix`](qiskit.quantum_info.DensityMatrix "qiskit.quantum_info.DensityMatrix") $\rho$ with respect to the Choi-matrix is given by

$$
\mathcal{E}(\rho) = \mbox{Tr}_{1}\left[\Lambda
                    (\rho^T \otimes \mathbb{I})\right]
$$

where $\mbox{Tr}_1$ is the [`partial_trace()`](qiskit.quantum_info.partial_trace "qiskit.quantum_info.partial_trace") over subsystem 1.

See reference \[1] for further details.

## References

1.  C.J. Wood, J.D. Biamonte, D.G. Cory, *Tensor networks and graphical calculus for open quantum systems*, Quant. Inf. Comp. 15, 0579-0811 (2015). [arXiv:1111.6950 \[quant-ph\]](https://arxiv.org/abs/1111.6950)

Initialize a quantum channel Choi matrix operator.

**Parameters**

*   \*\*(\*\***QuantumCircuit or** (*data*) – Instruction or BaseOperator or matrix): data to initialize superoperator.
*   **input\_dims** (*tuple*) – the input subsystem dimensions. \[Default: None]
*   **output\_dims** (*tuple*) – the output subsystem dimensions. \[Default: None]

**Raises**

**QiskitError** – if input data cannot be initialized as a Choi matrix.

**Additional Information:**

If the input or output dimensions are None, they will be automatically determined from the input data. If the input data is a Numpy array of shape (4\*\*N, 4\*\*N) qubit systems will be used. If the input operator is not an N-qubit operator, it will assign a single subsystem with dimension specified by the shape of the input.

### \_\_init\_\_

<span id="qiskit.quantum_info.Choi.__init__" />

`__init__(data, input_dims=None, output_dims=None)`

Initialize a quantum channel Choi matrix operator.

**Parameters**

*   \*\*(\*\***QuantumCircuit or** (*data*) – Instruction or BaseOperator or matrix): data to initialize superoperator.
*   **input\_dims** (*tuple*) – the input subsystem dimensions. \[Default: None]
*   **output\_dims** (*tuple*) – the output subsystem dimensions. \[Default: None]

**Raises**

**QiskitError** – if input data cannot be initialized as a Choi matrix.

**Additional Information:**

If the input or output dimensions are None, they will be automatically determined from the input data. If the input data is a Numpy array of shape (4\*\*N, 4\*\*N) qubit systems will be used. If the input operator is not an N-qubit operator, it will assign a single subsystem with dimension specified by the shape of the input.

## Methods

|                                                                                                                              |                                                                            |
| ---------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| [`__init__`](#qiskit.quantum_info.Choi.__init__ "qiskit.quantum_info.Choi.__init__")(data\[, input\_dims, output\_dims])     | Initialize a quantum channel Choi matrix operator.                         |
| [`adjoint`](#qiskit.quantum_info.Choi.adjoint "qiskit.quantum_info.Choi.adjoint")()                                          | Return the adjoint quantum channel.                                        |
| [`compose`](#qiskit.quantum_info.Choi.compose "qiskit.quantum_info.Choi.compose")(other\[, qargs, front])                    | Return the operator composition with another Choi.                         |
| [`conjugate`](#qiskit.quantum_info.Choi.conjugate "qiskit.quantum_info.Choi.conjugate")()                                    | Return the conjugate quantum channel.                                      |
| [`copy`](#qiskit.quantum_info.Choi.copy "qiskit.quantum_info.Choi.copy")()                                                   | Make a deep copy of current operator.                                      |
| [`dot`](#qiskit.quantum_info.Choi.dot "qiskit.quantum_info.Choi.dot")(other\[, qargs])                                       | Return the right multiplied operator self \* other.                        |
| [`expand`](#qiskit.quantum_info.Choi.expand "qiskit.quantum_info.Choi.expand")(other)                                        | Return the reverse-order tensor product with another Choi.                 |
| [`input_dims`](#qiskit.quantum_info.Choi.input_dims "qiskit.quantum_info.Choi.input_dims")(\[qargs])                         | Return tuple of input dimension for specified subsystems.                  |
| [`is_cp`](#qiskit.quantum_info.Choi.is_cp "qiskit.quantum_info.Choi.is_cp")(\[atol, rtol])                                   | Test if Choi-matrix is completely-positive (CP)                            |
| [`is_cptp`](#qiskit.quantum_info.Choi.is_cptp "qiskit.quantum_info.Choi.is_cptp")(\[atol, rtol])                             | Return True if completely-positive trace-preserving (CPTP).                |
| [`is_tp`](#qiskit.quantum_info.Choi.is_tp "qiskit.quantum_info.Choi.is_tp")(\[atol, rtol])                                   | Test if a channel is trace-preserving (TP)                                 |
| [`is_unitary`](#qiskit.quantum_info.Choi.is_unitary "qiskit.quantum_info.Choi.is_unitary")(\[atol, rtol])                    | Return True if QuantumChannel is a unitary channel.                        |
| [`output_dims`](#qiskit.quantum_info.Choi.output_dims "qiskit.quantum_info.Choi.output_dims")(\[qargs])                      | Return tuple of output dimension for specified subsystems.                 |
| [`power`](#qiskit.quantum_info.Choi.power "qiskit.quantum_info.Choi.power")(n)                                               | Return the power of the quantum channel.                                   |
| [`reshape`](#qiskit.quantum_info.Choi.reshape "qiskit.quantum_info.Choi.reshape")(\[input\_dims, output\_dims, num\_qubits]) | Return a shallow copy with reshaped input and output subsystem dimensions. |
| [`tensor`](#qiskit.quantum_info.Choi.tensor "qiskit.quantum_info.Choi.tensor")(other)                                        | Return the tensor product with another Choi.                               |
| [`to_instruction`](#qiskit.quantum_info.Choi.to_instruction "qiskit.quantum_info.Choi.to_instruction")()                     | Convert to a Kraus or UnitaryGate circuit instruction.                     |
| [`to_operator`](#qiskit.quantum_info.Choi.to_operator "qiskit.quantum_info.Choi.to_operator")()                              | Try to convert channel to a unitary representation Operator.               |
| [`transpose`](#qiskit.quantum_info.Choi.transpose "qiskit.quantum_info.Choi.transpose")()                                    | Return the transpose quantum channel.                                      |

## Attributes

|                                                                                            |                                                                      |
| ------------------------------------------------------------------------------------------ | -------------------------------------------------------------------- |
| [`atol`](#qiskit.quantum_info.Choi.atol "qiskit.quantum_info.Choi.atol")                   | Default absolute tolerance parameter for float comparisons.          |
| [`data`](#qiskit.quantum_info.Choi.data "qiskit.quantum_info.Choi.data")                   | Return data.                                                         |
| [`dim`](#qiskit.quantum_info.Choi.dim "qiskit.quantum_info.Choi.dim")                      | Return tuple (input\_shape, output\_shape).                          |
| [`num_qubits`](#qiskit.quantum_info.Choi.num_qubits "qiskit.quantum_info.Choi.num_qubits") | Return the number of qubits if a N-qubit operator or None otherwise. |
| [`qargs`](#qiskit.quantum_info.Choi.qargs "qiskit.quantum_info.Choi.qargs")                | Return the qargs for the operator.                                   |
| [`rtol`](#qiskit.quantum_info.Choi.rtol "qiskit.quantum_info.Choi.rtol")                   | Default relative tolerance parameter for float comparisons.          |
| [`settings`](#qiskit.quantum_info.Choi.settings "qiskit.quantum_info.Choi.settings")       | Return operator settings.                                            |

### adjoint

<span id="qiskit.quantum_info.Choi.adjoint" />

`adjoint()`

Return the adjoint quantum channel.

<Admonition title="Note" type="note">
  This is equivalent to the matrix Hermitian conjugate in the [`SuperOp`](qiskit.quantum_info.SuperOp "qiskit.quantum_info.SuperOp") representation ie. for a channel $\mathcal{E}$, the SuperOp of the adjoint channel $\mathcal{{E}}^\dagger$ is $S_{\mathcal{E}^\dagger} = S_{\mathcal{E}}^\dagger$.
</Admonition>

### atol

<span id="qiskit.quantum_info.Choi.atol" />

`property atol`

Default absolute tolerance parameter for float comparisons.

### compose

<span id="qiskit.quantum_info.Choi.compose" />

`compose(other, qargs=None, front=False)`

Return the operator composition with another Choi.

**Parameters**

*   **other** ([*Choi*](#qiskit.quantum_info.Choi "qiskit.quantum_info.Choi")) – a Choi object.
*   **qargs** (*list or None*) – Optional, a list of subsystem positions to apply other on. If None apply on all subsystems (default: None).
*   **front** (*bool*) – If True compose using right operator multiplication, instead of left multiplication \[default: False].

**Returns**

The composed Choi.

**Return type**

[Choi](#qiskit.quantum_info.Choi "qiskit.quantum_info.Choi")

**Raises**

**QiskitError** – if other cannot be converted to an operator, or has incompatible dimensions for specified subsystems.

<Admonition title="Note" type="note">
  Composition (`&`) by default is defined as left matrix multiplication for matrix operators, while [`dot()`](#qiskit.quantum_info.Choi.dot "qiskit.quantum_info.Choi.dot") is defined as right matrix multiplication. That is that `A & B == A.compose(B)` is equivalent to `B.dot(A)` when `A` and `B` are of the same type.

  Setting the `front=True` kwarg changes this to right matrix multiplication and is equivalent to the [`dot()`](#qiskit.quantum_info.Choi.dot "qiskit.quantum_info.Choi.dot") method `A.dot(B) == A.compose(B, front=True)`.
</Admonition>

### conjugate

<span id="qiskit.quantum_info.Choi.conjugate" />

`conjugate()`

Return the conjugate quantum channel.

<Admonition title="Note" type="note">
  This is equivalent to the matrix complex conjugate in the [`SuperOp`](qiskit.quantum_info.SuperOp "qiskit.quantum_info.SuperOp") representation ie. for a channel $\mathcal{E}$, the SuperOp of the conjugate channel $\overline{{\mathcal{{E}}}}$ is $S_{\overline{\mathcal{E}^\dagger}} = \overline{S_{\mathcal{E}}}$.
</Admonition>

### copy

<span id="qiskit.quantum_info.Choi.copy" />

`copy()`

Make a deep copy of current operator.

### data

<span id="qiskit.quantum_info.Choi.data" />

`property data`

Return data.

### dim

<span id="qiskit.quantum_info.Choi.dim" />

`property dim`

Return tuple (input\_shape, output\_shape).

### dot

<span id="qiskit.quantum_info.Choi.dot" />

`dot(other, qargs=None)`

Return the right multiplied operator self \* other.

**Parameters**

*   **other** ([*Operator*](qiskit.quantum_info.Operator "qiskit.quantum_info.Operator")) – an operator object.
*   **qargs** (*list or None*) – Optional, a list of subsystem positions to apply other on. If None apply on all subsystems (default: None).

**Returns**

The right matrix multiplied Operator.

**Return type**

[Operator](qiskit.quantum_info.Operator "qiskit.quantum_info.Operator")

### expand

<span id="qiskit.quantum_info.Choi.expand" />

`expand(other)`

Return the reverse-order tensor product with another Choi.

**Parameters**

**other** ([*Choi*](#qiskit.quantum_info.Choi "qiskit.quantum_info.Choi")) – a Choi object.

**Returns**

**the tensor product $b \otimes a$, where $a$**

is the current Choi, and $b$ is the other Choi.

**Return type**

[Choi](#qiskit.quantum_info.Choi "qiskit.quantum_info.Choi")

### input\_dims

<span id="qiskit.quantum_info.Choi.input_dims" />

`input_dims(qargs=None)`

Return tuple of input dimension for specified subsystems.

### is\_cp

<span id="qiskit.quantum_info.Choi.is_cp" />

`is_cp(atol=None, rtol=None)`

Test if Choi-matrix is completely-positive (CP)

### is\_cptp

<span id="qiskit.quantum_info.Choi.is_cptp" />

`is_cptp(atol=None, rtol=None)`

Return True if completely-positive trace-preserving (CPTP).

### is\_tp

<span id="qiskit.quantum_info.Choi.is_tp" />

`is_tp(atol=None, rtol=None)`

Test if a channel is trace-preserving (TP)

### is\_unitary

<span id="qiskit.quantum_info.Choi.is_unitary" />

`is_unitary(atol=None, rtol=None)`

Return True if QuantumChannel is a unitary channel.

### num\_qubits

<span id="qiskit.quantum_info.Choi.num_qubits" />

`property num_qubits`

Return the number of qubits if a N-qubit operator or None otherwise.

### output\_dims

<span id="qiskit.quantum_info.Choi.output_dims" />

`output_dims(qargs=None)`

Return tuple of output dimension for specified subsystems.

### power

<span id="qiskit.quantum_info.Choi.power" />

`power(n)`

Return the power of the quantum channel.

**Parameters**

**n** (*float*) – the power exponent.

**Returns**

the channel $\mathcal{{E}} ^n$.

**Return type**

[SuperOp](qiskit.quantum_info.SuperOp "qiskit.quantum_info.SuperOp")

**Raises**

**QiskitError** – if the input and output dimensions of the SuperOp are not equal.

<Admonition title="Note" type="note">
  For non-positive or non-integer exponents the power is defined as the matrix power of the [`SuperOp`](qiskit.quantum_info.SuperOp "qiskit.quantum_info.SuperOp") representation ie. for a channel $\mathcal{{E}}$, the SuperOp of the powered channel $\mathcal{{E}}^\n$ is $S_{{\mathcal{{E}}^n}} = S_{{\mathcal{{E}}}}^n$.
</Admonition>

### qargs

<span id="qiskit.quantum_info.Choi.qargs" />

`property qargs`

Return the qargs for the operator.

### reshape

<span id="qiskit.quantum_info.Choi.reshape" />

`reshape(input_dims=None, output_dims=None, num_qubits=None)`

Return a shallow copy with reshaped input and output subsystem dimensions.

**Parameters**

*   **input\_dims** (*None or tuple*) – new subsystem input dimensions. If None the original input dims will be preserved \[Default: None].
*   **output\_dims** (*None or tuple*) – new subsystem output dimensions. If None the original output dims will be preserved \[Default: None].
*   **num\_qubits** (*None or int*) – reshape to an N-qubit operator \[Default: None].

**Returns**

returns self with reshaped input and output dimensions.

**Return type**

BaseOperator

**Raises**

**QiskitError** – if combined size of all subsystem input dimension or subsystem output dimensions is not constant.

### rtol

<span id="qiskit.quantum_info.Choi.rtol" />

`property rtol`

Default relative tolerance parameter for float comparisons.

### settings

<span id="qiskit.quantum_info.Choi.settings" />

`property settings`

Return operator settings.

### tensor

<span id="qiskit.quantum_info.Choi.tensor" />

`tensor(other)`

Return the tensor product with another Choi.

**Parameters**

**other** ([*Choi*](#qiskit.quantum_info.Choi "qiskit.quantum_info.Choi")) – a Choi object.

**Returns**

**the tensor product $a \otimes b$, where $a$**

is the current Choi, and $b$ is the other Choi.

**Return type**

[Choi](#qiskit.quantum_info.Choi "qiskit.quantum_info.Choi")

<Admonition title="Note" type="note">
  The tensor product can be obtained using the `^` binary operator. Hence `a.tensor(b)` is equivalent to `a ^ b`.
</Admonition>

### to\_instruction

<span id="qiskit.quantum_info.Choi.to_instruction" />

`to_instruction()`

Convert to a Kraus or UnitaryGate circuit instruction.

If the channel is unitary it will be added as a unitary gate, otherwise it will be added as a kraus simulator instruction.

**Returns**

A kraus instruction for the channel.

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

**Raises**

**QiskitError** – if input data is not an N-qubit CPTP quantum channel.

### to\_operator

<span id="qiskit.quantum_info.Choi.to_operator" />

`to_operator()`

Try to convert channel to a unitary representation Operator.

### transpose

<span id="qiskit.quantum_info.Choi.transpose" />

`transpose()`

Return the transpose quantum channel.

<Admonition title="Note" type="note">
  This is equivalent to the matrix transpose in the [`SuperOp`](qiskit.quantum_info.SuperOp "qiskit.quantum_info.SuperOp") representation, ie. for a channel $\mathcal{E}$, the SuperOp of the transpose channel $\mathcal{{E}}^T$ is $S_{mathcal{E}^T} = S_{\mathcal{E}}^T$.
</Admonition>

