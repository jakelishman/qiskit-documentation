---
title: PauliList
description: API reference for qiskit.quantum_info.PauliList
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.quantum_info.PauliList
---

# qiskit.quantum\_info.PauliList

<span id="qiskit.quantum_info.PauliList" />

`PauliList(data)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/quantum_info/operators/symplectic/pauli_list.py "view source code")

List of N-qubit Pauli operators.

This class is an efficient representation of a list of [`Pauli`](qiskit.quantum_info.Pauli "qiskit.quantum_info.Pauli") operators. It supports 1D numpy array indexing returning a [`Pauli`](qiskit.quantum_info.Pauli "qiskit.quantum_info.Pauli") for integer indexes or a [`PauliList`](#qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList") for slice or list indices.

**Initialization**

A PauliList object can be initialized in several ways.

> **`PauliList(list[str])`**
>
> where strings are same representation with [`Pauli`](qiskit.quantum_info.Pauli "qiskit.quantum_info.Pauli").
>
> **`PauliList(Pauli) and PauliList(list[Pauli])`**
>
> where Pauli is [`Pauli`](qiskit.quantum_info.Pauli "qiskit.quantum_info.Pauli").
>
> **`PauliList.from_symplectic(z, x, phase)`**
>
> where `z` and `x` are 2 dimensional boolean `numpy.ndarrays` and `phase` is an integer in `[0, 1, 2, 3]`.

For example,

```python
import numpy as np

from qiskit.quantum_info import Pauli, PauliList

# 1. init from list[str]
pauli_list = PauliList(["II", "+ZI", "-iYY"])
print("1. ", pauli_list)

pauli1 = Pauli("iXI")
pauli2 = Pauli("iZZ")

# 2. init from Pauli
print("2. ", PauliList(pauli1))

# 3. init from list[Pauli]
print("3. ", PauliList([pauli1, pauli2]))

