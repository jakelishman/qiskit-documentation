---
title: SparseVectorStateFn
description: API reference for qiskit.opflow.state_fns.SparseVectorStateFn
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.opflow.state_fns.SparseVectorStateFn
---

# SparseVectorStateFn

<span id="qiskit.opflow.state_fns.SparseVectorStateFn" />

`SparseVectorStateFn(primitive, coeff=1.0, is_measurement=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/opflow/state_fns/sparse_vector_state_fn.py "view source code")

Bases: [`qiskit.opflow.state_fns.state_fn.StateFn`](qiskit.opflow.state_fns.StateFn "qiskit.opflow.state_fns.state_fn.StateFn")

A class for sparse state functions and measurements in vector representation.

This class uses `scipy.sparse.spmatrix` for the internal representation.

**Parameters**

*   **primitive** (`spmatrix`) – The underlying sparse vector.
*   **coeff** (`Union`\[`complex`, [`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")]) – A coefficient multiplying the state function.
*   **is\_measurement** (`bool`) – Whether the StateFn is a measurement operator

**Raises**

*   **ValueError** – If the primitive is not a column vector.
*   **ValueError** – If the number of elements in the primitive is not a power of 2.

## Methods Defined Here

### add

<span id="qiskit.opflow.state_fns.SparseVectorStateFn.add" />

`SparseVectorStateFn.add(other)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/opflow/state_fns/sparse_vector_state_fn.py "view source code")

Return Operator addition of self and other, overloaded by `+`.

**Parameters**

**other** ([`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")) – An `OperatorBase` with the same number of qubits as self, and in the same ‘Operator’, ‘State function’, or ‘Measurement’ category as self (i.e. the same type of underlying function).

**Return type**

[`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

**Returns**

An `OperatorBase` equivalent to the sum of self and other.

### adjoint

<span id="qiskit.opflow.state_fns.SparseVectorStateFn.adjoint" />

`SparseVectorStateFn.adjoint()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/opflow/state_fns/sparse_vector_state_fn.py "view source code")

Return a new Operator equal to the Operator’s adjoint (conjugate transpose), overloaded by `~`. For StateFns, this also turns the StateFn into a measurement.

**Return type**

[`SparseVectorStateFn`](qiskit.opflow.state_fns.SparseVectorStateFn "qiskit.opflow.state_fns.sparse_vector_state_fn.SparseVectorStateFn")

**Returns**

An `OperatorBase` equivalent to the adjoint of self.

### equals

<span id="qiskit.opflow.state_fns.SparseVectorStateFn.equals" />

`SparseVectorStateFn.equals(other)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/opflow/state_fns/sparse_vector_state_fn.py "view source code")

Evaluate Equality between Operators, overloaded by `==`. Only returns True if self and other are of the same representation (e.g. a DictStateFn and CircuitStateFn will never be equal, even if their vector representations are equal), their underlying primitives are equal (this means for ListOps, OperatorStateFns, or EvolvedOps the equality is evaluated recursively downwards), and their coefficients are equal.

**Parameters**

**other** ([`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")) – The `OperatorBase` to compare to self.

**Return type**

`bool`

**Returns**

A bool equal to the equality of self and other.

### eval

<span id="qiskit.opflow.state_fns.SparseVectorStateFn.eval" />

`SparseVectorStateFn.eval(front=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/opflow/state_fns/sparse_vector_state_fn.py "view source code")

Evaluate the Operator’s underlying function, either on a binary string or another Operator. A square binary Operator can be defined as a function taking a binary function to another binary function. This method returns the value of that function for a given StateFn or binary string. For example, `op.eval('0110').eval('1110')` can be seen as querying the Operator’s matrix representation by row 6 and column 14, and will return the complex value at those “indices.” Similarly for a StateFn, `op.eval('1011')` will return the complex value at row 11 of the vector representation of the StateFn, as all StateFns are defined to be evaluated from Zero implicitly (i.e. it is as if `.eval('0000')` is already called implicitly to always “indexing” from column 0).

If `front` is None, the matrix-representation of the operator is returned.

**Parameters**

**front** (`Union`\[`str`, `Dict`\[`str`, `complex`], `ndarray`, [`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase"), [`Statevector`](qiskit.quantum_info.Statevector "qiskit.quantum_info.states.statevector.Statevector"), `None`]) – The bitstring, dict of bitstrings (with values being coefficients), or StateFn to evaluated by the Operator’s underlying function, or None.

**Return type**

