---
title: EigensolverResult
description: API reference for qiskit.algorithms.eigensolvers.EigensolverResult
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.eigensolvers.EigensolverResult
---

# EigensolverResult

<span id="qiskit.algorithms.eigensolvers.EigensolverResult" />

`qiskit.algorithms.eigensolvers.EigensolverResult`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/algorithms/eigensolvers/eigensolver.py "view source code")

Bases: `AlgorithmResult`

Eigensolver result.

## Attributes

<span id="qiskit.algorithms.eigensolvers.EigensolverResult.aux_operators_evaluated" />

### aux\_operators\_evaluated

Return the aux operator expectation values.

These values are in fact tuples formatted as (mean, metadata).

<span id="qiskit.algorithms.eigensolvers.EigensolverResult.eigenvalues" />

### eigenvalues

Return the eigenvalues.

## Methods

### combine

<span id="qiskit.algorithms.eigensolvers.EigensolverResult.combine" />

`combine(result)`

Any property from the argument that exists in the receiver is updated. :param result: Argument result with properties to be set.

**Raises**

[**TypeError**](https://docs.python.org/3/library/exceptions.html#TypeError "(in Python v3.12)") – Argument is None