# 4. init from np.ndarray
z = np.array([[True, True], [False, False]])
x = np.array([[False, True], [True, False]])
phase = np.array([0, 1])
pauli_list = PauliList.from_symplectic(z, x)
print("4. ", pauli_list)
```

```python
1.  ['II', 'ZI', '-iYY']
2.  ['iXI']
3.  ['iXI', 'iZZ']
4.  ['YZ', 'IX']
```

**Data Access**

The individual Paulis can be accessed and updated using the `[]` operator which accepts integer, lists, or slices for selecting subsets of PauliList. If integer is given, it returns Pauli not PauliList.

```python
pauli_list = PauliList(["XX", "ZZ", "IZ"])
print("Integer: ", repr(pauli_list[1]))
print("List: ", repr(pauli_list[[0, 2]]))
print("Slice: ", repr(pauli_list[0:2]))
```

```python
Integer:  Pauli('ZZ')
List:  PauliList(['XX', 'IZ'])
Slice:  PauliList(['XX', 'ZZ'])
```

**Iteration**

Rows in the Pauli table can be iterated over like a list. Iteration can also be done using the label or matrix representation of each row using the [`label_iter()`](#qiskit.quantum_info.PauliList.label_iter "qiskit.quantum_info.PauliList.label_iter") and [`matrix_iter()`](#qiskit.quantum_info.PauliList.matrix_iter "qiskit.quantum_info.PauliList.matrix_iter") methods.

Initialize the PauliList.

**Parameters**

**data** ([*Pauli*](qiskit.quantum_info.Pauli "qiskit.quantum_info.Pauli") *or list*) – input data for Paulis. If input is a list each item in the list must be a Pauli object or Pauli str.

**Raises**

**QiskitError** – if input array is invalid shape.

**Additional Information:**

The input array is not copied so multiple Pauli tables can share the same underlying array.

### \_\_init\_\_

<span id="qiskit.quantum_info.PauliList.__init__" />

`__init__(data)`

Initialize the PauliList.

**Parameters**

**data** ([*Pauli*](qiskit.quantum_info.Pauli "qiskit.quantum_info.Pauli") *or list*) – input data for Paulis. If input is a list each item in the list must be a Pauli object or Pauli str.

**Raises**

**QiskitError** – if input array is invalid shape.

**Additional Information:**

The input array is not copied so multiple Pauli tables can share the same underlying array.

## Methods

|                                                                                                                                              |                                                                            |
| -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| [`__init__`](#qiskit.quantum_info.PauliList.__init__ "qiskit.quantum_info.PauliList.__init__")(data)                                         | Initialize the PauliList.                                                  |
| [`adjoint`](#qiskit.quantum_info.PauliList.adjoint "qiskit.quantum_info.PauliList.adjoint")()                                                | Return the adjoint of each Pauli in the list.                              |
| [`anticommutes`](#qiskit.quantum_info.PauliList.anticommutes "qiskit.quantum_info.PauliList.anticommutes")(other\[, qargs])                  | Return True if other Pauli that anticommutes with other.                   |
| [`anticommutes_with_all`](#qiskit.quantum_info.PauliList.anticommutes_with_all "qiskit.quantum_info.PauliList.anticommutes_with_all")(other) | Return indexes of rows that commute other.                                 |
| [`argsort`](#qiskit.quantum_info.PauliList.argsort "qiskit.quantum_info.PauliList.argsort")(\[weight, phase])                                | Return indices for sorting the rows of the table.                          |
| [`commutes`](#qiskit.quantum_info.PauliList.commutes "qiskit.quantum_info.PauliList.commutes")(other\[, qargs])                              | Return True for each Pauli that commutes with other.                       |
| [`commutes_with_all`](#qiskit.quantum_info.PauliList.commutes_with_all "qiskit.quantum_info.PauliList.commutes_with_all")(other)             | Return indexes of rows that commute other.                                 |
| [`compose`](#qiskit.quantum_info.PauliList.compose "qiskit.quantum_info.PauliList.compose")(other\[, qargs, front, inplace])                 | Return the composition self∘other for each Pauli in the list.              |
| [`conjugate`](#qiskit.quantum_info.PauliList.conjugate "qiskit.quantum_info.PauliList.conjugate")()                                          | Return the conjugate of each Pauli in the list.                            |
| [`copy`](#qiskit.quantum_info.PauliList.copy "qiskit.quantum_info.PauliList.copy")()                                                         | Make a deep copy of current operator.                                      |
| [`delete`](#qiskit.quantum_info.PauliList.delete "qiskit.quantum_info.PauliList.delete")(ind\[, qubit])                                      | Return a copy with Pauli rows deleted from table.                          |
| [`dot`](#qiskit.quantum_info.PauliList.dot "qiskit.quantum_info.PauliList.dot")(other\[, qargs, inplace])                                    | Return the composition other∘self for each Pauli in the list.              |
| [`equiv`](#qiskit.quantum_info.PauliList.equiv "qiskit.quantum_info.PauliList.equiv")(other)                                                 | Entrywise comparison of Pauli equivalence up to global phase.              |
| [`evolve`](#qiskit.quantum_info.PauliList.evolve "qiskit.quantum_info.PauliList.evolve")(other\[, qargs])                                    | Evolve the Pauli by a Clifford.                                            |
| [`expand`](#qiskit.quantum_info.PauliList.expand "qiskit.quantum_info.PauliList.expand")(other)                                              | Return the expand product of each Pauli in the list.                       |
| [`from_symplectic`](#qiskit.quantum_info.PauliList.from_symplectic "qiskit.quantum_info.PauliList.from_symplectic")(z, x\[, phase])          | Construct a PauliList from a symplectic data.                              |
| [`input_dims`](#qiskit.quantum_info.PauliList.input_dims "qiskit.quantum_info.PauliList.input_dims")(\[qargs])                               | Return tuple of input dimension for specified subsystems.                  |
| [`insert`](#qiskit.quantum_info.PauliList.insert "qiskit.quantum_info.PauliList.insert")(ind, value\[, qubit])                               | Insert Pauli’s into the table.                                             |
| [`inverse`](#qiskit.quantum_info.PauliList.inverse "qiskit.quantum_info.PauliList.inverse")()                                                | Return the inverse of each Pauli in the list.                              |
| [`label_iter`](#qiskit.quantum_info.PauliList.label_iter "qiskit.quantum_info.PauliList.label_iter")()                                       | Return a label representation iterator.                                    |
| [`matrix_iter`](#qiskit.quantum_info.PauliList.matrix_iter "qiskit.quantum_info.PauliList.matrix_iter")(\[sparse])                           | Return a matrix representation iterator.                                   |
| [`output_dims`](#qiskit.quantum_info.PauliList.output_dims "qiskit.quantum_info.PauliList.output_dims")(\[qargs])                            | Return tuple of output dimension for specified subsystems.                 |
| [`power`](#qiskit.quantum_info.PauliList.power "qiskit.quantum_info.PauliList.power")(n)                                                     | Return the compose of a operator with itself n times.                      |
| [`reshape`](#qiskit.quantum_info.PauliList.reshape "qiskit.quantum_info.PauliList.reshape")(\[input\_dims, output\_dims, num\_qubits])       | Return a shallow copy with reshaped input and output subsystem dimensions. |
| [`sort`](#qiskit.quantum_info.PauliList.sort "qiskit.quantum_info.PauliList.sort")(\[weight, phase])                                         | Sort the rows of the table.                                                |
| [`tensor`](#qiskit.quantum_info.PauliList.tensor "qiskit.quantum_info.PauliList.tensor")(other)                                              | Return the tensor product with each Pauli in the list.                     |
| [`to_labels`](#qiskit.quantum_info.PauliList.to_labels "qiskit.quantum_info.PauliList.to_labels")(\[array])                                  | Convert a PauliList to a list Pauli string labels.                         |
| [`to_matrix`](#qiskit.quantum_info.PauliList.to_matrix "qiskit.quantum_info.PauliList.to_matrix")(\[sparse, array])                          | Convert to a list or array of Pauli matrices.                              |
| [`transpose`](#qiskit.quantum_info.PauliList.transpose "qiskit.quantum_info.PauliList.transpose")()                                          | Return the transpose of each Pauli in the list.                            |
| [`unique`](#qiskit.quantum_info.PauliList.unique "qiskit.quantum_info.PauliList.unique")(\[return\_index, return\_counts])                   | Return unique Paulis from the table.                                       |

## Attributes

|                                                                                                      |                                                                      |
| ---------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| [`dim`](#qiskit.quantum_info.PauliList.dim "qiskit.quantum_info.PauliList.dim")                      | Return tuple (input\_shape, output\_shape).                          |
| [`num_qubits`](#qiskit.quantum_info.PauliList.num_qubits "qiskit.quantum_info.PauliList.num_qubits") | Return the number of qubits if a N-qubit operator or None otherwise. |
| [`phase`](#qiskit.quantum_info.PauliList.phase "qiskit.quantum_info.PauliList.phase")                | Return the phase exponent of the PauliList.                          |
| [`qargs`](#qiskit.quantum_info.PauliList.qargs "qiskit.quantum_info.PauliList.qargs")                | Return the qargs for the operator.                                   |
| [`settings`](#qiskit.quantum_info.PauliList.settings "qiskit.quantum_info.PauliList.settings")       | Return operator settings.                                            |
| [`shape`](#qiskit.quantum_info.PauliList.shape "qiskit.quantum_info.PauliList.shape")                | The full shape of the `array()`                                      |
| [`size`](#qiskit.quantum_info.PauliList.size "qiskit.quantum_info.PauliList.size")                   | The number of Pauli rows in the table.                               |
| [`x`](#qiskit.quantum_info.PauliList.x "qiskit.quantum_info.PauliList.x")                            | The x array for the symplectic representation.                       |
| [`z`](#qiskit.quantum_info.PauliList.z "qiskit.quantum_info.PauliList.z")                            | The z array for the symplectic representation.                       |

### adjoint

<span id="qiskit.quantum_info.PauliList.adjoint" />

`adjoint()`

Return the adjoint of each Pauli in the list.

### anticommutes

<span id="qiskit.quantum_info.PauliList.anticommutes" />

`anticommutes(other, qargs=None)`

Return True if other Pauli that anticommutes with other.

**Parameters**

*   **other** ([*PauliList*](#qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList")) – another PauliList operator.
*   **qargs** (*list*) – qubits to apply dot product on (default: None).

**Returns**

True if Pauli’s anticommute, False if they commute.

**Return type**

bool

### anticommutes\_with\_all

<span id="qiskit.quantum_info.PauliList.anticommutes_with_all" />

`anticommutes_with_all(other)`

Return indexes of rows that commute other.

If other is a multi-row Pauli list the returned vector indexes rows of the current PauliList that anti-commute with *all* Pauli’s in other. If no rows satisfy the condition the returned array will be empty.

**Parameters**

**other** ([*PauliList*](#qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList")) – a single Pauli or multi-row PauliList.

**Returns**

index array of the anti-commuting rows.

**Return type**

array

### argsort

<span id="qiskit.quantum_info.PauliList.argsort" />

`argsort(weight=False, phase=False)`

Return indices for sorting the rows of the table.

The default sort method is lexicographic sorting by qubit number. By using the weight kwarg the output can additionally be sorted by the number of non-identity terms in the Pauli, where the set of all Pauli’s of a given weight are still ordered lexicographically.

**Parameters**

*   **weight** (*bool*) – Optionally sort by weight if True (Default: False).
*   **phase** (*bool*) – Optionally sort by phase before weight or order (Default: False).

**Returns**

the indices for sorting the table.

**Return type**

array

### commutes

<span id="qiskit.quantum_info.PauliList.commutes" />

`commutes(other, qargs=None)`

Return True for each Pauli that commutes with other.

**Parameters**

*   **other** ([*PauliList*](#qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList")) – another PauliList operator.
*   **qargs** (*list*) – qubits to apply dot product on (default: None).

**Returns**

True if Pauli’s commute, False if they anti-commute.

**Return type**

bool

### commutes\_with\_all

<span id="qiskit.quantum_info.PauliList.commutes_with_all" />

`commutes_with_all(other)`

Return indexes of rows that commute other.

If other is a multi-row Pauli list the returned vector indexes rows of the current PauliList that commute with *all* Pauli’s in other. If no rows satisfy the condition the returned array will be empty.

**Parameters**

**other** ([*PauliList*](#qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList")) – a single Pauli or multi-row PauliList.

**Returns**

index array of the commuting rows.

**Return type**

array

### compose

<span id="qiskit.quantum_info.PauliList.compose" />

`compose(other, qargs=None, front=False, inplace=False)`

Return the composition self∘other for each Pauli in the list.

**Parameters**

*   **other** ([*PauliList*](#qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList")) – another PauliList.
*   **qargs** (*None or list*) – qubits to apply dot product on (Default: None).
*   **front** (*bool*) – If True use dot composition method \[default: False].
*   **inplace** (*bool*) – If True update in-place (default: False).

**Returns**

the list of composed Paulis.

**Return type**

[PauliList](#qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList")

**Raises**

**QiskitError** – if other cannot be converted to a PauliList, does not have either 1 or the same number of Paulis as the current list, or has the wrong number of qubits for the specified qargs.

### conjugate

<span id="qiskit.quantum_info.PauliList.conjugate" />

`conjugate()`

Return the conjugate of each Pauli in the list.

### copy

<span id="qiskit.quantum_info.PauliList.copy" />

`copy()`

Make a deep copy of current operator.

### delete

<span id="qiskit.quantum_info.PauliList.delete" />

`delete(ind, qubit=False)`

Return a copy with Pauli rows deleted from table.

When deleting qubits the qubit index is the same as the column index of the underlying `X` and `Z` arrays.

**Parameters**

*   **ind** (*int or list*) – index(es) to delete.
*   **qubit** (*bool*) – if True delete qubit columns, otherwise delete Pauli rows (Default: False).

**Returns**

the resulting table with the entries removed.

**Return type**

[PauliList](#qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList")

**Raises**

**QiskitError** – if ind is out of bounds for the array size or number of qubits.

### dim

<span id="qiskit.quantum_info.PauliList.dim" />

`property dim`

Return tuple (input\_shape, output\_shape).

### dot

<span id="qiskit.quantum_info.PauliList.dot" />

`dot(other, qargs=None, inplace=False)`

Return the composition other∘self for each Pauli in the list.

**Parameters**

*   **other** ([*PauliList*](#qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList")) – another PauliList.
*   **qargs** (*None or list*) – qubits to apply dot product on (Default: None).
*   **inplace** (*bool*) – If True update in-place (default: False).

**Returns**

the list of composed Paulis.

**Return type**

[PauliList](#qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList")

**Raises**

**QiskitError** – if other cannot be converted to a PauliList, does not have either 1 or the same number of Paulis as the current list, or has the wrong number of qubits for the specified qargs.

### equiv

<span id="qiskit.quantum_info.PauliList.equiv" />

`equiv(other)`

Entrywise comparison of Pauli equivalence up to global phase.

**Parameters**

**other** ([*PauliList*](#qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList")  *or*[*Pauli*](qiskit.quantum_info.Pauli "qiskit.quantum_info.Pauli")) – a comparison object.

**Returns**

**An array of True or False for entrywise equivalence**

of the current table.

**Return type**

np.ndarray

### evolve

<span id="qiskit.quantum_info.PauliList.evolve" />

`evolve(other, qargs=None)`

Evolve the Pauli by a Clifford.

This returns the Pauli $P^\prime = C.P.C^\dagger$.

**Parameters**

*   **other** ([*Pauli*](qiskit.quantum_info.Pauli "qiskit.quantum_info.Pauli")  *or*[*Clifford*](qiskit.quantum_info.Clifford "qiskit.quantum_info.Clifford")  *or*[*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – The Clifford operator to evolve by.
*   **qargs** (*list*) – a list of qubits to apply the Clifford to.

**Returns**

the Pauli $C.P.C^\dagger$.

**Return type**

[Pauli](qiskit.quantum_info.Pauli "qiskit.quantum_info.Pauli")

**Raises**

**QiskitError** – if the Clifford number of qubits and qargs don’t match.

### expand

<span id="qiskit.quantum_info.PauliList.expand" />

`expand(other)`

Return the expand product of each Pauli in the list.

**Parameters**

**other** ([*PauliList*](#qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList")) – another PauliList.

**Returns**

the list of tensor product Paulis.

**Return type**

[PauliList](#qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList")

**Raises**

**QiskitError** – if other cannot be converted to a PauliList, does not have either 1 or the same number of Paulis as the current list.

### from\_symplectic

<span id="qiskit.quantum_info.PauliList.from_symplectic" />

`classmethod from_symplectic(z, x, phase=0)`

Construct a PauliList from a symplectic data.

**Parameters**

*   **z** (*np.ndarray*) – 2D boolean Numpy array.
*   **x** (*np.ndarray*) – 2D boolean Numpy array.
*   **phase** (*np.ndarray or None*) – Optional, 1D integer array from Z\_4.

**Returns**

the constructed PauliList.

**Return type**

[PauliList](#qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList")

### input\_dims

<span id="qiskit.quantum_info.PauliList.input_dims" />

`input_dims(qargs=None)`

Return tuple of input dimension for specified subsystems.

### insert

<span id="qiskit.quantum_info.PauliList.insert" />

`insert(ind, value, qubit=False)`

Insert Pauli’s into the table.

When inserting qubits the qubit index is the same as the column index of the underlying `X` and `Z` arrays.

**Parameters**

*   **ind** (*int*) – index to insert at.
*   **value** ([*PauliList*](#qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList")) – values to insert.
*   **qubit** (*bool*) – if True delete qubit columns, otherwise delete Pauli rows (Default: False).

**Returns**

the resulting table with the entries inserted.

**Return type**

[PauliList](#qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList")

**Raises**

**QiskitError** – if the insertion index is invalid.

### inverse

<span id="qiskit.quantum_info.PauliList.inverse" />

`inverse()`

Return the inverse of each Pauli in the list.

### label\_iter

<span id="qiskit.quantum_info.PauliList.label_iter" />

`label_iter()`

Return a label representation iterator.

This is a lazy iterator that converts each row into the string label only as it is used. To convert the entire table to labels use the [`to_labels()`](#qiskit.quantum_info.PauliList.to_labels "qiskit.quantum_info.PauliList.to_labels") method.

**Returns**

label iterator object for the PauliList.

**Return type**

LabelIterator

### matrix\_iter

<span id="qiskit.quantum_info.PauliList.matrix_iter" />

`matrix_iter(sparse=False)`

Return a matrix representation iterator.

This is a lazy iterator that converts each row into the Pauli matrix representation only as it is used. To convert the entire table to matrices use the [`to_matrix()`](#qiskit.quantum_info.PauliList.to_matrix "qiskit.quantum_info.PauliList.to_matrix") method.

**Parameters**

**sparse** (*bool*) – optionally return sparse CSR matrices if True, otherwise return Numpy array matrices (Default: False)

**Returns**

matrix iterator object for the PauliList.

**Return type**

MatrixIterator

### num\_qubits

<span id="qiskit.quantum_info.PauliList.num_qubits" />

`property num_qubits`

Return the number of qubits if a N-qubit operator or None otherwise.

### output\_dims

<span id="qiskit.quantum_info.PauliList.output_dims" />

`output_dims(qargs=None)`

Return tuple of output dimension for specified subsystems.

### phase

<span id="qiskit.quantum_info.PauliList.phase" />

`property phase`

Return the phase exponent of the PauliList.

### power

<span id="qiskit.quantum_info.PauliList.power" />

`power(n)`

Return the compose of a operator with itself n times.

**Parameters**

**n** (*int*) – the number of times to compose with self (n>0).

**Returns**

the n-times composed operator.

**Return type**

[Pauli](qiskit.quantum_info.Pauli "qiskit.quantum_info.Pauli")

**Raises**

**QiskitError** – if the input and output dimensions of the operator are not equal, or the power is not a positive integer.

### qargs

<span id="qiskit.quantum_info.PauliList.qargs" />

`property qargs`

Return the qargs for the operator.

### reshape

<span id="qiskit.quantum_info.PauliList.reshape" />

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

### settings

<span id="qiskit.quantum_info.PauliList.settings" />

`property settings`

Return operator settings.

### shape

<span id="qiskit.quantum_info.PauliList.shape" />

`property shape`

The full shape of the `array()`

### size

<span id="qiskit.quantum_info.PauliList.size" />

`property size`

The number of Pauli rows in the table.

### sort

<span id="qiskit.quantum_info.PauliList.sort" />

`sort(weight=False, phase=False)`

Sort the rows of the table.

The default sort method is lexicographic sorting by qubit number. By using the weight kwarg the output can additionally be sorted by the number of non-identity terms in the Pauli, where the set of all Pauli’s of a given weight are still ordered lexicographically.

**Example**

Consider sorting all a random ordering of all 2-qubit Paulis

```python
from numpy.random import shuffle
from qiskit.quantum_info.operators import PauliList

