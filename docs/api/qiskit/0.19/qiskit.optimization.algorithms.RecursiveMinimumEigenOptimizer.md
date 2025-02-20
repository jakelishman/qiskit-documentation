---
title: RecursiveMinimumEigenOptimizer
description: API reference for qiskit.optimization.algorithms.RecursiveMinimumEigenOptimizer
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.optimization.algorithms.RecursiveMinimumEigenOptimizer
---

# RecursiveMinimumEigenOptimizer

<span id="qiskit.optimization.algorithms.RecursiveMinimumEigenOptimizer" />

`RecursiveMinimumEigenOptimizer(min_eigen_optimizer, min_num_vars=1, min_num_vars_optimizer=None, penalty=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/optimization/algorithms/recursive_minimum_eigen_optimizer.py "view source code")

A meta-algorithm that applies a recursive optimization.

The recursive minimum eigen optimizer applies a recursive optimization on top of [`MinimumEigenOptimizer`](qiskit.optimization.algorithms.MinimumEigenOptimizer "qiskit.optimization.algorithms.MinimumEigenOptimizer"). The algorithm is introduced in \[1].

## Examples

Outline of how to use this class:

```python
from qiskit.aqua.algorithms import QAOA
from qiskit.optimization.problems import QuadraticProgram
from qiskit.optimization.algorithms import RecursiveMinimumEigenOptimizer
problem = QuadraticProgram()
# specify problem here
# specify minimum eigen solver to be used, e.g., QAOA
qaoa = QAOA(...)
optimizer = RecursiveMinimumEigenOptimizer(qaoa)
result = optimizer.solve(problem)
```

## References

**\[1]: Bravyi et al. (2019), Obstacles to State Preparation and Variational Optimization**

from Symmetry Protection. [http://arxiv.org/abs/1910.08980](http://arxiv.org/abs/1910.08980).

Initializes the recursive minimum eigen optimizer.

This initializer takes a `MinimumEigenOptimizer`, the parameters to specify until when to to apply the iterative scheme, and the optimizer to be applied once the threshold number of variables is reached.

**Parameters**

*   **min\_eigen\_optimizer** ([`MinimumEigenOptimizer`](qiskit.optimization.algorithms.MinimumEigenOptimizer "qiskit.optimization.algorithms.minimum_eigen_optimizer.MinimumEigenOptimizer")) – The eigen optimizer to use in every iteration.
*   **min\_num\_vars** (`int`) – The minimum number of variables to apply the recursive scheme. If this threshold is reached, the min\_num\_vars\_optimizer is used.
*   **min\_num\_vars\_optimizer** (`Optional`\[[`OptimizationAlgorithm`](qiskit.optimization.algorithms.OptimizationAlgorithm "qiskit.optimization.algorithms.optimization_algorithm.OptimizationAlgorithm")]) – This optimizer is used after the recursive scheme for the problem with the remaining variables.
*   **penalty** (`Optional`\[`float`]) – The factor that is used to scale the penalty terms corresponding to linear equality constraints.

TODO: add flag to store full history.

**Raises**

[**QiskitOptimizationError**](qiskit.optimization.QiskitOptimizationError "qiskit.optimization.QiskitOptimizationError") – In case of invalid parameters (num\_min\_vars \< 1).

## Methods

### get\_compatibility\_msg

<span id="qiskit.optimization.algorithms.RecursiveMinimumEigenOptimizer.get_compatibility_msg" />

`RecursiveMinimumEigenOptimizer.get_compatibility_msg(problem)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/optimization/algorithms/recursive_minimum_eigen_optimizer.py "view source code")

Checks whether a given problem can be solved with this optimizer.

Checks whether the given problem is compatible, i.e., whether the problem can be converted to a QUBO, and otherwise, returns a message explaining the incompatibility.

**Parameters**

**problem** ([`QuadraticProgram`](qiskit.optimization.problems.QuadraticProgram "qiskit.optimization.problems.quadratic_program.QuadraticProgram")) – The optimization problem to check compatibility.

**Return type**

`str`

**Returns**

A message describing the incompatibility.

### is\_compatible

<span id="qiskit.optimization.algorithms.RecursiveMinimumEigenOptimizer.is_compatible" />

`RecursiveMinimumEigenOptimizer.is_compatible(problem)`

Checks whether a given problem can be solved with the optimizer implementing this method.

**Parameters**

**problem** ([`QuadraticProgram`](qiskit.optimization.problems.QuadraticProgram "qiskit.optimization.problems.quadratic_program.QuadraticProgram")) – The optimization problem to check compatibility.

**Return type**

`bool`

**Returns**

Returns True if the problem is compatible, False otherwise.

### solve

<span id="qiskit.optimization.algorithms.RecursiveMinimumEigenOptimizer.solve" />

`RecursiveMinimumEigenOptimizer.solve(problem)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/optimization/algorithms/recursive_minimum_eigen_optimizer.py "view source code")

Tries to solve the given problem using the recursive optimizer.

Runs the optimizer to try to solve the optimization problem.

**Parameters**

**problem** ([`QuadraticProgram`](qiskit.optimization.problems.QuadraticProgram "qiskit.optimization.problems.quadratic_program.QuadraticProgram")) – The problem to be solved.

**Return type**

`OptimizationResult`

**Returns**

The result of the optimizer applied to the problem.

**Raises**

*   [**QiskitOptimizationError**](qiskit.optimization.QiskitOptimizationError "qiskit.optimization.QiskitOptimizationError") – Incompatible problem.
*   [**QiskitOptimizationError**](qiskit.optimization.QiskitOptimizationError "qiskit.optimization.QiskitOptimizationError") – Infeasible due to variable substitution

