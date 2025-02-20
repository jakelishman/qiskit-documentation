---
title: MinimumEigensolver
description: API reference for qiskit.algorithms.minimum_eigensolvers.MinimumEigensolver
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.minimum_eigensolvers.MinimumEigensolver
---

# MinimumEigensolver

<span id="qiskit.algorithms.minimum_eigensolvers.MinimumEigensolver" />

`MinimumEigensolver`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/minimum_eigensolvers/minimum_eigensolver.py "view source code")

Bases: `abc.ABC`

The minimum eigensolver interface.

Algorithms that can compute a minimum eigenvalue for an operator may implement this interface to allow different algorithms to be used interchangeably.

## Methods

### compute\_minimum\_eigenvalue

<span id="qiskit.algorithms.minimum_eigensolvers.MinimumEigensolver.compute_minimum_eigenvalue" />

`abstract MinimumEigensolver.compute_minimum_eigenvalue(operator, aux_operators=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/minimum_eigensolvers/minimum_eigensolver.py "view source code")

Computes the minimum eigenvalue. The `operator` and `aux_operators` are supplied here. While an `operator` is required by algorithms, `aux_operators` are optional.

**Parameters**

*   **operator** (*BaseOperator |* [*PauliSumOp*](qiskit.opflow.primitive_ops.PauliSumOp "qiskit.opflow.primitive_ops.PauliSumOp")) – Qubit operator of the observable.
*   **aux\_operators** (*ListOrDict\[BaseOperator |* [*PauliSumOp*](qiskit.opflow.primitive_ops.PauliSumOp "qiskit.opflow.primitive_ops.PauliSumOp")*] | None*) – Optional list of auxiliary operators to be evaluated with the parameters of the minimum eigenvalue main result and their expectation values returned. For instance in chemistry these can be dipole operators and total particle count operators, so we can get values for these at the ground state.

**Return type**

[MinimumEigensolverResult](qiskit.algorithms.minimum_eigensolvers.MinimumEigensolverResult "qiskit.algorithms.minimum_eigensolvers.MinimumEigensolverResult")

**Returns**

A minimum eigensolver result.

### supports\_aux\_operators

<span id="qiskit.algorithms.minimum_eigensolvers.MinimumEigensolver.supports_aux_operators" />

`classmethod MinimumEigensolver.supports_aux_operators()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/minimum_eigensolvers/minimum_eigensolver.py "view source code")

Whether computing the expectation value of auxiliary operators is supported.

If the minimum eigensolver computes an eigenvalue of the main `operator` then it can compute the expectation value of the `aux_operators` for that state. Otherwise they will be ignored.

**Return type**

`bool`

**Returns**

True if aux\_operator expectations can be evaluated, False otherwise

