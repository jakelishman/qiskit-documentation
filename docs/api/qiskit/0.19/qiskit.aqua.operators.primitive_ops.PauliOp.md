---
title: PauliOp
description: API reference for qiskit.aqua.operators.primitive_ops.PauliOp
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.operators.primitive_ops.PauliOp
---

# PauliOp

<span id="qiskit.aqua.operators.primitive_ops.PauliOp" />

`PauliOp(primitive=None, coeff=1.0)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/operators/primitive_ops/pauli_op.py "view source code")

Class for Operators backed by Terra’s `Pauli` module.

**Parameters**

*   **primitive** (`Optional`\[[`Pauli`](qiskit.quantum_info.Pauli "qiskit.quantum_info.operators.pauli.Pauli")]) – The Pauli which defines the behavior of the underlying function.
*   **coeff** (`Union`\[`int`, `float`, `complex`, [`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression"), `None`]) – A coefficient multiplying the primitive.

**Raises**

**TypeError** – invalid parameters.

## Attributes

### coeff

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.coeff" />

`Union[int, float, complex, qiskit.circuit.parameterexpression.ParameterExpression]`

The scalar coefficient multiplying the Operator.

**Return type**

`Union`\[`int`, `float`, `complex`, [`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")]

**Returns**

The coefficient.

### num\_qubits

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.num_qubits" />

`int`

The number of qubits over which the Operator is defined. If `op.num_qubits == 5`, then `op.eval('1' * 5)` will be valid, but `op.eval('11')` will not.

**Return type**

`int`

**Returns**

The number of qubits accepted by the Operator’s underlying function.

### primitive

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.primitive" />

`Union[qiskit.circuit.instruction.Instruction, qiskit.circuit.quantumcircuit.QuantumCircuit, list, numpy.ndarray, scipy.sparse.base.spmatrix, qiskit.quantum_info.operators.operator.Operator, qiskit.quantum_info.operators.pauli.Pauli]`

The primitive defining the underlying function of the Operator.

**Return type**

`Union`\[[`Instruction`](qiskit.circuit.Instruction "qiskit.circuit.instruction.Instruction"), [`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit"), `list`, `ndarray`, `spmatrix`, [`Operator`](qiskit.quantum_info.Operator "qiskit.quantum_info.operators.operator.Operator"), [`Pauli`](qiskit.quantum_info.Pauli "qiskit.quantum_info.operators.pauli.Pauli")]

**Returns**

The primitive object.

## Methods

### \_\_mul\_\_

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.__mul__" />

`PauliOp.__mul__(other)`

Overload `*` for Operator scalar multiplication.

**Parameters**

**other** (`Number`) – The real or complex scalar by which to multiply the Operator, or the `ParameterExpression` to serve as a placeholder for a scalar factor.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

**Returns**

An `OperatorBase` equivalent to product of self and scalar.

### add

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.add" />

`PauliOp.add(other)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/operators/primitive_ops/pauli_op.py "view source code")

Return Operator addition of self and other, overloaded by `+`.

**Parameters**

**other** ([`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")) – An `OperatorBase` with the same number of qubits as self, and in the same ‘Operator’, ‘State function’, or ‘Measurement’ category as self (i.e. the same type of underlying function).

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

**Returns**

An `OperatorBase` equivalent to the sum of self and other.

### adjoint

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.adjoint" />

`PauliOp.adjoint()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/operators/primitive_ops/pauli_op.py "view source code")

Return a new Operator equal to the Operator’s adjoint (conjugate transpose), overloaded by `~`. For StateFns, this also turns the StateFn into a measurement.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

**Returns**

An `OperatorBase` equivalent to the adjoint of self.

### assign\_parameters

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.assign_parameters" />

`PauliOp.assign_parameters(param_dict)`

Binds scalar values to any Terra `Parameters` in the coefficients or primitives of the Operator, or substitutes one `Parameter` for another. This method differs from Terra’s `assign_parameters` in that it also supports lists of values to assign for a give `Parameter`, in which case self will be copied for each parameterization in the binding list(s), and all the copies will be returned in an `OpList`. If lists of parameterizations are used, every `Parameter` in the param\_dict must have the same length list of parameterizations.

**Parameters**

**param\_dict** (`dict`) – The dictionary of `Parameters` to replace, and values or lists of values by which to replace them.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

**Returns**

The `OperatorBase` with the `Parameters` in self replaced by the values or `Parameters` in param\_dict. If param\_dict contains parameterization lists, this `OperatorBase` is an `OpList`.

### bind\_parameters

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.bind_parameters" />

`PauliOp.bind_parameters(param_dict)`

Same as assign\_parameters, but maintained for consistency with QuantumCircuit in Terra (which has both assign\_parameters and bind\_parameters).

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

### commutes

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.commutes" />

`PauliOp.commutes(other_op)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/operators/primitive_ops/pauli_op.py "view source code")

Returns whether self commutes with other\_op.

**Parameters**

**other\_op** ([`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")) – An `OperatorBase` with which to evaluate whether self commutes.

**Return type**

`bool`

**Returns**

A bool equaling whether self commutes with other\_op

### compose

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.compose" />

`PauliOp.compose(other)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/operators/primitive_ops/pauli_op.py "view source code")

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

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.equals" />

`PauliOp.equals(other)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/operators/primitive_ops/pauli_op.py "view source code")

Evaluate Equality between Operators, overloaded by `==`. Only returns True if self and other are of the same representation (e.g. a DictStateFn and CircuitStateFn will never be equal, even if their vector representations are equal), their underlying primitives are equal (this means for ListOps, OperatorStateFns, or EvolvedOps the equality is evaluated recursively downwards), and their coefficients are equal.

**Parameters**

**other** ([`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")) – The `OperatorBase` to compare to self.

**Return type**

`bool`

**Returns**

A bool equal to the equality of self and other.

### eval

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.eval" />

`PauliOp.eval(front=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/operators/primitive_ops/pauli_op.py "view source code")

Evaluate the Operator’s underlying function, either on a binary string or another Operator. A square binary Operator can be defined as a function taking a binary function to another binary function. This method returns the value of that function for a given StateFn or binary string. For example, `op.eval('0110').eval('1110')` can be seen as querying the Operator’s matrix representation by row 6 and column 14, and will return the complex value at those “indices.” Similarly for a StateFn, `op.eval('1011')` will return the complex value at row 11 of the vector representation of the StateFn, as all StateFns are defined to be evaluated from Zero implicitly (i.e. it is as if `.eval('0000')` is already called implicitly to always “indexing” from column 0).

**Parameters**

**front** (`Union`\[`str`, `dict`, `ndarray`, [`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase"), `None`]) – The bitstring, dict of bitstrings (with values being coefficients), or StateFn to evaluated by the Operator’s underlying function.

**Return type**

`Union`\[[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase"), `float`, `complex`]

**Returns**

The output of the Operator’s evaluation function. If self is a `StateFn`, the result is a float or complex. If self is an Operator (`PrimitiveOp, ComposedOp, SummedOp, EvolvedOp,` etc.), the result is a StateFn. If either self or front contain proper `ListOps` (not ListOp subclasses), the result is an n-dimensional list of complex or StateFn results, resulting from the recursive evaluation by each OperatorBase in the ListOps.

### exp\_i

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.exp_i" />

`PauliOp.exp_i()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/operators/primitive_ops/pauli_op.py "view source code")

Return a `CircuitOp` equivalent to e^-iH for this operator H.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

### log\_i

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.log_i" />

`PauliOp.log_i(massive=False)`

Return a `MatrixOp` equivalent to log(H)/-i for this operator H. This function is the effective inverse of exp\_i, equivalent to finding the Hermitian Operator which produces self when exponentiated.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

### mul

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.mul" />

`PauliOp.mul(scalar)`

Returns the scalar multiplication of the Operator, overloaded by `*`, including support for Terra’s `Parameters`, which can be bound to values later (via `bind_parameters`).

**Parameters**

**scalar** (`Union`\[`int`, `float`, `complex`, [`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")]) – The real or complex scalar by which to multiply the Operator, or the `ParameterExpression` to serve as a placeholder for a scalar factor.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

**Returns**

An `OperatorBase` equivalent to product of self and scalar.

### neg

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.neg" />

`PauliOp.neg()`

Return the Operator’s negation, effectively just multiplying by -1.0, overloaded by `-`.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

**Returns**

An `OperatorBase` equivalent to the negation of self.

### power

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.power" />

`PauliOp.power(exponent)`

Return Operator composed with self multiple times, overloaded by `**`.

**Parameters**

**exponent** (`int`) – The int number of times to compose self with itself.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

**Returns**

An `OperatorBase` equivalent to self composed with itself exponent times.

### primitive\_strings

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.primitive_strings" />

`PauliOp.primitive_strings()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/operators/primitive_ops/pauli_op.py "view source code")

Return a set of strings describing the primitives contained in the Operator. For example, `{'QuantumCircuit', 'Pauli'}`. For hierarchical Operators, such as `ListOps`, this can help illuminate the primitives represented in the various recursive levels, and therefore which conversions can be applied.

**Return type**

`Set`\[`str`]

**Returns**

A set of strings describing the primitives contained within the Operator.

### reduce

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.reduce" />

`PauliOp.reduce()`

Try collapsing the Operator structure, usually after some type of conversion, e.g. trying to add Operators in a SummedOp or delete needless IGates in a CircuitOp. If no reduction is available, just returns self.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

**Returns**

The reduced `OperatorBase`.

### tensor

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.tensor" />

`PauliOp.tensor(other)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/operators/primitive_ops/pauli_op.py "view source code")

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

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.tensorpower" />

`PauliOp.tensorpower(other)`

Return tensor product with self multiple times, overloaded by `^`.

**Parameters**

**other** (`int`) – The int number of times to tensor product self with itself via `tensorpower`.

**Return type**

`Union`\[[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase"), `int`]

**Returns**

An `OperatorBase` equivalent to the tensorpower of self by other.

### to\_circuit

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.to_circuit" />

`PauliOp.to_circuit()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/operators/primitive_ops/pauli_op.py "view source code")

Returns a `QuantumCircuit` equivalent to this Operator.

**Return type**

[`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit")

### to\_circuit\_op

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.to_circuit_op" />

`PauliOp.to_circuit_op()`

Returns a `CircuitOp` equivalent to this Operator.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

### to\_instruction

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.to_instruction" />

`PauliOp.to_instruction()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/operators/primitive_ops/pauli_op.py "view source code")

Returns an `Instruction` equivalent to this Operator.

**Return type**

[`Instruction`](qiskit.circuit.Instruction "qiskit.circuit.instruction.Instruction")

### to\_legacy\_op

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.to_legacy_op" />

`PauliOp.to_legacy_op(massive=False)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/operators/primitive_ops/pauli_op.py "view source code")

Attempt to return the Legacy Operator representation of the Operator. If self is a `SummedOp` of `PauliOps`, will attempt to convert to `WeightedPauliOperator`, and otherwise will simply convert to `MatrixOp` and then to `MatrixOperator`. The Legacy Operators cannot represent `StateFns` or proper `ListOps` (meaning not one of the `ListOp` subclasses), so an error will be thrown if this method is called on such an Operator. Also, Legacy Operators cannot represent unbound Parameter coeffs, so an error will be thrown if any are present in self.

Warn if more than 16 qubits to force having to set `massive=True` if such a large vector is desired.

**Return type**

[`WeightedPauliOperator`](qiskit.aqua.operators.legacy.WeightedPauliOperator "qiskit.aqua.operators.legacy.weighted_pauli_operator.WeightedPauliOperator")

**Returns**

The `LegacyBaseOperator` representing this Operator.

**Raises**

**TypeError** – self is an Operator which cannot be represented by a `LegacyBaseOperator`, such as `StateFn`, proper (non-subclass) `ListOp`, or an Operator with an unbound coeff Parameter.

### to\_matrix

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.to_matrix" />

`PauliOp.to_matrix(massive=False)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/operators/primitive_ops/pauli_op.py "view source code")

Return NumPy representation of the Operator. Represents the evaluation of the Operator’s underlying function on every combination of basis binary strings. Warn if more than 16 qubits to force having to set `massive=True` if such a large vector is desired.

**Return type**

`ndarray`

**Returns**

The NumPy `ndarray` equivalent to this Operator.

### to\_matrix\_op

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.to_matrix_op" />

`PauliOp.to_matrix_op(massive=False)`

Returns a `MatrixOp` equivalent to this Operator.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

### to\_pauli\_op

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.to_pauli_op" />

`PauliOp.to_pauli_op(massive=False)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/operators/primitive_ops/pauli_op.py "view source code")

Returns a sum of `PauliOp` s equivalent to this Operator.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

### to\_spmatrix

<span id="qiskit.aqua.operators.primitive_ops.PauliOp.to_spmatrix" />

`PauliOp.to_spmatrix()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/operators/primitive_ops/pauli_op.py "view source code")

Returns SciPy sparse matrix representation of the Operator.

**Return type**

`spmatrix`

**Returns**

CSR sparse matrix representation of the Operator.

**Raises**

**ValueError** – invalid parameters.

