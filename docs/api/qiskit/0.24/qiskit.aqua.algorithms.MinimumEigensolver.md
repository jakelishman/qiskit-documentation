---
title: MinimumEigensolver
description: API reference for qiskit.aqua.algorithms.MinimumEigensolver
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.algorithms.MinimumEigensolver
---

<span id="qiskit-aqua-algorithms-minimumeigensolver" />

# qiskit.aqua.algorithms.MinimumEigensolver

<span id="qiskit.aqua.algorithms.MinimumEigensolver" />

`MinimumEigensolver`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.8/qiskit/aqua/algorithms/minimum_eigen_solvers/minimum_eigen_solver.py "view source code")

The Minimum Eigensolver Interface.

Algorithms that can compute a minimum eigenvalue for an operator may implement this interface to allow different algorithms to be used interchangeably.

### \_\_init\_\_

<span id="qiskit.aqua.algorithms.MinimumEigensolver.__init__" />

`__init__()`

Initialize self. See help(type(self)) for accurate signature.

## Methods

|                                                                                                                                                                                              |                                                                              |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| [`__init__`](#qiskit.aqua.algorithms.MinimumEigensolver.__init__ "qiskit.aqua.algorithms.MinimumEigensolver.__init__")()                                                                     | Initialize self.                                                             |
| [`compute_minimum_eigenvalue`](#qiskit.aqua.algorithms.MinimumEigensolver.compute_minimum_eigenvalue "qiskit.aqua.algorithms.MinimumEigensolver.compute_minimum_eigenvalue")(\[operator, …]) | Computes minimum eigenvalue.                                                 |
| [`supports_aux_operators`](#qiskit.aqua.algorithms.MinimumEigensolver.supports_aux_operators "qiskit.aqua.algorithms.MinimumEigensolver.supports_aux_operators")()                           | Whether computing the expectation value of auxiliary operators is supported. |

## Attributes

|                                                                                                                                       |                                  |
| ------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------- |
| [`aux_operators`](#qiskit.aqua.algorithms.MinimumEigensolver.aux_operators "qiskit.aqua.algorithms.MinimumEigensolver.aux_operators") | Returns the auxiliary operators. |
| [`operator`](#qiskit.aqua.algorithms.MinimumEigensolver.operator "qiskit.aqua.algorithms.MinimumEigensolver.operator")                | Return the operator.             |

### aux\_operators

<span id="qiskit.aqua.algorithms.MinimumEigensolver.aux_operators" />

`abstract property aux_operators`

Returns the auxiliary operators.

**Return type**

`Optional`\[`List`\[`Optional`\[`OperatorBase`]]]

### compute\_minimum\_eigenvalue

<span id="qiskit.aqua.algorithms.MinimumEigensolver.compute_minimum_eigenvalue" />

`abstract compute_minimum_eigenvalue(operator=None, aux_operators=None)`

Computes minimum eigenvalue. Operator and aux\_operators can be supplied here and if not None will override any already set into algorithm so it can be reused with different operators. While an operator is required by algorithms, aux\_operators are optional. To ‘remove’ a previous aux\_operators array use an empty list here.

**Parameters**

*   **operator** (`Union`\[`OperatorBase`, `LegacyBaseOperator`, `None`]) – If not None replaces operator in algorithm
*   **aux\_operators** (`Optional`\[`List`\[`Union`\[`OperatorBase`, `LegacyBaseOperator`, `None`]]]) – If not None replaces aux\_operators in algorithm

**Return type**

`MinimumEigensolverResult`

**Returns**

MinimumEigensolverResult

### operator

<span id="qiskit.aqua.algorithms.MinimumEigensolver.operator" />

`abstract property operator`

Return the operator.

**Return type**

`Union`\[`OperatorBase`, `LegacyBaseOperator`, `None`]

### supports\_aux\_operators

<span id="qiskit.aqua.algorithms.MinimumEigensolver.supports_aux_operators" />

`classmethod supports_aux_operators()`

Whether computing the expectation value of auxiliary operators is supported.

If the minimum eigensolver computes an eigenstate of the main operator then it can compute the expectation value of the aux\_operators for that state. Otherwise they will be ignored.

**Return type**

`bool`

**Returns**

True if aux\_operator expectations can be evaluated, False otherwise

