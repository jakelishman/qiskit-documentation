---
title: StabilizerTable
description: API reference for qiskit.quantum_info.StabilizerTable
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.quantum_info.StabilizerTable
---

# StabilizerTable

<span id="qiskit.quantum_info.StabilizerTable" />

`StabilizerTable(data, phase=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/quantum_info/operators/symplectic/stabilizer_table.py "view source code")

Bases: [`qiskit.quantum_info.operators.symplectic.pauli_table.PauliTable`](qiskit.quantum_info.PauliTable "qiskit.quantum_info.operators.symplectic.pauli_table.PauliTable"), `qiskit.quantum_info.operators.mixins.adjoint.AdjointMixin`

Symplectic representation of a list Stabilizer matrices.

**Symplectic Representation**

The symplectic representation of a single-qubit Stabilizer matrix is a pair of boolean values $[x, z]$ and a boolean phase p such that the Stabilizer matrix is given by $S = (-1)^p \sigma_z^z.\sigma_x^x$. The correspondence between labels, symplectic representation, stabilizer matrices, and Pauli matrices for the single-qubit case is shown in the following table.

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

Internally this is stored as a length N boolean phase vector $[p_{N-1}, ..., p_{0}]$ and a [`PauliTable`](qiskit.quantum_info.PauliTable "qiskit.quantum_info.PauliTable") $M \times 2N$ boolean matrix:

$$
\begin{split}\left(\begin{array}{ccc|ccc}
    x_{0,0} & ... & x_{0,N-1} & z_{0,0} & ... & z_{0,N-1}  \\
    x_{1,0} & ... & x_{1,N-1} & z_{1,0} & ... & z_{1,N-1}  \\
    \vdots & \ddots & \vdots & \vdots & \ddots & \vdots  \\
    x_{M-1,0} & ... & x_{M-1,N-1} & z_{M-1,0} & ... & z_{M-1,N-1}
\end{array}\right)\end{split}
$$

where each row is a block vector $[X_i, Z_i]$ with $X_i = [x_{i,0}, ..., x_{i,N-1}]$, $Z_i = [z_{i,0}, ..., z_{i,N-1}]$ is the symplectic representation of an N-qubit Pauli. This representation is based on reference \[1].

StabilizerTable’s can be created from a list of labels using [`from_labels()`](qiskit.quantum_info.StabilizerTable#from_labels "qiskit.quantum_info.StabilizerTable.from_labels"), and converted to a list of labels or a list of matrices using [`to_labels()`](qiskit.quantum_info.StabilizerTable#to_labels "qiskit.quantum_info.StabilizerTable.to_labels") and [`to_matrix()`](qiskit.quantum_info.StabilizerTable#to_matrix "qiskit.quantum_info.StabilizerTable.to_matrix") respectively.

**Group Product**

The product of the stabilizer elements is defined with respect to the matrix multiplication of the matrices in Table 1. In terms of stabilizes labels the dot product group structure is

| A.B   | I | X  | Y  | Z  |
| ----- | - | -- | -- | -- |
| **I** | I | X  | Y  | Z  |
| **X** | X | I  | -Z | Y  |
| **Y** | Y | Z  | -I | -X |
| **Z** | Z | -Y | X  | I  |

The [`dot()`](qiskit.quantum_info.StabilizerTable#dot "qiskit.quantum_info.StabilizerTable.dot") method will return the output for `row.dot(col) = row.col`, while the [`compose()`](qiskit.quantum_info.StabilizerTable#compose "qiskit.quantum_info.StabilizerTable.compose") will return `row.compose(col) = col.row` from the above table.

Note that while this dot product is different to the matrix product of the [`PauliTable`](qiskit.quantum_info.PauliTable "qiskit.quantum_info.PauliTable"), it does not change the commutation structure of elements. Hence `commutes:()` will be the same for the same labels.

**Qubit Ordering**

The qubits are ordered in the table such the least significant qubit \[x\_\{i, 0}, z\_\{i, 0}] is the first element of each of the $X_i, Z_i$ vector blocks. This is the opposite order to position in string labels or matrix tensor products where the least significant qubit is the right-most string character. For example Pauli `"ZX"` has `"X"` on qubit-0 and `"Z"` on qubit 1, and would have symplectic vectors $x=[1, 0]$, $z=[0, 1]$.

**Data Access**

Subsets of rows can be accessed using the list access `[]` operator and will return a table view of part of the StabilizerTable. The underlying phase vector and Pauli array can be directly accessed using the [`phase`](#qiskit.quantum_info.StabilizerTable.phase "qiskit.quantum_info.StabilizerTable.phase") and [`array`](#qiskit.quantum_info.StabilizerTable.array "qiskit.quantum_info.StabilizerTable.array") properties respectively. The sub-arrays for only the X or Z blocks can be accessed using the [`X`](#qiskit.quantum_info.StabilizerTable.X "qiskit.quantum_info.StabilizerTable.X") and [`Z`](#qiskit.quantum_info.StabilizerTable.Z "qiskit.quantum_info.StabilizerTable.Z") properties respectively.

The Pauli part of the Stabilizer table can be viewed and accessed as a [`PauliTable`](qiskit.quantum_info.PauliTable "qiskit.quantum_info.PauliTable") object using the [`pauli`](#qiskit.quantum_info.StabilizerTable.pauli "qiskit.quantum_info.StabilizerTable.pauli") property. Note that this doesn’t copy the underlying array so any changes made to the Pauli table will also change the stabilizer table.

**Iteration**

Rows in the Stabilizer table can be iterated over like a list. Iteration can also be done using the label or matrix representation of each row using the [`label_iter()`](qiskit.quantum_info.StabilizerTable#label_iter "qiskit.quantum_info.StabilizerTable.label_iter") and [`matrix_iter()`](qiskit.quantum_info.StabilizerTable#matrix_iter "qiskit.quantum_info.StabilizerTable.matrix_iter") methods.

## References

1.  S. Aaronson, D. Gottesman, *Improved Simulation of Stabilizer Circuits*, Phys. Rev. A 70, 052328 (2004). [arXiv:quant-ph/0406196](https://arxiv.org/abs/quant-ph/0406196)

Initialize the StabilizerTable.

**Parameters**

*   **data** (*array or str or* [*PauliTable*](qiskit.quantum_info.PauliTable "qiskit.quantum_info.PauliTable")) – input PauliTable data.
*   **phase** (*array or bool or None*) – optional phase vector for input data (Default: None).

**Raises**

**QiskitError** – if input array or phase vector has an invalid shape.

**Additional Information:**

The input array is not copied so multiple Pauli and Stabilizer tables can share the same underlying array.

## Methods

### adjoint

<span id="qiskit.quantum_info.StabilizerTable.adjoint" />

`StabilizerTable.adjoint()`

Return the adjoint of the Operator.

### anticommutes\_with\_all

<span id="qiskit.quantum_info.StabilizerTable.anticommutes_with_all" />

`StabilizerTable.anticommutes_with_all(other)`

Return indexes of rows that commute other.

If other is a multi-row Pauli table the returned vector indexes rows of the current PauliTable that anti-commute with *all* Pauli’s in other. If no rows satisfy the condition the returned array will be empty.

**Parameters**

**other** ([*PauliTable*](qiskit.quantum_info.PauliTable "qiskit.quantum_info.PauliTable")) – a single Pauli or multi-row PauliTable.

**Returns**

index array of the anti-commuting rows.

**Return type**

array

### argsort

<span id="qiskit.quantum_info.StabilizerTable.argsort" />

`StabilizerTable.argsort(weight=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/quantum_info/operators/symplectic/stabilizer_table.py "view source code")

