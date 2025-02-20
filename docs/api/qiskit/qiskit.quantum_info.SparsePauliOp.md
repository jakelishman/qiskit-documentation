---
title: SparsePauliOp
description: API reference for qiskit.quantum_info.SparsePauliOp
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.quantum_info.SparsePauliOp
---

# SparsePauliOp

<span id="qiskit.quantum_info.SparsePauliOp" />

`qiskit.quantum_info.SparsePauliOp(data, coeffs=None, *, ignore_pauli_phase=False, copy=True)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/quantum_info/operators/symplectic/sparse_pauli_op.py "view source code")

Bases: `LinearOp`

Sparse N-qubit operator in a Pauli basis representation.

This is a sparse representation of an N-qubit matrix [`Operator`](qiskit.quantum_info.Operator "qiskit.quantum_info.Operator") in terms of N-qubit [`PauliList`](qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList") and complex coefficients.

It can be used for performing operator arithmetic for hundred of qubits if the number of non-zero Pauli basis terms is sufficiently small.

The Pauli basis components are stored as a [`PauliList`](qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList") object and can be accessed using the [`paulis`](#qiskit.quantum_info.SparsePauliOp.paulis "qiskit.quantum_info.SparsePauliOp.paulis") attribute. The coefficients are stored as a complex Numpy array vector and can be accessed using the [`coeffs`](#qiskit.quantum_info.SparsePauliOp.coeffs "qiskit.quantum_info.SparsePauliOp.coeffs") attribute.

**Data type of coefficients**

The default `dtype` of the internal `coeffs` Numpy array is `complex128`. Users can configure this by passing `np.ndarray` with a different dtype. For example, a parameterized [`SparsePauliOp`](#qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp") can be made as follows:

```python
>>> import numpy as np
>>> from qiskit.circuit import ParameterVector
>>> from qiskit.quantum_info import SparsePauliOp

>>> SparsePauliOp(["II", "XZ"], np.array(ParameterVector("a", 2)))
SparsePauliOp(['II', 'XZ'],
      coeffs=[ParameterExpression(1.0*a[0]), ParameterExpression(1.0*a[1])])
