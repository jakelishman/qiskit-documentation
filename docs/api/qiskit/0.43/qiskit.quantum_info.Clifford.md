---
title: Clifford
description: API reference for qiskit.quantum_info.Clifford
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.quantum_info.Clifford
---

# Clifford

<span id="qiskit.quantum_info.Clifford" />

`Clifford(data, validate=True, copy=True)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/quantum_info/operators/symplectic/clifford.py "view source code")

Bases: `BaseOperator`, `AdjointMixin`, [`Operation`](qiskit.circuit.Operation "qiskit.circuit.operation.Operation")

An N-qubit unitary operator from the Clifford group.

**Representation**

An *N*-qubit Clifford operator is stored as a length *2N × (2N+1)* boolean tableau using the convention from reference \[1].

*   Rows 0 to *N-1* are the *destabilizer* group generators
*   Rows *N* to *2N-1* are the *stabilizer* group generators.

The internal boolean tableau for the Clifford can be accessed using the `tableau` attribute. The destabilizer or stabilizer rows can each be accessed as a length-N Stabilizer table using [`destab`](#qiskit.quantum_info.Clifford.destab "qiskit.quantum_info.Clifford.destab") and [`stab`](#qiskit.quantum_info.Clifford.stab "qiskit.quantum_info.Clifford.stab") attributes.

A more easily human readable representation of the Clifford operator can be obtained by calling the [`to_dict()`](qiskit.quantum_info.Clifford#to_dict "qiskit.quantum_info.Clifford.to_dict") method. This representation is also used if a Clifford object is printed as in the following example

```python
from qiskit import QuantumCircuit
from qiskit.quantum_info import Clifford

# Bell state generation circuit
qc = QuantumCircuit(2)
qc.h(0)
qc.cx(0, 1)
cliff = Clifford(qc)

# Print the Clifford
print(cliff)

# Print the Clifford destabilizer rows
print(cliff.to_labels(mode="D"))

# Print the Clifford stabilizer rows
print(cliff.to_labels(mode="S"))
```

```python
Clifford: Stabilizer = ['+XX', '+ZZ'], Destabilizer = ['+IZ', '+XI']
['+IZ', '+XI']
['+XX', '+ZZ']
```

**Circuit Conversion**

Clifford operators can be initialized from circuits containing *only* the following Clifford gates: [`IGate`](qiskit.circuit.library.IGate "qiskit.circuit.library.IGate"), [`XGate`](qiskit.circuit.library.XGate "qiskit.circuit.library.XGate"), [`YGate`](qiskit.circuit.library.YGate "qiskit.circuit.library.YGate"), [`ZGate`](qiskit.circuit.library.ZGate "qiskit.circuit.library.ZGate"), [`HGate`](qiskit.circuit.library.HGate "qiskit.circuit.library.HGate"), [`SGate`](qiskit.circuit.library.SGate "qiskit.circuit.library.SGate"), [`SdgGate`](qiskit.circuit.library.SdgGate "qiskit.circuit.library.SdgGate"), [`SXGate`](qiskit.circuit.library.SXGate "qiskit.circuit.library.SXGate"), [`SXdgGate`](qiskit.circuit.library.SXdgGate "qiskit.circuit.library.SXdgGate"), [`CXGate`](qiskit.circuit.library.CXGate "qiskit.circuit.library.CXGate"), [`CZGate`](qiskit.circuit.library.CZGate "qiskit.circuit.library.CZGate"), [`CYGate`](qiskit.circuit.library.CYGate "qiskit.circuit.library.CYGate"), `DXGate`, [`SwapGate`](qiskit.circuit.library.SwapGate "qiskit.circuit.library.SwapGate"), [`iSwapGate`](qiskit.circuit.library.iSwapGate "qiskit.circuit.library.iSwapGate"), [`ECRGate`](qiskit.circuit.library.ECRGate "qiskit.circuit.library.ECRGate"). They can be converted back into a [`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit"), or [`Gate`](qiskit.circuit.Gate "qiskit.circuit.Gate") object using the [`to_circuit()`](qiskit.quantum_info.Clifford#to_circuit "qiskit.quantum_info.Clifford.to_circuit") or [`to_instruction()`](qiskit.quantum_info.Clifford#to_instruction "qiskit.quantum_info.Clifford.to_instruction") methods respectively. Note that this decomposition is not necessarily optimal in terms of number of gates.