# 2-qubit labels
labels = ['II', 'IX', 'IY', 'IZ', 'XI', 'XX', 'XY', 'XZ',
          'YI', 'YX', 'YY', 'YZ', 'ZI', 'ZX', 'ZY', 'ZZ']
# Shuffle Labels
shuffle(labels)
pt = PauliList(labels)
print('Initial Ordering')
print(pt)

# Lexicographic Ordering
srt = pt.sort()
print('Lexicographically sorted')
print(srt)

# Weight Ordering
srt = pt.sort(weight=True)
print('Weight sorted')
print(srt)
```

```python
Initial Ordering
['XI', 'YI', 'ZX', 'IY', 'YX', 'IX', 'YZ', 'ZI', 'XY', 'IZ', 'XZ', 'YY',
 'ZY', 'ZZ', 'XX', 'II']
Lexicographically sorted
['II', 'IX', 'IY', 'IZ', 'XI', 'XX', 'XY', 'XZ', 'YI', 'YX', 'YY', 'YZ',
 'ZI', 'ZX', 'ZY', 'ZZ']
Weight sorted
['II', 'IX', 'IY', 'IZ', 'XI', 'YI', 'ZI', 'XX', 'XY', 'XZ', 'YX', 'YY',
 'YZ', 'ZX', 'ZY', 'ZZ']
