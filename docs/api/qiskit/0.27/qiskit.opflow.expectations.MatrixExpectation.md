---
title: MatrixExpectation
description: API reference for qiskit.opflow.expectations.MatrixExpectation
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.opflow.expectations.MatrixExpectation
---

# qiskit.opflow\.expectations.MatrixExpectation

<span id="qiskit.opflow.expectations.MatrixExpectation" />

`MatrixExpectation`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.17/qiskit/opflow/expectations/matrix_expectation.py "view source code")

An Expectation converter which converts Operator measurements to be matrix-based so they can be evaluated by matrix multiplication.

### \_\_init\_\_

<span id="qiskit.opflow.expectations.MatrixExpectation.__init__" />

`__init__()`

Initialize self. See help(type(self)) for accurate signature.

## Methods

|                                                                                                                                                               |                                                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.opflow.expectations.MatrixExpectation.__init__ "qiskit.opflow.expectations.MatrixExpectation.__init__")()                                | Initialize self.                                                                                                |
| [`compute_variance`](#qiskit.opflow.expectations.MatrixExpectation.compute_variance "qiskit.opflow.expectations.MatrixExpectation.compute_variance")(exp\_op) | Compute the variance of the expectation estimator.                                                              |
| [`convert`](#qiskit.opflow.expectations.MatrixExpectation.convert "qiskit.opflow.expectations.MatrixExpectation.convert")(operator)                           | Accept an Operator and return a new Operator with the Pauli measurements replaced by Matrix based measurements. |

### compute\_variance

<span id="qiskit.opflow.expectations.MatrixExpectation.compute_variance" />

`compute_variance(exp_op)`

Compute the variance of the expectation estimator. Because this expectation works by matrix multiplication, the estimation is exact and the variance is always 0, but we need to return those values in a way which matches the Operator’s structure.

**Parameters**

**exp\_op** (`OperatorBase`) – The full expectation value Operator.

**Return type**

`Union`\[`list`, `float`]

**Returns**

The variances or lists thereof (if exp\_op contains ListOps) of the expectation value estimation, equal to 0.

### convert

<span id="qiskit.opflow.expectations.MatrixExpectation.convert" />

`convert(operator)`

Accept an Operator and return a new Operator with the Pauli measurements replaced by Matrix based measurements.

**Parameters**

**operator** (`OperatorBase`) – The operator to convert.

**Return type**

`OperatorBase`

**Returns**

The converted operator.

