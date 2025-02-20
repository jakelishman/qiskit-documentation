---
title: TaperedPauliSumOp
description: API reference for qiskit.opflow.primitive_ops.TaperedPauliSumOp
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.opflow.primitive_ops.TaperedPauliSumOp
---

# qiskit.opflow\.primitive\_ops.TaperedPauliSumOp

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp" />

`TaperedPauliSumOp(primitive, z2_symmetries, coeff=1.0)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/opflow/primitive_ops/tapered_pauli_sum_op.py "view source code")

Class for PauliSumOp after tapering

**Parameters**

*   **primitive** (`SparsePauliOp`) – The SparsePauliOp which defines the behavior of the underlying function.
*   **z2\_symmetries** (`Z2Symmetries`) – Z2 symmetries which the Operator has.
*   **coeff** (`Union`\[`complex`, `ParameterExpression`]) – A coefficient multiplying the primitive.

**Raises**

**TypeError** – invalid parameters.

### \_\_init\_\_

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.__init__" />

`__init__(primitive, z2_symmetries, coeff=1.0)`

**Parameters**

*   **primitive** (`SparsePauliOp`) – The SparsePauliOp which defines the behavior of the underlying function.
*   **z2\_symmetries** (`Z2Symmetries`) – Z2 symmetries which the Operator has.
*   **coeff** (`Union`\[`complex`, `ParameterExpression`]) – A coefficient multiplying the primitive.

**Raises**

**TypeError** – invalid parameters.

## Methods

|                                                                                                                                                                        |                                                                                                                                                                               |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.__init__ "qiskit.opflow.primitive_ops.TaperedPauliSumOp.__init__")(primitive, z2\_symmetries\[, coeff])    | **type primitive**`SparsePauliOp`                                                                                                                                             |
| [`add`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.add "qiskit.opflow.primitive_ops.TaperedPauliSumOp.add")(other)                                                 | Return Operator addition of self and other, overloaded by `+`.                                                                                                                |
| [`adjoint`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.adjoint "qiskit.opflow.primitive_ops.TaperedPauliSumOp.adjoint")()                                          | Return a new Operator equal to the Operator’s adjoint (conjugate transpose), overloaded by `~`.                                                                               |
| [`assign_parameters`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.assign_parameters "qiskit.opflow.primitive_ops.TaperedPauliSumOp.assign_parameters")(param\_dict) | Binds scalar values to any Terra `Parameters` in the coefficients or primitives of the Operator, or substitutes one `Parameter` for another.                                  |
| [`bind_parameters`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.bind_parameters "qiskit.opflow.primitive_ops.TaperedPauliSumOp.bind_parameters")(param\_dict)       | Same as assign\_parameters, but maintained for consistency with QuantumCircuit in Terra (which has both assign\_parameters and bind\_parameters).                             |
| [`compose`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.compose "qiskit.opflow.primitive_ops.TaperedPauliSumOp.compose")(other\[, permutation, front])              | Return Operator Composition between self and other (linear algebra-style: A\@B(x) = A(B(x))), overloaded by `@`.                                                              |
| [`copy`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.copy "qiskit.opflow.primitive_ops.TaperedPauliSumOp.copy")()                                                   | Return a deep copy of the Operator.                                                                                                                                           |
| [`equals`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.equals "qiskit.opflow.primitive_ops.TaperedPauliSumOp.equals")(other)                                        | Evaluate Equality between Operators, overloaded by `==`.                                                                                                                      |
| [`eval`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.eval "qiskit.opflow.primitive_ops.TaperedPauliSumOp.eval")(\[front])                                           | Evaluate the Operator’s underlying function, either on a binary string or another Operator.                                                                                   |
| [`exp_i`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.exp_i "qiskit.opflow.primitive_ops.TaperedPauliSumOp.exp_i")()                                                | Return a `CircuitOp` equivalent to e^-iH for this operator H.                                                                                                                 |
| [`from_list`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.from_list "qiskit.opflow.primitive_ops.TaperedPauliSumOp.from_list")(pauli\_list\[, coeff])               | Construct from a pauli\_list with the form \[(pauli\_str, coeffs)]                                                                                                            |
| [`is_zero`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.is_zero "qiskit.opflow.primitive_ops.TaperedPauliSumOp.is_zero")()                                          | Return this operator is zero operator or not.                                                                                                                                 |
| [`log_i`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.log_i "qiskit.opflow.primitive_ops.TaperedPauliSumOp.log_i")(\[massive])                                      | Return a `MatrixOp` equivalent to log(H)/-i for this operator H.                                                                                                              |
| [`matrix_iter`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.matrix_iter "qiskit.opflow.primitive_ops.TaperedPauliSumOp.matrix_iter")(\[sparse])                     | Return a matrix representation iterator.                                                                                                                                      |
| [`mul`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.mul "qiskit.opflow.primitive_ops.TaperedPauliSumOp.mul")(scalar)                                                | Returns the scalar multiplication of the Operator, overloaded by `*`, including support for Terra’s `Parameters`, which can be bound to values later (via `bind_parameters`). |
| [`neg`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.neg "qiskit.opflow.primitive_ops.TaperedPauliSumOp.neg")()                                                      | Return the Operator’s negation, effectively just multiplying by -1.0, overloaded by `-`.                                                                                      |
| [`permute`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.permute "qiskit.opflow.primitive_ops.TaperedPauliSumOp.permute")(permutation)                               | Permutes the sequence of `PauliSumOp`.                                                                                                                                        |
| [`power`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.power "qiskit.opflow.primitive_ops.TaperedPauliSumOp.power")(exponent)                                        | Return Operator composed with self multiple times, overloaded by `**`.                                                                                                        |
| [`primitive_strings`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.primitive_strings "qiskit.opflow.primitive_ops.TaperedPauliSumOp.primitive_strings")()            | Return a set of strings describing the primitives contained in the Operator.                                                                                                  |
| [`reduce`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.reduce "qiskit.opflow.primitive_ops.TaperedPauliSumOp.reduce")(\[atol, rtol])                                | Simplify the primitive `SparsePauliOp`.                                                                                                                                       |
| [`tensor`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.tensor "qiskit.opflow.primitive_ops.TaperedPauliSumOp.tensor")(other)                                        | Return tensor product between self and other, overloaded by `^`.                                                                                                              |
| [`tensorpower`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.tensorpower "qiskit.opflow.primitive_ops.TaperedPauliSumOp.tensorpower")(other)                         | Return tensor product with self multiple times, overloaded by `^`.                                                                                                            |
| [`to_circuit`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.to_circuit "qiskit.opflow.primitive_ops.TaperedPauliSumOp.to_circuit")()                                 | Returns a `QuantumCircuit` equivalent to this Operator.                                                                                                                       |
| [`to_circuit_op`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.to_circuit_op "qiskit.opflow.primitive_ops.TaperedPauliSumOp.to_circuit_op")()                        | Returns a `CircuitOp` equivalent to this Operator.                                                                                                                            |
| [`to_instruction`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.to_instruction "qiskit.opflow.primitive_ops.TaperedPauliSumOp.to_instruction")()                     | Returns an `Instruction` equivalent to this Operator.                                                                                                                         |
| [`to_matrix`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.to_matrix "qiskit.opflow.primitive_ops.TaperedPauliSumOp.to_matrix")(\[massive])                          | Return NumPy representation of the Operator.                                                                                                                                  |
| [`to_matrix_op`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.to_matrix_op "qiskit.opflow.primitive_ops.TaperedPauliSumOp.to_matrix_op")(\[massive])                 | Returns a `MatrixOp` equivalent to this Operator.                                                                                                                             |
| [`to_pauli_op`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.to_pauli_op "qiskit.opflow.primitive_ops.TaperedPauliSumOp.to_pauli_op")(\[massive])                    | Returns a sum of `PauliOp` s equivalent to this Operator.                                                                                                                     |
| [`to_spmatrix`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.to_spmatrix "qiskit.opflow.primitive_ops.TaperedPauliSumOp.to_spmatrix")()                              | Returns SciPy sparse matrix representation of the `PauliSumOp`.                                                                                                               |

## Attributes

|                                                                                                                                               |                                                                 |
| --------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| `INDENTATION`                                                                                                                                 |                                                                 |
| [`coeff`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.coeff "qiskit.opflow.primitive_ops.TaperedPauliSumOp.coeff")                         | The scalar coefficient multiplying the Operator.                |
| [`coeffs`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.coeffs "qiskit.opflow.primitive_ops.TaperedPauliSumOp.coeffs")                      | Return the Pauli coefficients.                                  |
| [`grouping_type`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.grouping_type "qiskit.opflow.primitive_ops.TaperedPauliSumOp.grouping_type") | Type of Grouping                                                |
| [`instance_id`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.instance_id "qiskit.opflow.primitive_ops.TaperedPauliSumOp.instance_id")       | Return the unique instance id.                                  |
| [`num_qubits`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.num_qubits "qiskit.opflow.primitive_ops.TaperedPauliSumOp.num_qubits")          | The number of qubits over which the Operator is defined.        |
| [`parameters`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.parameters "qiskit.opflow.primitive_ops.TaperedPauliSumOp.parameters")          | Return a set of Parameter objects contained in the Operator.    |
| [`primitive`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.primitive "qiskit.opflow.primitive_ops.TaperedPauliSumOp.primitive")             | The primitive defining the underlying function of the Operator. |
| [`settings`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.settings "qiskit.opflow.primitive_ops.TaperedPauliSumOp.settings")                | Return operator settings.                                       |
| [`z2_symmetries`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.z2_symmetries "qiskit.opflow.primitive_ops.TaperedPauliSumOp.z2_symmetries") | Z2 symmetries which the Operator has.                           |

### add

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.add" />

`add(other)`

Return Operator addition of self and other, overloaded by `+`.

**Parameters**

**other** (`OperatorBase`) – An `OperatorBase` with the same number of qubits as self, and in the same ‘Operator’, ‘State function’, or ‘Measurement’ category as self (i.e. the same type of underlying function).

**Return type**

`OperatorBase`

**Returns**

An `OperatorBase` equivalent to the sum of self and other.

### adjoint

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.adjoint" />

`adjoint()`

Return a new Operator equal to the Operator’s adjoint (conjugate transpose), overloaded by `~`. For StateFns, this also turns the StateFn into a measurement.

**Return type**

`PauliSumOp`

**Returns**

An `OperatorBase` equivalent to the adjoint of self.

### assign\_parameters

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.assign_parameters" />

`assign_parameters(param_dict)`

Binds scalar values to any Terra `Parameters` in the coefficients or primitives of the Operator, or substitutes one `Parameter` for another. This method differs from Terra’s `assign_parameters` in that it also supports lists of values to assign for a give `Parameter`, in which case self will be copied for each parameterization in the binding list(s), and all the copies will be returned in an `OpList`. If lists of parameterizations are used, every `Parameter` in the param\_dict must have the same length list of parameterizations.

**Parameters**

**param\_dict** (`dict`) – The dictionary of `Parameters` to replace, and values or lists of values by which to replace them.

**Return type**

`OperatorBase`

**Returns**

The `OperatorBase` with the `Parameters` in self replaced by the values or `Parameters` in param\_dict. If param\_dict contains parameterization lists, this `OperatorBase` is an `OpList`.

### bind\_parameters

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.bind_parameters" />

`bind_parameters(param_dict)`

Same as assign\_parameters, but maintained for consistency with QuantumCircuit in Terra (which has both assign\_parameters and bind\_parameters).

**Return type**

`OperatorBase`

### coeff

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.coeff" />

`property coeff`

The scalar coefficient multiplying the Operator.

**Return type**

`Union`\[`complex`, `ParameterExpression`]

**Returns**

The coefficient.

### coeffs

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.coeffs" />

`property coeffs`

Return the Pauli coefficients.

### compose

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.compose" />

`compose(other, permutation=None, front=False)`

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

### copy

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.copy" />

`copy()`

Return a deep copy of the Operator.

**Return type**

`OperatorBase`

### equals

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.equals" />

`equals(other)`

Evaluate Equality between Operators, overloaded by `==`. Only returns True if self and other are of the same representation (e.g. a DictStateFn and CircuitStateFn will never be equal, even if their vector representations are equal), their underlying primitives are equal (this means for ListOps, OperatorStateFns, or EvolvedOps the equality is evaluated recursively downwards), and their coefficients are equal.

**Parameters**

**other** (`OperatorBase`) – The `OperatorBase` to compare to self.

**Return type**

`bool`

**Returns**

A bool equal to the equality of self and other.

### eval

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.eval" />

`eval(front=None)`

Evaluate the Operator’s underlying function, either on a binary string or another Operator. A square binary Operator can be defined as a function taking a binary function to another binary function. This method returns the value of that function for a given StateFn or binary string. For example, `op.eval('0110').eval('1110')` can be seen as querying the Operator’s matrix representation by row 6 and column 14, and will return the complex value at those “indices.” Similarly for a StateFn, `op.eval('1011')` will return the complex value at row 11 of the vector representation of the StateFn, as all StateFns are defined to be evaluated from Zero implicitly (i.e. it is as if `.eval('0000')` is already called implicitly to always “indexing” from column 0).

If `front` is None, the matrix-representation of the operator is returned.

**Parameters**

**front** (`Union`\[`str`, `Dict`\[`str`, `complex`], `ndarray`, `OperatorBase`, `Statevector`, `None`]) – The bitstring, dict of bitstrings (with values being coefficients), or StateFn to evaluated by the Operator’s underlying function, or None.

**Return type**

`Union`\[`OperatorBase`, `complex`]

**Returns**

The output of the Operator’s evaluation function. If self is a `StateFn`, the result is a float or complex. If self is an Operator (`PrimitiveOp, ComposedOp, SummedOp, EvolvedOp,` etc.), the result is a StateFn. If `front` is None, the matrix-representation of the operator is returned, which is a `MatrixOp` for the operators and a `VectorStateFn` for state-functions. If either self or front contain proper `ListOps` (not ListOp subclasses), the result is an n-dimensional list of complex or StateFn results, resulting from the recursive evaluation by each OperatorBase in the ListOps.

### exp\_i

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.exp_i" />

`exp_i()`

Return a `CircuitOp` equivalent to e^-iH for this operator H.

**Return type**

`OperatorBase`

### from\_list

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.from_list" />

`classmethod from_list(pauli_list, coeff=1.0)`

Construct from a pauli\_list with the form \[(pauli\_str, coeffs)]

**Parameters**

*   **pauli\_list** (`List`\[`Tuple`\[`str`, `complex`]]) – A list of Tuple of pauli\_str and coefficient.
*   **coeff** (`Union`\[`complex`, `ParameterExpression`]) – A coefficient multiplying the primitive.

**Return type**

`PauliSumOp`

**Returns**

The PauliSumOp constructed from the pauli\_list.

### grouping\_type

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.grouping_type" />

`property grouping_type`

Type of Grouping

**Type**

Returns

**Return type**

`str`

### instance\_id

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.instance_id" />

`property instance_id`

Return the unique instance id.

**Return type**

`int`

### is\_zero

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.is_zero" />

`is_zero()`

Return this operator is zero operator or not.

**Return type**

`bool`

### log\_i

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.log_i" />

`log_i(massive=False)`

Return a `MatrixOp` equivalent to log(H)/-i for this operator H. This function is the effective inverse of exp\_i, equivalent to finding the Hermitian Operator which produces self when exponentiated.

**Return type**

`OperatorBase`

### matrix\_iter

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.matrix_iter" />

`matrix_iter(sparse=False)`

Return a matrix representation iterator.

This is a lazy iterator that converts each term in the PauliSumOp into a matrix as it is used. To convert to a single matrix use the [`to_matrix()`](#qiskit.opflow.primitive_ops.TaperedPauliSumOp.to_matrix "qiskit.opflow.primitive_ops.TaperedPauliSumOp.to_matrix") method.

**Parameters**

**sparse** (*bool*) – optionally return sparse CSR matrices if True, otherwise return Numpy array matrices (Default: False)

**Returns**

matrix iterator object for the PauliTable.

**Return type**

MatrixIterator

### mul

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.mul" />

`mul(scalar)`

Returns the scalar multiplication of the Operator, overloaded by `*`, including support for Terra’s `Parameters`, which can be bound to values later (via `bind_parameters`).

**Parameters**

**scalar** (`Union`\[`complex`, `ParameterExpression`]) – The real or complex scalar by which to multiply the Operator, or the `ParameterExpression` to serve as a placeholder for a scalar factor.

**Return type**

`OperatorBase`

**Returns**

An `OperatorBase` equivalent to product of self and scalar.

### neg

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.neg" />

`neg()`

Return the Operator’s negation, effectively just multiplying by -1.0, overloaded by `-`.

**Return type**

`OperatorBase`

**Returns**

An `OperatorBase` equivalent to the negation of self.

### num\_qubits

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.num_qubits" />

`property num_qubits`

The number of qubits over which the Operator is defined. If `op.num_qubits == 5`, then `op.eval('1' * 5)` will be valid, but `op.eval('11')` will not.

**Return type**

`int`

**Returns**

The number of qubits accepted by the Operator’s underlying function.

### parameters

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.parameters" />

`property parameters`

Return a set of Parameter objects contained in the Operator.

### permute

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.permute" />

`permute(permutation)`

Permutes the sequence of `PauliSumOp`.

**Parameters**

**permutation** (`List`\[`int`]) – A list defining where each Pauli should be permuted. The Pauli at index j of the primitive should be permuted to position permutation\[j].

**Return type**

`PauliSumOp`

**Returns**

A new PauliSumOp representing the permuted operator. For operator (X ^ Y ^ Z) and indices=\[1,2,4], it returns (X ^ I ^ Y ^ Z ^ I).

**Raises**

[**OpflowError**](qiskit.opflow.OpflowError "qiskit.opflow.OpflowError") – if indices do not define a new index for each qubit.

### power

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.power" />

`power(exponent)`

Return Operator composed with self multiple times, overloaded by `**`.

### primitive

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.primitive" />

`property primitive`

The primitive defining the underlying function of the Operator.

**Return type**

`Union`\[`QuantumCircuit`, `Operator`, `Pauli`, `SparsePauliOp`, `OperatorBase`]

**Returns**

The primitive object.

### primitive\_strings

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.primitive_strings" />

`primitive_strings()`

Return a set of strings describing the primitives contained in the Operator. For example, `{'QuantumCircuit', 'Pauli'}`. For hierarchical Operators, such as `ListOps`, this can help illuminate the primitives represented in the various recursive levels, and therefore which conversions can be applied.

**Return type**

`Set`\[`str`]

**Returns**

A set of strings describing the primitives contained within the Operator.

### reduce

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.reduce" />

`reduce(atol=None, rtol=None)`

Simplify the primitive `SparsePauliOp`.

**Parameters**

*   **atol** (`Optional`\[`float`]) – Absolute tolerance for checking if coefficients are zero (Default: 1e-8).
*   **rtol** (`Optional`\[`float`]) – Relative tolerance for checking if coefficients are zero (Default: 1e-5).

**Return type**

`PauliSumOp`

**Returns**

The simplified `PauliSumOp`.

### settings

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.settings" />

`property settings`

Return operator settings.

**Return type**

`Dict`

### tensor

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.tensor" />

`tensor(other)`

Return tensor product between self and other, overloaded by `^`. Note: You must be conscious of Qiskit’s big-endian bit printing convention. Meaning, X.tensor(Y) produces an X on qubit 0 and an Y on qubit 1, or X⨂Y, but would produce a QuantumCircuit which looks like

> -\[Y]- -\[X]-

Because Terra prints circuits and results with qubit 0 at the end of the string or circuit.

**Parameters**

**other** (`OperatorBase`) – The `OperatorBase` to tensor product with self.

**Return type**

`Union`\[`PauliSumOp`, `TensoredOp`]

**Returns**

An `OperatorBase` equivalent to the tensor product of self and other.

### tensorpower

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.tensorpower" />

`tensorpower(other)`

Return tensor product with self multiple times, overloaded by `^`.

**Parameters**

**other** (`int`) – The int number of times to tensor product self with itself via `tensorpower`.

**Return type**

`Union`\[`OperatorBase`, `int`]

**Returns**

An `OperatorBase` equivalent to the tensorpower of self by other.

### to\_circuit

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.to_circuit" />

`to_circuit()`

Returns a `QuantumCircuit` equivalent to this Operator.

**Return type**

`QuantumCircuit`

### to\_circuit\_op

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.to_circuit_op" />

`to_circuit_op()`

Returns a `CircuitOp` equivalent to this Operator.

**Return type**

`OperatorBase`

### to\_instruction

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.to_instruction" />

`to_instruction()`

Returns an `Instruction` equivalent to this Operator.

**Return type**

`Instruction`

### to\_matrix

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.to_matrix" />

`to_matrix(massive=False)`

Return NumPy representation of the Operator. Represents the evaluation of the Operator’s underlying function on every combination of basis binary strings. Warn if more than 16 qubits to force having to set `massive=True` if such a large vector is desired.

**Return type**

`ndarray`

**Returns**

The NumPy `ndarray` equivalent to this Operator.

### to\_matrix\_op

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.to_matrix_op" />

`to_matrix_op(massive=False)`

Returns a `MatrixOp` equivalent to this Operator.

**Return type**

`OperatorBase`

### to\_pauli\_op

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.to_pauli_op" />

`to_pauli_op(massive=False)`

Returns a sum of `PauliOp` s equivalent to this Operator.

**Return type**

`Union`\[`PauliOp`, `SummedOp`]

### to\_spmatrix

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.to_spmatrix" />

`to_spmatrix()`

Returns SciPy sparse matrix representation of the `PauliSumOp`.

**Return type**

`spmatrix`

**Returns**

CSR sparse matrix representation of the `PauliSumOp`.

**Raises**

**ValueError** – invalid parameters.

### z2\_symmetries

<span id="qiskit.opflow.primitive_ops.TaperedPauliSumOp.z2_symmetries" />

`property z2_symmetries`

Z2 symmetries which the Operator has.

**Return type**

`Z2Symmetries`

**Returns**

The Z2 Symmetries.