Return indices for sorting the rows of the PauliTable.

The default sort method is lexicographic sorting of Paulis by qubit number. By using the weight kwarg the output can additionally be sorted by the number of non-identity terms in the Stabilizer, where the set of all Pauli’s of a given weight are still ordered lexicographically.

This does not sort based on phase values. It will preserve the original order of rows with the same Pauli’s but different phases.

**Parameters**

**weight** (*bool*) – optionally sort by weight if True (Default: False).

**Returns**

the indices for sorting the table.

**Return type**

array

### commutes

<span id="qiskit.quantum_info.StabilizerTable.commutes" />

`StabilizerTable.commutes(pauli)`

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

<span id="qiskit.quantum_info.StabilizerTable.commutes_with_all" />

`StabilizerTable.commutes_with_all(other)`

Return indexes of rows that commute other.

If other is a multi-row Pauli table the returned vector indexes rows of the current PauliTable that commute with *all* Pauli’s in other. If no rows satisfy the condition the returned array will be empty.

**Parameters**

**other** ([*PauliTable*](qiskit.quantum_info.PauliTable "qiskit.quantum_info.PauliTable")) – a single Pauli or multi-row PauliTable.

**Returns**

index array of the commuting rows.

**Return type**

array

### compose

<span id="qiskit.quantum_info.StabilizerTable.compose" />

