---
title: CVaRMeasurement
description: API reference for qiskit.aqua.operators.state_fns.CVaRMeasurement
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.operators.state_fns.CVaRMeasurement
---

# CVaRMeasurement

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement" />

`CVaRMeasurement(primitive=None, alpha=1.0, coeff=1.0)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/state_fns/cvar_measurement.py "view source code")

Bases: `qiskit.aqua.operators.state_fns.operator_state_fn.OperatorStateFn`

**A specialized measurement class to compute CVaR expectation values.**

See [https://arxiv.org/pdf/1907.04769.pdf](https://arxiv.org/pdf/1907.04769.pdf) for further details.

Used in `CVaRExpectation`, see there for more details.

**Parameters**

*   **primitive** (`Optional`\[`OperatorBase`]) – The `OperatorBase` which defines the diagonal operator measurement.
*   **coeff** (`Union`\[`int`, `float`, `complex`, `ParameterExpression`]) – A coefficient by which to multiply the state function
*   **alpha** (`float`) – A real-valued parameter between 0 and 1 which specifies the fraction of observed samples to include when computing the objective value. alpha = 1 corresponds to a standard observable expectation value. alpha = 0 corresponds to only using the single sample with the lowest energy. alpha = 0.5 corresponds to ranking each observation by lowest energy and using the best

**Raises**

*   **ValueError** – TODO remove that this raises an error
*   **ValueError** – If alpha is not in \[0, 1].
*   [**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – If the primitive is not diagonal.

## Methods

### add

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.add" />

`CVaRMeasurement.add(other)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/state_fns/cvar_measurement.py "view source code")

Return Operator addition of self and other, overloaded by `+`.

**Parameters**

**other** (`OperatorBase`) – An `OperatorBase` with the same number of qubits as self, and in the same ‘Operator’, ‘State function’, or ‘Measurement’ category as self (i.e. the same type of underlying function).

**Return type**

`OperatorBase`

**Returns**

An `OperatorBase` equivalent to the sum of self and other.

### adjoint

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.adjoint" />

`CVaRMeasurement.adjoint()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/state_fns/cvar_measurement.py "view source code")

The adjoint of a CVaRMeasurement is not defined.

**Return type**

`OperatorBase`

**Returns**

Does not return anything, raises an error.

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – The adjoint of a CVaRMeasurement is not defined.

### assign\_parameters

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.assign_parameters" />

`CVaRMeasurement.assign_parameters(param_dict)`

Binds scalar values to any Terra `Parameters` in the coefficients or primitives of the Operator, or substitutes one `Parameter` for another. This method differs from Terra’s `assign_parameters` in that it also supports lists of values to assign for a give `Parameter`, in which case self will be copied for each parameterization in the binding list(s), and all the copies will be returned in an `OpList`. If lists of parameterizations are used, every `Parameter` in the param\_dict must have the same length list of parameterizations.

**Parameters**

**param\_dict** (`dict`) – The dictionary of `Parameters` to replace, and values or lists of values by which to replace them.

**Return type**

`OperatorBase`

**Returns**

The `OperatorBase` with the `Parameters` in self replaced by the values or `Parameters` in param\_dict. If param\_dict contains parameterization lists, this `OperatorBase` is an `OpList`.

### bind\_parameters

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.bind_parameters" />

`CVaRMeasurement.bind_parameters(param_dict)`

Same as assign\_parameters, but maintained for consistency with QuantumCircuit in Terra (which has both assign\_parameters and bind\_parameters).

**Return type**

`OperatorBase`

### compose

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.compose" />

`CVaRMeasurement.compose(other, permutation=None, front=False)`

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

### compute\_cvar

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.compute_cvar" />

`CVaRMeasurement.compute_cvar(energies, probabilities)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/state_fns/cvar_measurement.py "view source code")