<Admonition title="Note" type="note">
  A minimally generating set of gates for Clifford circuits is the [`HGate`](qiskit.circuit.library.HGate "qiskit.circuit.library.HGate") and [`SGate`](qiskit.circuit.library.SGate "qiskit.circuit.library.SGate") gate and *either* the [`CXGate`](qiskit.circuit.library.CXGate "qiskit.circuit.library.CXGate") or [`CZGate`](qiskit.circuit.library.CZGate "qiskit.circuit.library.CZGate") two-qubit gate.
</Admonition>

Clifford operators can also be converted to [`Operator`](qiskit.quantum_info.Operator "qiskit.quantum_info.Operator") objects using the [`to_operator()`](qiskit.quantum_info.Clifford#to_operator "qiskit.quantum_info.Clifford.to_operator") method. This is done via decomposing to a circuit, and then simulating the circuit as a unitary operator.

## References

1.  S. Aaronson, D. Gottesman, *Improved Simulation of Stabilizer Circuits*, Phys. Rev. A 70, 052328 (2004). [arXiv:quant-ph/0406196](https://arxiv.org/abs/quant-ph/0406196)

Initialize an operator object.

## Methods

<span id="qiskit-quantum-info-clifford-adjoint" />

### adjoint

<span id="qiskit.quantum_info.Clifford.adjoint" />

`Clifford.adjoint()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/quantum_info/operators/symplectic/clifford.py "view source code")

Return the adjoint of the Operator.

<span id="qiskit-quantum-info-clifford-compose" />

### compose

<span id="qiskit.quantum_info.Clifford.compose" />

`Clifford.compose(other, qargs=None, front=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/quantum_info/operators/symplectic/clifford.py "view source code")

Return the operator composition with another Clifford.

**Parameters**

*   **other** ([*Clifford*](qiskit.quantum_info.Clifford "qiskit.quantum_info.Clifford")) – a Clifford object.
*   **qargs** (*list or None*) – Optional, a list of subsystem positions to apply other on. If None apply on all subsystems (default: None).
*   **front** (*bool*) – If True compose using right operator multiplication, instead of left multiplication \[default: False].

**Returns**

The composed Clifford.

**Return type**

[Clifford](qiskit.quantum_info.Clifford "qiskit.quantum_info.Clifford")

**Raises**

**QiskitError** – if other cannot be converted to an operator, or has incompatible dimensions for specified subsystems.

<Admonition title="Note" type="note">
  Composition (`&`) by default is defined as left matrix multiplication for matrix operators, while `@` (equivalent to [`dot()`](qiskit.quantum_info.Clifford#dot "qiskit.quantum_info.Clifford.dot")) is defined as right matrix multiplication. That is that `A & B == A.compose(B)` is equivalent to `B @ A == B.dot(A)` when `A` and `B` are of the same type.

  Setting the `front=True` kwarg changes this to right matrix multiplication and is equivalent to the [`dot()`](qiskit.quantum_info.Clifford#dot "qiskit.quantum_info.Clifford.dot") method `A.dot(B) == A.compose(B, front=True)`.
</Admonition>

<span id="qiskit-quantum-info-clifford-conjugate" />

### conjugate

<span id="qiskit.quantum_info.Clifford.conjugate" />

`Clifford.conjugate()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/quantum_info/operators/symplectic/clifford.py "view source code")

Return the conjugate of the Clifford.

<span id="qiskit-quantum-info-clifford-copy" />

### copy

<span id="qiskit.quantum_info.Clifford.copy" />

`Clifford.copy()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/quantum_info/operators/symplectic/clifford.py "view source code")

Make a deep copy of current operator.

<span id="qiskit-quantum-info-clifford-dot" />

### dot

<span id="qiskit.quantum_info.Clifford.dot" />

`Clifford.dot(other, qargs=None)`

Return the right multiplied operator self \* other.

**Parameters**

*   **other** ([*Operator*](qiskit.quantum_info.Operator "qiskit.quantum_info.Operator")) – an operator object.
*   **qargs** (*list or None*) – Optional, a list of subsystem positions to apply other on. If None apply on all subsystems (default: None).

**Returns**

The right matrix multiplied Operator.

**Return type**

[Operator](qiskit.quantum_info.Operator "qiskit.quantum_info.Operator")

<Admonition title="Note" type="note">
  The dot product can be obtained using the `@` binary operator. Hence `a.dot(b)` is equivalent to `a @ b`.
</Admonition>

<span id="qiskit-quantum-info-clifford-expand" />

### expand

<span id="qiskit.quantum_info.Clifford.expand" />

`Clifford.expand(other)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/quantum_info/operators/symplectic/clifford.py "view source code")

Return the reverse-order tensor product with another Clifford.

**Parameters**

**other** ([*Clifford*](qiskit.quantum_info.Clifford "qiskit.quantum_info.Clifford")) – a Clifford object.

**Returns**

**the tensor product $b \otimes a$, where $a$**

is the current Clifford, and $b$ is the other Clifford.

**Return type**

[Clifford](qiskit.quantum_info.Clifford "qiskit.quantum_info.Clifford")

<span id="qiskit-quantum-info-clifford-from-circuit" />

### from\_circuit

<span id="qiskit.quantum_info.Clifford.from_circuit" />

`static Clifford.from_circuit(circuit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/quantum_info/operators/symplectic/clifford.py "view source code")

Initialize from a QuantumCircuit or Instruction.

**Parameters**

**circuit** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")  *or*[*Instruction*](qiskit.circuit.Instruction "qiskit.circuit.Instruction")) – instruction to initialize.

**Returns**

the Clifford object for the instruction.

**Return type**

[Clifford](qiskit.quantum_info.Clifford "qiskit.quantum_info.Clifford")

**Raises**

**QiskitError** – if the input instruction is non-Clifford or contains classical register instruction.

<span id="qiskit-quantum-info-clifford-from-dict" />

### from\_dict

<span id="qiskit.quantum_info.Clifford.from_dict" />

`classmethod Clifford.from_dict(obj)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/quantum_info/operators/symplectic/clifford.py "view source code")

Load a Clifford from a dictionary

<span id="qiskit-quantum-info-clifford-from-label" />

### from\_label

<span id="qiskit.quantum_info.Clifford.from_label" />

`static Clifford.from_label(label)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/quantum_info/operators/symplectic/clifford.py "view source code")

Return a tensor product of single-qubit Clifford gates.

**Parameters**

**label** (*string*) – single-qubit operator string.

**Returns**

The N-qubit Clifford operator.

**Return type**

[Clifford](qiskit.quantum_info.Clifford "qiskit.quantum_info.Clifford")

**Raises**

**QiskitError** – if the label contains invalid characters.

#### Additional Information:

The labels correspond to the single-qubit Cliffords are

*   *   Label
    *   Stabilizer
    *   Destabilizer
*   *   `"I"`
    *   +Z
    *   +X
*   *   `"X"`
    *   -Z
    *   +X
*   *   `"Y"`
    *   -Z
    *   -X
*   *   `"Z"`
    *   +Z
    *   -X
*   *   `"H"`
    *   +X
    *   +Z
*   *   `"S"`
    *   +Z
    *   +Y

<span id="qiskit-quantum-info-clifford-from-matrix" />

### from\_matrix

<span id="qiskit.quantum_info.Clifford.from_matrix" />

`classmethod Clifford.from_matrix(matrix)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/quantum_info/operators/symplectic/clifford.py "view source code")

Create a Clifford from a unitary matrix.

Note that this function takes exponentially long time w\.r.t. the number of qubits.

**Parameters**

**matrix** (*np.array*) – A unitary matrix representing a Clifford to be converted.

**Returns**

the Clifford object for the unitary matrix.

**Return type**

[Clifford](qiskit.quantum_info.Clifford "qiskit.quantum_info.Clifford")

**Raises**

**QiskitError** – if the input is not a Clifford matrix.

<span id="qiskit-quantum-info-clifford-from-operator" />

### from\_operator

<span id="qiskit.quantum_info.Clifford.from_operator" />

`classmethod Clifford.from_operator(operator)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/quantum_info/operators/symplectic/clifford.py "view source code")

Create a Clifford from a operator.

Note that this function takes exponentially long time w\.r.t. the number of qubits.

**Parameters**

**operator** ([*Operator*](qiskit.quantum_info.Operator "qiskit.quantum_info.Operator")) – An operator representing a Clifford to be converted.

**Returns**

the Clifford object for the operator.

**Return type**

[Clifford](qiskit.quantum_info.Clifford "qiskit.quantum_info.Clifford")

**Raises**

**QiskitError** – if the input is not a Clifford operator.

<span id="qiskit-quantum-info-clifford-input-dims" />

### input\_dims

<span id="qiskit.quantum_info.Clifford.input_dims" />

`Clifford.input_dims(qargs=None)`

Return tuple of input dimension for specified subsystems.

<span id="qiskit-quantum-info-clifford-is-unitary" />

### is\_unitary

<span id="qiskit.quantum_info.Clifford.is_unitary" />

`Clifford.is_unitary()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/quantum_info/operators/symplectic/clifford.py "view source code")

Return True if the Clifford table is valid.

<span id="qiskit-quantum-info-clifford-output-dims" />

### output\_dims

<span id="qiskit.quantum_info.Clifford.output_dims" />

`Clifford.output_dims(qargs=None)`

Return tuple of output dimension for specified subsystems.

<span id="qiskit-quantum-info-clifford-power" />

### power

<span id="qiskit.quantum_info.Clifford.power" />

`Clifford.power(n)`

Return the compose of a operator with itself n times.

**Parameters**

**n** (*int*) – the number of times to compose with self (n>0).

**Returns**

the n-times composed operator.

**Return type**

[Pauli](qiskit.quantum_info.Pauli "qiskit.quantum_info.Pauli")

**Raises**

**QiskitError** – if the input and output dimensions of the operator are not equal, or the power is not a positive integer.

<span id="qiskit-quantum-info-clifford-reshape" />

### reshape

<span id="qiskit.quantum_info.Clifford.reshape" />

`Clifford.reshape(input_dims=None, output_dims=None, num_qubits=None)`

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

<span id="qiskit-quantum-info-clifford-tensor" />

### tensor

<span id="qiskit.quantum_info.Clifford.tensor" />

`Clifford.tensor(other)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/quantum_info/operators/symplectic/clifford.py "view source code")

Return the tensor product with another Clifford.

**Parameters**

**other** ([*Clifford*](qiskit.quantum_info.Clifford "qiskit.quantum_info.Clifford")) – a Clifford object.

**Returns**

**the tensor product $a \otimes b$, where $a$**

is the current Clifford, and $b$ is the other Clifford.

**Return type**

[Clifford](qiskit.quantum_info.Clifford "qiskit.quantum_info.Clifford")

<Admonition title="Note" type="note">
  The tensor product can be obtained using the `^` binary operator. Hence `a.tensor(b)` is equivalent to `a ^ b`.
</Admonition>

<span id="qiskit-quantum-info-clifford-to-circuit" />

### to\_circuit

<span id="qiskit.quantum_info.Clifford.to_circuit" />

`Clifford.to_circuit()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/quantum_info/operators/symplectic/clifford.py "view source code")

Return a QuantumCircuit implementing the Clifford.

For N \<= 3 qubits this is based on optimal CX cost decomposition from reference \[1]. For N > 3 qubits this is done using the general non-optimal compilation routine from reference \[2].

**Returns**

a circuit implementation of the Clifford.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

#### References

1.  S. Bravyi, D. Maslov, *Hadamard-free circuits expose the structure of the Clifford group*, [arXiv:2003.09412 \[quant-ph\]](https://arxiv.org/abs/2003.09412)
2.  S. Aaronson, D. Gottesman, *Improved Simulation of Stabilizer Circuits*, Phys. Rev. A 70, 052328 (2004). [arXiv:quant-ph/0406196](https://arxiv.org/abs/quant-ph/0406196)

<span id="qiskit-quantum-info-clifford-to-dict" />

### to\_dict

<span id="qiskit.quantum_info.Clifford.to_dict" />

`Clifford.to_dict()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/quantum_info/operators/symplectic/clifford.py "view source code")

