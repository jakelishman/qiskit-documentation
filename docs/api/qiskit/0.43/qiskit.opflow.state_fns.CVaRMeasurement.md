---
title: CVaRMeasurement
description: API reference for qiskit.opflow.state_fns.CVaRMeasurement
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.opflow.state_fns.CVaRMeasurement
---

# CVaRMeasurement

<span id="qiskit.opflow.state_fns.CVaRMeasurement" />

`CVaRMeasurement(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/state_fns/cvar_measurement.py "view source code")

Bases: [`OperatorStateFn`](qiskit.opflow.state_fns.OperatorStateFn "qiskit.opflow.state_fns.operator_state_fn.OperatorStateFn")

**Deprecated: A specialized measurement class to compute CVaR expectation values.**

See [https://arxiv.org/pdf/1907.04769.pdf](https://arxiv.org/pdf/1907.04769.pdf) for further details.

Used in `CVaRExpectation`, see there for more details.

<Admonition title="Deprecated since version 0.24.0" type="danger">
  The class `qiskit.opflow.state_fns.cvar_measurement.CVaRMeasurement` is deprecated as of qiskit-terra 0.24.0. It will be removed no earlier than 3 months after the release date. For code migration guidelines, visit [https://qisk.it/opflow\_migration](https://qisk.it/opflow_migration).
</Admonition>

**Parameters**

*   **primitive** – The `OperatorBase` which defines the diagonal operator measurement.
*   **coeff** – A coefficient by which to multiply the state function
*   **alpha** – A real-valued parameter between 0 and 1 which specifies the fraction of observed samples to include when computing the objective value. alpha = 1 corresponds to a standard observable expectation value. alpha = 0 corresponds to only using the single sample with the lowest energy. alpha = 0.5 corresponds to ranking each observation by lowest energy and using the best

**Raises**

*   **ValueError** – TODO remove that this raises an error
*   **ValueError** – If alpha is not in \[0, 1].
*   [**OpflowError**](qiskit.opflow.OpflowError "qiskit.opflow.OpflowError") – If the primitive is not diagonal.

## Methods Defined Here

<span id="qiskit-opflow-state-fns-cvarmeasurement-add" />

### add

<span id="qiskit.opflow.state_fns.CVaRMeasurement.add" />

`CVaRMeasurement.add(other)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/state_fns/cvar_measurement.py "view source code")

Return Operator addition of self and other, overloaded by `+`.

**Parameters**