```

<Admonition title="Note" type="note">
  Parameterized [`SparsePauliOp`](#qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp") does not support the following methods:

  *   `to_matrix(sparse=True)` since `scipy.sparse` cannot have objects as elements.
  *   `to_operator()` since [`Operator`](qiskit.quantum_info.Operator "qiskit.quantum_info.Operator") does not support objects.
  *   `sort`, `argsort` since [`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.ParameterExpression") does not support comparison.
  *   `equiv` since [`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.ParameterExpression") cannot be converted into complex.
  *   `chop` since [`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.ParameterExpression") does not support absolute value.
</Admonition>

Initialize an operator object.

**Parameters**

*   **data** ([*PauliList*](qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList")  *or*[*SparsePauliOp*](#qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp")  *or*[*Pauli*](qiskit.quantum_info.Pauli "qiskit.quantum_info.Pauli")  *or*[*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")  *or*[*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")) – Pauli list of terms. A list of Pauli strings or a Pauli string is also allowed.

*   **coeffs** (*np.ndarray*) –

    complex coefficients for Pauli terms.

    <Admonition title="Note" type="note">
      If `data` is a [`SparsePauliOp`](#qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp") and `coeffs` is not `None`, the value of the `SparsePauliOp.coeffs` will be ignored, and only the passed keyword argument `coeffs` will be used.
    </Admonition>

*   **ignore\_pauli\_phase** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – if true, any `phase` component of a given [`PauliList`](qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList") will be assumed to be zero. This is more efficient in cases where a [`PauliList`](qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList") has been constructed purely for this object, and it is already known that the phases in the ZX-convention are zero. It only makes sense to pass this option when giving [`PauliList`](qiskit.quantum_info.PauliList "qiskit.quantum_info.PauliList") data. (Default: False)

*   **copy** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – copy the input data if True, otherwise assign it directly, if possible. (Default: True)

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – If the input data or coeffs are invalid.

## Attributes

<span id="qiskit.quantum_info.SparsePauliOp.atol" />

### atol

`= 1e-08`

<span id="qiskit.quantum_info.SparsePauliOp.coeffs" />

### coeffs

Return the Pauli coefficients.

<span id="qiskit.quantum_info.SparsePauliOp.dim" />

### dim

Return tuple (input\_shape, output\_shape).

<span id="qiskit.quantum_info.SparsePauliOp.num_qubits" />

### num\_qubits

Return the number of qubits if a N-qubit operator or None otherwise.

<span id="qiskit.quantum_info.SparsePauliOp.parameters" />

### parameters

Return the free `Parameter`s in the coefficients.

<span id="qiskit.quantum_info.SparsePauliOp.paulis" />

### paulis

Return the PauliList.

<span id="qiskit.quantum_info.SparsePauliOp.qargs" />

### qargs

Return the qargs for the operator.

<span id="qiskit.quantum_info.SparsePauliOp.rtol" />

### rtol

`= 1e-05`

<span id="qiskit.quantum_info.SparsePauliOp.settings" />

### settings

Return settings.

<span id="qiskit.quantum_info.SparsePauliOp.size" />

### size

The number of Pauli of Pauli terms in the operator.

## Methods

### adjoint

<span id="qiskit.quantum_info.SparsePauliOp.adjoint" />

`adjoint()`

Return the adjoint of the Operator.

### apply\_layout

<span id="qiskit.quantum_info.SparsePauliOp.apply_layout" />

`apply_layout(layout, num_qubits=None)`

Apply a transpiler layout to this [`SparsePauliOp`](#qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp")

**Parameters**

*   **layout** ([*TranspileLayout*](qiskit.transpiler.TranspileLayout "qiskit.transpiler.TranspileLayout") *| List\[*[*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")*]*) – Either a [`TranspileLayout`](qiskit.transpiler.TranspileLayout "qiskit.transpiler.TranspileLayout") or a list of integers.
*   **num\_qubits** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)") *| None*) – The number of qubits to expand the operator to. If not provided then if `layout` is a [`TranspileLayout`](qiskit.transpiler.TranspileLayout "qiskit.transpiler.TranspileLayout") the number of the transpiler output circuit qubits will be used by default. If `layout` is a list of integers the permutation specified will be applied without any expansion.

**Returns**

A new [`SparsePauliOp`](#qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp") with the provided layout applied

**Return type**

[SparsePauliOp](#qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp")

### argsort

<span id="qiskit.quantum_info.SparsePauliOp.argsort" />

`argsort(weight=False)`

Return indices for sorting the rows of the table.

Returns the composition of permutations in the order of sorting by coefficient and sorting by Pauli. By using the weight kwarg the output can additionally be sorted by the number of non-identity terms in the Pauli, where the set of all Pauli’s of a given weight are still ordered lexicographically.

**Example**

Here is an example of how to use SparsePauliOp argsort.

```python
import numpy as np
from qiskit.quantum_info import SparsePauliOp

# 2-qubit labels
labels = ["XX", "XX", "XX", "YI", "II", "XZ", "XY", "XI"]
# coeffs
coeffs = [2.+1.j, 2.+2.j, 3.+0.j, 3.+0.j, 4.+0.j, 5.+0.j, 6.+0.j, 7.+0.j]

# init
spo = SparsePauliOp(labels, coeffs)
print('Initial Ordering')
print(spo)

# Lexicographic Ordering
srt = spo.argsort()
print('Lexicographically sorted')
print(srt)

# Lexicographic Ordering
srt = spo.argsort(weight=False)
print('Lexicographically sorted')
print(srt)

# Weight Ordering
srt = spo.argsort(weight=True)
print('Weight sorted')
print(srt)
```

```python
Initial Ordering
SparsePauliOp(['XX', 'XX', 'XX', 'YI', 'II', 'XZ', 'XY', 'XI'],
              coeffs=[2.+1.j, 2.+2.j, 3.+0.j, 3.+0.j, 4.+0.j, 5.+0.j, 6.+0.j, 7.+0.j])
Lexicographically sorted
[4 7 0 1 2 6 5 3]
Lexicographically sorted
[4 7 0 1 2 6 5 3]
Weight sorted
[4 7 3 0 1 2 6 5]
```

**Parameters**

*   **weight** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – optionally sort by weight if True (Default: False).
*   **sorted** (*By using the weight kwarg the output can additionally be*) –
*   **Pauli.** (*by the number of non-identity terms in the*) –

**Returns**

the indices for sorting the table.

**Return type**

array

### assign\_parameters

<span id="qiskit.quantum_info.SparsePauliOp.assign_parameters" />

`assign_parameters(parameters, inplace=False)`

Bind the free `Parameter`s in the coefficients to provided values.

**Parameters**

*   **parameters** (*Mapping\[*[*Parameter*](qiskit.circuit.Parameter "qiskit.circuit.Parameter")*,* [*complex*](https://docs.python.org/3/library/functions.html#complex "(in Python v3.12)")  *|*[*ParameterExpression*](qiskit.circuit.ParameterExpression "qiskit.circuit.ParameterExpression")*] | Sequence\[*[*complex*](https://docs.python.org/3/library/functions.html#complex "(in Python v3.12)")  *|*[*ParameterExpression*](qiskit.circuit.ParameterExpression "qiskit.circuit.ParameterExpression")*]*) – The values to bind the parameters to.
*   **inplace** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – If `False`, a copy of the operator with the bound parameters is returned. If `True` the operator itself is modified.

**Returns**

A copy of the operator with bound parameters, if `inplace` is `False`, otherwise `None`.

**Return type**

[SparsePauliOp](#qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp") | None

### chop

<span id="qiskit.quantum_info.SparsePauliOp.chop" />

`chop(tol=1e-14)`

Set real and imaginary parts of the coefficients to 0 if `< tol` in magnitude.

For example, the operator representing `1+1e-17j X + 1e-17 Y` with a tolerance larger than `1e-17` will be reduced to `1 X` whereas [`SparsePauliOp.simplify()`](#qiskit.quantum_info.SparsePauliOp.simplify "qiskit.quantum_info.SparsePauliOp.simplify") would return `1+1e-17j X`.

If a both the real and imaginary part of a coefficient is 0 after chopping, the corresponding Pauli is removed from the operator.

**Parameters**

**tol** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")) – The absolute tolerance to check whether a real or imaginary part should be set to 0.

**Returns**

This operator with chopped coefficients.

**Return type**

[SparsePauliOp](#qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp")

### compose

<span id="qiskit.quantum_info.SparsePauliOp.compose" />

`compose(other, qargs=None, front=False)`

Return the operator composition with another SparsePauliOp.

**Parameters**

*   **other** ([*SparsePauliOp*](#qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp")) – a SparsePauliOp object.
*   **qargs** ([*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)") *or None*) – Optional, a list of subsystem positions to apply other on. If None apply on all subsystems (default: None).
*   **front** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – If True compose using right operator multiplication, instead of left multiplication \[default: False].

**Returns**

The composed SparsePauliOp.

**Return type**

[SparsePauliOp](#qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp")

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if other cannot be converted to an operator, or has incompatible dimensions for specified subsystems.

<Admonition title="Note" type="note">
  Composition (`&`) by default is defined as left matrix multiplication for matrix operators, while `@` (equivalent to [`dot()`](#qiskit.quantum_info.SparsePauliOp.dot "qiskit.quantum_info.SparsePauliOp.dot")) is defined as right matrix multiplication. That is that `A & B == A.compose(B)` is equivalent to `B @ A == B.dot(A)` when `A` and `B` are of the same type.

  Setting the `front=True` kwarg changes this to right matrix multiplication and is equivalent to the [`dot()`](#qiskit.quantum_info.SparsePauliOp.dot "qiskit.quantum_info.SparsePauliOp.dot") method `A.dot(B) == A.compose(B, front=True)`.
</Admonition>

### conjugate

<span id="qiskit.quantum_info.SparsePauliOp.conjugate" />

`conjugate()`

Return the conjugate of the SparsePauliOp.

### copy

<span id="qiskit.quantum_info.SparsePauliOp.copy" />

`copy()`

Make a deep copy of current operator.

### dot

<span id="qiskit.quantum_info.SparsePauliOp.dot" />

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

### equiv

<span id="qiskit.quantum_info.SparsePauliOp.equiv" />

`equiv(other, atol=None)`

Check if two SparsePauliOp operators are equivalent.

**Parameters**

*   **other** ([*SparsePauliOp*](#qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp")) – an operator object.
*   **atol** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)") *| None*) – Absolute numerical tolerance for checking equivalence.

**Returns**

True if the operator is equivalent to `self`.

**Return type**

[bool](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")

### expand

<span id="qiskit.quantum_info.SparsePauliOp.expand" />

`expand(other)`

Return the reverse-order tensor product with another SparsePauliOp.

**Parameters**

**other** ([*SparsePauliOp*](#qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp")) – a SparsePauliOp object.

**Returns**

**the tensor product $b \otimes a$, where $a$**

is the current SparsePauliOp, and $b$ is the other SparsePauliOp.

**Return type**

[SparsePauliOp](#qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp")

### from\_list

<span id="qiskit.quantum_info.SparsePauliOp.from_list" />

`static from_list(obj, dtype=<class 'complex'>, *, num_qubits=None)`

Construct from a list of Pauli strings and coefficients.

For example, the 5-qubit Hamiltonian

$$
H = Z_1 X_4 + 2 Y_0 Y_3
$$

can be constructed as

```python
# via tuples and the full Pauli string
op = SparsePauliOp.from_list([("XIIZI", 1), ("IYIIY", 2)])
```

**Parameters**

*   **obj** (*Iterable\[Tuple\[*[*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")*,* [*complex*](https://docs.python.org/3/library/functions.html#complex "(in Python v3.12)")*]]*) – The list of 2-tuples specifying the Pauli terms.
*   **dtype** ([*type*](https://docs.python.org/3/library/functions.html#type "(in Python v3.12)")) – The dtype of coeffs (Default: complex).
*   **num\_qubits** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – The number of qubits of the operator (Default: None).

**Returns**

The SparsePauliOp representation of the Pauli terms.

**Return type**

[SparsePauliOp](#qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp")

**Raises**

*   [**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – If an empty list is passed and num\_qubits is None.
*   [**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – If num\_qubits and the objects in the input list do not match.

### from\_operator

<span id="qiskit.quantum_info.SparsePauliOp.from_operator" />

`static from_operator(obj, atol=None, rtol=None)`

Construct from an Operator objector.

Note that the cost of this construction is exponential as it involves taking inner products with every element of the N-qubit Pauli basis.

**Parameters**

*   **obj** ([*Operator*](qiskit.quantum_info.Operator "qiskit.quantum_info.Operator")) – an N-qubit operator.
*   **atol** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")) – Optional. Absolute tolerance for checking if coefficients are zero (Default: 1e-8).
*   **rtol** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")) – Optional. relative tolerance for checking if coefficients are zero (Default: 1e-5).

**Returns**

the SparsePauliOp representation of the operator.

**Return type**

[SparsePauliOp](#qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp")

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if the input operator is not an N-qubit operator.

### from\_sparse\_list

<span id="qiskit.quantum_info.SparsePauliOp.from_sparse_list" />

`static from_sparse_list(obj, num_qubits, do_checks=True, dtype=<class 'complex'>)`

Construct from a list of local Pauli strings and coefficients.

Each list element is a 3-tuple of a local Pauli string, indices where to apply it, and a coefficient.

For example, the 5-qubit Hamiltonian

$$
H = Z_1 X_4 + 2 Y_0 Y_3
$$

can be constructed as

```python
# via triples and local Paulis with indices
op = SparsePauliOp.from_sparse_list([("ZX", [1, 4], 1), ("YY", [0, 3], 2)], num_qubits=5)

# equals the following construction from "dense" Paulis
op = SparsePauliOp.from_list([("XIIZI", 1), ("IYIIY", 2)])
```

**Parameters**

*   **obj** (*Iterable\[*[*tuple*](https://docs.python.org/3/library/stdtypes.html#tuple "(in Python v3.12)")*\[*[*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")*,* [*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")*\[*[*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")*],* [*complex*](https://docs.python.org/3/library/functions.html#complex "(in Python v3.12)")*]]*) – The list 3-tuples specifying the Paulis.
*   **num\_qubits** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – The number of qubits of the operator.
*   **do\_checks** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – The flag of checking if the input indices are not duplicated
*   \*\*(\*\***Default** – True).
*   **dtype** ([*type*](https://docs.python.org/3/library/functions.html#type "(in Python v3.12)")) – The dtype of coeffs (Default: complex).

**Returns**

The SparsePauliOp representation of the Pauli terms.

**Return type**

[SparsePauliOp](#qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp")

**Raises**

*   [**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – If the number of qubits is incompatible with the indices of the Pauli terms.
*   [**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – If the designated qubit is already assigned.

### group\_commuting

<span id="qiskit.quantum_info.SparsePauliOp.group_commuting" />

`group_commuting(qubit_wise=False)`

Partition a SparsePauliOp into sets of commuting Pauli strings.

**Parameters**

**qubit\_wise** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) –

whether the commutation rule is applied to the whole operator, or on a per-qubit basis. For example:

```python
>>> op = SparsePauliOp.from_list([("XX", 2), ("YY", 1), ("IZ",2j), ("ZZ",1j)])
>>> op.group_commuting()
[SparsePauliOp(["IZ", "ZZ"], coeffs=[0.+2.j, 0.+1j]),
 SparsePauliOp(["XX", "YY"], coeffs=[2.+0.j, 1.+0.j])]
>>> op.group_commuting(qubit_wise=True)
[SparsePauliOp(['XX'], coeffs=[2.+0.j]),
 SparsePauliOp(['YY'], coeffs=[1.+0.j]),
 SparsePauliOp(['IZ', 'ZZ'], coeffs=[0.+2.j, 0.+1.j])]
```

**Returns**

**List of SparsePauliOp where each SparsePauliOp contains**

commuting Pauli operators.

**Return type**

[list](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")\[[SparsePauliOp](#qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp")]

### input\_dims

<span id="qiskit.quantum_info.SparsePauliOp.input_dims" />

`input_dims(qargs=None)`

Return tuple of input dimension for specified subsystems.

### is\_unitary

<span id="qiskit.quantum_info.SparsePauliOp.is_unitary" />

`is_unitary(atol=None, rtol=None)`

Return True if operator is a unitary matrix.

**Parameters**

*   **atol** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")) – Optional. Absolute tolerance for checking if coefficients are zero (Default: 1e-8).
*   **rtol** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")) – Optional. relative tolerance for checking if coefficients are zero (Default: 1e-5).

**Returns**

True if the operator is unitary, False otherwise.

**Return type**

[bool](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")

### label\_iter

<span id="qiskit.quantum_info.SparsePauliOp.label_iter" />

`label_iter()`

Return a label representation iterator.

This is a lazy iterator that converts each term in the SparsePauliOp into a tuple (label, coeff). To convert the entire table to labels use the `to_labels()` method.

**Returns**

label iterator object for the SparsePauliOp.

**Return type**

LabelIterator

### matrix\_iter

<span id="qiskit.quantum_info.SparsePauliOp.matrix_iter" />

`matrix_iter(sparse=False)`

Return a matrix representation iterator.

This is a lazy iterator that converts each term in the SparsePauliOp into a matrix as it is used. To convert to a single matrix use the [`to_matrix()`](#qiskit.quantum_info.SparsePauliOp.to_matrix "qiskit.quantum_info.SparsePauliOp.to_matrix") method.

**Parameters**

**sparse** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – optionally return sparse CSR matrices if True, otherwise return Numpy array matrices (Default: False)

**Returns**

matrix iterator object for the PauliList.

**Return type**

MatrixIterator

### output\_dims

<span id="qiskit.quantum_info.SparsePauliOp.output_dims" />

`output_dims(qargs=None)`

Return tuple of output dimension for specified subsystems.

### power

<span id="qiskit.quantum_info.SparsePauliOp.power" />

`power(n)`

Return the compose of a operator with itself n times.

**Parameters**

**n** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – the number of times to compose with self (n>0).

**Returns**

the n-times composed operator.

**Return type**

[Clifford](qiskit.quantum_info.Clifford "qiskit.quantum_info.Clifford")

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if the input and output dimensions of the operator are not equal, or the power is not a positive integer.

### reshape

<span id="qiskit.quantum_info.SparsePauliOp.reshape" />

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

### simplify

<span id="qiskit.quantum_info.SparsePauliOp.simplify" />

`simplify(atol=None, rtol=None)`

Simplify PauliList by combining duplicates and removing zeros.

**Parameters**

*   **atol** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")) – Optional. Absolute tolerance for checking if coefficients are zero (Default: 1e-8).
*   **rtol** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")) – Optional. relative tolerance for checking if coefficients are zero (Default: 1e-5).

**Returns**

the simplified SparsePauliOp operator.

**Return type**

[SparsePauliOp](#qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp")

### sort

<span id="qiskit.quantum_info.SparsePauliOp.sort" />

`sort(weight=False)`

Sort the rows of the table.

After sorting the coefficients using numpy’s argsort, sort by Pauli. Pauli sort takes precedence. If Pauli is the same, it will be sorted by coefficient. By using the weight kwarg the output can additionally be sorted by the number of non-identity terms in the Pauli, where the set of all Pauli’s of a given weight are still ordered lexicographically.

**Example**

Here is an example of how to use SparsePauliOp sort.

```python
import numpy as np
from qiskit.quantum_info import SparsePauliOp

# 2-qubit labels
labels = ["XX", "XX", "XX", "YI", "II", "XZ", "XY", "XI"]
# coeffs
coeffs = [2.+1.j, 2.+2.j, 3.+0.j, 3.+0.j, 4.+0.j, 5.+0.j, 6.+0.j, 7.+0.j]

# init
spo = SparsePauliOp(labels, coeffs)
print('Initial Ordering')
print(spo)

# Lexicographic Ordering
srt = spo.sort()
print('Lexicographically sorted')
print(srt)

# Lexicographic Ordering
srt = spo.sort(weight=False)
print('Lexicographically sorted')
print(srt)

# Weight Ordering
srt = spo.sort(weight=True)
print('Weight sorted')
print(srt)
```

```python
Initial Ordering
SparsePauliOp(['XX', 'XX', 'XX', 'YI', 'II', 'XZ', 'XY', 'XI'],
              coeffs=[2.+1.j, 2.+2.j, 3.+0.j, 3.+0.j, 4.+0.j, 5.+0.j, 6.+0.j, 7.+0.j])
Lexicographically sorted
SparsePauliOp(['II', 'XI', 'XX', 'XX', 'XX', 'XY', 'XZ', 'YI'],
              coeffs=[4.+0.j, 7.+0.j, 2.+1.j, 2.+2.j, 3.+0.j, 6.+0.j, 5.+0.j, 3.+0.j])
Lexicographically sorted
SparsePauliOp(['II', 'XI', 'XX', 'XX', 'XX', 'XY', 'XZ', 'YI'],
              coeffs=[4.+0.j, 7.+0.j, 2.+1.j, 2.+2.j, 3.+0.j, 6.+0.j, 5.+0.j, 3.+0.j])
Weight sorted
SparsePauliOp(['II', 'XI', 'YI', 'XX', 'XX', 'XX', 'XY', 'XZ'],
              coeffs=[4.+0.j, 7.+0.j, 3.+0.j, 2.+1.j, 2.+2.j, 3.+0.j, 6.+0.j, 5.+0.j])
```

**Parameters**

*   **weight** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – optionally sort by weight if True (Default: False).
*   **sorted** (*By using the weight kwarg the output can additionally be*) –
*   **Pauli.** (*by the number of non-identity terms in the*) –

**Returns**

a sorted copy of the original table.

**Return type**

[SparsePauliOp](#qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp")

### sum

<span id="qiskit.quantum_info.SparsePauliOp.sum" />

`static sum(ops)`

Sum of SparsePauliOps.

This is a specialized version of the builtin `sum` function for SparsePauliOp with smaller overhead.

**Parameters**

**ops** ([*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")*\[*[*SparsePauliOp*](#qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp")*]*) – a list of SparsePauliOps.

**Returns**

the SparsePauliOp representing the sum of the input list.

**Return type**

[SparsePauliOp](#qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp")

**Raises**

*   [**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if the input list is empty.
*   [**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if the input list includes an object that is not SparsePauliOp.
*   [**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if the numbers of qubits of the objects in the input list do not match.

### tensor

<span id="qiskit.quantum_info.SparsePauliOp.tensor" />

`tensor(other)`

Return the tensor product with another SparsePauliOp.

**Parameters**

**other** ([*SparsePauliOp*](#qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp")) – a SparsePauliOp object.

**Returns**

**the tensor product $a \otimes b$, where $a$**

is the current SparsePauliOp, and $b$ is the other SparsePauliOp.

**Return type**

[SparsePauliOp](#qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp")

<Admonition title="Note" type="note">
  The tensor product can be obtained using the `^` binary operator. Hence `a.tensor(b)` is equivalent to `a ^ b`.
</Admonition>

### to\_list

<span id="qiskit.quantum_info.SparsePauliOp.to_list" />

`to_list(array=False)`

Convert to a list Pauli string labels and coefficients.

For operators with a lot of terms converting using the `array=True` kwarg will be more efficient since it allocates memory for the full Numpy array of labels in advance.

**Parameters**

**array** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – return a Numpy array if True, otherwise return a list (Default: False).

**Returns**

List of pairs (label, coeff) for rows of the PauliList.

**Return type**

[list](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)") or array

### to\_matrix

<span id="qiskit.quantum_info.SparsePauliOp.to_matrix" />

`to_matrix(sparse=False)`

Convert to a dense or sparse matrix.

**Parameters**

**sparse** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – if True return a sparse CSR matrix, otherwise return dense Numpy array (Default: False).

**Returns**

A dense matrix if sparse=False. csr\_matrix: A sparse matrix in CSR format if sparse=True.

**Return type**

array

### to\_operator

<span id="qiskit.quantum_info.SparsePauliOp.to_operator" />

`to_operator()`

Convert to a matrix Operator object

**Return type**

[*Operator*](qiskit.quantum_info.Operator "qiskit.quantum_info.operators.operator.Operator")

### transpose

<span id="qiskit.quantum_info.SparsePauliOp.transpose" />

`transpose()`

Return the transpose of the SparsePauliOp.

