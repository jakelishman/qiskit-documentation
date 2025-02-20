---
title: LinearExpression
description: API reference for qiskit.optimization.problems.LinearExpression
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.optimization.problems.LinearExpression
---

<span id="qiskit-optimization-problems-linearexpression" />

# qiskit.optimization.problems.LinearExpression

<span id="qiskit.optimization.problems.LinearExpression" />

`LinearExpression(quadratic_program, coefficients)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.8/qiskit/optimization/problems/linear_expression.py "view source code")

Representation of a linear expression by its coefficients.

Creates a new linear expression.

The linear expression can be defined via an array, a list, a sparse matrix, or a dictionary that uses variable names or indices as keys and stores the values internally as a dok\_matrix.

**Parameters**

*   **quadratic\_program** (`Any`) – The parent QuadraticProgram.
*   **coefficients** (`Union`\[`ndarray`, `spmatrix`, `List`\[`float`], `Dict`\[`Union`\[`int`, `str`], `float`]]) – The (sparse) representation of the coefficients.

### \_\_init\_\_

<span id="qiskit.optimization.problems.LinearExpression.__init__" />

`__init__(quadratic_program, coefficients)`

Creates a new linear expression.

The linear expression can be defined via an array, a list, a sparse matrix, or a dictionary that uses variable names or indices as keys and stores the values internally as a dok\_matrix.

**Parameters**

*   **quadratic\_program** (`Any`) – The parent QuadraticProgram.
*   **coefficients** (`Union`\[`ndarray`, `spmatrix`, `List`\[`float`], `Dict`\[`Union`\[`int`, `str`], `float`]]) – The (sparse) representation of the coefficients.

## Methods

|                                                                                                                                                                  |                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.optimization.problems.LinearExpression.__init__ "qiskit.optimization.problems.LinearExpression.__init__")(quadratic\_program, coefficients) | Creates a new linear expression.                                                                                 |
| [`evaluate`](#qiskit.optimization.problems.LinearExpression.evaluate "qiskit.optimization.problems.LinearExpression.evaluate")(x)                                | Evaluate the linear expression for given variables.                                                              |
| [`evaluate_gradient`](#qiskit.optimization.problems.LinearExpression.evaluate_gradient "qiskit.optimization.problems.LinearExpression.evaluate_gradient")(x)     | Evaluate the gradient of the linear expression for given variables.                                              |
| [`to_array`](#qiskit.optimization.problems.LinearExpression.to_array "qiskit.optimization.problems.LinearExpression.to_array")()                                 | Returns the coefficients of the linear expression as array.                                                      |
| [`to_dict`](#qiskit.optimization.problems.LinearExpression.to_dict "qiskit.optimization.problems.LinearExpression.to_dict")(\[use\_name])                        | Returns the coefficients of the linear expression as dictionary, either using variable names or indices as keys. |

## Attributes

|                                                                                                                                                           |                                                    |
| --------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------- |
| [`coefficients`](#qiskit.optimization.problems.LinearExpression.coefficients "qiskit.optimization.problems.LinearExpression.coefficients")                | Returns the coefficients of the linear expression. |
| [`quadratic_program`](#qiskit.optimization.problems.LinearExpression.quadratic_program "qiskit.optimization.problems.LinearExpression.quadratic_program") | Returns the parent QuadraticProgram.               |

### coefficients

<span id="qiskit.optimization.problems.LinearExpression.coefficients" />

`property coefficients`

Returns the coefficients of the linear expression.

**Return type**

`dok_matrix`

**Returns**

The coefficients of the linear expression.

### evaluate

<span id="qiskit.optimization.problems.LinearExpression.evaluate" />

`evaluate(x)`

Evaluate the linear expression for given variables.

**Parameters**

**x** (`Union`\[`ndarray`, `List`, `Dict`\[`Union`\[`int`, `str`], `float`]]) – The values of the variables to be evaluated.

**Return type**

`float`

**Returns**

The value of the linear expression given the variable values.

### evaluate\_gradient

<span id="qiskit.optimization.problems.LinearExpression.evaluate_gradient" />

`evaluate_gradient(x)`

Evaluate the gradient of the linear expression for given variables.

**Parameters**

**x** (`Union`\[`ndarray`, `List`, `Dict`\[`Union`\[`int`, `str`], `float`]]) – The values of the variables to be evaluated.

**Return type**

`ndarray`

**Returns**

The value of the gradient of the linear expression given the variable values.

### quadratic\_program

<span id="qiskit.optimization.problems.LinearExpression.quadratic_program" />

`property quadratic_program`

Returns the parent QuadraticProgram.

**Return type**

`Any`

**Returns**

The parent QuadraticProgram.

### to\_array

<span id="qiskit.optimization.problems.LinearExpression.to_array" />

`to_array()`

Returns the coefficients of the linear expression as array.

**Return type**

`ndarray`

**Returns**

An array with the coefficients corresponding to the linear expression.

### to\_dict

<span id="qiskit.optimization.problems.LinearExpression.to_dict" />

`to_dict(use_name=False)`

Returns the coefficients of the linear expression as dictionary, either using variable names or indices as keys.

**Parameters**

**use\_name** (`bool`) – Determines whether to use index or names to refer to variables.

**Return type**

`Dict`\[`Union`\[`int`, `str`], `float`]

**Returns**

An dictionary with the coefficients corresponding to the linear expression.

