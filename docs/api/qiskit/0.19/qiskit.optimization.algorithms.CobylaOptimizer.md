---
title: CobylaOptimizer
description: API reference for qiskit.optimization.algorithms.CobylaOptimizer
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.optimization.algorithms.CobylaOptimizer
---

# CobylaOptimizer

<span id="qiskit.optimization.algorithms.CobylaOptimizer" />

`CobylaOptimizer(rhobeg=1.0, rhoend=0.0001, maxfun=1000, disp=None, catol=0.0002)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/optimization/algorithms/cobyla_optimizer.py "view source code")

The SciPy COBYLA optimizer wrapped as an Qiskit [`OptimizationAlgorithm`](qiskit.optimization.algorithms.OptimizationAlgorithm "qiskit.optimization.algorithms.OptimizationAlgorithm").

This class provides a wrapper for `scipy.optimize.fmin_cobyla` ([https://docs.scipy.org/doc/scipy-0.14.0/reference/generated/scipy.optimize.fmin\_cobyla.html](https://docs.scipy.org/doc/scipy-0.14.0/reference/generated/scipy.optimize.fmin_cobyla.html)) to be used within the optimization module. The arguments for `fmin_cobyla` are passed via the constructor.

## Examples

```python
>>> from qiskit.optimization.problems import QuadraticProgram
>>> from qiskit.optimization.algorithms import CobylaOptimizer
>>> problem = QuadraticProgram()
>>> # specify problem here
>>> optimizer = CobylaOptimizer()
>>> result = optimizer.solve(problem)
```

Initializes the CobylaOptimizer.

This initializer takes the algorithmic parameters of COBYLA and stores them for later use of `fmin_cobyla` when [`solve()`](qiskit.optimization.algorithms.CobylaOptimizer#solve "qiskit.optimization.algorithms.CobylaOptimizer.solve") is invoked. This optimizer can be applied to find a (local) optimum for problems consisting of only continuous variables.

**Parameters**

*   **rhobeg** (`float`) – Reasonable initial changes to the variables.
*   **rhoend** (`float`) – Final accuracy in the optimization (not precisely guaranteed). This is a lower bound on the size of the trust region.
*   **disp** (`Optional`\[`int`]) – Controls the frequency of output; 0 implies no output. Feasible values are \{0, 1, 2, 3}.
*   **maxfun** (`int`) – Maximum number of function evaluations.
*   **catol** (`float`) – Absolute tolerance for constraint violations.

## Methods

### get\_compatibility\_msg

<span id="qiskit.optimization.algorithms.CobylaOptimizer.get_compatibility_msg" />

`CobylaOptimizer.get_compatibility_msg(problem)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/optimization/algorithms/cobyla_optimizer.py "view source code")

Checks whether a given problem can be solved with this optimizer.

Checks whether the given problem is compatible, i.e., whether the problem contains only continuous variables, and otherwise, returns a message explaining the incompatibility.

**Parameters**

**problem** ([`QuadraticProgram`](qiskit.optimization.problems.QuadraticProgram "qiskit.optimization.problems.quadratic_program.QuadraticProgram")) – The optimization problem to check compatibility.

**Return type**

`str`

**Returns**

Returns a string describing the incompatibility.

### is\_compatible

<span id="qiskit.optimization.algorithms.CobylaOptimizer.is_compatible" />

`CobylaOptimizer.is_compatible(problem)`

Checks whether a given problem can be solved with the optimizer implementing this method.

**Parameters**

**problem** ([`QuadraticProgram`](qiskit.optimization.problems.QuadraticProgram "qiskit.optimization.problems.quadratic_program.QuadraticProgram")) – The optimization problem to check compatibility.

**Return type**

`bool`

**Returns**

Returns True if the problem is compatible, False otherwise.

### solve

<span id="qiskit.optimization.algorithms.CobylaOptimizer.solve" />

`CobylaOptimizer.solve(problem)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/optimization/algorithms/cobyla_optimizer.py "view source code")

Tries to solves the given problem using the optimizer.

Runs the optimizer to try to solve the optimization problem.

**Parameters**

**problem** ([`QuadraticProgram`](qiskit.optimization.problems.QuadraticProgram "qiskit.optimization.problems.quadratic_program.QuadraticProgram")) – The problem to be solved.

**Return type**

`OptimizationResult`

**Returns**

The result of the optimizer applied to the problem.

**Raises**

[**QiskitOptimizationError**](qiskit.optimization.QiskitOptimizationError "qiskit.optimization.QiskitOptimizationError") – If the problem is incompatible with the optimizer.

