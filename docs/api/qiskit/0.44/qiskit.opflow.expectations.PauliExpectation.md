---
title: PauliExpectation
description: API reference for qiskit.opflow.expectations.PauliExpectation
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.opflow.expectations.PauliExpectation
---

# PauliExpectation

<span id="qiskit.opflow.expectations.PauliExpectation" />

`qiskit.opflow.expectations.PauliExpectation(group_paulis=True)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.25/qiskit/opflow/expectations/pauli_expectation.py "view source code")

Bases: [`ExpectationBase`](qiskit.opflow.expectations.ExpectationBase "qiskit.opflow.expectations.expectation_base.ExpectationBase")

An Expectation converter for Pauli-basis observables by changing Pauli measurements to a diagonal (\{Z, I}^n) basis and appending circuit post-rotations to the measured state function. Optionally groups the Paulis with the same post-rotations (those that commute with one another, or form Abelian groups) into single measurements to reduce circuit execution overhead.

<Admonition title="Deprecated since version 0.24.0" type="danger">
  The class `qiskit.opflow.expectations.pauli_expectation.PauliExpectation` is deprecated as of qiskit-terra 0.24.0. It will be removed no earlier than 3 months after the release date. For code migration guidelines, visit [https://qisk.it/opflow\_migration](https://qisk.it/opflow_migration).
</Admonition>

**Parameters**

**group\_paulis** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – Whether to group the Pauli measurements into commuting sums, which all have the same diagonalizing circuit.

## Methods

### compute\_variance

<span id="qiskit.opflow.expectations.PauliExpectation.compute_variance" />

`compute_variance(exp_op)`

Compute the variance of the expectation estimator.

**Parameters**

**exp\_op** ([*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")) – The full expectation value Operator after sampling.

**Returns**

The variances or lists thereof (if exp\_op contains ListOps) of the expectation value estimation.

**Return type**

[list](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)") | [float](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)") | [*ndarray*](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.26)")

### convert

<span id="qiskit.opflow.expectations.PauliExpectation.convert" />

`convert(operator)`

Accepts an Operator and returns a new Operator with the Pauli measurements replaced by diagonal Pauli post-rotation based measurements so they can be evaluated by sampling and averaging.

**Parameters**

**operator** ([*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")) – The operator to convert.

**Returns**

The converted operator.

**Return type**

[*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

