---
title: ADMMOptimizationResult
description: API reference for qiskit.optimization.algorithms.ADMMOptimizationResult
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.optimization.algorithms.ADMMOptimizationResult
---

<span id="qiskit-optimization-algorithms-admmoptimizationresult" />

# qiskit.optimization.algorithms.ADMMOptimizationResult

<span id="qiskit.optimization.algorithms.ADMMOptimizationResult" />

`ADMMOptimizationResult(x, fval, variables, state, status)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.8/qiskit/optimization/algorithms/admm_optimizer.py "view source code")

ADMMOptimization Result.

**Parameters**

*   **x** (`ndarray`) – the optimal value found by ADMM.
*   **fval** (`float`) – the optimal function value.
*   **variables** (`List`\[`Variable`]) – the list of variables of the optimization problem.
*   **state** (`ADMMState`) – the internal computation state of ADMM.
*   **status** (`OptimizationResultStatus`) – Termination status of an optimization algorithm

### \_\_init\_\_

<span id="qiskit.optimization.algorithms.ADMMOptimizationResult.__init__" />

`__init__(x, fval, variables, state, status)`

**Parameters**

*   **x** (`ndarray`) – the optimal value found by ADMM.
*   **fval** (`float`) – the optimal function value.
*   **variables** (`List`\[`Variable`]) – the list of variables of the optimization problem.
*   **state** (`ADMMState`) – the internal computation state of ADMM.
*   **status** (`OptimizationResultStatus`) – Termination status of an optimization algorithm

## Methods

|                                                                                                                                                                                   |                     |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- |
| [`__init__`](#qiskit.optimization.algorithms.ADMMOptimizationResult.__init__ "qiskit.optimization.algorithms.ADMMOptimizationResult.__init__")(x, fval, variables, state, status) | **type x**`ndarray` |

## Attributes

|                                                                                                                                                                  |                                                                                         |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| [`fval`](#qiskit.optimization.algorithms.ADMMOptimizationResult.fval "qiskit.optimization.algorithms.ADMMOptimizationResult.fval")                               | Returns the optimal function value.                                                     |
| [`raw_results`](#qiskit.optimization.algorithms.ADMMOptimizationResult.raw_results "qiskit.optimization.algorithms.ADMMOptimizationResult.raw_results")          | Return the original results object from the optimization algorithm.                     |
| [`state`](#qiskit.optimization.algorithms.ADMMOptimizationResult.state "qiskit.optimization.algorithms.ADMMOptimizationResult.state")                            | returns state                                                                           |
| [`status`](#qiskit.optimization.algorithms.ADMMOptimizationResult.status "qiskit.optimization.algorithms.ADMMOptimizationResult.status")                         | Returns the termination status of the optimization algorithm.                           |
| [`variable_names`](#qiskit.optimization.algorithms.ADMMOptimizationResult.variable_names "qiskit.optimization.algorithms.ADMMOptimizationResult.variable_names") | Returns the list of variable names of the optimization problem.                         |
| [`variables`](#qiskit.optimization.algorithms.ADMMOptimizationResult.variables "qiskit.optimization.algorithms.ADMMOptimizationResult.variables")                | Returns the list of variables of the optimization problem.                              |
| [`variables_dict`](#qiskit.optimization.algorithms.ADMMOptimizationResult.variables_dict "qiskit.optimization.algorithms.ADMMOptimizationResult.variables_dict") | Returns the optimal value as a dictionary of the variable name and corresponding value. |
| [`x`](#qiskit.optimization.algorithms.ADMMOptimizationResult.x "qiskit.optimization.algorithms.ADMMOptimizationResult.x")                                        | Returns the optimal value found in the optimization or None in case of FAILURE.         |

### fval

<span id="qiskit.optimization.algorithms.ADMMOptimizationResult.fval" />

`property fval`

Returns the optimal function value.

**Return type**

`float`

**Returns**

The function value corresponding to the optimal value found in the optimization.

### raw\_results

<span id="qiskit.optimization.algorithms.ADMMOptimizationResult.raw_results" />

`property raw_results`

Return the original results object from the optimization algorithm.

Currently a dump for any leftovers.

**Return type**

`Any`

**Returns**

Additional result information of the optimization algorithm.

### state

<span id="qiskit.optimization.algorithms.ADMMOptimizationResult.state" />

`property state`

returns state

**Return type**

`ADMMState`

### status

<span id="qiskit.optimization.algorithms.ADMMOptimizationResult.status" />

`property status`

Returns the termination status of the optimization algorithm.

**Return type**

`OptimizationResultStatus`

**Returns**

The termination status of the algorithm.

### variable\_names

<span id="qiskit.optimization.algorithms.ADMMOptimizationResult.variable_names" />

`property variable_names`

Returns the list of variable names of the optimization problem.

**Return type**

`List`\[`str`]

**Returns**

The list of variable names of the optimization problem.

### variables

<span id="qiskit.optimization.algorithms.ADMMOptimizationResult.variables" />

`property variables`

Returns the list of variables of the optimization problem.

**Return type**

`List`\[`Variable`]

**Returns**

The list of variables.

### variables\_dict

<span id="qiskit.optimization.algorithms.ADMMOptimizationResult.variables_dict" />

`property variables_dict`

Returns the optimal value as a dictionary of the variable name and corresponding value.

**Return type**

`Dict`\[`str`, `float`]

**Returns**

The optimal value as a dictionary of the variable name and corresponding value.

### x

<span id="qiskit.optimization.algorithms.ADMMOptimizationResult.x" />

`property x`

Returns the optimal value found in the optimization or None in case of FAILURE.

**Return type**

`Optional`\[`ndarray`]

**Returns**

The optimal value found in the optimization.