`Union`\[[`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase"), `complex`]

**Returns**

The output of the Operator’s evaluation function. If self is a `StateFn`, the result is a float or complex. If self is an Operator (`PrimitiveOp, ComposedOp, SummedOp, EvolvedOp,` etc.), the result is a StateFn. If `front` is None, the matrix-representation of the operator is returned, which is a `MatrixOp` for the operators and a `VectorStateFn` for state-functions. If either self or front contain proper `ListOps` (not ListOp subclasses), the result is an n-dimensional list of complex or StateFn results, resulting from the recursive evaluation by each OperatorBase in the ListOps.

### primitive\_strings

<span id="qiskit.opflow.state_fns.SparseVectorStateFn.primitive_strings" />

`SparseVectorStateFn.primitive_strings()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/opflow/state_fns/sparse_vector_state_fn.py "view source code")

Return a set of strings describing the primitives contained in the Operator. For example, `{'QuantumCircuit', 'Pauli'}`. For hierarchical Operators, such as `ListOps`, this can help illuminate the primitives represented in the various recursive levels, and therefore which conversions can be applied.

**Return type**

`Set`\[`str`]

**Returns**

A set of strings describing the primitives contained within the Operator.

### sample

<span id="qiskit.opflow.state_fns.SparseVectorStateFn.sample" />

`SparseVectorStateFn.sample(shots=1024, massive=False, reverse_endianness=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/opflow/state_fns/sparse_vector_state_fn.py "view source code")

Sample the state function as a normalized probability distribution. Returns dict of bitstrings in order of probability, with values being probability.

**Parameters**

*   **shots** (`int`) – The number of samples to take to approximate the State function.
*   **massive** (`bool`) – Whether to allow large conversions, e.g. creating a matrix representing over 16 qubits.
*   **reverse\_endianness** (`bool`) – Whether to reverse the endianness of the bitstrings in the return dict to match Terra’s big-endianness.

**Return type**

`dict`

**Returns**

A dict containing pairs sampled strings from the State function and sampling frequency divided by shots.

### to\_circuit\_op

<span id="qiskit.opflow.state_fns.SparseVectorStateFn.to_circuit_op" />

`SparseVectorStateFn.to_circuit_op()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/opflow/state_fns/sparse_vector_state_fn.py "view source code")

Convert this state function to a `CircuitStateFn`.

**Return type**

[`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

### to\_dict\_fn

<span id="qiskit.opflow.state_fns.SparseVectorStateFn.to_dict_fn" />

`SparseVectorStateFn.to_dict_fn()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/opflow/state_fns/sparse_vector_state_fn.py "view source code")

Convert this state function to a `DictStateFn`.

**Return type**

[`StateFn`](qiskit.opflow.state_fns.StateFn "qiskit.opflow.state_fns.state_fn.StateFn")

**Returns**

A new DictStateFn equivalent to `self`.

### to\_matrix

<span id="qiskit.opflow.state_fns.SparseVectorStateFn.to_matrix" />

`SparseVectorStateFn.to_matrix(massive=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/opflow/state_fns/sparse_vector_state_fn.py "view source code")

Return NumPy representation of the Operator. Represents the evaluation of the Operator’s underlying function on every combination of basis binary strings. Warn if more than 16 qubits to force having to set `massive=True` if such a large vector is desired.

**Return type**

`ndarray`

**Returns**

The NumPy `ndarray` equivalent to this Operator.

### to\_matrix\_op

<span id="qiskit.opflow.state_fns.SparseVectorStateFn.to_matrix_op" />

`SparseVectorStateFn.to_matrix_op(massive=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/opflow/state_fns/sparse_vector_state_fn.py "view source code")

Return a `VectorStateFn` for this `StateFn`.

**Parameters**

**massive** (`bool`) – Whether to allow large conversions, e.g. creating a matrix representing over 16 qubits.

**Return type**

[`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

**Returns**

A VectorStateFn equivalent to self.

### to\_spmatrix

<span id="qiskit.opflow.state_fns.SparseVectorStateFn.to_spmatrix" />

`SparseVectorStateFn.to_spmatrix()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/opflow/state_fns/sparse_vector_state_fn.py "view source code")

Return SciPy sparse matrix representation of the Operator. Represents the evaluation of the Operator’s underlying function on every combination of basis binary strings.

**Return type**

[`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

**Returns**

The SciPy `spmatrix` equivalent to this Operator.

## Attributes

<span id="qiskit.opflow.state_fns.SparseVectorStateFn.INDENTATION" />

### INDENTATION

`= '  '`

<span id="qiskit.opflow.state_fns.SparseVectorStateFn.coeff" />

### coeff

A coefficient by which the state function is multiplied.

**Return type**

`Union`\[`complex`, [`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")]

<span id="qiskit.opflow.state_fns.SparseVectorStateFn.instance_id" />

### instance\_id

Return the unique instance id.

**Return type**

`int`

<span id="qiskit.opflow.state_fns.SparseVectorStateFn.is_measurement" />

### is\_measurement

Whether the StateFn object is a measurement Operator.

**Return type**

`bool`

<span id="qiskit.opflow.state_fns.SparseVectorStateFn.num_qubits" />

### num\_qubits

**Return type**

`int`

<span id="qiskit.opflow.state_fns.SparseVectorStateFn.parameters" />

### parameters

<span id="qiskit.opflow.state_fns.SparseVectorStateFn.primitive" />

### primitive

`scipy.sparse._base.spmatrix`

The primitive which defines the behavior of the underlying State function.

<span id="qiskit.opflow.state_fns.SparseVectorStateFn.settings" />

### settings

Return settings.

**Return type**

`Dict`

