---
title: OptimizationAlgorithm
description: API reference for qiskit.optimization.algorithms.OptimizationAlgorithm
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.optimization.algorithms.OptimizationAlgorithm
---

# OptimizationAlgorithm

<span id="qiskit.optimization.algorithms.OptimizationAlgorithm" />

`OptimizationAlgorithm`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/optimization/algorithms/optimization_algorithm.py "view source code")

Bases: `abc.ABC`

An abstract class for optimization algorithms in Qiskit’s optimization module.

## Methods

### get\_compatibility\_msg

<span id="qiskit.optimization.algorithms.OptimizationAlgorithm.get_compatibility_msg" />

`abstract OptimizationAlgorithm.get_compatibility_msg(problem)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/optimization/algorithms/optimization_algorithm.py "view source code")

Checks whether a given problem can be solved with the optimizer implementing this method.

**Parameters**

**problem** (`QuadraticProgram`) – The optimization problem to check compatibility.

**Return type**

`str`

**Returns**

Returns the incompatibility message. If the message is empty no issues were found.

### is\_compatible

<span id="qiskit.optimization.algorithms.OptimizationAlgorithm.is_compatible" />

`OptimizationAlgorithm.is_compatible(problem)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/optimization/algorithms/optimization_algorithm.py "view source code")

Checks whether a given problem can be solved with the optimizer implementing this method.

**Parameters**

**problem** (`QuadraticProgram`) – The optimization problem to check compatibility.

**Return type**

`bool`

**Returns**

Returns True if the problem is compatible, False otherwise.

### solve

<span id="qiskit.optimization.algorithms.OptimizationAlgorithm.solve" />

`abstract OptimizationAlgorithm.solve(problem)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/optimization/algorithms/optimization_algorithm.py "view source code")

Tries to solves the given problem using the optimizer.

Runs the optimizer to try to solve the optimization problem.

**Parameters**

**problem** (`QuadraticProgram`) – The problem to be solved.

**Return type**

`OptimizationResult`

**Returns**

The result of the optimizer applied to the problem.

**Raises**

[**QiskitOptimizationError**](qiskit.optimization.QiskitOptimizationError "qiskit.optimization.QiskitOptimizationError") – If the problem is incompatible with the optimizer.

