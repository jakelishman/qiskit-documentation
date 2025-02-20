---
title: MatrixOp
description: API reference for qiskit.opflow.primitive_ops.MatrixOp
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.opflow.primitive_ops.MatrixOp
---

# MatrixOp

<span id="qiskit.opflow.primitive_ops.MatrixOp" />

`MatrixOp(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/primitive_ops/matrix_op.py "view source code")

Bases: [`PrimitiveOp`](qiskit.opflow.primitive_ops.PrimitiveOp "qiskit.opflow.primitive_ops.primitive_op.PrimitiveOp")

Deprecated: Class for Operators represented by matrices, backed by Terra’s `Operator` module.

<Admonition title="Deprecated since version 0.24.0" type="danger">
  The class `qiskit.opflow.primitive_ops.matrix_op.MatrixOp` is deprecated as of qiskit-terra 0.24.0. It will be removed no earlier than 3 months after the release date. For code migration guidelines, visit [https://qisk.it/opflow\_migration](https://qisk.it/opflow_migration).
</Admonition>

**Parameters**

*   **primitive** – The matrix-like object which defines the behavior of the underlying function.
*   **coeff** – A coefficient multiplying the primitive

**Raises**

*   **TypeError** – invalid parameters.
*   **ValueError** – invalid parameters.

## Methods Defined Here

<span id="qiskit-opflow-primitive-ops-matrixop-add" />

### add

<span id="qiskit.opflow.primitive_ops.MatrixOp.add" />

`MatrixOp.add(other)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/primitive_ops/matrix_op.py "view source code")

Return Operator addition of self and other, overloaded by `+`.

**Parameters**