```

**Parameters**

*   **weight** (*bool*) – optionally sort by weight if True (Default: False).
*   **phase** (*bool*) – Optionally sort by phase before weight or order (Default: False).

**Returns**

a sorted copy of the original table.

**Return type**

[PauliList](#qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList")

### tensor

<span id="qiskit.quantum_info.PauliList.tensor" />

`tensor(other)`

Return the tensor product with each Pauli in the list.

**Parameters**

**other** ([*PauliList*](#qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList")) – another PauliList.

**Returns**

the list of tensor product Paulis.

**Return type**

[PauliList](#qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList")

**Raises**

**QiskitError** – if other cannot be converted to a PauliList, does not have either 1 or the same number of Paulis as the current list.

### to\_labels

<span id="qiskit.quantum_info.PauliList.to_labels" />

`to_labels(array=False)`

Convert a PauliList to a list Pauli string labels.

For large PauliLists converting using the `array=True` kwarg will be more efficient since it allocates memory for the full Numpy array of labels in advance.

| Label | Symplectic | Matrix                                          |
| ----- | ---------- | ----------------------------------------------- |
| `"I"` | $[0, 0]$   | $\begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}$  |
| `"X"` | $[1, 0]$   | $\begin{bmatrix} 0 & 1 \\ 1 & 0 \end{bmatrix}$  |
| `"Y"` | $[1, 1]$   | $\begin{bmatrix} 0 & -i \\ i & 0 \end{bmatrix}$ |
| `"Z"` | $[0, 1]$   | $\begin{bmatrix} 1 & 0 \\ 0 & -1 \end{bmatrix}$ |

**Parameters**

**array** (*bool*) – return a Numpy array if True, otherwise return a list (Default: False).

**Returns**

The rows of the PauliList in label form.

**Return type**

list or array

### to\_matrix

<span id="qiskit.quantum_info.PauliList.to_matrix" />

`to_matrix(sparse=False, array=False)`

Convert to a list or array of Pauli matrices.

For large PauliLists converting using the `array=True` kwarg will be more efficient since it allocates memory a full rank-3 Numpy array of matrices in advance.

| Label | Symplectic | Matrix                                          |
| ----- | ---------- | ----------------------------------------------- |
| `"I"` | $[0, 0]$   | $\begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}$  |
| `"X"` | $[1, 0]$   | $\begin{bmatrix} 0 & 1 \\ 1 & 0 \end{bmatrix}$  |
| `"Y"` | $[1, 1]$   | $\begin{bmatrix} 0 & -i \\ i & 0 \end{bmatrix}$ |
| `"Z"` | $[0, 1]$   | $\begin{bmatrix} 1 & 0 \\ 0 & -1 \end{bmatrix}$ |

**Parameters**

*   **sparse** (*bool*) – if True return sparse CSR matrices, otherwise return dense Numpy arrays (Default: False).
*   **array** (*bool*) – return as rank-3 numpy array if True, otherwise return a list of Numpy arrays (Default: False).

**Returns**

A list of dense Pauli matrices if array=False and sparse=False. list: A list of sparse Pauli matrices if array=False and sparse=True. array: A dense rank-3 array of Pauli matrices if array=True.

**Return type**

list

### transpose

<span id="qiskit.quantum_info.PauliList.transpose" />

`transpose()`

Return the transpose of each Pauli in the list.

### unique

<span id="qiskit.quantum_info.PauliList.unique" />

`unique(return_index=False, return_counts=False)`

Return unique Paulis from the table.

**Example**

```python
from qiskit.quantum_info.operators import PauliList

pt = PauliList(['X', 'Y', '-X', 'I', 'I', 'Z', 'X', 'iZ'])
unique = pt.unique()
print(unique)
```

```python
['X', 'Y', '-X', 'I', 'Z', 'iZ']
```

**Parameters**

*   **return\_index** (*bool*) – If True, also return the indices that result in the unique array. (Default: False)
*   **return\_counts** (*bool*) – If True, also return the number of times each unique item appears in the table.

**Returns**

**unique**

the table of the unique rows.

**unique\_indices: np.ndarray, optional**

The indices of the first occurrences of the unique values in the original array. Only provided if `return_index` is True.

**unique\_counts: np.array, optional**

The number of times each of the unique values comes up in the original array. Only provided if `return_counts` is True.

**Return type**

[PauliList](#qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList")

### x

<span id="qiskit.quantum_info.PauliList.x" />

`property x`

The x array for the symplectic representation.

### z

<span id="qiskit.quantum_info.PauliList.z" />

`property z`

The z array for the symplectic representation.

