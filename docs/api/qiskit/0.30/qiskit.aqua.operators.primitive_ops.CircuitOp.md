---
title: CircuitOp
description: API reference for qiskit.aqua.operators.primitive_ops.CircuitOp
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.operators.primitive_ops.CircuitOp
---

# CircuitOp

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp" />

`CircuitOp(primitive, coeff=1.0)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/primitive_ops/circuit_op.py "view source code")

Bases: `qiskit.aqua.operators.primitive_ops.primitive_op.PrimitiveOp`

Class for Operators backed by Terra’s `QuantumCircuit` module.

**Parameters**

*   **primitive** (`Union`\[`Instruction`, `QuantumCircuit`]) – The QuantumCircuit which defines the
*   **of the underlying function.** (*behavior*) –
*   **coeff** (`Union`\[`int`, `float`, `complex`, `ParameterExpression`]) – A coefficient multiplying the primitive

**Raises**

**TypeError** – Unsupported primitive, or primitive has ClassicalRegisters.

## Methods

### add

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.add" />

`CircuitOp.add(other)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/primitive_ops/circuit_op.py "view source code")

Return Operator addition of self and other, overloaded by `+`.

**Parameters**

**other** (`OperatorBase`) – An `OperatorBase` with the same number of qubits as self, and in the same ‘Operator’, ‘State function’, or ‘Measurement’ category as self (i.e. the same type of underlying function).

**Return type**

`OperatorBase`

**Returns**

An `OperatorBase` equivalent to the sum of self and other.

### adjoint

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.adjoint" />

`CircuitOp.adjoint()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/primitive_ops/circuit_op.py "view source code")

Return a new Operator equal to the Operator’s adjoint (conjugate transpose), overloaded by `~`. For StateFns, this also turns the StateFn into a measurement.

**Return type**

`OperatorBase`

**Returns**

An `OperatorBase` equivalent to the adjoint of self.

### assign\_parameters

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.assign_parameters" />

`CircuitOp.assign_parameters(param_dict)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/primitive_ops/circuit_op.py "view source code")

Binds scalar values to any Terra `Parameters` in the coefficients or primitives of the Operator, or substitutes one `Parameter` for another. This method differs from Terra’s `assign_parameters` in that it also supports lists of values to assign for a give `Parameter`, in which case self will be copied for each parameterization in the binding list(s), and all the copies will be returned in an `OpList`. If lists of parameterizations are used, every `Parameter` in the param\_dict must have the same length list of parameterizations.

**Parameters**

**param\_dict** (`dict`) – The dictionary of `Parameters` to replace, and values or lists of values by which to replace them.

**Return type**

`OperatorBase`

**Returns**

The `OperatorBase` with the `Parameters` in self replaced by the values or `Parameters` in param\_dict. If param\_dict contains parameterization lists, this `OperatorBase` is an `OpList`.

### bind\_parameters

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.bind_parameters" />

`CircuitOp.bind_parameters(param_dict)`

Same as assign\_parameters, but maintained for consistency with QuantumCircuit in Terra (which has both assign\_parameters and bind\_parameters).

**Return type**

`OperatorBase`

### compose

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.compose" />

`CircuitOp.compose(other, permutation=None, front=False)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/primitive_ops/circuit_op.py "view source code")

Return Operator Composition between self and other (linear algebra-style: A\@B(x) = A(B(x))), overloaded by `@`.

Note: You must be conscious of Quantum Circuit vs. Linear Algebra ordering conventions. Meaning, X.compose(Y) produces an X∘Y on qubit 0, but would produce a QuantumCircuit which looks like

> -\[Y]-\[X]-

Because Terra prints circuits with the initial state at the left side of the circuit.

**Parameters**

*   **other** (`OperatorBase`) – The `OperatorBase` with which to compose self.
*   **permutation** (`Optional`\[`List`\[`int`]]) – `List[int]` which defines permutation on other operator.
*   **front** (`bool`) – If front==True, return `other.compose(self)`.

**Return type**

`OperatorBase`

**Returns**

An `OperatorBase` equivalent to the function composition of self and other.

### equals

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.equals" />

`CircuitOp.equals(other)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/primitive_ops/circuit_op.py "view source code")

Evaluate Equality between Operators, overloaded by `==`. Only returns True if self and other are of the same representation (e.g. a DictStateFn and CircuitStateFn will never be equal, even if their vector representations are equal), their underlying primitives are equal (this means for ListOps, OperatorStateFns, or EvolvedOps the equality is evaluated recursively downwards), and their coefficients are equal.

**Parameters**

**other** (`OperatorBase`) – The `OperatorBase` to compare to self.

**Return type**

