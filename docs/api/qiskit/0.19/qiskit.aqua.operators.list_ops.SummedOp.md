---
title: SummedOp
description: API reference for qiskit.aqua.operators.list_ops.SummedOp
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.operators.list_ops.SummedOp
---

# SummedOp

<span id="qiskit.aqua.operators.list_ops.SummedOp" />

`SummedOp(oplist, coeff=1.0, abelian=False)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/operators/list_ops/summed_op.py "view source code")

A class for lazily representing sums of Operators. Often Operators cannot be efficiently added to one another, but may be manipulated further so that they can be later. This class holds logic to indicate that the Operators in `oplist` are meant to be added together, and therefore if they reach a point in which they can be, such as after evaluation or conversion to matrices, they can be reduced by addition.

**Parameters**

*   **oplist** (`List`\[[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")]) – The Operators being summed.
*   **coeff** (`Union`\[`int`, `float`, `complex`, [`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")]) – A coefficient multiplying the operator
*   **abelian** (`bool`) – Indicates whether the Operators in `oplist` are known to mutually commute.

## Attributes

### abelian

<span id="qiskit.aqua.operators.list_ops.SummedOp.abelian" />

`bool`

Whether the Operators in `oplist` are known to commute with one another.

**Return type**

`bool`

**Returns**

A bool indicating whether the `oplist` is Abelian.

### coeff

<span id="qiskit.aqua.operators.list_ops.SummedOp.coeff" />

`Union[int, float, complex, qiskit.circuit.parameterexpression.ParameterExpression]`

The scalar coefficient multiplying the Operator.

**Return type**

