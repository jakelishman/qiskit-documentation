---
title: MinimumEigensolver
description: API reference for qiskit.algorithms.MinimumEigensolver
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.MinimumEigensolver
---

# MinimumEigensolver

<span id="qiskit.algorithms.MinimumEigensolver" />

`MinimumEigensolver`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/algorithms/minimum_eigen_solvers/minimum_eigen_solver.py "view source code")

Bases: `abc.ABC`

The Minimum Eigensolver Interface.

Algorithms that can compute a minimum eigenvalue for an operator may implement this interface to allow different algorithms to be used interchangeably.

## Methods

### compute\_minimum\_eigenvalue

<span id="qiskit.algorithms.MinimumEigensolver.compute_minimum_eigenvalue" />

`abstract MinimumEigensolver.compute_minimum_eigenvalue(operator, aux_operators=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/algorithms/minimum_eigen_solvers/minimum_eigen_solver.py "view source code")

Computes minimum eigenvalue. Operator and aux\_operators can be supplied here and if not None will override any already set into algorithm so it can be reused with different operators. While an operator is required by algorithms, aux\_operators are optional. To ‘remove’ a previous aux\_operators array use an empty list here.

**Parameters**

*   **operator** (`OperatorBase`) – Qubit operator of the Observable
*   **aux\_operators** (`Optional`\[`List`\[`Optional`\[`OperatorBase`]]]) – Optional list of auxiliary operators to be evaluated with the eigenstate of the minimum eigenvalue main result and their expectation values returned. For instance in chemistry these can be dipole operators, total particle count operators so we can get values for these at the ground state.

**Return type**

`MinimumEigensolverResult`

**Returns**

MinimumEigensolverResult

### supports\_aux\_operators

<span id="qiskit.algorithms.MinimumEigensolver.supports_aux_operators" />

`classmethod MinimumEigensolver.supports_aux_operators()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/algorithms/minimum_eigen_solvers/minimum_eigen_solver.py "view source code")

Whether computing the expectation value of auxiliary operators is supported.

If the minimum eigensolver computes an eigenstate of the main operator then it can compute the expectation value of the aux\_operators for that state. Otherwise they will be ignored.

**Return type**

`bool`

**Returns**

True if aux\_operator expectations can be evaluated, False otherwise