`bool`

**Returns**

A bool equal to the equality of self and other.

### eval

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.eval" />

`CircuitOp.eval(front=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/primitive_ops/circuit_op.py "view source code")

Evaluate the Operator’s underlying function, either on a binary string or another Operator. A square binary Operator can be defined as a function taking a binary function to another binary function. This method returns the value of that function for a given StateFn or binary string. For example, `op.eval('0110').eval('1110')` can be seen as querying the Operator’s matrix representation by row 6 and column 14, and will return the complex value at those “indices.” Similarly for a StateFn, `op.eval('1011')` will return the complex value at row 11 of the vector representation of the StateFn, as all StateFns are defined to be evaluated from Zero implicitly (i.e. it is as if `.eval('0000')` is already called implicitly to always “indexing” from column 0).

If `front` is None, the matrix-representation of the operator is returned.

**Parameters**

**front** (`Union`\[`str`, `Dict`\[`str`, `complex`], `ndarray`, `OperatorBase`, `None`]) – The bitstring, dict of bitstrings (with values being coefficients), or StateFn to evaluated by the Operator’s underlying function, or None.

**Return type**

`Union`\[`OperatorBase`, `float`, `complex`]

**Returns**

The output of the Operator’s evaluation function. If self is a `StateFn`, the result is a float or complex. If self is an Operator (`PrimitiveOp, ComposedOp, SummedOp, EvolvedOp,` etc.), the result is a StateFn. If `front` is None, the matrix-representation of the operator is returned, which is a `MatrixOp` for the operators and a `VectorStateFn` for state-functions. If either self or front contain proper `ListOps` (not ListOp subclasses), the result is an n-dimensional list of complex or StateFn results, resulting from the recursive evaluation by each OperatorBase in the ListOps.

### exp\_i

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.exp_i" />

`CircuitOp.exp_i()`

Return Operator exponentiation, equaling e^(-i \* op)

**Return type**

`OperatorBase`

### log\_i

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.log_i" />

`CircuitOp.log_i(massive=False)`

Return a `MatrixOp` equivalent to log(H)/-i for this operator H. This function is the effective inverse of exp\_i, equivalent to finding the Hermitian Operator which produces self when exponentiated.

**Return type**

`OperatorBase`

### mul

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.mul" />

`CircuitOp.mul(scalar)`

Returns the scalar multiplication of the Operator, overloaded by `*`, including support for Terra’s `Parameters`, which can be bound to values later (via `bind_parameters`).

**Parameters**

**scalar** (`Union`\[`int`, `float`, `complex`, `ParameterExpression`]) – The real or complex scalar by which to multiply the Operator, or the `ParameterExpression` to serve as a placeholder for a scalar factor.

**Return type**

`OperatorBase`

**Returns**

An `OperatorBase` equivalent to product of self and scalar.

### neg

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.neg" />

`CircuitOp.neg()`

Return the Operator’s negation, effectively just multiplying by -1.0, overloaded by `-`.

**Return type**

`OperatorBase`

**Returns**

An `OperatorBase` equivalent to the negation of self.

### permute

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.permute" />

`CircuitOp.permute(permutation)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/primitive_ops/circuit_op.py "view source code")

Permute the qubits of the circuit.

**Parameters**

**permutation** (`List`\[`int`]) – A list defining where each qubit should be permuted. The qubit at index j of the circuit should be permuted to position permutation\[j].

**Return type**

`CircuitOp`

**Returns**

A new CircuitOp containing the permuted circuit.

### power

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.power" />

`CircuitOp.power(exponent)`

Return Operator composed with self multiple times, overloaded by `**`.

**Parameters**

**exponent** (`int`) – The int number of times to compose self with itself.

**Return type**

`OperatorBase`

**Returns**

An `OperatorBase` equivalent to self composed with itself exponent times.

### primitive\_strings

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.primitive_strings" />

`CircuitOp.primitive_strings()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/primitive_ops/circuit_op.py "view source code")

Return a set of strings describing the primitives contained in the Operator. For example, `{'QuantumCircuit', 'Pauli'}`. For hierarchical Operators, such as `ListOps`, this can help illuminate the primitives represented in the various recursive levels, and therefore which conversions can be applied.

**Return type**

`Set`\[`str`]

**Returns**

A set of strings describing the primitives contained within the Operator.

### reduce

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.reduce" />

`CircuitOp.reduce()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/primitive_ops/circuit_op.py "view source code")

Try collapsing the Operator structure, usually after some type of conversion, e.g. trying to add Operators in a SummedOp or delete needless IGates in a CircuitOp. If no reduction is available, just returns self.

**Return type**

`OperatorBase`

