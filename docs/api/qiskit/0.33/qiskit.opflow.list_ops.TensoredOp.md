---
title: TensoredOp
description: API reference for qiskit.opflow.list_ops.TensoredOp
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.opflow.list_ops.TensoredOp
---

# TensoredOp

<span id="qiskit.opflow.list_ops.TensoredOp" />

`TensoredOp(oplist, coeff=1.0, abelian=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/opflow/list_ops/tensored_op.py "view source code")

Bases: `qiskit.opflow.list_ops.list_op.ListOp`

A class for lazily representing tensor products of Operators. Often Operators cannot be efficiently tensored to one another, but may be manipulated further so that they can be later. This class holds logic to indicate that the Operators in `oplist` are meant to be tensored together, and therefore if they reach a point in which they can be, such as after conversion to QuantumCircuits, they can be reduced by tensor product.

**Parameters**

*   **oplist** (`List`\[`OperatorBase`]) – The Operators being tensored.
*   **coeff** (`Union`\[`complex`, `ParameterExpression`]) – A coefficient multiplying the operator
*   **abelian** (`bool`) – Indicates whether the Operators in `oplist` are known to mutually commute.

## Methods Defined Here

### eval

<span id="qiskit.opflow.list_ops.TensoredOp.eval" />

`TensoredOp.eval(front=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/opflow/list_ops/tensored_op.py "view source code")

Evaluate the Operator’s underlying function, either on a binary string or another Operator. A square binary Operator can be defined as a function taking a binary function to another binary function. This method returns the value of that function for a given StateFn or binary string. For example, `op.eval('0110').eval('1110')` can be seen as querying the Operator’s matrix representation by row 6 and column 14, and will return the complex value at those “indices.” Similarly for a StateFn, `op.eval('1011')` will return the complex value at row 11 of the vector representation of the StateFn, as all StateFns are defined to be evaluated from Zero implicitly (i.e. it is as if `.eval('0000')` is already called implicitly to always “indexing” from column 0).

ListOp’s eval recursively evaluates each Operator in `oplist`, and combines the results using the recombination function `combo_fn`.

**Parameters**

**front** (`Union`\[`str`, `dict`, `ndarray`, `OperatorBase`, `Statevector`, `None`]) – The bitstring, dict of bitstrings (with values being coefficients), or StateFn to evaluated by the Operator’s underlying function.

**Return type**

`Union`\[`OperatorBase`, `complex`]

**Returns**

The output of the `oplist` Operators’ evaluation function, combined with the `combo_fn`. If either self or front contain proper `ListOps` (not ListOp subclasses), the result is an n-dimensional list of complex or StateFn results, resulting from the recursive evaluation by each OperatorBase in the ListOps.

**Raises**

*   **NotImplementedError** – Raised if called for a subclass which is not distributive.
*   **TypeError** – Operators with mixed hierarchies, such as a ListOp containing both PrimitiveOps and ListOps, are not supported.
*   **NotImplementedError** – Attempting to call ListOp’s eval from a non-distributive subclass.

### reduce

<span id="qiskit.opflow.list_ops.TensoredOp.reduce" />

`TensoredOp.reduce()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/opflow/list_ops/tensored_op.py "view source code")

Try collapsing the Operator structure, usually after some type of conversion, e.g. trying to add Operators in a SummedOp or delete needless IGates in a CircuitOp. If no reduction is available, just returns self.

**Return type**

`OperatorBase`

**Returns**

The reduced `OperatorBase`.

### tensor

<span id="qiskit.opflow.list_ops.TensoredOp.tensor" />

`TensoredOp.tensor(other)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/opflow/list_ops/tensored_op.py "view source code")

Return tensor product between self and other, overloaded by `^`. Note: You must be conscious of Qiskit’s big-endian bit printing convention. Meaning, X.tensor(Y) produces an X on qubit 0 and an Y on qubit 1, or X⨂Y, but would produce a QuantumCircuit which looks like

> -\[Y]- -\[X]-

Because Terra prints circuits and results with qubit 0 at the end of the string or circuit.

**Parameters**

**other** (`OperatorBase`) – The `OperatorBase` to tensor product with self.

**Return type**

`OperatorBase`

**Returns**

An `OperatorBase` equivalent to the tensor product of self and other.

### to\_circuit

<span id="qiskit.opflow.list_ops.TensoredOp.to_circuit" />

`TensoredOp.to_circuit()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/opflow/list_ops/tensored_op.py "view source code")

Returns the quantum circuit, representing the tensored operator.

**Return type**

`QuantumCircuit`

**Returns**

The circuit representation of the tensored operator.

**Raises**

[**OpflowError**](qiskit.opflow.OpflowError "qiskit.opflow.OpflowError") – for operators where a single underlying circuit can not be produced.

## Attributes

<span id="qiskit.opflow.list_ops.TensoredOp.INDENTATION" />

### INDENTATION

`= ' '`

<span id="qiskit.opflow.list_ops.TensoredOp.abelian" />

### abelian

Whether the Operators in `oplist` are known to commute with one another.

**Return type**

`bool`

**Returns**

A bool indicating whether the `oplist` is Abelian.

<span id="qiskit.opflow.list_ops.TensoredOp.coeff" />

### coeff

The scalar coefficient multiplying the Operator.

**Return type**

`Union`\[`complex`, `ParameterExpression`]

**Returns**

The coefficient.

<span id="qiskit.opflow.list_ops.TensoredOp.coeffs" />

### coeffs

Return a list of the coefficients of the operators listed. Raises exception for nested Listops.

**Return type**

`List`\[`Union`\[`complex`, `ParameterExpression`]]

<span id="qiskit.opflow.list_ops.TensoredOp.combo_fn" />

### combo\_fn

The function defining how to combine `oplist` (or Numbers, or NumPy arrays) to produce the Operator’s underlying function. For example, SummedOp’s combination function is to add all of the Operators in `oplist`.

**Return type**

`Callable`

**Returns**

The combination function.

<span id="qiskit.opflow.list_ops.TensoredOp.distributive" />

### distributive

**Return type**

`bool`

<span id="qiskit.opflow.list_ops.TensoredOp.grad_combo_fn" />

### grad\_combo\_fn

The gradient of `combo_fn`.

**Return type**

`Optional`\[`Callable`]

<span id="qiskit.opflow.list_ops.TensoredOp.instance_id" />

### instance\_id

Return the unique instance id.

**Return type**

`int`

<span id="qiskit.opflow.list_ops.TensoredOp.num_qubits" />

### num\_qubits

**Return type**

`int`

<span id="qiskit.opflow.list_ops.TensoredOp.oplist" />

### oplist

The list of `OperatorBases` defining the underlying function of this Operator.

**Return type**

`List`\[`OperatorBase`]

**Returns**

The Operators defining the ListOp

<span id="qiskit.opflow.list_ops.TensoredOp.parameters" />

### parameters

<span id="qiskit.opflow.list_ops.TensoredOp.settings" />

### settings

Return settings.

**Return type**

`Dict`