**other** ([*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")) – An `OperatorBase` with the same number of qubits as self, and in the same ‘Operator’, ‘State function’, or ‘Measurement’ category as self (i.e. the same type of underlying function).

**Returns**

An `OperatorBase` equivalent to the sum of self and other.

**Return type**

[*SummedOp*](qiskit.opflow.list_ops.SummedOp "qiskit.opflow.list_ops.summed_op.SummedOp")

<span id="qiskit-opflow-state-fns-cvarmeasurement-adjoint" />

### adjoint

<span id="qiskit.opflow.state_fns.CVaRMeasurement.adjoint" />

`CVaRMeasurement.adjoint()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/state_fns/cvar_measurement.py "view source code")

The adjoint of a CVaRMeasurement is not defined.

**Returns**

Does not return anything, raises an error.

**Raises**

[**OpflowError**](qiskit.opflow.OpflowError "qiskit.opflow.OpflowError") – The adjoint of a CVaRMeasurement is not defined.

<span id="qiskit-opflow-state-fns-cvarmeasurement-compute-cvar" />

### compute\_cvar

<span id="qiskit.opflow.state_fns.CVaRMeasurement.compute_cvar" />

`CVaRMeasurement.compute_cvar(energies, probabilities)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/state_fns/cvar_measurement.py "view source code")

Given the energies of each sampled measurement outcome (H\_i) as well as the sampling probability of each measurement outcome (p\_i, we can compute the CVaR. Note that the sampling probabilities serve as an alternative to knowing the counts of each observation and that the input energies are assumed to be sorted in increasing order.

Consider the outcome with index j, such that only some of the samples with measurement outcome j will be used in computing CVaR. The CVaR calculation can then be separated into two parts. First we sum each of the energies for outcomes i \< j, weighted by the probability of observing that outcome (i.e the normalized counts). Second, we add the energy for outcome j, weighted by the difference (α - sum\_i\<j p\_i)

**Parameters**

*   **energies** (*list*) – A list containing the energies (H\_i) of each sample measurement outcome, sorted in increasing order.
*   **probabilities** (*list*) – The sampling probabilities (p\_i) for each corresponding measurement outcome.

**Returns**

**The CVaR of the diagonal observable specified by self.primitive and**

the sampled quantum state described by the inputs (energies, probabilities). For index j (described above), the CVaR is computed as H\_j + 1/α \* (sum\_i\<j p\_i\*(H\_i - H\_j))

**Raises**

**ValueError** – front isn’t a DictStateFn or VectorStateFn

**Return type**

complex

<span id="qiskit-opflow-state-fns-cvarmeasurement-eval" />

### eval

<span id="qiskit.opflow.state_fns.CVaRMeasurement.eval" />

`CVaRMeasurement.eval(front=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/state_fns/cvar_measurement.py "view source code")

Given the energies of each sampled measurement outcome (H\_i) as well as the sampling probability of each measurement outcome (p\_i, we can compute the CVaR as H\_j + 1/α\*(sum\_i\<j p\_i\*(H\_i - H\_j)). Note that index j corresponds to the measurement outcome such that only some of the samples with measurement outcome j will be used in computing CVaR. Note also that the sampling probabilities serve as an alternative to knowing the counts of each observation.

This computation is broken up into two subroutines. One which evaluates each measurement outcome and determines the sampling probabilities of each. And one which carries out the above calculation. The computation is split up this way to enable a straightforward calculation of the variance of this estimator.

**Parameters**

**front** (*str | dict |* [*ndarray*](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.25)")  *|*[*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")  *|*[*Statevector*](qiskit.quantum_info.Statevector "qiskit.quantum_info.states.statevector.Statevector") *| None*) – A StateFn or primitive which specifies the results of evaluating a quantum state.

**Returns**

**The CVaR of the diagonal observable specified by self.primitive and**

the sampled quantum state described by the inputs (energies, probabilities). For index j (described above), the CVaR is computed as H\_j + 1/α\*(sum\_i\<j p\_i\*(H\_i - H\_j))

**Return type**

complex

<span id="qiskit-opflow-state-fns-cvarmeasurement-eval-variance" />

### eval\_variance

<span id="qiskit.opflow.state_fns.CVaRMeasurement.eval_variance" />

`CVaRMeasurement.eval_variance(front=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/state_fns/cvar_measurement.py "view source code")

Given the energies of each sampled measurement outcome (H\_i) as well as the sampling probability of each measurement outcome (p\_i, we can compute the variance of the CVaR estimator as H\_j^2 + 1/α \* (sum\_i\<j p\_i\*(H\_i^2 - H\_j^2)). This follows from the definition that Var\[X] = E\[X^2] - E\[X]^2. In this case, X = E\[\<bi|H|bi>], where H is the diagonal observable and bi corresponds to measurement outcome i. Given this, E\[X^2] = E\[\<bi|H|bi>^2]

**Parameters**

**front** (*str | dict |* [*ndarray*](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.25)")  *|*[*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase") *| None*) – A StateFn or primitive which specifies the results of evaluating a quantum state.

**Returns**

**The Var\[CVaR] of the diagonal observable specified by self.primitive**

and the sampled quantum state described by the inputs (energies, probabilities). For index j (described above), the CVaR is computed as H\_j^2 + 1/α\*(sum\_i\<j p\_i\*(H\_i^2 - H\_j^2))

**Return type**

complex

<span id="qiskit-opflow-state-fns-cvarmeasurement-get-outcome-energies-probabilities" />

### get\_outcome\_energies\_probabilities

<span id="qiskit.opflow.state_fns.CVaRMeasurement.get_outcome_energies_probabilities" />

`CVaRMeasurement.get_outcome_energies_probabilities(front=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/state_fns/cvar_measurement.py "view source code")

In order to compute the CVaR of an observable expectation, we require the energies of each sampled measurement outcome as well as the sampling probability of each measurement outcome. Note that the counts for each measurement outcome will also suffice (and this is often how the CVaR is presented).

**Parameters**

**front** (*str | dict |* [*ndarray*](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.25)")  *|*[*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")  *|*[*Statevector*](qiskit.quantum_info.Statevector "qiskit.quantum_info.states.statevector.Statevector") *| None*) – A StateFn or a primitive which defines a StateFn. This input holds the results of a sampled/simulated circuit.

**Returns**

**Two lists of equal length. energies contains the energy of each**

unique measurement outcome computed against the diagonal observable stored in self.primitive. probabilities contains the corresponding sampling probability for each measurement outcome in energies.

**Raises**

**ValueError** – front isn’t a DictStateFn or VectorStateFn

**Return type**

*Tuple*\[list, list]

<span id="qiskit-opflow-state-fns-cvarmeasurement-mul" />

### mul

<span id="qiskit.opflow.state_fns.CVaRMeasurement.mul" />

`CVaRMeasurement.mul(scalar)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/state_fns/cvar_measurement.py "view source code")

Returns the scalar multiplication of the Operator, overloaded by `*`, including support for Terra’s `Parameters`, which can be bound to values later (via `bind_parameters`).

**Parameters**

**scalar** (*complex |* [*ParameterExpression*](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")) – The real or complex scalar by which to multiply the Operator, or the `ParameterExpression` to serve as a placeholder for a scalar factor.

**Returns**

An `OperatorBase` equivalent to product of self and scalar.

**Return type**

[*CVaRMeasurement*](qiskit.opflow.state_fns.CVaRMeasurement "qiskit.opflow.state_fns.cvar_measurement.CVaRMeasurement")

<span id="qiskit-opflow-state-fns-cvarmeasurement-sample" />

### sample

<span id="qiskit.opflow.state_fns.CVaRMeasurement.sample" />

`CVaRMeasurement.sample(shots=1024, massive=False, reverse_endianness=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/state_fns/cvar_measurement.py "view source code")

Sample the state function as a normalized probability distribution. Returns dict of bitstrings in order of probability, with values being probability.

**Parameters**

*   **shots** (*int*) – The number of samples to take to approximate the State function.
*   **massive** (*bool*) – Whether to allow large conversions, e.g. creating a matrix representing over 16 qubits.
*   **reverse\_endianness** (*bool*) – Whether to reverse the endianness of the bitstrings in the return dict to match Terra’s big-endianness.

**Returns**

A dict containing pairs sampled strings from the State function and sampling frequency divided by shots.

<span id="qiskit-opflow-state-fns-cvarmeasurement-tensor" />

### tensor

<span id="qiskit.opflow.state_fns.CVaRMeasurement.tensor" />

`CVaRMeasurement.tensor(other)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/state_fns/cvar_measurement.py "view source code")

Return tensor product between self and other, overloaded by `^`. Note: You must be conscious of Qiskit’s big-endian bit printing convention. Meaning, Plus.tensor(Zero) produces a |+⟩ on qubit 0 and a |0⟩ on qubit 1, or |+⟩⨂|0⟩, but would produce a QuantumCircuit like

> |0⟩– |+⟩–

Because Terra prints circuits and results with qubit 0 at the end of the string or circuit.

**Parameters**

**other** ([*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")) – The `OperatorBase` to tensor product with self.

**Returns**

An `OperatorBase` equivalent to the tensor product of self and other.

**Return type**

[*OperatorStateFn*](qiskit.opflow.state_fns.OperatorStateFn "qiskit.opflow.state_fns.operator_state_fn.OperatorStateFn") | [*TensoredOp*](qiskit.opflow.list_ops.TensoredOp "qiskit.opflow.list_ops.tensored_op.TensoredOp")

<span id="qiskit-opflow-state-fns-cvarmeasurement-to-circuit-op" />

### to\_circuit\_op

<span id="qiskit.opflow.state_fns.CVaRMeasurement.to_circuit_op" />

`CVaRMeasurement.to_circuit_op()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/state_fns/cvar_measurement.py "view source code")

Not defined.

<span id="qiskit-opflow-state-fns-cvarmeasurement-to-density-matrix" />

### to\_density\_matrix

<span id="qiskit.opflow.state_fns.CVaRMeasurement.to_density_matrix" />

`CVaRMeasurement.to_density_matrix(massive=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/state_fns/cvar_measurement.py "view source code")

Not defined.

<span id="qiskit-opflow-state-fns-cvarmeasurement-to-matrix" />

### to\_matrix

<span id="qiskit.opflow.state_fns.CVaRMeasurement.to_matrix" />

`CVaRMeasurement.to_matrix(massive=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/state_fns/cvar_measurement.py "view source code")

Not defined.

<span id="qiskit-opflow-state-fns-cvarmeasurement-to-matrix-op" />

### to\_matrix\_op

<span id="qiskit.opflow.state_fns.CVaRMeasurement.to_matrix_op" />

`CVaRMeasurement.to_matrix_op(massive=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/state_fns/cvar_measurement.py "view source code")

Not defined.

<span id="qiskit-opflow-state-fns-cvarmeasurement-traverse" />

### traverse

<span id="qiskit.opflow.state_fns.CVaRMeasurement.traverse" />

`CVaRMeasurement.traverse(convert_fn, coeff=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/state_fns/cvar_measurement.py "view source code")

Apply the convert\_fn to the internal primitive if the primitive is an Operator (as in the case of `OperatorStateFn`). Otherwise do nothing. Used by converters.

**Parameters**

*   **convert\_fn** (*Callable*) – The function to apply to the internal OperatorBase.
*   **coeff** (*complex |* [*ParameterExpression*](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression") *| None*) – A coefficient to multiply by after applying convert\_fn. If it is None, self.coeff is used instead.

**Returns**

The converted StateFn.

**Return type**

[*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

## Attributes

<span id="qiskit.opflow.state_fns.CVaRMeasurement.INDENTATION" />

### INDENTATION

`= '  '`

<span id="qiskit.opflow.state_fns.CVaRMeasurement.alpha" />

### alpha

**A real-valued parameter between 0 and 1 which specifies the**

fraction of observed samples to include when computing the objective value. alpha = 1 corresponds to a standard observable expectation value. alpha = 0 corresponds to only using the single sample with the lowest energy. alpha = 0.5 corresponds to ranking each observation by lowest energy and using the best half.

**Returns**

The parameter alpha which was given at initialization

<span id="qiskit.opflow.state_fns.CVaRMeasurement.coeff" />

### coeff

A coefficient by which the state function is multiplied.

<span id="qiskit.opflow.state_fns.CVaRMeasurement.instance_id" />

### instance\_id

Return the unique instance id.

<span id="qiskit.opflow.state_fns.CVaRMeasurement.is_measurement" />

### is\_measurement

Whether the StateFn object is a measurement Operator.

<span id="qiskit.opflow.state_fns.CVaRMeasurement.num_qubits" />

### num\_qubits

<span id="qiskit.opflow.state_fns.CVaRMeasurement.parameters" />

### parameters

<span id="qiskit.opflow.state_fns.CVaRMeasurement.primitive" />

### primitive

`OperatorBase`

The primitive which defines the behavior of the underlying State function.

<span id="qiskit.opflow.state_fns.CVaRMeasurement.settings" />

### settings

Return settings.