`StabilizerTable.compose(other, qargs=None, front=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/quantum_info/operators/symplectic/stabilizer_table.py "view source code")

Return the compose output product of two tables.

This returns the combination of the compose product of all stabilizers in the current table with all stabilizers in the other table.

The individual stabilizer compose product is given by

| `A.compose(B)` | I | X  | Y  | Z  |
| -------------- | - | -- | -- | -- |
| **I**          | I | X  | Y  | Z  |
| **X**          | X | I  | Z  | -Y |
| **Y**          | Y | -Z | -I | X  |
| **Z**          | Z | Y  | -X | I  |

If front=True the composition will be given by the [`dot()`](qiskit.quantum_info.StabilizerTable#dot "qiskit.quantum_info.StabilizerTable.dot") method.

**Example**

```python
from qiskit.quantum_info.operators import StabilizerTable

current = StabilizerTable.from_labels(['+I', '-X'])
other =  StabilizerTable.from_labels(['+X', '-Z'])
print(current.compose(other))
```

```python
StabilizerTable: ['+X', '-Z', '-I', '-Y']
```

**Parameters**

*   **other** ([*StabilizerTable*](qiskit.quantum_info.StabilizerTable "qiskit.quantum_info.StabilizerTable")) – another StabilizerTable.
*   **qargs** (*None or list*) – qubits to apply compose product on (Default: None).
*   **front** (*bool*) – If True use dot composition method (default: False).

**Returns**

the compose outer product table.

**Return type**

[StabilizerTable](qiskit.quantum_info.StabilizerTable "qiskit.quantum_info.StabilizerTable")

**Raises**

**QiskitError** – if other cannot be converted to a StabilizerTable.

### conjugate

<span id="qiskit.quantum_info.StabilizerTable.conjugate" />

`StabilizerTable.conjugate()`

Not implemented.

### copy

<span id="qiskit.quantum_info.StabilizerTable.copy" />

`StabilizerTable.copy()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/quantum_info/operators/symplectic/stabilizer_table.py "view source code")

Return a copy of the StabilizerTable.

### delete

<span id="qiskit.quantum_info.StabilizerTable.delete" />

`StabilizerTable.delete(ind, qubit=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/quantum_info/operators/symplectic/stabilizer_table.py "view source code")

Return a copy with Stabilizer rows deleted from table.

When deleting qubit columns, qubit-0 is the right-most (largest index) column, and qubit-(N-1) is the left-most (0 index) column of the underlying [`X`](qiskit.quantum_info.StabilizerTable#x "qiskit.quantum_info.StabilizerTable.X") and [`Z`](qiskit.quantum_info.StabilizerTable#z "qiskit.quantum_info.StabilizerTable.Z") arrays.

**Parameters**

*   **ind** (*int or list*) – index(es) to delete.
*   **qubit** (*bool*) – if True delete qubit columns, otherwise delete Stabilizer rows (Default: False).

**Returns**

the resulting table with the entries removed.

**Return type**

[StabilizerTable](qiskit.quantum_info.StabilizerTable "qiskit.quantum_info.StabilizerTable")

**Raises**

**QiskitError** – if ind is out of bounds for the array size or number of qubits.

### dot

<span id="qiskit.quantum_info.StabilizerTable.dot" />

`StabilizerTable.dot(other, qargs=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/quantum_info/operators/symplectic/stabilizer_table.py "view source code")

