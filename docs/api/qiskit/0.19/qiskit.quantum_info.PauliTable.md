---
title: PauliTable
description: API reference for qiskit.quantum_info.PauliTable
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.quantum_info.PauliTable
---

# PauliTable

<span id="qiskit.quantum_info.PauliTable" />

`PauliTable(data)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/operators/symplectic/pauli_table.py "view source code")

Symplectic representation of a list Pauli matrices.

**Symplectic Representation**

The symplectic representation of a single-qubit Pauli matrix is a pair of boolean values $[x, z]$ such that the Pauli matrix is given by $P = (-i)^{z * x} \sigma_z^z.\sigma_x^x$. The correspondence between labels, symplectic representation, and matrices for single-qubit Paulis are shown in Table 1.

| Label | Symplectic | Matrix                                          |
| ----- | ---------- | ----------------------------------------------- |
| `"I"` | $[0, 0]$   | $\begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}$  |
| `"X"` | $[1, 0]$   | $\begin{bmatrix} 0 & 1 \\ 1 & 0 \end{bmatrix}$  |
| `"Y"` | $[1, 1]$   | $\begin{bmatrix} 0 & -i \\ i & 0 \end{bmatrix}$ |
| `"Z"` | $[0, 1]$   | $\begin{bmatrix} 1 & 0 \\ 0 & -1 \end{bmatrix}$ |

The full Pauli table is a M x 2N boolean matrix:

$$
\begin{split}\left(\begin{array}{ccc|ccc}
    x_{0,0} & ... & x_{0,N-1} & z_{0,0} & ... & z_{0,N-1}  \\
    x_{1,0} & ... & x_{1,N-1} & z_{1,0} & ... & z_{1,N-1}  \\
    \vdots & \ddots & \vdots & \vdots & \ddots & \vdots  \\
    x_{M-1,0} & ... & x_{M-1,N-1} & z_{M-1,0} & ... & z_{M-1,N-1}
\end{array}\right)\end{split}
$$

where each row is a block vector $[X_i, Z_i]$ with $X = [x_{i,0}, ..., x_{i,N-1}]$, $Z = [z_{i,0}, ..., z_{i,N-1}]$ is the symplectic representation of an N-qubit Pauli. This representation is based on reference \[1].

PauliTable’s can be created from a list of labels using [`from_labels()`](qiskit.quantum_info.PauliTable#from_labels "qiskit.quantum_info.PauliTable.from_labels"), and converted to a list of labels or a list of matrices using [`to_labels()`](qiskit.quantum_info.PauliTable#to_labels "qiskit.quantum_info.PauliTable.to_labels") and [`to_matrix()`](qiskit.quantum_info.PauliTable#to_matrix "qiskit.quantum_info.PauliTable.to_matrix") respectively.

**Group Product**

The Pauli’s in the Pauli table do not represent the full Pauli as they are restricted to having +1 phase. The dot-product for the Pauli’s is defined to discard any phase obtained from matrix multiplication so that we have $X.Z = Z.X = Y$, etc. This means that for the PauliTable class the operator methods [`compose()`](qiskit.quantum_info.PauliTable#compose "qiskit.quantum_info.PauliTable.compose") and [`dot()`](qiskit.quantum_info.PauliTable#dot "qiskit.quantum_info.PauliTable.dot") are equivalent.

| A.B   | I | X | Y | Z |
| ----- | - | - | - | - |
| **I** | I | X | Y | Z |
| **X** | X | I | Z | Y |
| **Y** | Y | Z | I | X |
| **Z** | Z | Y | X | I |

**Qubit Ordering**

The qubits are ordered in the table such the least significant qubit \[x\_\{i, 0}, z\_\{i, 0}] is the first element of each of the $X_i, Z_i$ vector blocks. This is the opposite order to position in string labels or matrix tensor products where the least significant qubit is the right-most string character. For example Pauli `"ZX"` has `"X"` on qubit-0 and `"Z"` on qubit 1, and would have symplectic vectors $x=[1, 0]$, $z=[0, 1]$.

**Data Access**

Subsets of rows can be accessed using the list access `[]` operator and will return a table view of part of the PauliTable. The underlying Numpy array can be directly accessed using the [`array`](qiskit.quantum_info.PauliTable#array "qiskit.quantum_info.PauliTable.array") property, and the sub-arrays for only the X or Z blocks can be accessed using the [`X`](qiskit.quantum_info.PauliTable#x "qiskit.quantum_info.PauliTable.X") and [`Z`](qiskit.quantum_info.PauliTable#z "qiskit.quantum_info.PauliTable.Z") properties respectively.

**Iteration**

Rows in the Pauli table can be iterated over like a list. Iteration can also be done using the label or matrix representation of each row using the [`label_iter()`](qiskit.quantum_info.PauliTable#label_iter "qiskit.quantum_info.PauliTable.label_iter") and [`matrix_iter()`](qiskit.quantum_info.PauliTable#matrix_iter "qiskit.quantum_info.PauliTable.matrix_iter") methods.

## References

1.  S. Aaronson, D. Gottesman, *Improved Simulation of Stabilizer Circuits*, Phys. Rev. A 70, 052328 (2004). [arXiv:quant-ph/0406196](https://arxiv.org/abs/quant-ph/0406196)

Initialize the PauliTable.

**Parameters**

**data** (*array or str or* [*ScalarOp*](qiskit.quantum_info.ScalarOp "qiskit.quantum_info.ScalarOp")  *or*[*PauliTable*](#qiskit.quantum_info.PauliTable "qiskit.quantum_info.PauliTable")) – input data.

**Raises**

**QiskitError** – if input array is invalid shape.

**Additional Information:**

The input array is not copied so multiple Pauli tables can share the same underlying array.

## Attributes

### X

The X block of the [`array`](qiskit.quantum_info.PauliTable#array "qiskit.quantum_info.PauliTable.array").

### Z

The Z block of the [`array`](qiskit.quantum_info.PauliTable#array "qiskit.quantum_info.PauliTable.array").

### array

The underlying boolean array.

### atol

The default absolute tolerance parameter for float comparisons.

### dim

Return tuple (input\_shape, output\_shape).

### num\_qubits

Return the number of qubits if a N-qubit operator or None otherwise.

### qargs

Return the qargs for the operator.

### rtol

The relative tolerance parameter for float comparisons.

### shape

The full shape of the [`array()`](qiskit.quantum_info.PauliTable#array "qiskit.quantum_info.PauliTable.array")

### size

The number of Pauli rows in the table.

## Methods

### \_\_call\_\_

<span id="qiskit.quantum_info.PauliTable.__call__" />

`PauliTable.__call__(qargs)`

Return a clone with qargs set

### \_\_getitem\_\_

<span id="qiskit.quantum_info.PauliTable.__getitem__" />

`PauliTable.__getitem__(key)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/operators/symplectic/pauli_table.py "view source code")

