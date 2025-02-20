---
title: ListOp
description: API reference for qiskit.opflow.list_ops.ListOp
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.opflow.list_ops.ListOp
---

# ListOp

<span id="qiskit.opflow.list_ops.ListOp" />

`ListOp(oplist, combo_fn=None, coeff=1.0, abelian=False, grad_combo_fn=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/list_ops/list_op.py "view source code")

Bases: [`qiskit.opflow.operator_base.OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

A Class for manipulating List Operators, and parent class to `SummedOp`, `ComposedOp`, and `TensoredOp`.

List Operators are classes for storing and manipulating lists of Operators, State functions, or Measurements, and include some rule or `combo_fn` defining how the Operator functions of the list constituents should be combined to form to cumulative Operator function of the `ListOp`. For example, a `SummedOp` has an addition-based `combo_fn`, so once the Operators in its list are evaluated against some bitstring to produce a list of results, we know to add up those results to produce the final result of the `SummedOp`’s evaluation. In theory, this `combo_fn` can be any function over classical complex values, but for convenience we’ve chosen for them to be defined over NumPy arrays and values. This way, large numbers of evaluations, such as after calling `to_matrix` on the list constituents, can be efficiently combined. While the combination function is defined over classical values, it should be understood as the operation by which each Operators’ underlying function is combined to form the underlying Operator function of the `ListOp`. In this way, the `ListOps` are the basis for constructing large and sophisticated Operators, State Functions, and Measurements.

The base `ListOp` class is particularly interesting, as its `combo_fn` is “the identity list Operation”. Meaning, if we understand the `combo_fn` as a function from a list of complex values to some output, one such function is returning the list as-is. This is powerful for constructing compact hierarchical Operators which return many measurements in multiple dimensional lists.

**Parameters**

