---
title: Eigensolver
description: API reference for qiskit.algorithms.eigensolvers.Eigensolver
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.eigensolvers.Eigensolver
---

# Eigensolver

<span id="qiskit.algorithms.eigensolvers.Eigensolver" />

`Eigensolver`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/algorithms/eigensolvers/eigensolver.py "view source code")

Bases: `ABC`

The eigensolver interface.

Algorithms that can compute eigenvalues for an operator may implement this interface to allow different algorithms to be used interchangeably.

## Methods

<span id="qiskit-algorithms-eigensolvers-eigensolver-compute-eigenvalues" />

### compute\_eigenvalues

<span id="qiskit.algorithms.eigensolvers.Eigensolver.compute_eigenvalues" />

`abstract Eigensolver.compute_eigenvalues(operator, aux_operators=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/algorithms/eigensolvers/eigensolver.py "view source code")

Computes the minimum eigenvalue. The `operator` and `aux_operators` are supplied here. While an `operator` is required by algorithms, `aux_operators` are optional.

**Parameters**

*   **operator** (*BaseOperator |* [*PauliSumOp*](qiskit.opflow.primitive_ops.PauliSumOp "qiskit.opflow.primitive_ops.PauliSumOp")) – Qubit operator of the observable.
*   **aux\_operators** (*ListOrDict\[BaseOperator |* [*PauliSumOp*](qiskit.opflow.primitive_ops.PauliSumOp "qiskit.opflow.primitive_ops.PauliSumOp")*] | None*) – Optional list of auxiliary operators to be evaluated with the eigenstate of the minimum eigenvalue main result and their expectation values returned. For instance, in chemistry, these can be dipole operators and total particle count operators, so we can get values for these at the ground state.

**Returns**

An eigensolver result.

**Return type**

[EigensolverResult](qiskit.algorithms.eigensolvers.EigensolverResult "qiskit.algorithms.eigensolvers.EigensolverResult")

<span id="qiskit-algorithms-eigensolvers-eigensolver-supports-aux-operators" />

### supports\_aux\_operators

<span id="qiskit.algorithms.eigensolvers.Eigensolver.supports_aux_operators" />

`classmethod Eigensolver.supports_aux_operators()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/algorithms/eigensolvers/eigensolver.py "view source code")

Whether computing the expectation value of auxiliary operators is supported.

If the eigensolver computes the eigenvalues of the main operator, then it can compute the expectation value of the `aux_operators` for that state. Otherwise they will be ignored.

**Returns**

`True` if `aux_operator` expectations can be evaluated, `False` otherwise.

**Return type**

bool

