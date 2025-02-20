---
title: EigensolverResult
description: API reference for qiskit.algorithms.EigensolverResult
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.EigensolverResult
---

# EigensolverResult

<span id="qiskit.algorithms.EigensolverResult" />

`qiskit.algorithms.EigensolverResult`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/algorithms/eigen_solvers/eigen_solver.py "view source code")

Bases: `AlgorithmResult`

Deprecated: Eigensolver Result.

The EigensolverResult class has been superseded by the [`qiskit.algorithms.eigensolvers.EigensolverResult`](qiskit.algorithms.eigensolvers.EigensolverResult "qiskit.algorithms.eigensolvers.EigensolverResult") class. This class will be deprecated in a future release and subsequently removed after that.

<Admonition title="Deprecated since version 0.24.0" type="danger">
  The class `qiskit.algorithms.eigen_solvers.eigen_solver.EigensolverResult` is deprecated as of qiskit 0.24.0. It will be removed no earlier than 3 months after the release date. Instead, use the class `qiskit.algorithms.eigensolvers.EigensolverResult`. See [https://qisk.it/algo\_migration](https://qisk.it/algo_migration) for a migration guide.
</Admonition>

## Attributes

<span id="qiskit.algorithms.EigensolverResult.aux_operator_eigenvalues" />

### aux\_operator\_eigenvalues

Return aux operator expectation values.

These values are in fact tuples formatted as (mean, standard deviation).

<span id="qiskit.algorithms.EigensolverResult.eigenstates" />

### eigenstates

return eigen states

<span id="qiskit.algorithms.EigensolverResult.eigenvalues" />

### eigenvalues

returns eigen values

## Methods

### combine

<span id="qiskit.algorithms.EigensolverResult.combine" />

`combine(result)`

Any property from the argument that exists in the receiver is updated. :param result: Argument result with properties to be set.

**Raises**

[**TypeError**](https://docs.python.org/3/library/exceptions.html#TypeError "(in Python v3.12)") – Argument is None