Return a view of the PauliTable.

### \_\_len\_\_

<span id="qiskit.quantum_info.PauliTable.__len__" />

`PauliTable.__len__()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/operators/symplectic/pauli_table.py "view source code")

Return the number of Pauli rows in the table.

### \_\_mul\_\_

<span id="qiskit.quantum_info.PauliTable.__mul__" />

`PauliTable.__mul__(other)`

### add

<span id="qiskit.quantum_info.PauliTable.add" />

`PauliTable.add(other)`

Return the linear operator self + other.

DEPRECATED: use `operator + other` instead.

**Parameters**

**other** (*BaseOperator*) – an operator object.

**Returns**

the operator self + other.

**Return type**

BaseOperator

### adjoint

<span id="qiskit.quantum_info.PauliTable.adjoint" />

`PauliTable.adjoint()`

Return the adjoint of the operator.

### anticommutes\_with\_all

<span id="qiskit.quantum_info.PauliTable.anticommutes_with_all" />

`PauliTable.anticommutes_with_all(other)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/operators/symplectic/pauli_table.py "view source code")

Return indexes of rows that commute other.

If other is a multi-row Pauli table the returned vector indexes rows of the current PauliTable that anti-commute with *all* Pauli’s in other. If no rows satisfy the condition the returned array will be empty.

**Parameters**

**other** ([*PauliTable*](qiskit.quantum_info.PauliTable "qiskit.quantum_info.PauliTable")) – a single Pauli or multi-row PauliTable.

**Returns**

index array of the anti-commuting rows.

**Return type**

array

### argsort

<span id="qiskit.quantum_info.PauliTable.argsort" />

