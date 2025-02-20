---
title: Eigensolver
description: API reference for qiskit.algorithms.Eigensolver
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.Eigensolver
---

# Eigensolver

<span id="qiskit.algorithms.Eigensolver" />

`Eigensolver`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/algorithms/eigen_solvers/eigen_solver.py "view source code")

Bases: `abc.ABC`

The Eigensolver Interface.

Algorithms that can compute eigenvalues for an operator may implement this interface to allow different algorithms to be used interchangeably.

## Methods

### compute\_eigenvalues

<span id="qiskit.algorithms.Eigensolver.compute_eigenvalues" />

`abstract Eigensolver.compute_eigenvalues(operator, aux_operators=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/algorithms/eigen_solvers/eigen_solver.py "view source code")

Computes eigenvalues. Operator and aux\_operators can be supplied here and if not None will override any already set into algorithm so it can be reused with different operators. While an operator is required by algorithms, aux\_operators are optional. To ‘remove’ a previous aux\_operators array use an empty list here.

**Parameters**

*   **operator** (`OperatorBase`) – Qubit operator of the Observable
*   **aux\_operators** (`Union`\[`List`\[`Optional`\[`OperatorBase`]], `Dict`\[`str`, `OperatorBase`], `None`]) – Optional list of auxiliary operators to be evaluated with the eigenstate of the minimum eigenvalue main result and their expectation values returned. For instance in chemistry these can be dipole operators, total particle count operators so we can get values for these at the ground state.

**Return type**

`EigensolverResult`

**Returns**

EigensolverResult

### supports\_aux\_operators

<span id="qiskit.algorithms.Eigensolver.supports_aux_operators" />

`classmethod Eigensolver.supports_aux_operators()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/algorithms/eigen_solvers/eigen_solver.py "view source code")

Whether computing the expectation value of auxiliary operators is supported.

**Return type**

`bool`

**Returns**

True if aux\_operator expectations can be evaluated, False otherwise