Return the dot output product of two tables.

This returns the combination of the compose product of all stabilizers in the current table with all stabilizers in the other table.

The individual stabilizer dot product is given by

| `A.dot(B)` | I | X  | Y  | Z  |
| ---------- | - | -- | -- | -- |
| **I**      | I | X  | Y  | Z  |
| **X**      | X | I  | -Z | Y  |
| **Y**      | Y | Z  | -I | -X |
| **Z**      | Z | -Y | X  | I  |

**Example**

```python
from qiskit.quantum_info.operators import StabilizerTable

current = StabilizerTable.from_labels(['+I', '-X'])
other =  StabilizerTable.from_labels(['+X', '-Z'])
print(current.dot(other))
```

```python
StabilizerTable: ['+X', '-Z', '-I', '+Y']
```

**Parameters**

*   **other** ([*StabilizerTable*](qiskit.quantum_info.StabilizerTable "qiskit.quantum_info.StabilizerTable")) – another StabilizerTable.
*   **qargs** (*None or list*) – qubits to apply dot product on (Default: None).

**Returns**

the dot outer product table.

**Return type**

[StabilizerTable](qiskit.quantum_info.StabilizerTable "qiskit.quantum_info.StabilizerTable")

**Raises**

**QiskitError** – if other cannot be converted to a StabilizerTable.

### expand

<span id="qiskit.quantum_info.StabilizerTable.expand" />

`StabilizerTable.expand(other)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/quantum_info/operators/symplectic/stabilizer_table.py "view source code")

Return the expand output product of two tables.

This returns the combination of the tensor product of all stabilizers in the other table with all stabilizers in the current table. The current tables qubits will be the least-significant in the returned table. This is the opposite tensor order to [`tensor()`](qiskit.quantum_info.StabilizerTable#tensor "qiskit.quantum_info.StabilizerTable.tensor").

**Example**

```python
from qiskit.quantum_info.operators import StabilizerTable

current = StabilizerTable.from_labels(['+I', '-X'])
other =  StabilizerTable.from_labels(['-Y', '+Z'])
print(current.expand(other))
```

```python
StabilizerTable: ['-YI', '+YX', '+ZI', '-ZX']
```

**Parameters**

**other** ([*StabilizerTable*](qiskit.quantum_info.StabilizerTable "qiskit.quantum_info.StabilizerTable")) – another StabilizerTable.

**Returns**

the expand outer product table.

**Return type**

[StabilizerTable](qiskit.quantum_info.StabilizerTable "qiskit.quantum_info.StabilizerTable")

**Raises**

**QiskitError** – if other cannot be converted to a StabilizerTable.

### from\_labels

<span id="qiskit.quantum_info.StabilizerTable.from_labels" />

`classmethod StabilizerTable.from_labels(labels)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/quantum_info/operators/symplectic/stabilizer_table.py "view source code")

Construct a StabilizerTable from a list of Pauli stabilizer strings.

Pauli Stabilizer string labels are Pauli strings with an optional `"+"` or `"-"` character. If there is no +/-sign a + phase is used by default.

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

**labels** (*list*) – Pauli stabilizer string label(es).

**Returns**

the constructed StabilizerTable.

**Return type**

[StabilizerTable](qiskit.quantum_info.StabilizerTable "qiskit.quantum_info.StabilizerTable")

**Raises**

**QiskitError** – If the input list is empty or contains invalid Pauli stabilizer strings.

### input\_dims

<span id="qiskit.quantum_info.StabilizerTable.input_dims" />

`StabilizerTable.input_dims(qargs=None)`

