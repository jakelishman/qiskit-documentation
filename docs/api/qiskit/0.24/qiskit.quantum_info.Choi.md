---
title: Choi
description: API reference for qiskit.quantum_info.Choi
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.quantum_info.Choi
---

<span id="qiskit-quantum-info-choi" />

# qiskit.quantum\_info.Choi

<span id="qiskit.quantum_info.Choi" />

`Choi(data, input_dims=None, output_dims=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.16/qiskit/quantum_info/operators/channel/choi.py "view source code")

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

|                                                                                                                          |                                                                            |
| ------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------- |
| [`__init__`](#qiskit.quantum_info.Choi.__init__ "qiskit.quantum_info.Choi.__init__")(data\[, input\_dims, output\_dims]) | Initialize a quantum channel Choi matrix operator.                         |
| [`add`](#qiskit.quantum_info.Choi.add "qiskit.quantum_info.Choi.add")(other)                                             | Return the linear operator self + other.                                   |
| [`adjoint`](#qiskit.quantum_info.Choi.adjoint "qiskit.quantum_info.Choi.adjoint")()                                      | Return the adjoint of the operator.                                        |
| [`compose`](#qiskit.quantum_info.Choi.compose "qiskit.quantum_info.Choi.compose")(other\[, qargs, front])                | Return the composed quantum channel self @ other.                          |
| [`conjugate`](#qiskit.quantum_info.Choi.conjugate "qiskit.quantum_info.Choi.conjugate")()                                | Return the conjugate of the QuantumChannel.                                |
| [`copy`](#qiskit.quantum_info.Choi.copy "qiskit.quantum_info.Choi.copy")()                                               | Make a deep copy of current operator.                                      |
| [`dot`](#qiskit.quantum_info.Choi.dot "qiskit.quantum_info.Choi.dot")(other\[, qargs])                                   | Return the right multiplied operator self \* other.                        |
| [`expand`](#qiskit.quantum_info.Choi.expand "qiskit.quantum_info.Choi.expand")(other)                                    | Return the tensor product channel other ⊗ self.                            |
| [`input_dims`](#qiskit.quantum_info.Choi.input_dims "qiskit.quantum_info.Choi.input_dims")(\[qargs])                     | Return tuple of input dimension for specified subsystems.                  |
| [`is_cp`](#qiskit.quantum_info.Choi.is_cp "qiskit.quantum_info.Choi.is_cp")(\[atol, rtol])                               | Test if Choi-matrix is completely-positive (CP)                            |
| [`is_cptp`](#qiskit.quantum_info.Choi.is_cptp "qiskit.quantum_info.Choi.is_cptp")(\[atol, rtol])                         | Return True if completely-positive trace-preserving (CPTP).                |
| [`is_tp`](#qiskit.quantum_info.Choi.is_tp "qiskit.quantum_info.Choi.is_tp")(\[atol, rtol])                               | Test if a channel is completely-positive (CP)                              |
| [`is_unitary`](#qiskit.quantum_info.Choi.is_unitary "qiskit.quantum_info.Choi.is_unitary")(\[atol, rtol])                | Return True if QuantumChannel is a unitary channel.                        |
| [`multiply`](#qiskit.quantum_info.Choi.multiply "qiskit.quantum_info.Choi.multiply")(other)                              | Return the linear operator other \* self.                                  |
| [`output_dims`](#qiskit.quantum_info.Choi.output_dims "qiskit.quantum_info.Choi.output_dims")(\[qargs])                  | Return tuple of output dimension for specified subsystems.                 |
| [`power`](#qiskit.quantum_info.Choi.power "qiskit.quantum_info.Choi.power")(n)                                           | The matrix power of the channel.                                           |
| [`reshape`](#qiskit.quantum_info.Choi.reshape "qiskit.quantum_info.Choi.reshape")(\[input\_dims, output\_dims])          | Return a shallow copy with reshaped input and output subsystem dimensions. |
| [`set_atol`](#qiskit.quantum_info.Choi.set_atol "qiskit.quantum_info.Choi.set_atol")(value)                              | Set the class default absolute tolerance parameter for float comparisons.  |
| [`set_rtol`](#qiskit.quantum_info.Choi.set_rtol "qiskit.quantum_info.Choi.set_rtol")(value)                              | Set the class default relative tolerance parameter for float comparisons.  |
| [`subtract`](#qiskit.quantum_info.Choi.subtract "qiskit.quantum_info.Choi.subtract")(other)                              | Return the linear operator self - other.                                   |
| [`tensor`](#qiskit.quantum_info.Choi.tensor "qiskit.quantum_info.Choi.tensor")(other)                                    | Return the tensor product channel self ⊗ other.                            |
| [`to_instruction`](#qiskit.quantum_info.Choi.to_instruction "qiskit.quantum_info.Choi.to_instruction")()                 | Convert to a Kraus or UnitaryGate circuit instruction.                     |
| [`to_operator`](#qiskit.quantum_info.Choi.to_operator "qiskit.quantum_info.Choi.to_operator")()                          | Try to convert channel to a unitary representation Operator.               |
| [`transpose`](#qiskit.quantum_info.Choi.transpose "qiskit.quantum_info.Choi.transpose")()                                | Return the transpose of the QuantumChannel.                                |

## Attributes

|                                                                                            |                                                                      |
| ------------------------------------------------------------------------------------------ | -------------------------------------------------------------------- |
| [`atol`](#qiskit.quantum_info.Choi.atol "qiskit.quantum_info.Choi.atol")                   | The default absolute tolerance parameter for float comparisons.      |
| [`data`](#qiskit.quantum_info.Choi.data "qiskit.quantum_info.Choi.data")                   | Return data.                                                         |
| [`dim`](#qiskit.quantum_info.Choi.dim "qiskit.quantum_info.Choi.dim")                      | Return tuple (input\_shape, output\_shape).                          |
| [`num_qubits`](#qiskit.quantum_info.Choi.num_qubits "qiskit.quantum_info.Choi.num_qubits") | Return the number of qubits if a N-qubit operator or None otherwise. |
| [`qargs`](#qiskit.quantum_info.Choi.qargs "qiskit.quantum_info.Choi.qargs")                | Return the qargs for the operator.                                   |
| [`rtol`](#qiskit.quantum_info.Choi.rtol "qiskit.quantum_info.Choi.rtol")                   | The relative tolerance parameter for float comparisons.              |

### add

<span id="qiskit.quantum_info.Choi.add" />

`add(other)`

Return the linear operator self + other.

DEPRECATED: use `operator + other` instead.

**Parameters**

**other** (*BaseOperator*) – an operator object.

**Returns**

the operator self + other.

**Return type**

BaseOperator

### adjoint

<span id="qiskit.quantum_info.Choi.adjoint" />

`adjoint()`

Return the adjoint of the operator.

### atol

<span id="qiskit.quantum_info.Choi.atol" />

`property atol`

The default absolute tolerance parameter for float comparisons.

### compose

<span id="qiskit.quantum_info.Choi.compose" />

`compose(other, qargs=None, front=False)`

Return the composed quantum channel self @ other.

**Parameters**

*   **other** (*QuantumChannel*) – a quantum channel.
*   **qargs** (*list or None*) – a list of subsystem positions to apply other on. If None apply on all subsystems \[default: None].
*   **front** (*bool*) – If True compose using right operator multiplication, instead of left multiplication \[default: False].

**Returns**

The quantum channel self @ other.

**Return type**

[Choi](#qiskit.quantum_info.Choi "qiskit.quantum_info.Choi")

**Raises**

**QiskitError** – if other has incompatible dimensions.

**Additional Information:**

Composition (`@`) is defined as left matrix multiplication for [`SuperOp`](qiskit.quantum_info.SuperOp "qiskit.quantum_info.SuperOp") matrices. That is that `A @ B` is equal to `B * A`. Setting `front=True` returns right matrix multiplication `A * B` and is equivalent to the [`dot()`](#qiskit.quantum_info.Choi.dot "qiskit.quantum_info.Choi.dot") method.

### conjugate

<span id="qiskit.quantum_info.Choi.conjugate" />

`conjugate()`

Return the conjugate of the QuantumChannel.

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

*   **other** (*BaseOperator*) – an operator object.
*   **qargs** (*list or None*) – a list of subsystem positions to apply other on. If None apply on all subsystems \[default: None].

**Returns**

The operator self \* other.

**Return type**

BaseOperator

**Raises**

**QiskitError** – if other cannot be converted to an operator, or has incompatible dimensions for specified subsystems.

### expand

<span id="qiskit.quantum_info.Choi.expand" />

`expand(other)`

Return the tensor product channel other ⊗ self.

**Parameters**

**other** (*QuantumChannel*) – a quantum channel.

**Returns**

the tensor product channel other ⊗ self as a Choi object.

**Return type**

[Choi](#qiskit.quantum_info.Choi "qiskit.quantum_info.Choi")

**Raises**

**QiskitError** – if other cannot be converted to a channel.

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

Test if a channel is completely-positive (CP)

### is\_unitary

<span id="qiskit.quantum_info.Choi.is_unitary" />

`is_unitary(atol=None, rtol=None)`

Return True if QuantumChannel is a unitary channel.

### multiply

<span id="qiskit.quantum_info.Choi.multiply" />

`multiply(other)`

Return the linear operator other \* self.

DEPRECATED: use `other * operator` instead.

**Parameters**

**other** (*complex*) – a complex number.

**Returns**

the linear operator other \* self.

**Return type**

BaseOperator

**Raises**

**NotImplementedError** – if subclass does not support multiplication.

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

The matrix power of the channel.

**Parameters**

**n** (*int*) – compute the matrix power of the superoperator matrix.

**Returns**

the matrix power of the SuperOp converted to a Choi channel.

**Return type**

[Choi](#qiskit.quantum_info.Choi "qiskit.quantum_info.Choi")

**Raises**

**QiskitError** – if the input and output dimensions of the QuantumChannel are not equal, or the power is not an integer.

### qargs

<span id="qiskit.quantum_info.Choi.qargs" />

`property qargs`

Return the qargs for the operator.

### reshape

<span id="qiskit.quantum_info.Choi.reshape" />

`reshape(input_dims=None, output_dims=None)`

Return a shallow copy with reshaped input and output subsystem dimensions.

**Arg:**

**input\_dims (None or tuple): new subsystem input dimensions.**

If None the original input dims will be preserved \[Default: None].

**output\_dims (None or tuple): new subsystem output dimensions.**

If None the original output dims will be preserved \[Default: None].

**Returns**

returns self with reshaped input and output dimensions.

**Return type**

BaseOperator

**Raises**

**QiskitError** – if combined size of all subsystem input dimension or subsystem output dimensions is not constant.

### rtol

<span id="qiskit.quantum_info.Choi.rtol" />

`property rtol`

The relative tolerance parameter for float comparisons.

### set\_atol

<span id="qiskit.quantum_info.Choi.set_atol" />

`classmethod set_atol(value)`

Set the class default absolute tolerance parameter for float comparisons.

DEPRECATED: use operator.atol = value instead

### set\_rtol

<span id="qiskit.quantum_info.Choi.set_rtol" />

`classmethod set_rtol(value)`

Set the class default relative tolerance parameter for float comparisons.

DEPRECATED: use operator.rtol = value instead

### subtract

<span id="qiskit.quantum_info.Choi.subtract" />

`subtract(other)`

Return the linear operator self - other.

DEPRECATED: use `operator - other` instead.

**Parameters**

**other** (*BaseOperator*) – an operator object.

**Returns**

the operator self - other.

**Return type**

BaseOperator

### tensor

<span id="qiskit.quantum_info.Choi.tensor" />

`tensor(other)`

Return the tensor product channel self ⊗ other.

**Parameters**

**other** (*QuantumChannel*) – a quantum channel.

**Returns**

the tensor product channel self ⊗ other as a Choi object.

**Return type**

[Choi](#qiskit.quantum_info.Choi "qiskit.quantum_info.Choi")

**Raises**

**QiskitError** – if other cannot be converted to a channel.

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

Return the transpose of the QuantumChannel.