Return dictionary representation of Clifford object.

<span id="qiskit-quantum-info-clifford-to-instruction" />

### to\_instruction

<span id="qiskit.quantum_info.Clifford.to_instruction" />

`Clifford.to_instruction()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/quantum_info/operators/symplectic/clifford.py "view source code")

Return a Gate instruction implementing the Clifford.

<span id="qiskit-quantum-info-clifford-to-labels" />

### to\_labels

<span id="qiskit.quantum_info.Clifford.to_labels" />

`Clifford.to_labels(array=False, mode='B')`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/quantum_info/operators/symplectic/clifford.py "view source code")

Convert a Clifford to a list Pauli (de)stabilizer string labels.

For large Clifford converting using the `array=True` kwarg will be more efficient since it allocates memory for the full Numpy array of labels in advance.

| Label  | Phase | Symplectic | Matrix                                           | Pauli |
| ------ | ----- | ---------- | ------------------------------------------------ | ----- |
| `"+I"` | 0     | $[0, 0]$   | $\begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}$   | $I$   |
| `"-I"` | 1     | $[0, 0]$   | $\begin{bmatrix} -1 & 0 \\ 0 & -1 \end{bmatrix}$ | $-I$  |
| `"X"`  | 0     | $[1, 0]$   | $\begin{bmatrix} 0 & 1 \\ 1 & 0 \end{bmatrix}$   | $X$   |
| `"-X"` | 1     | $[1, 0]$   | $\begin{bmatrix} 0 & -1 \\ -1 & 0 \end{bmatrix}$ | $-X$  |
| `"Y"`  | 0     | $[1, 1]$   | $\begin{bmatrix} 0 & 1 \\ -1 & 0 \end{bmatrix}$  | $iY$  |
| `"-Y"` | 1     | $[1, 1]$   | $\begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix}$  | $-iY$ |
| `"Z"`  | 0     | $[0, 1]$   | $\begin{bmatrix} 1 & 0 \\ 0 & -1 \end{bmatrix}$  | $Z$   |
| `"-Z"` | 1     | $[0, 1]$   | $\begin{bmatrix} -1 & 0 \\ 0 & 1 \end{bmatrix}$  | $-Z$  |

**Parameters**

*   **array** (*bool*) – return a Numpy array if True, otherwise return a list (Default: False).
*   **mode** (*Literal\["S", "D", "B"]*) – return both stabilizer and destablizer if “B”, return only stabilizer if “S” and return only destablizer if “D”.

**Returns**

The rows of the StabilizerTable in label form.

**Return type**

list or array

**Raises**

**QiskitError** – if stabilizer and destabilizer are both False.

<span id="qiskit-quantum-info-clifford-to-matrix" />

### to\_matrix

<span id="qiskit.quantum_info.Clifford.to_matrix" />

`Clifford.to_matrix()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/quantum_info/operators/symplectic/clifford.py "view source code")