`PauliTable.argsort(weight=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/operators/symplectic/pauli_table.py "view source code")

Return indices for sorting the rows of the table.

The default sort method is lexicographic sorting by qubit number. By using the weight kwarg the output can additionally be sorted by the number of non-identity terms in the Pauli, where the set of all Pauli’s of a given weight are still ordered lexicographically.

**Parameters**

**weight** (*bool*) – optionally sort by weight if True (Default: False).

**Returns**

the indices for sorting the table.

**Return type**

array

### commutes

<span id="qiskit.quantum_info.PauliTable.commutes" />

`PauliTable.commutes(pauli)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/operators/symplectic/pauli_table.py "view source code")

Return list of commutation properties for each row with a Pauli.

The returned vector is the same length as the size of the table and contains True for rows that commute with the Pauli, and False for the rows that anti-commute.

**Parameters**

**pauli** ([*PauliTable*](qiskit.quantum_info.PauliTable "qiskit.quantum_info.PauliTable")) – a single Pauli row.

**Returns**

The boolean vector of which rows commute or anti-commute.

**Return type**

array

**Raises**

**QiskitError** – if input is not a single Pauli row.

### commutes\_with\_all

<span id="qiskit.quantum_info.PauliTable.commutes_with_all" />

`PauliTable.commutes_with_all(other)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/operators/symplectic/pauli_table.py "view source code")

Return indexes of rows that commute other.

If other is a multi-row Pauli table the returned vector indexes rows of the current PauliTable that commute with *all* Pauli’s in other. If no rows satisfy the condition the returned array will be empty.

**Parameters**

**other** ([*PauliTable*](qiskit.quantum_info.PauliTable "qiskit.quantum_info.PauliTable")) – a single Pauli or multi-row PauliTable.

**Returns**

index array of the commuting rows.

**Return type**

array

### compose

<span id="qiskit.quantum_info.PauliTable.compose" />

`PauliTable.compose(other, qargs=None, front=True)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/operators/symplectic/pauli_table.py "view source code")

Return the compose output product of two tables.