Given the energies of each sampled measurement outcome (H\_i) as well as the sampling probability of each measurement outcome (p\_i, we can compute the CVaR. Note that the sampling probabilities serve as an alternative to knowing the counts of each observation and that the input energies are assumed to be sorted in increasing order.

Consider the outcome with index j, such that only some of the samples with measurement outcome j will be used in computing CVaR. The CVaR calculation can then be separated into two parts. First we sum each of the energies for outcomes i \< j, weighted by the probability of observing that outcome (i.e the normalized counts). Second, we add the energy for outcome j, weighted by the difference (α - sum\_i\<j p\_i)

**Parameters**

*   **energies** (`list`) – A list containing the energies (H\_i) of each sample measurement outcome, sorted in increasing order.
*   **probabilities** (`list`) – The sampling probabilities (p\_i) for each corresponding measurement outcome.

**Return type**

`Union`\[`float`, `complex`]

**Returns**

**The CVaR of the diagonal observable specified by self.primitive and**

the sampled quantum state described by the inputs (energies, probabilities). For index j (described above), the CVaR is computed as H\_j + 1/α \* (sum\_i\<j p\_i\*(H\_i - H\_j))

**Raises**

**ValueError** – front isn’t a DictStateFn or VectorStateFn

### equals

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.equals" />

`CVaRMeasurement.equals(other)`

Evaluate Equality between Operators, overloaded by `==`. Only returns True if self and other are of the same representation (e.g. a DictStateFn and CircuitStateFn will never be equal, even if their vector representations are equal), their underlying primitives are equal (this means for ListOps, OperatorStateFns, or EvolvedOps the equality is evaluated recursively downwards), and their coefficients are equal.

**Parameters**

**other** (`OperatorBase`) – The `OperatorBase` to compare to self.

**Return type**

`bool`

**Returns**

A bool equal to the equality of self and other.

### eval

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.eval" />

`CVaRMeasurement.eval(front=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/state_fns/cvar_measurement.py "view source code")

Given the energies of each sampled measurement outcome (H\_i) as well as the sampling probability of each measurement outcome (p\_i, we can compute the CVaR as H\_j + 1/α\*(sum\_i\<j p\_i\*(H\_i - H\_j)). Note that index j corresponds to the measurement outcome such that only some of the samples with measurement outcome j will be used in computing CVaR. Note also that the sampling probabilities serve as an alternative to knowing the counts of each observation.

This computation is broken up into two subroutines. One which evaluates each measurement outcome and determines the sampling probabilities of each. And one which carries out the above calculation. The computation is split up this way to enable a straightforward calculation of the variance of this estimator.

**Parameters**

**front** (`Union`\[`str`, `dict`, `ndarray`, `OperatorBase`, `None`]) – A StateFn or primitive which specifies the results of evaluating a quantum state.

**Return type**

`Union`\[`float`, `complex`]

**Returns**

**The CVaR of the diagonal observable specified by self.primitive and**

the sampled quantum state described by the inputs (energies, probabilities). For index j (described above), the CVaR is computed as H\_j + 1/α\*(sum\_i\<j p\_i\*(H\_i - H\_j))

### eval\_variance

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.eval_variance" />

`CVaRMeasurement.eval_variance(front=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/state_fns/cvar_measurement.py "view source code")

Given the energies of each sampled measurement outcome (H\_i) as well as the sampling probability of each measurement outcome (p\_i, we can compute the variance of the CVaR estimator as H\_j^2 + 1/α \* (sum\_i\<j p\_i\*(H\_i^2 - H\_j^2)). This follows from the definition that Var\[X] = E\[X^2] - E\[X]^2. In this case, X = E\[\<bi|H|bi>], where H is the diagonal observable and bi corresponds to measurement outcome i. Given this, E\[X^2] = E\[\<bi|H|bi>^2]

**Parameters**

**front** (`Union`\[`str`, `dict`, `ndarray`, `OperatorBase`, `None`]) – A StateFn or primitive which specifies the results of evaluating a quantum state.

**Return type**

`Union`\[`float`, `complex`]

**Returns**

**The Var\[CVaR] of the diagonal observable specified by self.primitive**

and the sampled quantum state described by the inputs (energies, probabilities). For index j (described above), the CVaR is computed as H\_j^2 + 1/α\*(sum\_i\<j p\_i\*(H\_i^2 - H\_j^2))

### get\_outcome\_energies\_probabilities

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.get_outcome_energies_probabilities" />

`CVaRMeasurement.get_outcome_energies_probabilities(front=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/state_fns/cvar_measurement.py "view source code")

In order to compute the CVaR of an observable expectation, we require the energies of each sampled measurement outcome as well as the sampling probability of each measurement outcome. Note that the counts for each measurement outcome will also suffice (and this is often how the CVaR is presented).

**Parameters**

**front** (`Union`\[`str`, `dict`, `ndarray`, `OperatorBase`, `None`]) – A StateFn or a primitive which defines a StateFn. This input holds the results of a sampled/simulated circuit.

**Return type**

`Tuple`\[`list`, `list`]

**Returns**

**Two lists of equal length. energies contains the energy of each**

unique measurement outcome computed against the diagonal observable stored in self.primitive. probabilities contains the corresponding sampling probability for each measurement outcome in energies.

**Raises**

**ValueError** – front isn’t a DictStateFn or VectorStateFn

### mul

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.mul" />

`CVaRMeasurement.mul(scalar)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/state_fns/cvar_measurement.py "view source code")

Returns the scalar multiplication of the Operator, overloaded by `*`, including support for Terra’s `Parameters`, which can be bound to values later (via `bind_parameters`).

**Parameters**

**scalar** (`Union`\[`int`, `float`, `complex`, `ParameterExpression`]) – The real or complex scalar by which to multiply the Operator, or the `ParameterExpression` to serve as a placeholder for a scalar factor.

**Return type**

`OperatorBase`

**Returns**

An `OperatorBase` equivalent to product of self and scalar.

### neg

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.neg" />

`CVaRMeasurement.neg()`

Return the Operator’s negation, effectively just multiplying by -1.0, overloaded by `-`.

**Return type**

`OperatorBase`

**Returns**

An `OperatorBase` equivalent to the negation of self.

### permute

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.permute" />

`CVaRMeasurement.permute(permutation)`

Permute the qubits of the state function.

**Parameters**

**permutation** (`List`\[`int`]) – A list defining where each qubit should be permuted. The qubit at index j of the circuit should be permuted to position permutation\[j].

**Return type**

`OperatorStateFn`

**Returns**

A new StateFn containing the permuted primitive.

### power

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.power" />

`CVaRMeasurement.power(exponent)`

Compose with Self Multiple Times, undefined for StateFns.

**Parameters**

**exponent** (`int`) – The number of times to compose self with self.

**Raises**

**ValueError** – This function is not defined for StateFns.

**Return type**

`OperatorBase`

### primitive\_strings

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.primitive_strings" />

`CVaRMeasurement.primitive_strings()`

Return a set of strings describing the primitives contained in the Operator. For example, `{'QuantumCircuit', 'Pauli'}`. For hierarchical Operators, such as `ListOps`, this can help illuminate the primitives represented in the various recursive levels, and therefore which conversions can be applied.

**Return type**

`Set`\[`str`]

**Returns**

A set of strings describing the primitives contained within the Operator.

### reduce

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.reduce" />

`CVaRMeasurement.reduce()`

Try collapsing the Operator structure, usually after some type of conversion, e.g. trying to add Operators in a SummedOp or delete needless IGates in a CircuitOp. If no reduction is available, just returns self.

**Return type**

`OperatorBase`

**Returns**

The reduced `OperatorBase`.

### sample

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.sample" />

`CVaRMeasurement.sample(shots=1024, massive=False, reverse_endianness=False)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/state_fns/cvar_measurement.py "view source code")

Sample the state function as a normalized probability distribution. Returns dict of bitstrings in order of probability, with values being probability.

**Parameters**

*   **shots** (`int`) – The number of samples to take to approximate the State function.
*   **massive** (`bool`) – Whether to allow large conversions, e.g. creating a matrix representing over 16 qubits.
*   **reverse\_endianness** (`bool`) – Whether to reverse the endianness of the bitstrings in the return dict to match Terra’s big-endianness.

**Return type**

`dict`

**Returns**

A dict containing pairs sampled strings from the State function and sampling frequency divided by shots.

### tensor

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.tensor" />

`CVaRMeasurement.tensor(other)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/state_fns/cvar_measurement.py "view source code")