Convert operator to Numpy matrix.

<span id="qiskit-quantum-info-clifford-to-operator" />

### to\_operator

<span id="qiskit.quantum_info.Clifford.to_operator" />

`Clifford.to_operator()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/quantum_info/operators/symplectic/clifford.py "view source code")

Convert to an Operator object.

<span id="qiskit-quantum-info-clifford-transpose" />

### transpose

<span id="qiskit.quantum_info.Clifford.transpose" />

`Clifford.transpose()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/quantum_info/operators/symplectic/clifford.py "view source code")

Return the transpose of the Clifford.

## Attributes

<span id="qiskit.quantum_info.Clifford.destab" />

### destab

The destabilizer array for the symplectic representation.

<span id="qiskit.quantum_info.Clifford.destab_phase" />

### destab\_phase

Return phase of destaibilizer with boolean representation.

<span id="qiskit.quantum_info.Clifford.destab_x" />

### destab\_x

The destabilizer x array for the symplectic representation.

<span id="qiskit.quantum_info.Clifford.destab_z" />

### destab\_z

The destabilizer z array for the symplectic representation.

<span id="qiskit.quantum_info.Clifford.destabilizer" />

### destabilizer

Return the destabilizer block of the StabilizerTable.

<Admonition title="Deprecated since version 0.24.0" type="danger">
  The property `qiskit.quantum_info.operators.symplectic.clifford.Clifford.destabilizer` is deprecated as of qiskit-terra 0.24.0. It will be removed no earlier than 3 months after the release date. Use Clifford.destab properties instead.
