---
title: Estimator
description: API reference for qiskit.primitives.Estimator
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.primitives.Estimator
---

# Estimator

<span id="qiskit.primitives.Estimator" />

`Estimator(*, options=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/primitives/estimator.py "view source code")

Bases: [`BaseEstimator`](qiskit.primitives.BaseEstimator "qiskit.primitives.base.base_estimator.BaseEstimator")\[`PrimitiveJob`\[[`EstimatorResult`](qiskit.primitives.EstimatorResult "qiskit.primitives.base.estimator_result.EstimatorResult")]]

Reference implementation of [`BaseEstimator`](qiskit.primitives.BaseEstimator "qiskit.primitives.BaseEstimator").

**Run Options**

*   **shots** (None or int) – The number of shots. If None, it calculates the exact expectation values. Otherwise, it samples from normal distributions with standard errors as standard deviations using normal distribution approximation.
*   **seed** (np.random.Generator or int) – Set a fixed seed or generator for the normal distribution. If shots is None, this option is ignored.

**Parameters**

**options** – Default options.

**Raises**

**QiskitError** – if some classical bits are not used for measurements.

## Methods

<span id="qiskit-primitives-estimator-run" />

### run

<span id="qiskit.primitives.Estimator.run" />

`Estimator.run(circuits, observables, parameter_values=None, **run_options)`

Run the job of the estimation of expectation value(s).

`circuits`, `observables`, and `parameter_values` should have the same length. The i-th element of the result is the expectation of observable

```python
obs = observables[i]
```

for the state prepared by

```python
circ = circuits[i]
```

with bound parameters

```python
values = parameter_values[i].
```

**Parameters**

*   **circuits** (*Sequence\[*[*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")*] |* [*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – one or more circuit objects.
*   **observables** (*Sequence\[BaseOperator |* [*PauliSumOp*](qiskit.opflow.primitive_ops.PauliSumOp "qiskit.opflow.primitive_ops.PauliSumOp")  *| str] | BaseOperator |*[*PauliSumOp*](qiskit.opflow.primitive_ops.PauliSumOp "qiskit.opflow.primitive_ops.PauliSumOp") *| str*) – one or more observable objects. Several formats are allowed; importantly, `str` should follow the string representation format for [`Pauli`](qiskit.quantum_info.Pauli "qiskit.quantum_info.Pauli") objects.
*   **parameter\_values** (*Sequence\[Sequence\[float]] | Sequence\[float] | float | None*) – concrete parameters to be bound.
*   **run\_options** – runtime options used for circuit execution.

**Returns**

The job object of EstimatorResult.

**Raises**

*   **TypeError** – Invalid argument type given.
*   **ValueError** – Invalid argument values given.

**Return type**

T

<span id="qiskit-primitives-estimator-set-options" />

### set\_options

<span id="qiskit.primitives.Estimator.set_options" />

`Estimator.set_options(**fields)`

Set options values for the estimator.

**Parameters**

**\*\*fields** – The fields to update the options

## Attributes

<span id="qiskit.primitives.Estimator.circuits" />

### circuits

Quantum circuits that represents quantum states.

**Returns**

The quantum circuits.

<span id="qiskit.primitives.Estimator.observables" />

### observables

Observables to be estimated.

**Returns**

The observables.

<span id="qiskit.primitives.Estimator.options" />

### options

Return options values for the estimator.

**Returns**

options

<span id="qiskit.primitives.Estimator.parameters" />

### parameters

Parameters of the quantum circuits.

**Returns**

Parameters, where `parameters[i][j]` is the j-th parameter of the i-th circuit.