Return tensor product between self and other, overloaded by `^`. Note: You must be conscious of Qiskit’s big-endian bit printing convention. Meaning, Plus.tensor(Zero) produces a |+⟩ on qubit 0 and a |0⟩ on qubit 1, or |+⟩⨂|0⟩, but would produce a QuantumCircuit like

> |0⟩– |+⟩–

Because Terra prints circuits and results with qubit 0 at the end of the string or circuit.

**Parameters**

**other** (`OperatorBase`) – The `OperatorBase` to tensor product with self.

**Return type**

`OperatorBase`

**Returns**

An `OperatorBase` equivalent to the tensor product of self and other.

### tensorpower

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.tensorpower" />

`CVaRMeasurement.tensorpower(other)`

Return tensor product with self multiple times, overloaded by `^`.

**Parameters**

**other** (`int`) – The int number of times to tensor product self with itself via `tensorpower`.

**Return type**

`Union`\[`OperatorBase`, `int`]

**Returns**

An `OperatorBase` equivalent to the tensorpower of self by other.

### to\_circuit\_op

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.to_circuit_op" />

`CVaRMeasurement.to_circuit_op()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/state_fns/cvar_measurement.py "view source code")

Not defined.

**Return type**

`OperatorBase`

### to\_density\_matrix

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.to_density_matrix" />

`CVaRMeasurement.to_density_matrix(massive=False)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/state_fns/cvar_measurement.py "view source code")

