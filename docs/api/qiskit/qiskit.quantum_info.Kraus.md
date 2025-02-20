---
title: Kraus
description: API reference for qiskit.quantum_info.Kraus
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.quantum_info.Kraus
---

# Kraus

<span id="qiskit.quantum_info.Kraus" />

`qiskit.quantum_info.Kraus(data, input_dims=None, output_dims=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/quantum_info/operators/channel/kraus.py "view source code")

Bases: `QuantumChannel`

Kraus representation of a quantum channel.

For a quantum channel $\mathcal{E}$, the Kraus representation is given by a set of matrices $[A_0,...,A_{K-1}]$ such that the evolution of a [`DensityMatrix`](qiskit.quantum_info.DensityMatrix "qiskit.quantum_info.DensityMatrix") $\rho$ is given by

$$
\mathcal{E}(\rho) = \sum_{i=0}^{K-1} A_i \rho A_i^\dagger
$$

A general operator map $\mathcal{G}$ can also be written using the generalized Kraus representation which is given by two sets of matrices $[A_0,...,A_{K-1}]$, $[B_0,...,A_{B-1}]$ such that

$$
\mathcal{G}(\rho) = \sum_{i=0}^{K-1} A_i \rho B_i^\dagger
$$

See reference \[1] for further details.

**References**

1.  C.J. Wood, J.D. Biamonte, D.G. Cory, *Tensor networks and graphical calculus for open quantum systems*, Quant. Inf. Comp. 15, 0579-0811 (2015). [arXiv:1111.6950 \[quant-ph\]](https://arxiv.org/abs/1111.6950)

Initialize a quantum channel Kraus operator.

**Parameters**

*   **data** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")  *|*[*circuit.instruction.Instruction*](qiskit.circuit.Instruction "qiskit.circuit.instruction.Instruction") *| BaseOperator | np.ndarray*) – data to initialize superoperator.
*   **input\_dims** ([*tuple*](https://docs.python.org/3/library/stdtypes.html#tuple "(in Python v3.12)") *| None*) – the input subsystem dimensions.
*   **output\_dims** ([*tuple*](https://docs.python.org/3/library/stdtypes.html#tuple "(in Python v3.12)") *| None*) – the output subsystem dimensions.

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if input data cannot be initialized as a list of Kraus matrices.

**Additional Information:**

If the input or output dimensions are None, they will be automatically determined from the input data. If the input data is a list of Numpy arrays of shape $(2^N,\,2^N)$ qubit systems will be used. If the input does not correspond to an N-qubit channel, it will assign a single subsystem with dimension specified by the shape of the input.

## Attributes

<span id="qiskit.quantum_info.Kraus.atol" />

### atol

`= 1e-08`

<span id="qiskit.quantum_info.Kraus.data" />

### data

Return list of Kraus matrices for channel.

<span id="qiskit.quantum_info.Kraus.dim" />

### dim

Return tuple (input\_shape, output\_shape).

<span id="qiskit.quantum_info.Kraus.num_qubits" />

### num\_qubits

Return the number of qubits if a N-qubit operator or None otherwise.

<span id="qiskit.quantum_info.Kraus.qargs" />

### qargs

Return the qargs for the operator.

<span id="qiskit.quantum_info.Kraus.rtol" />

### rtol

`= 1e-05`

<span id="qiskit.quantum_info.Kraus.settings" />

### settings

Return settings.

## Methods

### adjoint

<span id="qiskit.quantum_info.Kraus.adjoint" />

`adjoint()`

Return the adjoint quantum channel.

<Admonition title="Note" type="note">
  This is equivalent to the matrix Hermitian conjugate in the [`SuperOp`](qiskit.quantum_info.SuperOp "qiskit.quantum_info.SuperOp") representation ie. for a channel $\mathcal{E}$, the SuperOp of the adjoint channel $\mathcal{{E}}^\dagger$ is $S_{\mathcal{E}^\dagger} = S_{\mathcal{E}}^\dagger$.
</Admonition>

### compose

<span id="qiskit.quantum_info.Kraus.compose" />

`compose(other, qargs=None, front=False)`

Return the operator composition with another Kraus.

**Parameters**

*   **other** ([*Kraus*](#qiskit.quantum_info.Kraus "qiskit.quantum_info.Kraus")) – a Kraus object.
*   **qargs** ([*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)") *or None*) – Optional, a list of subsystem positions to apply other on. If None apply on all subsystems (default: None).
*   **front** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – If True compose using right operator multiplication, instead of left multiplication \[default: False].

**Returns**

The composed Kraus.

**Return type**

[Kraus](#qiskit.quantum_info.Kraus "qiskit.quantum_info.Kraus")

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if other cannot be converted to an operator, or has incompatible dimensions for specified subsystems.

<Admonition title="Note" type="note">
  Composition (`&`) by default is defined as left matrix multiplication for matrix operators, while `@` (equivalent to [`dot()`](#qiskit.quantum_info.Kraus.dot "qiskit.quantum_info.Kraus.dot")) is defined as right matrix multiplication. That is that `A & B == A.compose(B)` is equivalent to `B @ A == B.dot(A)` when `A` and `B` are of the same type.

  Setting the `front=True` kwarg changes this to right matrix multiplication and is equivalent to the [`dot()`](#qiskit.quantum_info.Kraus.dot "qiskit.quantum_info.Kraus.dot") method `A.dot(B) == A.compose(B, front=True)`.
</Admonition>

### conjugate

<span id="qiskit.quantum_info.Kraus.conjugate" />

`conjugate()`

Return the conjugate quantum channel.

<Admonition title="Note" type="note">
  This is equivalent to the matrix complex conjugate in the [`SuperOp`](qiskit.quantum_info.SuperOp "qiskit.quantum_info.SuperOp") representation ie. for a channel $\mathcal{E}$, the SuperOp of the conjugate channel $\overline{{\mathcal{{E}}}}$ is $S_{\overline{\mathcal{E}^\dagger}} = \overline{S_{\mathcal{E}}}$.
</Admonition>

### copy

<span id="qiskit.quantum_info.Kraus.copy" />

`copy()`

Make a deep copy of current operator.

### dot

<span id="qiskit.quantum_info.Kraus.dot" />

`dot(other, qargs=None)`

Return the right multiplied operator self \* other.

**Parameters**

*   **other** ([*Operator*](qiskit.quantum_info.Operator "qiskit.quantum_info.Operator")) – an operator object.
*   **qargs** ([*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)") *or None*) – Optional, a list of subsystem positions to apply other on. If None apply on all subsystems (default: None).

**Returns**

The right matrix multiplied Operator.

**Return type**

[Operator](qiskit.quantum_info.Operator "qiskit.quantum_info.Operator")

<Admonition title="Note" type="note">
  The dot product can be obtained using the `@` binary operator. Hence `a.dot(b)` is equivalent to `a @ b`.
</Admonition>

### expand

<span id="qiskit.quantum_info.Kraus.expand" />

`expand(other)`

Return the reverse-order tensor product with another Kraus.

**Parameters**

**other** ([*Kraus*](#qiskit.quantum_info.Kraus "qiskit.quantum_info.Kraus")) – a Kraus object.

**Returns**

**the tensor product $b \otimes a$, where $a$**

is the current Kraus, and $b$ is the other Kraus.

**Return type**

[Kraus](#qiskit.quantum_info.Kraus "qiskit.quantum_info.Kraus")

### input\_dims

<span id="qiskit.quantum_info.Kraus.input_dims" />

`input_dims(qargs=None)`

Return tuple of input dimension for specified subsystems.

### is\_cp

<span id="qiskit.quantum_info.Kraus.is_cp" />

`is_cp(atol=None, rtol=None)`

Test if Choi-matrix is completely-positive (CP)

**Return type**

[bool](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")

### is\_cptp

<span id="qiskit.quantum_info.Kraus.is_cptp" />

`is_cptp(atol=None, rtol=None)`

Return True if completely-positive trace-preserving.

### is\_tp

<span id="qiskit.quantum_info.Kraus.is_tp" />

`is_tp(atol=None, rtol=None)`

Test if a channel is trace-preserving (TP)

**Return type**

[bool](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")

### is\_unitary

<span id="qiskit.quantum_info.Kraus.is_unitary" />

`is_unitary(atol=None, rtol=None)`

Return True if QuantumChannel is a unitary channel.

**Return type**

[bool](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")

### output\_dims

<span id="qiskit.quantum_info.Kraus.output_dims" />

`output_dims(qargs=None)`

Return tuple of output dimension for specified subsystems.

### power

<span id="qiskit.quantum_info.Kraus.power" />

`power(n)`

Return the power of the quantum channel.

**Parameters**

**n** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")) – the power exponent.

**Returns**

the channel $\mathcal{{E}} ^n$.

**Return type**

[SuperOp](qiskit.quantum_info.SuperOp "qiskit.quantum_info.SuperOp")

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if the input and output dimensions of the SuperOp are not equal.

<Admonition title="Note" type="note">
  For non-positive or non-integer exponents the power is defined as the matrix power of the [`SuperOp`](qiskit.quantum_info.SuperOp "qiskit.quantum_info.SuperOp") representation ie. for a channel $\mathcal{{E}}$, the SuperOp of the powered channel $\mathcal{{E}}^\n$ is $S_{{\mathcal{{E}}^n}} = S_{{\mathcal{{E}}}}^n$.
</Admonition>

### reshape

<span id="qiskit.quantum_info.Kraus.reshape" />

`reshape(input_dims=None, output_dims=None, num_qubits=None)`

Return a shallow copy with reshaped input and output subsystem dimensions.

**Parameters**

*   **input\_dims** (*None or* [*tuple*](https://docs.python.org/3/library/stdtypes.html#tuple "(in Python v3.12)")) – new subsystem input dimensions. If None the original input dims will be preserved \[Default: None].
*   **output\_dims** (*None or* [*tuple*](https://docs.python.org/3/library/stdtypes.html#tuple "(in Python v3.12)")) – new subsystem output dimensions. If None the original output dims will be preserved \[Default: None].
*   **num\_qubits** (*None or* [*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – reshape to an N-qubit operator \[Default: None].

**Returns**

returns self with reshaped input and output dimensions.

**Return type**

BaseOperator

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if combined size of all subsystem input dimension or subsystem output dimensions is not constant.

### tensor

<span id="qiskit.quantum_info.Kraus.tensor" />

`tensor(other)`

Return the tensor product with another Kraus.

**Parameters**

**other** ([*Kraus*](#qiskit.quantum_info.Kraus "qiskit.quantum_info.Kraus")) – a Kraus object.

**Returns**

**the tensor product $a \otimes b$, where $a$**

is the current Kraus, and $b$ is the other Kraus.

**Return type**

[Kraus](#qiskit.quantum_info.Kraus "qiskit.quantum_info.Kraus")

<Admonition title="Note" type="note">
  The tensor product can be obtained using the `^` binary operator. Hence `a.tensor(b)` is equivalent to `a ^ b`.
</Admonition>

### to\_instruction

<span id="qiskit.quantum_info.Kraus.to_instruction" />

`to_instruction()`

Convert to a Kraus or UnitaryGate circuit instruction.

If the channel is unitary it will be added as a unitary gate, otherwise it will be added as a kraus simulator instruction.

**Returns**

A kraus instruction for the channel.

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if input data is not an N-qubit CPTP quantum channel.

### to\_operator

<span id="qiskit.quantum_info.Kraus.to_operator" />

`to_operator()`

Try to convert channel to a unitary representation Operator.

**Return type**

[*Operator*](qiskit.quantum_info.Operator "qiskit.quantum_info.operators.operator.Operator")

### transpose

<span id="qiskit.quantum_info.Kraus.transpose" />

`transpose()`

Return the transpose quantum channel.

<Admonition title="Note" type="note">
  This is equivalent to the matrix transpose in the [`SuperOp`](qiskit.quantum_info.SuperOp "qiskit.quantum_info.SuperOp") representation, ie. for a channel $\mathcal{E}$, the SuperOp of the transpose channel $\mathcal{{E}}^T$ is $S_{mathcal{E}^T} = S_{\mathcal{E}}^T$.
</Admonition>

