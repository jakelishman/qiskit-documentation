---
title: CircuitStateFn
description: API reference for qiskit.opflow.state_fns.CircuitStateFn
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.opflow.state_fns.CircuitStateFn
---

# qiskit.opflow\.state\_fns.CircuitStateFn

<span id="qiskit.opflow.state_fns.CircuitStateFn" />

`CircuitStateFn(primitive=None, coeff=1.0, is_measurement=False, from_operator=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/opflow/state_fns/circuit_state_fn.py "view source code")

A class for state functions and measurements which are defined by the action of a QuantumCircuit starting from |0⟩, and stored using Terra’s `QuantumCircuit` class.

**Parameters**

*   **primitive** (`Union`\[`QuantumCircuit`, `Instruction`, `None`]) – The `QuantumCircuit` (or `Instruction`, which will be converted) which defines the behavior of the underlying function.
*   **coeff** (`Union`\[`complex`, `ParameterExpression`]) – A coefficient multiplying the state function.
*   **is\_measurement** (`bool`) – Whether the StateFn is a measurement operator.
*   **from\_operator** (`bool`) – if True the StateFn is derived from OperatorStateFn. (Default: False)

**Raises**

**TypeError** – Unsupported primitive, or primitive has ClassicalRegisters.

### \_\_init\_\_

<span id="qiskit.opflow.state_fns.CircuitStateFn.__init__" />

`__init__(primitive=None, coeff=1.0, is_measurement=False, from_operator=False)`

**Parameters**

*   **primitive** (`Union`\[`QuantumCircuit`, `Instruction`, `None`]) – The `QuantumCircuit` (or `Instruction`, which will be converted) which defines the behavior of the underlying function.
*   **coeff** (`Union`\[`complex`, `ParameterExpression`]) – A coefficient multiplying the state function.
*   **is\_measurement** (`bool`) – Whether the StateFn is a measurement operator.
*   **from\_operator** (`bool`) – if True the StateFn is derived from OperatorStateFn. (Default: False)

**Raises**

**TypeError** – Unsupported primitive, or primitive has ClassicalRegisters.

## Methods

|                                                                                                                                                           |                                                                                                                                                                               |
| --------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.opflow.state_fns.CircuitStateFn.__init__ "qiskit.opflow.state_fns.CircuitStateFn.__init__")(\[primitive, coeff, is\_measurement, …]) | **type primitive**`Union`\[`QuantumCircuit`, `Instruction`, `None`]                                                                                                           |
| [`add`](#qiskit.opflow.state_fns.CircuitStateFn.add "qiskit.opflow.state_fns.CircuitStateFn.add")(other)                                                  | Return Operator addition of self and other, overloaded by `+`.                                                                                                                |
| [`adjoint`](#qiskit.opflow.state_fns.CircuitStateFn.adjoint "qiskit.opflow.state_fns.CircuitStateFn.adjoint")()                                           | Return a new Operator equal to the Operator’s adjoint (conjugate transpose), overloaded by `~`.                                                                               |
| [`assign_parameters`](#qiskit.opflow.state_fns.CircuitStateFn.assign_parameters "qiskit.opflow.state_fns.CircuitStateFn.assign_parameters")(param\_dict)  | Binds scalar values to any Terra `Parameters` in the coefficients or primitives of the Operator, or substitutes one `Parameter` for another.                                  |
| [`bind_parameters`](#qiskit.opflow.state_fns.CircuitStateFn.bind_parameters "qiskit.opflow.state_fns.CircuitStateFn.bind_parameters")(param\_dict)        | Same as assign\_parameters, but maintained for consistency with QuantumCircuit in Terra (which has both assign\_parameters and bind\_parameters).                             |
| [`compose`](#qiskit.opflow.state_fns.CircuitStateFn.compose "qiskit.opflow.state_fns.CircuitStateFn.compose")(other\[, permutation, front])               | Composition (Linear algebra-style: A\@B(x) = A(B(x))) is not well defined for states in the binary function model, but is well defined for measurements.                      |
| [`copy`](#qiskit.opflow.state_fns.CircuitStateFn.copy "qiskit.opflow.state_fns.CircuitStateFn.copy")()                                                    | Return a deep copy of the Operator.                                                                                                                                           |
| [`equals`](#qiskit.opflow.state_fns.CircuitStateFn.equals "qiskit.opflow.state_fns.CircuitStateFn.equals")(other)                                         | Evaluate Equality between Operators, overloaded by `==`.                                                                                                                      |
| [`eval`](#qiskit.opflow.state_fns.CircuitStateFn.eval "qiskit.opflow.state_fns.CircuitStateFn.eval")(\[front])                                            | Evaluate the Operator’s underlying function, either on a binary string or another Operator.                                                                                   |
| [`from_dict`](#qiskit.opflow.state_fns.CircuitStateFn.from_dict "qiskit.opflow.state_fns.CircuitStateFn.from_dict")(density\_dict)                        | Construct the CircuitStateFn from a dict mapping strings to probability densities.                                                                                            |
| [`from_vector`](#qiskit.opflow.state_fns.CircuitStateFn.from_vector "qiskit.opflow.state_fns.CircuitStateFn.from_vector")(statevector)                    | Construct the CircuitStateFn from a vector representing the statevector.                                                                                                      |
| [`mul`](#qiskit.opflow.state_fns.CircuitStateFn.mul "qiskit.opflow.state_fns.CircuitStateFn.mul")(scalar)                                                 | Returns the scalar multiplication of the Operator, overloaded by `*`, including support for Terra’s `Parameters`, which can be bound to values later (via `bind_parameters`). |
| [`neg`](#qiskit.opflow.state_fns.CircuitStateFn.neg "qiskit.opflow.state_fns.CircuitStateFn.neg")()                                                       | Return the Operator’s negation, effectively just multiplying by -1.0, overloaded by `-`.                                                                                      |
| [`permute`](#qiskit.opflow.state_fns.CircuitStateFn.permute "qiskit.opflow.state_fns.CircuitStateFn.permute")(permutation)                                | Permute the qubits of the circuit.                                                                                                                                            |
| [`power`](#qiskit.opflow.state_fns.CircuitStateFn.power "qiskit.opflow.state_fns.CircuitStateFn.power")(exponent)                                         | Compose with Self Multiple Times, undefined for StateFns.                                                                                                                     |
| [`primitive_strings`](#qiskit.opflow.state_fns.CircuitStateFn.primitive_strings "qiskit.opflow.state_fns.CircuitStateFn.primitive_strings")()             | Return a set of strings describing the primitives contained in the Operator.                                                                                                  |
| [`reduce`](#qiskit.opflow.state_fns.CircuitStateFn.reduce "qiskit.opflow.state_fns.CircuitStateFn.reduce")()                                              | Try collapsing the Operator structure, usually after some type of conversion, e.g.                                                                                            |
| [`sample`](#qiskit.opflow.state_fns.CircuitStateFn.sample "qiskit.opflow.state_fns.CircuitStateFn.sample")(\[shots, massive, reverse\_endianness])        | Sample the state function as a normalized probability distribution.                                                                                                           |
| [`tensor`](#qiskit.opflow.state_fns.CircuitStateFn.tensor "qiskit.opflow.state_fns.CircuitStateFn.tensor")(other)                                         | Return tensor product between self and other, overloaded by `^`.                                                                                                              |
| [`tensorpower`](#qiskit.opflow.state_fns.CircuitStateFn.tensorpower "qiskit.opflow.state_fns.CircuitStateFn.tensorpower")(other)                          | Return tensor product with self multiple times, overloaded by `^`.                                                                                                            |
| [`to_circuit`](#qiskit.opflow.state_fns.CircuitStateFn.to_circuit "qiskit.opflow.state_fns.CircuitStateFn.to_circuit")(\[meas])                           | Return QuantumCircuit representing StateFn                                                                                                                                    |
| [`to_circuit_op`](#qiskit.opflow.state_fns.CircuitStateFn.to_circuit_op "qiskit.opflow.state_fns.CircuitStateFn.to_circuit_op")()                         | Return `StateFnCircuit` corresponding to this StateFn.                                                                                                                        |
| [`to_density_matrix`](#qiskit.opflow.state_fns.CircuitStateFn.to_density_matrix "qiskit.opflow.state_fns.CircuitStateFn.to_density_matrix")(\[massive])   | Return numpy matrix of density operator, warn if more than 16 qubits to force the user to set massive=True if they want such a large matrix.                                  |
| [`to_instruction`](#qiskit.opflow.state_fns.CircuitStateFn.to_instruction "qiskit.opflow.state_fns.CircuitStateFn.to_instruction")()                      | Return Instruction corresponding to primitive.                                                                                                                                |
| [`to_matrix`](#qiskit.opflow.state_fns.CircuitStateFn.to_matrix "qiskit.opflow.state_fns.CircuitStateFn.to_matrix")(\[massive])                           | Return NumPy representation of the Operator.                                                                                                                                  |
| [`to_matrix_op`](#qiskit.opflow.state_fns.CircuitStateFn.to_matrix_op "qiskit.opflow.state_fns.CircuitStateFn.to_matrix_op")(\[massive])                  | Return a `VectorStateFn` for this `StateFn`.                                                                                                                                  |
| [`to_spmatrix`](#qiskit.opflow.state_fns.CircuitStateFn.to_spmatrix "qiskit.opflow.state_fns.CircuitStateFn.to_spmatrix")()                               | Return SciPy sparse matrix representation of the Operator.                                                                                                                    |
| [`traverse`](#qiskit.opflow.state_fns.CircuitStateFn.traverse "qiskit.opflow.state_fns.CircuitStateFn.traverse")(convert\_fn\[, coeff])                   | Apply the convert\_fn to the internal primitive if the primitive is an Operator (as in the case of `OperatorStateFn`).                                                        |

## Attributes

|                                                                                                                                    |                                                                            |
| ---------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| `INDENTATION`                                                                                                                      |                                                                            |
| [`coeff`](#qiskit.opflow.state_fns.CircuitStateFn.coeff "qiskit.opflow.state_fns.CircuitStateFn.coeff")                            | A coefficient by which the state function is multiplied.                   |
| [`instance_id`](#qiskit.opflow.state_fns.CircuitStateFn.instance_id "qiskit.opflow.state_fns.CircuitStateFn.instance_id")          | Return the unique instance id.                                             |
| [`is_measurement`](#qiskit.opflow.state_fns.CircuitStateFn.is_measurement "qiskit.opflow.state_fns.CircuitStateFn.is_measurement") | Whether the StateFn object is a measurement Operator.                      |
| [`num_qubits`](#qiskit.opflow.state_fns.CircuitStateFn.num_qubits "qiskit.opflow.state_fns.CircuitStateFn.num_qubits")             | The number of qubits over which the Operator is defined.                   |
| [`parameters`](#qiskit.opflow.state_fns.CircuitStateFn.parameters "qiskit.opflow.state_fns.CircuitStateFn.parameters")             | Return a set of Parameter objects contained in the Operator.               |
| [`primitive`](#qiskit.opflow.state_fns.CircuitStateFn.primitive "qiskit.opflow.state_fns.CircuitStateFn.primitive")                | The primitive which defines the behavior of the underlying State function. |
| [`settings`](#qiskit.opflow.state_fns.CircuitStateFn.settings "qiskit.opflow.state_fns.CircuitStateFn.settings")                   | Return settings.                                                           |

### add

<span id="qiskit.opflow.state_fns.CircuitStateFn.add" />

`add(other)`

Return Operator addition of self and other, overloaded by `+`.

**Parameters**

**other** (`OperatorBase`) – An `OperatorBase` with the same number of qubits as self, and in the same ‘Operator’, ‘State function’, or ‘Measurement’ category as self (i.e. the same type of underlying function).

**Return type**

`OperatorBase`

**Returns**

An `OperatorBase` equivalent to the sum of self and other.

### adjoint

<span id="qiskit.opflow.state_fns.CircuitStateFn.adjoint" />

`adjoint()`

Return a new Operator equal to the Operator’s adjoint (conjugate transpose), overloaded by `~`. For StateFns, this also turns the StateFn into a measurement.

**Return type**

`CircuitStateFn`

**Returns**

An `OperatorBase` equivalent to the adjoint of self.

### assign\_parameters

<span id="qiskit.opflow.state_fns.CircuitStateFn.assign_parameters" />

`assign_parameters(param_dict)`

Binds scalar values to any Terra `Parameters` in the coefficients or primitives of the Operator, or substitutes one `Parameter` for another. This method differs from Terra’s `assign_parameters` in that it also supports lists of values to assign for a give `Parameter`, in which case self will be copied for each parameterization in the binding list(s), and all the copies will be returned in an `OpList`. If lists of parameterizations are used, every `Parameter` in the param\_dict must have the same length list of parameterizations.

**Parameters**

**param\_dict** (`dict`) – The dictionary of `Parameters` to replace, and values or lists of values by which to replace them.

**Return type**

`Union`\[`CircuitStateFn`, `ListOp`]

**Returns**

The `OperatorBase` with the `Parameters` in self replaced by the values or `Parameters` in param\_dict. If param\_dict contains parameterization lists, this `OperatorBase` is an `OpList`.

### bind\_parameters

<span id="qiskit.opflow.state_fns.CircuitStateFn.bind_parameters" />

`bind_parameters(param_dict)`

Same as assign\_parameters, but maintained for consistency with QuantumCircuit in Terra (which has both assign\_parameters and bind\_parameters).

**Return type**

`OperatorBase`

### coeff

<span id="qiskit.opflow.state_fns.CircuitStateFn.coeff" />

`property coeff`

A coefficient by which the state function is multiplied.

**Return type**

`Union`\[`complex`, `ParameterExpression`]

### compose

<span id="qiskit.opflow.state_fns.CircuitStateFn.compose" />

`compose(other, permutation=None, front=False)`

Composition (Linear algebra-style: A\@B(x) = A(B(x))) is not well defined for states in the binary function model, but is well defined for measurements.

**Parameters**

*   **other** (`OperatorBase`) – The Operator to compose with self.
*   **permutation** (`Optional`\[`List`\[`int`]]) – `List[int]` which defines permutation on other operator.
*   **front** (`bool`) – If front==True, return `other.compose(self)`.

**Return type**

`OperatorBase`

**Returns**

An Operator equivalent to the function composition of self and other.

**Raises**

**ValueError** – If self is not a measurement, it cannot be composed from the right.

### copy

<span id="qiskit.opflow.state_fns.CircuitStateFn.copy" />

`copy()`

Return a deep copy of the Operator.

**Return type**

`OperatorBase`

### equals

<span id="qiskit.opflow.state_fns.CircuitStateFn.equals" />

`equals(other)`

Evaluate Equality between Operators, overloaded by `==`. Only returns True if self and other are of the same representation (e.g. a DictStateFn and CircuitStateFn will never be equal, even if their vector representations are equal), their underlying primitives are equal (this means for ListOps, OperatorStateFns, or EvolvedOps the equality is evaluated recursively downwards), and their coefficients are equal.

**Parameters**

**other** (`OperatorBase`) – The `OperatorBase` to compare to self.

**Return type**

`bool`

**Returns**

A bool equal to the equality of self and other.

### eval

<span id="qiskit.opflow.state_fns.CircuitStateFn.eval" />

`eval(front=None)`

Evaluate the Operator’s underlying function, either on a binary string or another Operator. A square binary Operator can be defined as a function taking a binary function to another binary function. This method returns the value of that function for a given StateFn or binary string. For example, `op.eval('0110').eval('1110')` can be seen as querying the Operator’s matrix representation by row 6 and column 14, and will return the complex value at those “indices.” Similarly for a StateFn, `op.eval('1011')` will return the complex value at row 11 of the vector representation of the StateFn, as all StateFns are defined to be evaluated from Zero implicitly (i.e. it is as if `.eval('0000')` is already called implicitly to always “indexing” from column 0).

If `front` is None, the matrix-representation of the operator is returned.

**Parameters**

**front** (`Union`\[`str`, `Dict`\[`str`, `complex`], `ndarray`, `OperatorBase`, `Statevector`, `None`]) – The bitstring, dict of bitstrings (with values being coefficients), or StateFn to evaluated by the Operator’s underlying function, or None.

**Return type**

`Union`\[`OperatorBase`, `complex`]

**Returns**

The output of the Operator’s evaluation function. If self is a `StateFn`, the result is a float or complex. If self is an Operator (`PrimitiveOp, ComposedOp, SummedOp, EvolvedOp,` etc.), the result is a StateFn. If `front` is None, the matrix-representation of the operator is returned, which is a `MatrixOp` for the operators and a `VectorStateFn` for state-functions. If either self or front contain proper `ListOps` (not ListOp subclasses), the result is an n-dimensional list of complex or StateFn results, resulting from the recursive evaluation by each OperatorBase in the ListOps.

### from\_dict

<span id="qiskit.opflow.state_fns.CircuitStateFn.from_dict" />

`static from_dict(density_dict)`

Construct the CircuitStateFn from a dict mapping strings to probability densities.

**Parameters**

**density\_dict** (`dict`) – The dict representing the desired state.

**Return type**

`CircuitStateFn`

**Returns**

The CircuitStateFn created from the dict.

### from\_vector

<span id="qiskit.opflow.state_fns.CircuitStateFn.from_vector" />

`static from_vector(statevector)`

Construct the CircuitStateFn from a vector representing the statevector.

**Parameters**

**statevector** (`ndarray`) – The statevector representing the desired state.

**Return type**

`CircuitStateFn`

**Returns**

The CircuitStateFn created from the vector.

### instance\_id

<span id="qiskit.opflow.state_fns.CircuitStateFn.instance_id" />

`property instance_id`

Return the unique instance id.

**Return type**

`int`

### is\_measurement

<span id="qiskit.opflow.state_fns.CircuitStateFn.is_measurement" />

`property is_measurement`

Whether the StateFn object is a measurement Operator.

**Return type**

`bool`

### mul

<span id="qiskit.opflow.state_fns.CircuitStateFn.mul" />

`mul(scalar)`

Returns the scalar multiplication of the Operator, overloaded by `*`, including support for Terra’s `Parameters`, which can be bound to values later (via `bind_parameters`).

**Parameters**

**scalar** (`Union`\[`complex`, `ParameterExpression`]) – The real or complex scalar by which to multiply the Operator, or the `ParameterExpression` to serve as a placeholder for a scalar factor.

**Return type**

`OperatorBase`

**Returns**

An `OperatorBase` equivalent to product of self and scalar.

### neg

<span id="qiskit.opflow.state_fns.CircuitStateFn.neg" />

`neg()`

Return the Operator’s negation, effectively just multiplying by -1.0, overloaded by `-`.

**Return type**

`OperatorBase`

**Returns**

An `OperatorBase` equivalent to the negation of self.

### num\_qubits

<span id="qiskit.opflow.state_fns.CircuitStateFn.num_qubits" />

`property num_qubits`

The number of qubits over which the Operator is defined. If `op.num_qubits == 5`, then `op.eval('1' * 5)` will be valid, but `op.eval('11')` will not.

**Return type**

`int`

**Returns**

The number of qubits accepted by the Operator’s underlying function.

### parameters

<span id="qiskit.opflow.state_fns.CircuitStateFn.parameters" />

`property parameters`

Return a set of Parameter objects contained in the Operator.

### permute

<span id="qiskit.opflow.state_fns.CircuitStateFn.permute" />

`permute(permutation)`

Permute the qubits of the circuit.

**Parameters**

**permutation** (`List`\[`int`]) – A list defining where each qubit should be permuted. The qubit at index j of the circuit should be permuted to position permutation\[j].

**Return type**

`CircuitStateFn`

**Returns**

A new CircuitStateFn containing the permuted circuit.

### power

<span id="qiskit.opflow.state_fns.CircuitStateFn.power" />

`power(exponent)`

Compose with Self Multiple Times, undefined for StateFns.

**Parameters**

**exponent** (`int`) – The number of times to compose self with self.

**Raises**

**ValueError** – This function is not defined for StateFns.

**Return type**

`OperatorBase`

### primitive

<span id="qiskit.opflow.state_fns.CircuitStateFn.primitive" />

`property primitive`

The primitive which defines the behavior of the underlying State function.

### primitive\_strings

<span id="qiskit.opflow.state_fns.CircuitStateFn.primitive_strings" />

`primitive_strings()`

Return a set of strings describing the primitives contained in the Operator. For example, `{'QuantumCircuit', 'Pauli'}`. For hierarchical Operators, such as `ListOps`, this can help illuminate the primitives represented in the various recursive levels, and therefore which conversions can be applied.

**Return type**

`Set`\[`str`]

**Returns**

A set of strings describing the primitives contained within the Operator.

### reduce

<span id="qiskit.opflow.state_fns.CircuitStateFn.reduce" />

`reduce()`

Try collapsing the Operator structure, usually after some type of conversion, e.g. trying to add Operators in a SummedOp or delete needless IGates in a CircuitOp. If no reduction is available, just returns self.

**Return type**

`CircuitStateFn`

**Returns**

The reduced `OperatorBase`.

### sample

<span id="qiskit.opflow.state_fns.CircuitStateFn.sample" />

`sample(shots=1024, massive=False, reverse_endianness=False)`

Sample the state function as a normalized probability distribution. Returns dict of bitstrings in order of probability, with values being probability.

**Return type**

`dict`

### settings

<span id="qiskit.opflow.state_fns.CircuitStateFn.settings" />

`property settings`

Return settings.

**Return type**

`Dict`

### tensor

<span id="qiskit.opflow.state_fns.CircuitStateFn.tensor" />

`tensor(other)`

Return tensor product between self and other, overloaded by `^`. Note: You must be conscious of Qiskit’s big-endian bit printing convention. Meaning, Plus.tensor(Zero) produces a |+⟩ on qubit 0 and a |0⟩ on qubit 1, or |+⟩⨂|0⟩, but would produce a QuantumCircuit like:

> |0⟩– |+⟩–

Because Terra prints circuits and results with qubit 0 at the end of the string or circuit.

**Parameters**

**other** (`OperatorBase`) – The `OperatorBase` to tensor product with self.

**Return type**

`Union`\[`CircuitStateFn`, `TensoredOp`]

**Returns**

An `OperatorBase` equivalent to the tensor product of self and other.

### tensorpower

<span id="qiskit.opflow.state_fns.CircuitStateFn.tensorpower" />

`tensorpower(other)`

Return tensor product with self multiple times, overloaded by `^`.

**Parameters**

**other** (`int`) – The int number of times to tensor product self with itself via `tensorpower`.

**Return type**

`Union`\[`OperatorBase`, `int`]

**Returns**

An `OperatorBase` equivalent to the tensorpower of self by other.

### to\_circuit

<span id="qiskit.opflow.state_fns.CircuitStateFn.to_circuit" />

`to_circuit(meas=False)`

Return QuantumCircuit representing StateFn

**Return type**

`QuantumCircuit`

### to\_circuit\_op

<span id="qiskit.opflow.state_fns.CircuitStateFn.to_circuit_op" />

`to_circuit_op()`

Return `StateFnCircuit` corresponding to this StateFn.

**Return type**

`OperatorBase`

### to\_density\_matrix

<span id="qiskit.opflow.state_fns.CircuitStateFn.to_density_matrix" />

`to_density_matrix(massive=False)`

Return numpy matrix of density operator, warn if more than 16 qubits to force the user to set massive=True if they want such a large matrix. Generally big methods like this should require the use of a converter, but in this case a convenience method for quick hacking and access to classical tools is appropriate.

**Return type**

`ndarray`

### to\_instruction

<span id="qiskit.opflow.state_fns.CircuitStateFn.to_instruction" />

`to_instruction()`

Return Instruction corresponding to primitive.

### to\_matrix

<span id="qiskit.opflow.state_fns.CircuitStateFn.to_matrix" />

`to_matrix(massive=False)`

Return NumPy representation of the Operator. Represents the evaluation of the Operator’s underlying function on every combination of basis binary strings. Warn if more than 16 qubits to force having to set `massive=True` if such a large vector is desired.

**Return type**

`ndarray`

**Returns**

The NumPy `ndarray` equivalent to this Operator.

### to\_matrix\_op

<span id="qiskit.opflow.state_fns.CircuitStateFn.to_matrix_op" />

`to_matrix_op(massive=False)`

Return a `VectorStateFn` for this `StateFn`.

**Parameters**

**massive** (`bool`) – Whether to allow large conversions, e.g. creating a matrix representing over 16 qubits.

**Return type**

`OperatorBase`

**Returns**

A VectorStateFn equivalent to self.

### to\_spmatrix

<span id="qiskit.opflow.state_fns.CircuitStateFn.to_spmatrix" />

`to_spmatrix()`

Return SciPy sparse matrix representation of the Operator. Represents the evaluation of the Operator’s underlying function on every combination of basis binary strings.

**Return type**

`spmatrix`

**Returns**

The SciPy `spmatrix` equivalent to this Operator.

### traverse

<span id="qiskit.opflow.state_fns.CircuitStateFn.traverse" />

`traverse(convert_fn, coeff=None)`

Apply the convert\_fn to the internal primitive if the primitive is an Operator (as in the case of `OperatorStateFn`). Otherwise do nothing. Used by converters.

**Parameters**

*   **convert\_fn** (`Callable`) – The function to apply to the internal OperatorBase.
*   **coeff** (`Union`\[`complex`, `ParameterExpression`, `None`]) – A coefficient to multiply by after applying convert\_fn. If it is None, self.coeff is used instead.

**Return type**

`OperatorBase`

**Returns**

The converted StateFn.