Not defined.

**Return type**

`ndarray`

### to\_legacy\_op

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.to_legacy_op" />

`CVaRMeasurement.to_legacy_op(massive=False)`

Attempt to return the Legacy Operator representation of the Operator. If self is a `SummedOp` of `PauliOps`, will attempt to convert to `WeightedPauliOperator`, and otherwise will simply convert to `MatrixOp` and then to `MatrixOperator`. The Legacy Operators cannot represent `StateFns` or proper `ListOps` (meaning not one of the `ListOp` subclasses), so an error will be thrown if this method is called on such an Operator. Also, Legacy Operators cannot represent unbound Parameter coeffs, so an error will be thrown if any are present in self.

Warn if more than 16 qubits to force having to set `massive=True` if such a large vector is desired.

**Return type**

`LegacyBaseOperator`

**Returns**

The `LegacyBaseOperator` representing this Operator.

**Raises**

**TypeError** – self is an Operator which cannot be represented by a `LegacyBaseOperator`, such as `StateFn`, proper (non-subclass) `ListOp`, or an Operator with an unbound coeff Parameter.

### to\_matrix

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.to_matrix" />

`CVaRMeasurement.to_matrix(massive=False)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/state_fns/cvar_measurement.py "view source code")

Not defined.

**Return type**

`ndarray`

### to\_matrix\_op

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.to_matrix_op" />

`CVaRMeasurement.to_matrix_op(massive=False)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/state_fns/cvar_measurement.py "view source code")

Not defined.

**Return type**

`OperatorBase`

### traverse

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.traverse" />

`CVaRMeasurement.traverse(convert_fn, coeff=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/state_fns/cvar_measurement.py "view source code")

Apply the convert\_fn to the internal primitive if the primitive is an Operator (as in the case of `OperatorStateFn`). Otherwise do nothing. Used by converters.

**Parameters**

*   **convert\_fn** (`Callable`) – The function to apply to the internal OperatorBase.
*   **coeff** (`Union`\[`int`, `float`, `complex`, `ParameterExpression`, `None`]) – A coefficient to multiply by after applying convert\_fn. If it is None, self.coeff is used instead.

**Return type**

`OperatorBase`

**Returns**

The converted StateFn.

## Attributes

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.ENABLE_DEPRECATION" />

### ENABLE\_DEPRECATION

`= True`

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.INDENTATION" />

### INDENTATION

`= ' '`

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.alpha" />

### alpha

**A real-valued parameter between 0 and 1 which specifies the**

fraction of observed samples to include when computing the objective value. alpha = 1 corresponds to a standard observable expectation value. alpha = 0 corresponds to only using the single sample with the lowest energy. alpha = 0.5 corresponds to ranking each observation by lowest energy and using the best half.

**Return type**

`float`

**Returns**

The parameter alpha which was given at initialization

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.coeff" />

### coeff

A coefficient by which the state function is multiplied.

**Return type**

`Union`\[`int`, `float`, `complex`, `ParameterExpression`]

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.is_measurement" />

### is\_measurement

Whether the StateFn object is a measurement Operator.

**Return type**

`bool`

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.num_qubits" />

### num\_qubits

**Return type**

`int`

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.parameters" />

### parameters

<span id="qiskit.aqua.operators.state_fns.CVaRMeasurement.primitive" />

### primitive

The primitive which defines the behavior of the underlying State function.