**other** ([*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")) – An `OperatorBase` with the same number of qubits as self, and in the same ‘Operator’, ‘State function’, or ‘Measurement’ category as self (i.e. the same type of underlying function).

**Returns**

An `OperatorBase` equivalent to the sum of self and other.

**Return type**

[*MatrixOp*](qiskit.opflow.primitive_ops.MatrixOp "qiskit.opflow.primitive_ops.matrix_op.MatrixOp") | [*SummedOp*](qiskit.opflow.list_ops.SummedOp "qiskit.opflow.list_ops.summed_op.SummedOp")

<span id="qiskit-opflow-primitive-ops-matrixop-adjoint" />

### adjoint

<span id="qiskit.opflow.primitive_ops.MatrixOp.adjoint" />

`MatrixOp.adjoint()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/primitive_ops/matrix_op.py "view source code")

Return a new Operator equal to the Operator’s adjoint (conjugate transpose), overloaded by `~`. For StateFns, this also turns the StateFn into a measurement.

**Returns**

An `OperatorBase` equivalent to the adjoint of self.

**Return type**

[*MatrixOp*](qiskit.opflow.primitive_ops.MatrixOp "qiskit.opflow.primitive_ops.matrix_op.MatrixOp")

<span id="qiskit-opflow-primitive-ops-matrixop-compose" />

### compose

<span id="qiskit.opflow.primitive_ops.MatrixOp.compose" />

`MatrixOp.compose(other, permutation=None, front=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/primitive_ops/matrix_op.py "view source code")

Return Operator Composition between self and other (linear algebra-style: A\@B(x) = A(B(x))), overloaded by `@`.

Note: You must be conscious of Quantum Circuit vs. Linear Algebra ordering conventions. Meaning, X.compose(Y) produces an X∘Y on qubit 0, but would produce a QuantumCircuit which looks like

> -\[Y]-\[X]-

Because Terra prints circuits with the initial state at the left side of the circuit.

**Parameters**

*   **other** ([*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")) – The `OperatorBase` with which to compose self.
*   **permutation** (*List\[int] | None*) – `List[int]` which defines permutation on other operator.
*   **front** (*bool*) – If front==True, return `other.compose(self)`.

**Returns**

An `OperatorBase` equivalent to the function composition of self and other.

**Return type**

[*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

<span id="qiskit-opflow-primitive-ops-matrixop-equals" />

### equals

<span id="qiskit.opflow.primitive_ops.MatrixOp.equals" />

`MatrixOp.equals(other)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/primitive_ops/matrix_op.py "view source code")

Evaluate Equality between Operators, overloaded by `==`. Only returns True if self and other are of the same representation (e.g. a DictStateFn and CircuitStateFn will never be equal, even if their vector representations are equal), their underlying primitives are equal (this means for ListOps, OperatorStateFns, or EvolvedOps the equality is evaluated recursively downwards), and their coefficients are equal.

**Parameters**

**other** ([*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")) – The `OperatorBase` to compare to self.

**Returns**

A bool equal to the equality of self and other.

**Return type**

bool

<span id="qiskit-opflow-primitive-ops-matrixop-eval" />

### eval

<span id="qiskit.opflow.primitive_ops.MatrixOp.eval" />

`MatrixOp.eval(front=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/primitive_ops/matrix_op.py "view source code")

Evaluate the Operator’s underlying function, either on a binary string or another Operator. A square binary Operator can be defined as a function taking a binary function to another binary function. This method returns the value of that function for a given StateFn or binary string. For example, `op.eval('0110').eval('1110')` can be seen as querying the Operator’s matrix representation by row 6 and column 14, and will return the complex value at those “indices.” Similarly for a StateFn, `op.eval('1011')` will return the complex value at row 11 of the vector representation of the StateFn, as all StateFns are defined to be evaluated from Zero implicitly (i.e. it is as if `.eval('0000')` is already called implicitly to always “indexing” from column 0).

If `front` is None, the matrix-representation of the operator is returned.

**Parameters**

**front** (*str | Dict\[str, complex] |* [*ndarray*](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.25)")  *|*[*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")  *|*[*Statevector*](qiskit.quantum_info.Statevector "qiskit.quantum_info.states.statevector.Statevector") *| None*) – The bitstring, dict of bitstrings (with values being coefficients), or StateFn to evaluated by the Operator’s underlying function, or None.

**Returns**

The output of the Operator’s evaluation function. If self is a `StateFn`, the result is a float or complex. If self is an Operator (`PrimitiveOp, ComposedOp, SummedOp, EvolvedOp,` etc.), the result is a StateFn. If `front` is None, the matrix-representation of the operator is returned, which is a `MatrixOp` for the operators and a `VectorStateFn` for state-functions. If either self or front contain proper `ListOps` (not ListOp subclasses), the result is an n-dimensional list of complex or StateFn results, resulting from the recursive evaluation by each OperatorBase in the ListOps.

**Return type**

[*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase") | complex

<span id="qiskit-opflow-primitive-ops-matrixop-exp-i" />

### exp\_i

<span id="qiskit.opflow.primitive_ops.MatrixOp.exp_i" />

`MatrixOp.exp_i()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/primitive_ops/matrix_op.py "view source code")

Return a `CircuitOp` equivalent to e^-iH for this operator H

**Return type**

[*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

<span id="qiskit-opflow-primitive-ops-matrixop-permute" />

### permute

<span id="qiskit.opflow.primitive_ops.MatrixOp.permute" />

`MatrixOp.permute(permutation=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/primitive_ops/matrix_op.py "view source code")

Creates a new MatrixOp that acts on the permuted qubits.

**Parameters**

**permutation** (*List\[int] | None*) – A list defining where each qubit should be permuted. The qubit at index j should be permuted to position permutation\[j].

**Returns**

A new MatrixOp representing the permuted operator.

**Raises**

[**OpflowError**](qiskit.opflow.OpflowError "qiskit.opflow.OpflowError") – if indices do not define a new index for each qubit.

**Return type**

[*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

<span id="qiskit-opflow-primitive-ops-matrixop-primitive-strings" />

### primitive\_strings

<span id="qiskit.opflow.primitive_ops.MatrixOp.primitive_strings" />

`MatrixOp.primitive_strings()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/primitive_ops/matrix_op.py "view source code")

Return a set of strings describing the primitives contained in the Operator. For example, `{'QuantumCircuit', 'Pauli'}`. For hierarchical Operators, such as `ListOps`, this can help illuminate the primitives represented in the various recursive levels, and therefore which conversions can be applied.

**Returns**

A set of strings describing the primitives contained within the Operator.

**Return type**

*Set*\[str]

<span id="qiskit-opflow-primitive-ops-matrixop-tensor" />

### tensor

<span id="qiskit.opflow.primitive_ops.MatrixOp.tensor" />

`MatrixOp.tensor(other)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/primitive_ops/matrix_op.py "view source code")

Return tensor product between self and other, overloaded by `^`. Note: You must be conscious of Qiskit’s big-endian bit printing convention. Meaning, X.tensor(Y) produces an X on qubit 0 and an Y on qubit 1, or X⨂Y, but would produce a QuantumCircuit which looks like

> -\[Y]- -\[X]-

Because Terra prints circuits and results with qubit 0 at the end of the string or circuit.

**Parameters**

**other** ([*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")) – The `OperatorBase` to tensor product with self.

**Returns**

An `OperatorBase` equivalent to the tensor product of self and other.

**Return type**

[*MatrixOp*](qiskit.opflow.primitive_ops.MatrixOp "qiskit.opflow.primitive_ops.matrix_op.MatrixOp") | [*TensoredOp*](qiskit.opflow.list_ops.TensoredOp "qiskit.opflow.list_ops.tensored_op.TensoredOp")

<span id="qiskit-opflow-primitive-ops-matrixop-to-instruction" />

### to\_instruction

<span id="qiskit.opflow.primitive_ops.MatrixOp.to_instruction" />

`MatrixOp.to_instruction()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/primitive_ops/matrix_op.py "view source code")

Returns an `Instruction` equivalent to this Operator.

**Return type**

[*Instruction*](qiskit.circuit.Instruction "qiskit.circuit.instruction.Instruction")

<span id="qiskit-opflow-primitive-ops-matrixop-to-matrix" />

### to\_matrix

<span id="qiskit.opflow.primitive_ops.MatrixOp.to_matrix" />

`MatrixOp.to_matrix(massive=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/primitive_ops/matrix_op.py "view source code")

Return NumPy representation of the Operator. Represents the evaluation of the Operator’s underlying function on every combination of basis binary strings. Warn if more than 16 qubits to force having to set `massive=True` if such a large vector is desired.

**Returns**

The NumPy `ndarray` equivalent to this Operator.

**Return type**

[*ndarray*](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.25)")

<span id="qiskit-opflow-primitive-ops-matrixop-to-matrix-op" />

### to\_matrix\_op

<span id="qiskit.opflow.primitive_ops.MatrixOp.to_matrix_op" />

`MatrixOp.to_matrix_op(massive=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/primitive_ops/matrix_op.py "view source code")

Returns a `MatrixOp` equivalent to this Operator.

**Return type**

[*MatrixOp*](qiskit.opflow.primitive_ops.MatrixOp "qiskit.opflow.primitive_ops.matrix_op.MatrixOp")

## Attributes

<span id="qiskit.opflow.primitive_ops.MatrixOp.INDENTATION" />

### INDENTATION

`= '  '`

<span id="qiskit.opflow.primitive_ops.MatrixOp.coeff" />

### coeff

The scalar coefficient multiplying the Operator.

**Returns**

The coefficient.

<span id="qiskit.opflow.primitive_ops.MatrixOp.instance_id" />

### instance\_id

Return the unique instance id.

<span id="qiskit.opflow.primitive_ops.MatrixOp.num_qubits" />

### num\_qubits

<span id="qiskit.opflow.primitive_ops.MatrixOp.parameters" />

### parameters

<span id="qiskit.opflow.primitive_ops.MatrixOp.primitive" />

### primitive

`Operator`

The primitive defining the underlying function of the Operator.

**Returns**

The primitive object.

<span id="qiskit.opflow.primitive_ops.MatrixOp.settings" />

### settings

Return operator settings.