Return tuple of input dimension for specified subsystems.

### insert

<span id="qiskit.quantum_info.StabilizerTable.insert" />

`StabilizerTable.insert(ind, value, qubit=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/quantum_info/operators/symplectic/stabilizer_table.py "view source code")

Insert stabilizers’s into the table.

When inserting qubit columns, qubit-0 is the right-most (largest index) column, and qubit-(N-1) is the left-most (0 index) column of the underlying [`X`](qiskit.quantum_info.StabilizerTable#x "qiskit.quantum_info.StabilizerTable.X") and [`Z`](qiskit.quantum_info.StabilizerTable#z "qiskit.quantum_info.StabilizerTable.Z") arrays.

**Parameters**

*   **ind** (*int*) – index to insert at.
*   **value** ([*StabilizerTable*](qiskit.quantum_info.StabilizerTable "qiskit.quantum_info.StabilizerTable")) – values to insert.
*   **qubit** (*bool*) – if True delete qubit columns, otherwise delete Pauli rows (Default: False).

**Returns**

the resulting table with the entries inserted.

**Return type**

[StabilizerTable](qiskit.quantum_info.StabilizerTable "qiskit.quantum_info.StabilizerTable")

**Raises**

**QiskitError** – if the insertion index is invalid.

### label\_iter

<span id="qiskit.quantum_info.StabilizerTable.label_iter" />

`StabilizerTable.label_iter()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/quantum_info/operators/symplectic/stabilizer_table.py "view source code")

Return a label representation iterator.