*   **oplist** (`Sequence`\[[`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")]) – The list of `OperatorBases` defining this Operator’s underlying function.
*   **combo\_fn** (`Optional`\[`Callable`]) – The recombination function to combine classical results of the `oplist` Operators’ eval functions (e.g. sum). Default is lambda x: x.
*   **coeff** (`Union`\[`complex`, [`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")]) – A coefficient multiplying the operator
*   **abelian** (`bool`) – Indicates whether the Operators in `oplist` are known to mutually commute.
*   **grad\_combo\_fn** (`Optional`\[`Callable`]) – The gradient of recombination function. If None, the gradient will be computed automatically.
*   **the** (*Note that the default "recombination function" lambda above is essentially*) –
*   **values** (*identity - it accepts the list of*) –
*   **list.** (*and returns them in a*) –

## Methods Defined Here

### add

<span id="qiskit.opflow.list_ops.ListOp.add" />

`ListOp.add(other)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/list_ops/list_op.py "view source code")

Return Operator addition of self and other, overloaded by `+`.

**Parameters**

**other** ([`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")) – An `OperatorBase` with the same number of qubits as self, and in the same ‘Operator’, ‘State function’, or ‘Measurement’ category as self (i.e. the same type of underlying function).

**Return type**

[`ListOp`](qiskit.opflow.list_ops.ListOp "qiskit.opflow.list_ops.list_op.ListOp")

**Returns**

An `OperatorBase` equivalent to the sum of self and other.

### adjoint

<span id="qiskit.opflow.list_ops.ListOp.adjoint" />

`ListOp.adjoint()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/list_ops/list_op.py "view source code")

Return a new Operator equal to the Operator’s adjoint (conjugate transpose), overloaded by `~`. For StateFns, this also turns the StateFn into a measurement.

**Return type**

[`ListOp`](qiskit.opflow.list_ops.ListOp "qiskit.opflow.list_ops.list_op.ListOp")

**Returns**

An `OperatorBase` equivalent to the adjoint of self.

### assign\_parameters

<span id="qiskit.opflow.list_ops.ListOp.assign_parameters" />

`ListOp.assign_parameters(param_dict)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/list_ops/list_op.py "view source code")

Binds scalar values to any Terra `Parameters` in the coefficients or primitives of the Operator, or substitutes one `Parameter` for another. This method differs from Terra’s `assign_parameters` in that it also supports lists of values to assign for a give `Parameter`, in which case self will be copied for each parameterization in the binding list(s), and all the copies will be returned in an `OpList`. If lists of parameterizations are used, every `Parameter` in the param\_dict must have the same length list of parameterizations.

**Parameters**

**param\_dict** (`dict`) – The dictionary of `Parameters` to replace, and values or lists of values by which to replace them.

**Return type**

[`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

**Returns**

The `OperatorBase` with the `Parameters` in self replaced by the values or `Parameters` in param\_dict. If param\_dict contains parameterization lists, this `OperatorBase` is an `OpList`.

### compose

<span id="qiskit.opflow.list_ops.ListOp.compose" />

`ListOp.compose(other, permutation=None, front=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/list_ops/list_op.py "view source code")

Return Operator Composition between self and other (linear algebra-style: A\@B(x) = A(B(x))), overloaded by `@`.

Note: You must be conscious of Quantum Circuit vs. Linear Algebra ordering conventions. Meaning, X.compose(Y) produces an X∘Y on qubit 0, but would produce a QuantumCircuit which looks like

> -\[Y]-\[X]-

Because Terra prints circuits with the initial state at the left side of the circuit.

**Parameters**

*   **other** ([`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")) – The `OperatorBase` with which to compose self.
*   **permutation** (`Optional`\[`List`\[`int`]]) – `List[int]` which defines permutation on other operator.
*   **front** (`bool`) – If front==True, return `other.compose(self)`.

**Return type**

[`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

**Returns**

An `OperatorBase` equivalent to the function composition of self and other.

### default\_combo\_fn

<span id="qiskit.opflow.list_ops.ListOp.default_combo_fn" />

`static ListOp.default_combo_fn(x)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/list_ops/list_op.py "view source code")

ListOp default combo function i.e. lambda x: x

**Return type**

`Any`

### equals

<span id="qiskit.opflow.list_ops.ListOp.equals" />

`ListOp.equals(other)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/list_ops/list_op.py "view source code")

Evaluate Equality between Operators, overloaded by `==`. Only returns True if self and other are of the same representation (e.g. a DictStateFn and CircuitStateFn will never be equal, even if their vector representations are equal), their underlying primitives are equal (this means for ListOps, OperatorStateFns, or EvolvedOps the equality is evaluated recursively downwards), and their coefficients are equal.

**Parameters**

**other** ([`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")) – The `OperatorBase` to compare to self.

**Return type**

`bool`

**Returns**

A bool equal to the equality of self and other.

### eval

<span id="qiskit.opflow.list_ops.ListOp.eval" />

`ListOp.eval(front=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/list_ops/list_op.py "view source code")

Evaluate the Operator’s underlying function, either on a binary string or another Operator. A square binary Operator can be defined as a function taking a binary function to another binary function. This method returns the value of that function for a given StateFn or binary string. For example, `op.eval('0110').eval('1110')` can be seen as querying the Operator’s matrix representation by row 6 and column 14, and will return the complex value at those “indices.” Similarly for a StateFn, `op.eval('1011')` will return the complex value at row 11 of the vector representation of the StateFn, as all StateFns are defined to be evaluated from Zero implicitly (i.e. it is as if `.eval('0000')` is already called implicitly to always “indexing” from column 0).

ListOp’s eval recursively evaluates each Operator in `oplist`, and combines the results using the recombination function `combo_fn`.

**Parameters**

**front** (`Union`\[`str`, `Dict`\[`str`, `complex`], `ndarray`, [`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase"), [`Statevector`](qiskit.quantum_info.Statevector "qiskit.quantum_info.states.statevector.Statevector"), `None`]) – The bitstring, dict of bitstrings (with values being coefficients), or StateFn to evaluated by the Operator’s underlying function.

**Return type**

`Union`\[[`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase"), `complex`]

**Returns**

The output of the `oplist` Operators’ evaluation function, combined with the `combo_fn`. If either self or front contain proper `ListOps` (not ListOp subclasses), the result is an n-dimensional list of complex or StateFn results, resulting from the recursive evaluation by each OperatorBase in the ListOps.

**Raises**

*   **NotImplementedError** – Raised if called for a subclass which is not distributive.
*   **TypeError** – Operators with mixed hierarchies, such as a ListOp containing both PrimitiveOps and ListOps, are not supported.
*   **NotImplementedError** – Attempting to call ListOp’s eval from a non-distributive subclass.

### exp\_i

<span id="qiskit.opflow.list_ops.ListOp.exp_i" />

`ListOp.exp_i()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/list_ops/list_op.py "view source code")

Return an `OperatorBase` equivalent to an exponentiation of self \* -i, e^(-i\*op).

**Return type**

[`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

### log\_i

<span id="qiskit.opflow.list_ops.ListOp.log_i" />

`ListOp.log_i(massive=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/list_ops/list_op.py "view source code")

Return a `MatrixOp` equivalent to log(H)/-i for this operator H. This function is the effective inverse of exp\_i, equivalent to finding the Hermitian Operator which produces self when exponentiated. For proper ListOps, applies `log_i` to all ops in oplist.

**Return type**

[`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

### mul

<span id="qiskit.opflow.list_ops.ListOp.mul" />

`ListOp.mul(scalar)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/list_ops/list_op.py "view source code")

Returns the scalar multiplication of the Operator, overloaded by `*`, including support for Terra’s `Parameters`, which can be bound to values later (via `bind_parameters`).

**Parameters**

**scalar** (`Union`\[`complex`, [`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")]) – The real or complex scalar by which to multiply the Operator, or the `ParameterExpression` to serve as a placeholder for a scalar factor.

**Return type**

[`ListOp`](qiskit.opflow.list_ops.ListOp "qiskit.opflow.list_ops.list_op.ListOp")

**Returns**

An `OperatorBase` equivalent to product of self and scalar.

### permute

<span id="qiskit.opflow.list_ops.ListOp.permute" />

`ListOp.permute(permutation)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/list_ops/list_op.py "view source code")

Permute the qubits of the operator.

**Parameters**

**permutation** (`List`\[`int`]) – A list defining where each qubit should be permuted. The qubit at index j should be permuted to position permutation\[j].

**Return type**

[`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

**Returns**

A new ListOp representing the permuted operator.

**Raises**

[**OpflowError**](qiskit.opflow.OpflowError "qiskit.opflow.OpflowError") – if indices do not define a new index for each qubit.

### power

<span id="qiskit.opflow.list_ops.ListOp.power" />

`ListOp.power(exponent)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/list_ops/list_op.py "view source code")

Return Operator composed with self multiple times, overloaded by `**`.

**Return type**

[`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

### primitive\_strings

<span id="qiskit.opflow.list_ops.ListOp.primitive_strings" />

`ListOp.primitive_strings()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/list_ops/list_op.py "view source code")

Return a set of strings describing the primitives contained in the Operator. For example, `{'QuantumCircuit', 'Pauli'}`. For hierarchical Operators, such as `ListOps`, this can help illuminate the primitives represented in the various recursive levels, and therefore which conversions can be applied.

**Return type**

`Set`\[`str`]

**Returns**

A set of strings describing the primitives contained within the Operator.

### reduce

<span id="qiskit.opflow.list_ops.ListOp.reduce" />

`ListOp.reduce()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/list_ops/list_op.py "view source code")

Try collapsing the Operator structure, usually after some type of conversion, e.g. trying to add Operators in a SummedOp or delete needless IGates in a CircuitOp. If no reduction is available, just returns self.

**Return type**

[`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

**Returns**

The reduced `OperatorBase`.

### tensor

<span id="qiskit.opflow.list_ops.ListOp.tensor" />

`ListOp.tensor(other)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/list_ops/list_op.py "view source code")

Return tensor product between self and other, overloaded by `^`. Note: You must be conscious of Qiskit’s big-endian bit printing convention. Meaning, X.tensor(Y) produces an X on qubit 0 and an Y on qubit 1, or X⨂Y, but would produce a QuantumCircuit which looks like

> -\[Y]- -\[X]-

Because Terra prints circuits and results with qubit 0 at the end of the string or circuit.

**Parameters**

**other** ([`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")) – The `OperatorBase` to tensor product with self.

**Return type**

[`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

**Returns**

An `OperatorBase` equivalent to the tensor product of self and other.

### tensorpower

<span id="qiskit.opflow.list_ops.ListOp.tensorpower" />

`ListOp.tensorpower(other)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/list_ops/list_op.py "view source code")

Return tensor product with self multiple times, overloaded by `^`.

**Parameters**

**other** (`int`) – The int number of times to tensor product self with itself via `tensorpower`.

**Return type**

`Union`\[[`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase"), `int`]

**Returns**

An `OperatorBase` equivalent to the tensorpower of self by other.

### to\_circuit\_op

<span id="qiskit.opflow.list_ops.ListOp.to_circuit_op" />

`ListOp.to_circuit_op()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/list_ops/list_op.py "view source code")

Returns an equivalent Operator composed of only QuantumCircuit-based primitives, such as `CircuitOp` and `CircuitStateFn`.

**Return type**

[`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

### to\_matrix

<span id="qiskit.opflow.list_ops.ListOp.to_matrix" />

`ListOp.to_matrix(massive=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/list_ops/list_op.py "view source code")

Return NumPy representation of the Operator. Represents the evaluation of the Operator’s underlying function on every combination of basis binary strings. Warn if more than 16 qubits to force having to set `massive=True` if such a large vector is desired.

**Return type**

`ndarray`

**Returns**

The NumPy `ndarray` equivalent to this Operator.

### to\_matrix\_op

<span id="qiskit.opflow.list_ops.ListOp.to_matrix_op" />

`ListOp.to_matrix_op(massive=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/list_ops/list_op.py "view source code")

Returns an equivalent Operator composed of only NumPy-based primitives, such as `MatrixOp` and `VectorStateFn`.

**Return type**

[`ListOp`](qiskit.opflow.list_ops.ListOp "qiskit.opflow.list_ops.list_op.ListOp")

### to\_pauli\_op

<span id="qiskit.opflow.list_ops.ListOp.to_pauli_op" />

`ListOp.to_pauli_op(massive=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/list_ops/list_op.py "view source code")

Returns an equivalent Operator composed of only Pauli-based primitives, such as `PauliOp`.

**Return type**

[`ListOp`](qiskit.opflow.list_ops.ListOp "qiskit.opflow.list_ops.list_op.ListOp")

### to\_spmatrix

<span id="qiskit.opflow.list_ops.ListOp.to_spmatrix" />

`ListOp.to_spmatrix()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/list_ops/list_op.py "view source code")

Returns SciPy sparse matrix representation of the Operator.

**Return type**

`Union`\[`spmatrix`, `List`\[`spmatrix`]]

**Returns**

CSR sparse matrix representation of the Operator, or List thereof.

### traverse

<span id="qiskit.opflow.list_ops.ListOp.traverse" />

`ListOp.traverse(convert_fn, coeff=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/list_ops/list_op.py "view source code")

Apply the convert\_fn to each node in the oplist.

**Parameters**

*   **convert\_fn** (`Callable`) – The function to apply to the internal OperatorBase.
*   **coeff** (`Union`\[`complex`, [`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression"), `None`]) – A coefficient to multiply by after applying convert\_fn. If it is None, self.coeff is used instead.

**Return type**

[`ListOp`](qiskit.opflow.list_ops.ListOp "qiskit.opflow.list_ops.list_op.ListOp")

**Returns**

The converted ListOp.

## Attributes

<span id="qiskit.opflow.list_ops.ListOp.INDENTATION" />

### INDENTATION

`= '  '`

<span id="qiskit.opflow.list_ops.ListOp.abelian" />

### abelian

Whether the Operators in `oplist` are known to commute with one another.

**Return type**

`bool`

**Returns**

A bool indicating whether the `oplist` is Abelian.

<span id="qiskit.opflow.list_ops.ListOp.coeff" />

### coeff

The scalar coefficient multiplying the Operator.

**Return type**

`Union`\[`complex`, [`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")]

**Returns**

The coefficient.

<span id="qiskit.opflow.list_ops.ListOp.coeffs" />

### coeffs

Return a list of the coefficients of the operators listed. Raises exception for nested Listops.

**Return type**

`List`\[`Union`\[`complex`, [`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")]]

<span id="qiskit.opflow.list_ops.ListOp.combo_fn" />

### combo\_fn

The function defining how to combine `oplist` (or Numbers, or NumPy arrays) to produce the Operator’s underlying function. For example, SummedOp’s combination function is to add all of the Operators in `oplist`.

**Return type**

`Callable`

**Returns**

The combination function.

<span id="qiskit.opflow.list_ops.ListOp.distributive" />

### distributive

Indicates whether the ListOp or subclass is distributive under composition. ListOp and SummedOp are, meaning that (opv @ op) = (opv\[0] @ op + opv\[1] @ op) (using plus for SummedOp, list for ListOp, etc.), while ComposedOp and TensoredOp do not behave this way.

**Return type**

`bool`

**Returns**

A bool indicating whether the ListOp is distributive under composition.

<span id="qiskit.opflow.list_ops.ListOp.grad_combo_fn" />

### grad\_combo\_fn

The gradient of `combo_fn`.

**Return type**

`Optional`\[`Callable`]

<span id="qiskit.opflow.list_ops.ListOp.instance_id" />

### instance\_id

Return the unique instance id.

**Return type**

`int`

<span id="qiskit.opflow.list_ops.ListOp.num_qubits" />

### num\_qubits

**Return type**

`int`

<span id="qiskit.opflow.list_ops.ListOp.oplist" />

### oplist

The list of `OperatorBases` defining the underlying function of this Operator.

**Return type**

`List`\[[`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")]

**Returns**

The Operators defining the ListOp

<span id="qiskit.opflow.list_ops.ListOp.parameters" />

### parameters

<span id="qiskit.opflow.list_ops.ListOp.settings" />

### settings

Return settings.

**Return type**

`Dict`