`Union`\[`int`, `float`, `complex`, [`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")]

**Returns**

The coefficient.

### combo\_fn

<span id="qiskit.aqua.operators.list_ops.SummedOp.combo_fn" />

`Callable`

The function defining how to combine `oplist` (or Numbers, or NumPy arrays) to produce the Operator’s underlying function. For example, SummedOp’s combination function is to add all of the Operators in `oplist`.

**Return type**

`Callable`

**Returns**

The combination function.

### distributive

<span id="qiskit.aqua.operators.list_ops.SummedOp.distributive" />

`bool`

Indicates whether the ListOp or subclass is distributive under composition. ListOp and SummedOp are, meaning that (opv @ op) = (opv\[0] @ op + opv\[1] @ op) (using plus for SummedOp, list for ListOp, etc.), while ComposedOp and TensoredOp do not behave this way.

**Return type**

`bool`

**Returns**

A bool indicating whether the ListOp is distributive under composition.

### num\_qubits

<span id="qiskit.aqua.operators.list_ops.SummedOp.num_qubits" />

`int`

The number of qubits over which the Operator is defined. If `op.num_qubits == 5`, then `op.eval('1' * 5)` will be valid, but `op.eval('11')` will not.

**Return type**

`int`

**Returns**

The number of qubits accepted by the Operator’s underlying function.

### oplist

<span id="qiskit.aqua.operators.list_ops.SummedOp.oplist" />

`List[qiskit.aqua.operators.operator_base.OperatorBase]`

The list of `OperatorBases` defining the underlying function of this Operator.

**Return type**

`List`\[[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")]

**Returns**

The Operators defining the ListOp

## Methods

### \_\_getitem\_\_

<span id="qiskit.aqua.operators.list_ops.SummedOp.__getitem__" />

`SummedOp.__getitem__(offset)`

Allows array-indexing style access to the Operators in `oplist`.

**Parameters**

**offset** (`int`) – The index of `oplist` desired.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

**Returns**

The `OperatorBase` at index `offset` of `oplist`.

### \_\_len\_\_

<span id="qiskit.aqua.operators.list_ops.SummedOp.__len__" />

`SummedOp.__len__()`

Length of `oplist`.

**Return type**

`int`

**Returns**

An int equal to the length of `oplist`.

### \_\_mul\_\_

<span id="qiskit.aqua.operators.list_ops.SummedOp.__mul__" />

`SummedOp.__mul__(other)`

Overload `*` for Operator scalar multiplication.

**Parameters**

**other** (`Number`) – The real or complex scalar by which to multiply the Operator, or the `ParameterExpression` to serve as a placeholder for a scalar factor.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

**Returns**

An `OperatorBase` equivalent to product of self and scalar.

### add

<span id="qiskit.aqua.operators.list_ops.SummedOp.add" />

`SummedOp.add(other)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/operators/list_ops/summed_op.py "view source code")

Return Operator addition of self and other, overloaded by `+`.

**Parameters**

**other** ([`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")) – An `OperatorBase` with the same number of qubits as self, and in the same ‘Operator’, ‘State function’, or ‘Measurement’ category as self (i.e. the same type of underlying function).

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

**Returns**

An `OperatorBase` equivalent to the sum of self and other.

### adjoint

<span id="qiskit.aqua.operators.list_ops.SummedOp.adjoint" />

`SummedOp.adjoint()`

Return a new Operator equal to the Operator’s adjoint (conjugate transpose), overloaded by `~`. For StateFns, this also turns the StateFn into a measurement.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

**Returns**

An `OperatorBase` equivalent to the adjoint of self.

### assign\_parameters

<span id="qiskit.aqua.operators.list_ops.SummedOp.assign_parameters" />

`SummedOp.assign_parameters(param_dict)`

Binds scalar values to any Terra `Parameters` in the coefficients or primitives of the Operator, or substitutes one `Parameter` for another. This method differs from Terra’s `assign_parameters` in that it also supports lists of values to assign for a give `Parameter`, in which case self will be copied for each parameterization in the binding list(s), and all the copies will be returned in an `OpList`. If lists of parameterizations are used, every `Parameter` in the param\_dict must have the same length list of parameterizations.

**Parameters**

**param\_dict** (`dict`) – The dictionary of `Parameters` to replace, and values or lists of values by which to replace them.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

**Returns**

The `OperatorBase` with the `Parameters` in self replaced by the values or `Parameters` in param\_dict. If param\_dict contains parameterization lists, this `OperatorBase` is an `OpList`.

### bind\_parameters

<span id="qiskit.aqua.operators.list_ops.SummedOp.bind_parameters" />

`SummedOp.bind_parameters(param_dict)`

Same as assign\_parameters, but maintained for consistency with QuantumCircuit in Terra (which has both assign\_parameters and bind\_parameters).

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

### compose

<span id="qiskit.aqua.operators.list_ops.SummedOp.compose" />

`SummedOp.compose(other)`

Return Operator Composition between self and other (linear algebra-style: A\@B(x) = A(B(x))), overloaded by `@`.

Note: You must be conscious of Quantum Circuit vs. Linear Algebra ordering conventions. Meaning, X.compose(Y) produces an X∘Y on qubit 0, but would produce a QuantumCircuit which looks like

> -\[Y]-\[X]-

Because Terra prints circuits with the initial state at the left side of the circuit.

**Parameters**

**other** ([`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")) – The `OperatorBase` with which to compose self.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

**Returns**

An `OperatorBase` equivalent to the function composition of self and other.

### equals

<span id="qiskit.aqua.operators.list_ops.SummedOp.equals" />

`SummedOp.equals(other)`

Evaluate Equality between Operators, overloaded by `==`. Only returns True if self and other are of the same representation (e.g. a DictStateFn and CircuitStateFn will never be equal, even if their vector representations are equal), their underlying primitives are equal (this means for ListOps, OperatorStateFns, or EvolvedOps the equality is evaluated recursively downwards), and their coefficients are equal.

**Parameters**

**other** ([`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")) – The `OperatorBase` to compare to self.

**Return type**

`bool`

**Returns**

A bool equal to the equality of self and other.

### eval

<span id="qiskit.aqua.operators.list_ops.SummedOp.eval" />

`SummedOp.eval(front=None)`

Evaluate the Operator’s underlying function, either on a binary string or another Operator. A square binary Operator can be defined as a function taking a binary function to another binary function. This method returns the value of that function for a given StateFn or binary string. For example, `op.eval('0110').eval('1110')` can be seen as querying the Operator’s matrix representation by row 6 and column 14, and will return the complex value at those “indices.” Similarly for a StateFn, `op.eval('1011')` will return the complex value at row 11 of the vector representation of the StateFn, as all StateFns are defined to be evaluated from Zero implicitly (i.e. it is as if `.eval('0000')` is already called implicitly to always “indexing” from column 0).

ListOp’s eval recursively evaluates each Operator in `oplist`, and combines the results using the recombination function `combo_fn`.

**Parameters**

**front** (`Union`\[`str`, `Dict`\[`str`, `complex`], [`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase"), `None`]) – The bitstring, dict of bitstrings (with values being coefficients), or StateFn to evaluated by the Operator’s underlying function.

**Return type**

`Union`\[[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase"), `float`, `complex`, `list`]

**Returns**

The output of the `oplist` Operators’ evaluation function, combined with the `combo_fn`. If either self or front contain proper `ListOps` (not ListOp subclasses), the result is an n-dimensional list of complex or StateFn results, resulting from the recursive evaluation by each OperatorBase in the ListOps.

**Raises**

*   **NotImplementedError** – Raised if called for a subclass which is not distributive.
*   **TypeError** – Operators with mixed hierarchies, such as a ListOp containing both PrimitiveOps and ListOps, are not supported.
*   **NotImplementedError** – Attempting to call ListOp’s eval from a non-distributive subclass.

### exp\_i

<span id="qiskit.aqua.operators.list_ops.SummedOp.exp_i" />

`SummedOp.exp_i()`

Return an `OperatorBase` equivalent to an exponentiation of self \* -i, e^(-i\*op).

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

### log\_i

<span id="qiskit.aqua.operators.list_ops.SummedOp.log_i" />

`SummedOp.log_i(massive=False)`

Return a `MatrixOp` equivalent to log(H)/-i for this operator H. This function is the effective inverse of exp\_i, equivalent to finding the Hermitian Operator which produces self when exponentiated. For proper ListOps, applies `log_i` to all ops in oplist.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

### mul

<span id="qiskit.aqua.operators.list_ops.SummedOp.mul" />

`SummedOp.mul(scalar)`

Returns the scalar multiplication of the Operator, overloaded by `*`, including support for Terra’s `Parameters`, which can be bound to values later (via `bind_parameters`).

**Parameters**

**scalar** (`Union`\[`int`, `float`, `complex`, [`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")]) – The real or complex scalar by which to multiply the Operator, or the `ParameterExpression` to serve as a placeholder for a scalar factor.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

**Returns**

An `OperatorBase` equivalent to product of self and scalar.

### neg

<span id="qiskit.aqua.operators.list_ops.SummedOp.neg" />

`SummedOp.neg()`

Return the Operator’s negation, effectively just multiplying by -1.0, overloaded by `-`.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

**Returns**

An `OperatorBase` equivalent to the negation of self.

### power

<span id="qiskit.aqua.operators.list_ops.SummedOp.power" />

`SummedOp.power(exponent)`

Return Operator composed with self multiple times, overloaded by `**`.

**Parameters**

**exponent** (`int`) – The int number of times to compose self with itself.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

**Returns**

An `OperatorBase` equivalent to self composed with itself exponent times.

### primitive\_strings

<span id="qiskit.aqua.operators.list_ops.SummedOp.primitive_strings" />

`SummedOp.primitive_strings()`

Return a set of strings describing the primitives contained in the Operator. For example, `{'QuantumCircuit', 'Pauli'}`. For hierarchical Operators, such as `ListOps`, this can help illuminate the primitives represented in the various recursive levels, and therefore which conversions can be applied.

**Return type**

`Set`\[`str`]

**Returns**

A set of strings describing the primitives contained within the Operator.

### reduce

<span id="qiskit.aqua.operators.list_ops.SummedOp.reduce" />

`SummedOp.reduce()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/operators/list_ops/summed_op.py "view source code")

Try collapsing the Operator structure, usually after some type of conversion, e.g. trying to add Operators in a SummedOp or delete needless IGates in a CircuitOp. If no reduction is available, just returns self.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

**Returns**

The reduced `OperatorBase`.

### tensor

<span id="qiskit.aqua.operators.list_ops.SummedOp.tensor" />

`SummedOp.tensor(other)`

Return tensor product between self and other, overloaded by `^`. Note: You must be conscious of Qiskit’s big-endian bit printing convention. Meaning, X.tensor(Y) produces an X on qubit 0 and an Y on qubit 1, or X⨂Y, but would produce a QuantumCircuit which looks like

> -\[Y]- -\[X]-

Because Terra prints circuits and results with qubit 0 at the end of the string or circuit.

**Parameters**

**other** ([`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")) – The `OperatorBase` to tensor product with self.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

**Returns**

An `OperatorBase` equivalent to the tensor product of self and other.

### tensorpower

<span id="qiskit.aqua.operators.list_ops.SummedOp.tensorpower" />

`SummedOp.tensorpower(other)`

Return tensor product with self multiple times, overloaded by `^`.

**Parameters**

**other** (`int`) – The int number of times to tensor product self with itself via `tensorpower`.

**Return type**

`Union`\[[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase"), `int`]

**Returns**

An `OperatorBase` equivalent to the tensorpower of self by other.

### to\_circuit\_op

<span id="qiskit.aqua.operators.list_ops.SummedOp.to_circuit_op" />

`SummedOp.to_circuit_op()`

Returns an equivalent Operator composed of only QuantumCircuit-based primitives, such as `CircuitOp` and `CircuitStateFn`.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

### to\_legacy\_op

<span id="qiskit.aqua.operators.list_ops.SummedOp.to_legacy_op" />

`SummedOp.to_legacy_op(massive=False)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/operators/list_ops/summed_op.py "view source code")

Attempt to return the Legacy Operator representation of the Operator. If self is a `SummedOp` of `PauliOps`, will attempt to convert to `WeightedPauliOperator`, and otherwise will simply convert to `MatrixOp` and then to `MatrixOperator`. The Legacy Operators cannot represent `StateFns` or proper `ListOps` (meaning not one of the `ListOp` subclasses), so an error will be thrown if this method is called on such an Operator. Also, Legacy Operators cannot represent unbound Parameter coeffs, so an error will be thrown if any are present in self.

Warn if more than 16 qubits to force having to set `massive=True` if such a large vector is desired.

**Return type**

[`LegacyBaseOperator`](qiskit.aqua.operators.legacy.LegacyBaseOperator "qiskit.aqua.operators.legacy.base_operator.LegacyBaseOperator")

**Returns**

The `LegacyBaseOperator` representing this Operator.

**Raises**

**TypeError** – self is an Operator which cannot be represented by a `LegacyBaseOperator`, such as `StateFn`, proper (non-subclass) `ListOp`, or an Operator with an unbound coeff Parameter.

### to\_matrix

<span id="qiskit.aqua.operators.list_ops.SummedOp.to_matrix" />

`SummedOp.to_matrix(massive=False)`

Return NumPy representation of the Operator. Represents the evaluation of the Operator’s underlying function on every combination of basis binary strings. Warn if more than 16 qubits to force having to set `massive=True` if such a large vector is desired.

**Return type**

`ndarray`

**Returns**

The NumPy `ndarray` equivalent to this Operator.

### to\_matrix\_op

<span id="qiskit.aqua.operators.list_ops.SummedOp.to_matrix_op" />

`SummedOp.to_matrix_op(massive=False)`

Returns an equivalent Operator composed of only NumPy-based primitives, such as `MatrixOp` and `VectorStateFn`.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

### to\_pauli\_op

<span id="qiskit.aqua.operators.list_ops.SummedOp.to_pauli_op" />

`SummedOp.to_pauli_op(massive=False)`

Returns an equivalent Operator composed of only Pauli-based primitives, such as `PauliOp`.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

### to\_spmatrix

<span id="qiskit.aqua.operators.list_ops.SummedOp.to_spmatrix" />

`SummedOp.to_spmatrix()`

Returns SciPy sparse matrix representation of the Operator.

**Return type**

`Union`\[`spmatrix`, `List`\[`spmatrix`]]

**Returns**

CSR sparse matrix representation of the Operator, or List thereof.

### traverse

<span id="qiskit.aqua.operators.list_ops.SummedOp.traverse" />

`SummedOp.traverse(convert_fn, coeff=None)`

Apply the convert\_fn to each node in the oplist.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