This is a lazy iterator that converts each row into the string label only as it is used. To convert the entire table to labels use the [`to_labels()`](qiskit.quantum_info.StabilizerTable#to_labels "qiskit.quantum_info.StabilizerTable.to_labels") method.

**Returns**

label iterator object for the StabilizerTable.

**Return type**

LabelIterator

### matrix\_iter

<span id="qiskit.quantum_info.StabilizerTable.matrix_iter" />

`StabilizerTable.matrix_iter(sparse=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/quantum_info/operators/symplectic/stabilizer_table.py "view source code")

Return a matrix representation iterator.

This is a lazy iterator that converts each row into the Pauli matrix representation only as it is used. To convert the entire table to matrices use the [`to_matrix()`](qiskit.quantum_info.StabilizerTable#to_matrix "qiskit.quantum_info.StabilizerTable.to_matrix") method.

**Parameters**

**sparse** (*bool*) – optionally return sparse CSR matrices if True, otherwise return Numpy array matrices (Default: False)

**Returns**

matrix iterator object for the StabilizerTable.

**Return type**

MatrixIterator

### output\_dims

<span id="qiskit.quantum_info.StabilizerTable.output_dims" />

`StabilizerTable.output_dims(qargs=None)`

Return tuple of output dimension for specified subsystems.

### power

<span id="qiskit.quantum_info.StabilizerTable.power" />

`StabilizerTable.power(n)`

Return the compose of a operator with itself n times.

**Parameters**

**n** (*int*) – the number of times to compose with self (n>0).

**Returns**

the n-times composed operator.

**Return type**

[Pauli](qiskit.quantum_info.Pauli "qiskit.quantum_info.Pauli")

**Raises**

**QiskitError** – if the input and output dimensions of the operator are not equal, or the power is not a positive integer.

### reshape

<span id="qiskit.quantum_info.StabilizerTable.reshape" />

`StabilizerTable.reshape(input_dims=None, output_dims=None, num_qubits=None)`

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

### sort

<span id="qiskit.quantum_info.StabilizerTable.sort" />

`StabilizerTable.sort(weight=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/quantum_info/operators/symplectic/stabilizer_table.py "view source code")

Sort the rows of the table.

The default sort method is lexicographic sorting by qubit number. By using the weight kwarg the output can additionally be sorted by the number of non-identity terms in the Pauli, where the set of all Pauli’s of a given weight are still ordered lexicographically.

This does not sort based on phase values. It will preserve the original order of rows with the same Pauli’s but different phases.

Consider sorting all a random ordering of all 2-qubit Paulis

```python
from numpy.random import shuffle
from qiskit.quantum_info.operators import StabilizerTable

# 2-qubit labels
labels = ['+II', '+IX', '+IY', '+IZ', '+XI', '+XX', '+XY', '+XZ',
          '+YI', '+YX', '+YY', '+YZ', '+ZI', '+ZX', '+ZY', '+ZZ',
          '-II', '-IX', '-IY', '-IZ', '-XI', '-XX', '-XY', '-XZ',
          '-YI', '-YX', '-YY', '-YZ', '-ZI', '-ZX', '-ZY', '-ZZ']
# Shuffle Labels
shuffle(labels)
st = StabilizerTable.from_labels(labels)
print('Initial Ordering')
print(st)

# Lexicographic Ordering
srt = st.sort()
print('Lexicographically sorted')
print(srt)

# Weight Ordering
srt = st.sort(weight=True)
print('Weight sorted')
print(srt)
```

```python
Initial Ordering
StabilizerTable: ['+XI', '-IY', '+IY', '+YX', '+ZX', '-XX', '+XY', '+ZZ', '+XX', '-XY', '-ZZ', '-IZ', '-ZX', '-ZI', '+ZI', '+IX', '-ZY', '+YI', '-XI', '+II', '-XZ', '-IX', '+IZ', '-YY', '+YZ', '-YZ', '+XZ', '-II', '+ZY', '-YI', '-YX', '+YY']
Lexicographically sorted
StabilizerTable: ['+II', '-II', '+IX', '-IX', '-IY', '+IY', '-IZ', '+IZ', '+XI', '-XI', '-XX', '+XX', '+XY', '-XY', '-XZ', '+XZ', '+YI', '-YI', '+YX', '-YX', '-YY', '+YY', '+YZ', '-YZ', '-ZI', '+ZI', '+ZX', '-ZX', '-ZY', '+ZY', '+ZZ', '-ZZ']
Weight sorted
StabilizerTable: ['+II', '-II', '+IX', '-IX', '-IY', '+IY', '-IZ', '+IZ', '+XI', '-XI', '+YI', '-YI', '-ZI', '+ZI', '-XX', '+XX', '+XY', '-XY', '-XZ', '+XZ', '+YX', '-YX', '-YY', '+YY', '+YZ', '-YZ', '+ZX', '-ZX', '-ZY', '+ZY', '+ZZ', '-ZZ']
```

**Parameters**

**weight** (*bool*) – optionally sort by weight if True (Default: False).

**Returns**

a sorted copy of the original table.

**Return type**

[StabilizerTable](qiskit.quantum_info.StabilizerTable "qiskit.quantum_info.StabilizerTable")

### tensor

<span id="qiskit.quantum_info.StabilizerTable.tensor" />

`StabilizerTable.tensor(other)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/quantum_info/operators/symplectic/stabilizer_table.py "view source code")

Return the tensor output product of two tables.

This returns the combination of the tensor product of all stabilizers in the current table with all stabilizers in the other table. The other tables qubits will be the least-significant in the returned table. This is the opposite tensor order to [`tensor()`](#qiskit.quantum_info.StabilizerTable.tensor "qiskit.quantum_info.StabilizerTable.tensor").

**Example**

```python
from qiskit.quantum_info.operators import StabilizerTable

current = StabilizerTable.from_labels(['+I', '-X'])
other =  StabilizerTable.from_labels(['-Y', '+Z'])
print(current.tensor(other))
```

```python
StabilizerTable: ['-IY', '+IZ', '+XY', '-XZ']
```

**Parameters**

**other** ([*StabilizerTable*](qiskit.quantum_info.StabilizerTable "qiskit.quantum_info.StabilizerTable")) – another StabilizerTable.

**Returns**

the tensor outer product table.

**Return type**

[StabilizerTable](qiskit.quantum_info.StabilizerTable "qiskit.quantum_info.StabilizerTable")

**Raises**

**QiskitError** – if other cannot be converted to a StabilizerTable.

### to\_labels

<span id="qiskit.quantum_info.StabilizerTable.to_labels" />

`StabilizerTable.to_labels(array=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/quantum_info/operators/symplectic/stabilizer_table.py "view source code")

Convert a StabilizerTable to a list Pauli stabilizer string labels.

For large StabilizerTables converting using the `array=True` kwarg will be more efficient since it allocates memory for the full Numpy array of labels in advance.

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

**array** (*bool*) – return a Numpy array if True, otherwise return a list (Default: False).

**Returns**

The rows of the StabilizerTable in label form.

**Return type**

list or array

### to\_matrix

<span id="qiskit.quantum_info.StabilizerTable.to_matrix" />

`StabilizerTable.to_matrix(sparse=False, array=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/quantum_info/operators/symplectic/stabilizer_table.py "view source code")

Convert to a list or array of Stabilizer matrices.

For large StabilizerTables converting using the `array=True` kwarg will be more efficient since it allocates memory for the full rank-3 Numpy array of matrices in advance.

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

*   **sparse** (*bool*) – if True return sparse CSR matrices, otherwise return dense Numpy arrays (Default: False).
*   **array** (*bool*) – return as rank-3 numpy array if True, otherwise return a list of Numpy arrays (Default: False).

**Returns**

A list of dense Pauli matrices if array=False and sparse=False. list: A list of sparse Pauli matrices if array=False and sparse=True. array: A dense rank-3 array of Pauli matrices if array=True.

**Return type**

list

### transpose

<span id="qiskit.quantum_info.StabilizerTable.transpose" />

`StabilizerTable.transpose()`

Not implemented.

### unique

<span id="qiskit.quantum_info.StabilizerTable.unique" />

`StabilizerTable.unique(return_index=False, return_counts=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/quantum_info/operators/symplectic/stabilizer_table.py "view source code")

Return unique stabilizers from the table.

**Example**

```python
from qiskit.quantum_info.operators import StabilizerTable

st = StabilizerTable.from_labels(['+X', '+I', '-I', '-X', '+X', '-X', '+I'])
unique = st.unique()
print(unique)
```

```python
StabilizerTable: ['+X', '+I', '-I', '-X']
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

[StabilizerTable](qiskit.quantum_info.StabilizerTable "qiskit.quantum_info.StabilizerTable")

## Attributes

<span id="qiskit.quantum_info.StabilizerTable.X" />

### X

The X block of the [`array`](#qiskit.quantum_info.StabilizerTable.array "qiskit.quantum_info.StabilizerTable.array").

<span id="qiskit.quantum_info.StabilizerTable.Z" />

### Z

The Z block of the [`array`](#qiskit.quantum_info.StabilizerTable.array "qiskit.quantum_info.StabilizerTable.array").

<span id="qiskit.quantum_info.StabilizerTable.array" />

### array

The underlying boolean array.

<span id="qiskit.quantum_info.StabilizerTable.dim" />

### dim

Return tuple (input\_shape, output\_shape).

<span id="qiskit.quantum_info.StabilizerTable.num_qubits" />

### num\_qubits

Return the number of qubits if a N-qubit operator or None otherwise.

<span id="qiskit.quantum_info.StabilizerTable.pauli" />

### pauli

Return PauliTable

<span id="qiskit.quantum_info.StabilizerTable.phase" />

### phase

Return phase vector

<span id="qiskit.quantum_info.StabilizerTable.qargs" />

### qargs

Return the qargs for the operator.

<span id="qiskit.quantum_info.StabilizerTable.settings" />

### settings

Return settings.

**Return type**

`Dict`

<span id="qiskit.quantum_info.StabilizerTable.shape" />

### shape

The full shape of the [`array()`](#qiskit.quantum_info.StabilizerTable.array "qiskit.quantum_info.StabilizerTable.array")

<span id="qiskit.quantum_info.StabilizerTable.size" />

### size

The number of Pauli rows in the table.