This returns the combination of the dot product of all Paulis in the current table with all Pauli’s in the other table and discards the complex phase from the product. Note that for PauliTables this method is equivalent to [`dot()`](qiskit.quantum_info.PauliTable#dot "qiskit.quantum_info.PauliTable.dot") and hence the `front` kwarg does not change the output.

**Example**

```python
from qiskit.quantum_info.operators import PauliTable

current = PauliTable.from_labels(['I', 'X'])
other =  PauliTable.from_labels(['Y', 'Z'])
print(current.compose(other))
```

```python
PauliTable: ['Y', 'Z', 'Z', 'Y']
```

**Parameters**

*   **other** ([*PauliTable*](qiskit.quantum_info.PauliTable "qiskit.quantum_info.PauliTable")) – another PauliTable.
*   **qargs** (*None or list*) – qubits to apply dot product on (Default: None).
*   **front** (*bool*) – If True use dot composition method \[default: False].

**Returns**

the compose outer product table.

**Return type**

[PauliTable](qiskit.quantum_info.PauliTable "qiskit.quantum_info.PauliTable")

**Raises**

**QiskitError** – if other cannot be converted to a PauliTable.

### conjugate

<span id="qiskit.quantum_info.PauliTable.conjugate" />

`PauliTable.conjugate()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/operators/symplectic/pauli_table.py "view source code")

Not implemented.

### copy

<span id="qiskit.quantum_info.PauliTable.copy" />

`PauliTable.copy()`

Make a deep copy of current operator.

### delete

<span id="qiskit.quantum_info.PauliTable.delete" />

`PauliTable.delete(ind, qubit=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/operators/symplectic/pauli_table.py "view source code")

Return a copy with Pauli rows deleted from table.

When deleting qubits the qubit index is the same as the column index of the underlying [`X`](qiskit.quantum_info.PauliTable#x "qiskit.quantum_info.PauliTable.X") and [`Z`](qiskit.quantum_info.PauliTable#z "qiskit.quantum_info.PauliTable.Z") arrays.

**Parameters**

*   **ind** (*int or list*) – index(es) to delete.
*   **qubit** (*bool*) – if True delete qubit columns, otherwise delete Pauli rows (Default: False).

**Returns**

the resulting table with the entries removed.

**Return type**

[PauliTable](qiskit.quantum_info.PauliTable "qiskit.quantum_info.PauliTable")

**Raises**

**QiskitError** – if ind is out of bounds for the array size or number of qubits.

### dot

<span id="qiskit.quantum_info.PauliTable.dot" />

`PauliTable.dot(other, qargs=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/operators/symplectic/pauli_table.py "view source code")

Return the dot output product of two tables.

This returns the combination of the dot product of all Paulis in the current table with all Pauli’s in the other table and discards the complex phase from the product. Note that for PauliTables this method is equivalent to [`compose()`](qiskit.quantum_info.PauliTable#compose "qiskit.quantum_info.PauliTable.compose").

**Example**

```python
from qiskit.quantum_info.operators import PauliTable

current = PauliTable.from_labels(['I', 'X'])
other =  PauliTable.from_labels(['Y', 'Z'])
print(current.dot(other))
```

```python
PauliTable: ['Y', 'Z', 'Z', 'Y']
```

**Parameters**

*   **other** ([*PauliTable*](qiskit.quantum_info.PauliTable "qiskit.quantum_info.PauliTable")) – another PauliTable.
*   **qargs** (*None or list*) – qubits to apply dot product on (Default: None).

**Returns**

the dot outer product table.

**Return type**

[PauliTable](qiskit.quantum_info.PauliTable "qiskit.quantum_info.PauliTable")

**Raises**

**QiskitError** – if other cannot be converted to a PauliTable.

### expand

<span id="qiskit.quantum_info.PauliTable.expand" />

`PauliTable.expand(other)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/operators/symplectic/pauli_table.py "view source code")

Return the expand output product of two tables.

This returns the combination of the tensor product of all Paulis in the other table with all Pauli’s in the current table, with the current tables qubits being the least-significant in the returned table. This is the opposite tensor order to [`tensor()`](qiskit.quantum_info.PauliTable#tensor "qiskit.quantum_info.PauliTable.tensor").

**Example**

```python
from qiskit.quantum_info.operators import PauliTable

current = PauliTable.from_labels(['I', 'X'])
other =  PauliTable.from_labels(['Y', 'Z'])
print(current.expand(other))
```

```python
PauliTable: ['YI', 'ZI', 'YX', 'ZX']
```

**Parameters**

**other** ([*PauliTable*](qiskit.quantum_info.PauliTable "qiskit.quantum_info.PauliTable")) – another PauliTable.

**Returns**

the expand outer product table.

**Return type**

[PauliTable](qiskit.quantum_info.PauliTable "qiskit.quantum_info.PauliTable")

**Raises**

**QiskitError** – if other cannot be converted to a PauliTable.

### from\_labels

<span id="qiskit.quantum_info.PauliTable.from_labels" />

`classmethod PauliTable.from_labels(labels)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/operators/symplectic/pauli_table.py "view source code")

Construct a PauliTable from a list of Pauli strings.

**Parameters**

**labels** (*list*) – Pauli string label(es).

**Returns**

the constructed PauliTable.

**Return type**

[PauliTable](qiskit.quantum_info.PauliTable "qiskit.quantum_info.PauliTable")

**Raises**

*   **QiskitError** – If the input list is empty or contains invalid
*   **Pauli strings.** –

### input\_dims

<span id="qiskit.quantum_info.PauliTable.input_dims" />

`PauliTable.input_dims(qargs=None)`

Return tuple of input dimension for specified subsystems.

### insert

<span id="qiskit.quantum_info.PauliTable.insert" />

`PauliTable.insert(ind, value, qubit=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/operators/symplectic/pauli_table.py "view source code")

Insert Pauli’s into the table.

When inserting qubits the qubit index is the same as the column index of the underlying [`X`](qiskit.quantum_info.PauliTable#x "qiskit.quantum_info.PauliTable.X") and [`Z`](qiskit.quantum_info.PauliTable#z "qiskit.quantum_info.PauliTable.Z") arrays.

**Parameters**

*   **ind** (*int*) – index to insert at.
*   **value** ([*PauliTable*](qiskit.quantum_info.PauliTable "qiskit.quantum_info.PauliTable")) – values to insert.
*   **qubit** (*bool*) – if True delete qubit columns, otherwise delete Pauli rows (Default: False).

**Returns**

the resulting table with the entries inserted.

**Return type**

[PauliTable](qiskit.quantum_info.PauliTable "qiskit.quantum_info.PauliTable")

**Raises**

**QiskitError** – if the insertion index is invalid.

### label\_iter

<span id="qiskit.quantum_info.PauliTable.label_iter" />

`PauliTable.label_iter()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/operators/symplectic/pauli_table.py "view source code")

Return a label representation iterator.

This is a lazy iterator that converts each row into the string label only as it is used. To convert the entire table to labels use the [`to_labels()`](qiskit.quantum_info.PauliTable#to_labels "qiskit.quantum_info.PauliTable.to_labels") method.

**Returns**

label iterator object for the PauliTable.

**Return type**

LabelIterator

### matrix\_iter

<span id="qiskit.quantum_info.PauliTable.matrix_iter" />

`PauliTable.matrix_iter(sparse=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/operators/symplectic/pauli_table.py "view source code")

Return a matrix representation iterator.

This is a lazy iterator that converts each row into the Pauli matrix representation only as it is used. To convert the entire table to matrices use the [`to_matrix()`](qiskit.quantum_info.PauliTable#to_matrix "qiskit.quantum_info.PauliTable.to_matrix") method.

**Parameters**

**sparse** (*bool*) – optionally return sparse CSR matrices if True, otherwise return Numpy array matrices (Default: False)

**Returns**

matrix iterator object for the PauliTable.

**Return type**

MatrixIterator

### multiply

<span id="qiskit.quantum_info.PauliTable.multiply" />

`PauliTable.multiply(other)`

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

### output\_dims

<span id="qiskit.quantum_info.PauliTable.output_dims" />

`PauliTable.output_dims(qargs=None)`

Return tuple of output dimension for specified subsystems.

### power

<span id="qiskit.quantum_info.PauliTable.power" />

`PauliTable.power(n)`

Return the compose of a operator with itself n times.

**Parameters**

**n** (*int*) – the number of times to compose with self (n>0).

**Returns**

the n-times composed operator.

**Return type**

BaseOperator

**Raises**

**QiskitError** – if the input and output dimensions of the operator are not equal, or the power is not a positive integer.

### reshape

<span id="qiskit.quantum_info.PauliTable.reshape" />

`PauliTable.reshape(input_dims=None, output_dims=None)`

Return a shallow copy with reshaped input and output subsystem dimensions.

#### Arg:

#### input\_dims (None or tuple): new subsystem input dimensions.

If None the original input dims will be preserved \[Default: None].

#### output\_dims (None or tuple): new subsystem output dimensions.

If None the original output dims will be preserved \[Default: None].

**Returns**

returns self with reshaped input and output dimensions.

**Return type**

BaseOperator

**Raises**

**QiskitError** – if combined size of all subsystem input dimension or subsystem output dimensions is not constant.

### set\_atol

<span id="qiskit.quantum_info.PauliTable.set_atol" />

`classmethod PauliTable.set_atol(value)`

Set the class default absolute tolerance parameter for float comparisons.

### set\_rtol

<span id="qiskit.quantum_info.PauliTable.set_rtol" />

`classmethod PauliTable.set_rtol(value)`

Set the class default relative tolerance parameter for float comparisons.

### sort

<span id="qiskit.quantum_info.PauliTable.sort" />

`PauliTable.sort(weight=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/operators/symplectic/pauli_table.py "view source code")

Sort the rows of the table.

The default sort method is lexicographic sorting by qubit number. By using the weight kwarg the output can additionally be sorted by the number of non-identity terms in the Pauli, where the set of all Pauli’s of a given weight are still ordered lexicographically.

**Example**

Consider sorting all a random ordering of all 2-qubit Paulis

```python
from numpy.random import shuffle
from qiskit.quantum_info.operators import PauliTable

# 2-qubit labels
labels = ['II', 'IX', 'IY', 'IZ', 'XI', 'XX', 'XY', 'XZ',
          'YI', 'YX', 'YY', 'YZ', 'ZI', 'ZX', 'ZY', 'ZZ']
# Shuffle Labels
shuffle(labels)
pt = PauliTable.from_labels(labels)
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
PauliTable: ['XI', 'ZI', 'XZ', 'YX', 'IY', 'ZZ', 'XY', 'YZ', 'IX', 'II', 'ZY', 'ZX', 'XX', 'YY', 'IZ', 'YI']
Lexicographically sorted
PauliTable: ['II', 'IX', 'IY', 'IZ', 'XI', 'XX', 'XY', 'XZ', 'YI', 'YX', 'YY', 'YZ', 'ZI', 'ZX', 'ZY', 'ZZ']
Weight sorted
PauliTable: ['II', 'IX', 'IY', 'IZ', 'XI', 'YI', 'ZI', 'XX', 'XY', 'XZ', 'YX', 'YY', 'YZ', 'ZX', 'ZY', 'ZZ']
```

**Parameters**

**weight** (*bool*) – optionally sort by weight if True (Default: False).

**Returns**

a sorted copy of the original table.

**Return type**

[PauliTable](qiskit.quantum_info.PauliTable "qiskit.quantum_info.PauliTable")

### subtract

<span id="qiskit.quantum_info.PauliTable.subtract" />

`PauliTable.subtract(other)`

Return the linear operator self - other.

DEPRECATED: use `operator - other` instead.

**Parameters**

**other** (*BaseOperator*) – an operator object.

**Returns**

the operator self - other.

**Return type**

BaseOperator

### tensor

<span id="qiskit.quantum_info.PauliTable.tensor" />

`PauliTable.tensor(other)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/operators/symplectic/pauli_table.py "view source code")

Return the tensor output product of two tables.

This returns the combination of the tensor product of all Paulis in the current table with all Pauli’s in the other table, with the other tables qubits being the least-significant in the returned table. This is the opposite tensor order to [`expand()`](qiskit.quantum_info.PauliTable#expand "qiskit.quantum_info.PauliTable.expand").

**Example**

```python
from qiskit.quantum_info.operators import PauliTable

current = PauliTable.from_labels(['I', 'X'])
other =  PauliTable.from_labels(['Y', 'Z'])
print(current.tensor(other))
```

```python
PauliTable: ['IY', 'IZ', 'XY', 'XZ']
```

**Parameters**

**other** ([*PauliTable*](qiskit.quantum_info.PauliTable "qiskit.quantum_info.PauliTable")) – another PauliTable.

**Returns**

the tensor outer product table.

**Return type**

[PauliTable](qiskit.quantum_info.PauliTable "qiskit.quantum_info.PauliTable")

**Raises**

**QiskitError** – if other cannot be converted to a PauliTable.

### to\_labels

<span id="qiskit.quantum_info.PauliTable.to_labels" />

`PauliTable.to_labels(array=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/operators/symplectic/pauli_table.py "view source code")

Convert a PauliTable to a list Pauli string labels.

For large PauliTables converting using the `array=True` kwarg will be more efficient since it allocates memory for the full Numpy array of labels in advance.

| Label | Symplectic | Matrix                                          |
| ----- | ---------- | ----------------------------------------------- |
| `"I"` | $[0, 0]$   | $\begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}$  |
| `"X"` | $[1, 0]$   | $\begin{bmatrix} 0 & 1 \\ 1 & 0 \end{bmatrix}$  |
| `"Y"` | $[1, 1]$   | $\begin{bmatrix} 0 & -i \\ i & 0 \end{bmatrix}$ |
| `"Z"` | $[0, 1]$   | $\begin{bmatrix} 1 & 0 \\ 0 & -1 \end{bmatrix}$ |

**Parameters**

**array** (*bool*) – return a Numpy array if True, otherwise return a list (Default: False).

**Returns**

The rows of the PauliTable in label form.

**Return type**

list or array

### to\_matrix

<span id="qiskit.quantum_info.PauliTable.to_matrix" />

`PauliTable.to_matrix(sparse=False, array=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/operators/symplectic/pauli_table.py "view source code")

Convert to a list or array of Pauli matrices.

For large PauliTables converting using the `array=True` kwarg will be more efficient since it allocates memory a full rank-3 Numpy array of matrices in advance.

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

<span id="qiskit.quantum_info.PauliTable.transpose" />

`PauliTable.transpose()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/operators/symplectic/pauli_table.py "view source code")

Not implemented.

### unique

<span id="qiskit.quantum_info.PauliTable.unique" />

`PauliTable.unique(return_index=False, return_counts=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/operators/symplectic/pauli_table.py "view source code")

Return unique Paulis from the table.

**Example**

```python
from qiskit.quantum_info.operators import PauliTable

pt = PauliTable.from_labels(['X', 'Y', 'X', 'I', 'I', 'Z', 'X', 'Z'])
unique = pt.unique()
print(unique)
```

```python
PauliTable: ['X', 'Y', 'I', 'Z']
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

[PauliTable](qiskit.quantum_info.PauliTable "qiskit.quantum_info.PauliTable")