**Returns**

The reduced `OperatorBase`.

### tensor

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.tensor" />

`CircuitOp.tensor(other)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/primitive_ops/circuit_op.py "view source code")

Return tensor product between self and other, overloaded by `^`. Note: You must be conscious of Qiskit’s big-endian bit printing convention. Meaning, X.tensor(Y) produces an X on qubit 0 and an Y on qubit 1, or X⨂Y, but would produce a QuantumCircuit which looks like

> -\[Y]- -\[X]-

Because Terra prints circuits and results with qubit 0 at the end of the string or circuit.

**Parameters**

**other** (`OperatorBase`) – The `OperatorBase` to tensor product with self.

**Return type**

`OperatorBase`

**Returns**

An `OperatorBase` equivalent to the tensor product of self and other.

### tensorpower

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.tensorpower" />

`CircuitOp.tensorpower(other)`

Return tensor product with self multiple times, overloaded by `^`.

**Parameters**

**other** (`int`) – The int number of times to tensor product self with itself via `tensorpower`.

**Return type**

`Union`\[`OperatorBase`, `int`]

**Returns**

An `OperatorBase` equivalent to the tensorpower of self by other.

### to\_circuit

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.to_circuit" />

`CircuitOp.to_circuit()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/primitive_ops/circuit_op.py "view source code")

Returns a `QuantumCircuit` equivalent to this Operator.

**Return type**

`QuantumCircuit`

### to\_circuit\_op

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.to_circuit_op" />

`CircuitOp.to_circuit_op()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/primitive_ops/circuit_op.py "view source code")

Returns a `CircuitOp` equivalent to this Operator.

**Return type**

`OperatorBase`

### to\_instruction

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.to_instruction" />

`CircuitOp.to_instruction()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/primitive_ops/circuit_op.py "view source code")

Returns an `Instruction` equivalent to this Operator.

**Return type**

`Instruction`

### to\_legacy\_op

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.to_legacy_op" />

`CircuitOp.to_legacy_op(massive=False)`

Attempt to return the Legacy Operator representation of the Operator. If self is a `SummedOp` of `PauliOps`, will attempt to convert to `WeightedPauliOperator`, and otherwise will simply convert to `MatrixOp` and then to `MatrixOperator`. The Legacy Operators cannot represent `StateFns` or proper `ListOps` (meaning not one of the `ListOp` subclasses), so an error will be thrown if this method is called on such an Operator. Also, Legacy Operators cannot represent unbound Parameter coeffs, so an error will be thrown if any are present in self.

Warn if more than 16 qubits to force having to set `massive=True` if such a large vector is desired.

**Return type**

`LegacyBaseOperator`

**Returns**

The `LegacyBaseOperator` representing this Operator.

**Raises**

**TypeError** – self is an Operator which cannot be represented by a `LegacyBaseOperator`, such as `StateFn`, proper (non-subclass) `ListOp`, or an Operator with an unbound coeff Parameter.

### to\_matrix

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.to_matrix" />

`CircuitOp.to_matrix(massive=False)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/primitive_ops/circuit_op.py "view source code")

Return NumPy representation of the Operator. Represents the evaluation of the Operator’s underlying function on every combination of basis binary strings. Warn if more than 16 qubits to force having to set `massive=True` if such a large vector is desired.

**Return type**

`ndarray`

**Returns**

The NumPy `ndarray` equivalent to this Operator.

### to\_matrix\_op

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.to_matrix_op" />

`CircuitOp.to_matrix_op(massive=False)`

Returns a `MatrixOp` equivalent to this Operator.

**Return type**

`OperatorBase`

### to\_pauli\_op

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.to_pauli_op" />

`CircuitOp.to_pauli_op(massive=False)`

Returns a sum of `PauliOp` s equivalent to this Operator.

**Return type**

`OperatorBase`

## Attributes

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.ENABLE_DEPRECATION" />

### ENABLE\_DEPRECATION

`= True`

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.INDENTATION" />

### INDENTATION

`= ' '`

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.coeff" />

### coeff

The scalar coefficient multiplying the Operator.

**Return type**

`Union`\[`int`, `float`, `complex`, `ParameterExpression`]

**Returns**

The coefficient.

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.num_qubits" />

### num\_qubits

**Return type**

`int`

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.parameters" />

### parameters

<span id="qiskit.aqua.operators.primitive_ops.CircuitOp.primitive" />

### primitive

The primitive defining the underlying function of the Operator.

**Return type**

`Union`\[`Instruction`, `QuantumCircuit`, `List`, `ndarray`, `spmatrix`, `Operator`, `Pauli`]

**Returns**

The primitive object.