</Admonition>

<span id="qiskit.quantum_info.Clifford.dim" />

### dim

Return tuple (input\_shape, output\_shape).

<span id="qiskit.quantum_info.Clifford.name" />

### name

Unique string identifier for operation type.

<span id="qiskit.quantum_info.Clifford.num_clbits" />

### num\_clbits

Number of classical bits.

<span id="qiskit.quantum_info.Clifford.num_qubits" />

### num\_qubits

Return the number of qubits if a N-qubit operator or None otherwise.

<span id="qiskit.quantum_info.Clifford.phase" />

### phase

Return phase with boolean representation.

<span id="qiskit.quantum_info.Clifford.qargs" />

### qargs

Return the qargs for the operator.

<span id="qiskit.quantum_info.Clifford.stab" />

### stab

The stabilizer array for the symplectic representation.

<span id="qiskit.quantum_info.Clifford.stab_phase" />

### stab\_phase

Return phase of stablizer with boolean representation.

<span id="qiskit.quantum_info.Clifford.stab_x" />

### stab\_x

The stabilizer x array for the symplectic representation.

<span id="qiskit.quantum_info.Clifford.stab_z" />

### stab\_z

The stabilizer array for the symplectic representation.

<span id="qiskit.quantum_info.Clifford.stabilizer" />

### stabilizer

Return the stabilizer block of the StabilizerTable.

<Admonition title="Deprecated since version 0.24.0" type="danger">
  The property `qiskit.quantum_info.operators.symplectic.clifford.Clifford.stabilizer` is deprecated as of qiskit-terra 0.24.0. It will be removed no earlier than 3 months after the release date. Use Clifford.stab properties instead.
</Admonition>

<span id="qiskit.quantum_info.Clifford.symplectic_matrix" />

### symplectic\_matrix

Return boolean symplectic matrix.

<span id="qiskit.quantum_info.Clifford.table" />

### table

Return StabilizerTable

<Admonition title="Deprecated since version 0.24.0" type="danger">
  The property `qiskit.quantum_info.operators.symplectic.clifford.Clifford.table` is deprecated as of qiskit-terra 0.24.0. It will be removed no earlier than 3 months after the release date. Use Clifford.stab and Clifford.destab properties instead.
</Admonition>

<span id="qiskit.quantum_info.Clifford.x" />

### x

The x array for the symplectic representation.

<span id="qiskit.quantum_info.Clifford.z" />

### z

The z array for the symplectic representation.

