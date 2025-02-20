---
title: ClassicalCPLEX
description: API reference for qiskit.aqua.algorithms.ClassicalCPLEX
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.algorithms.ClassicalCPLEX
---

# qiskit.aqua.algorithms.ClassicalCPLEX

<span id="qiskit.aqua.algorithms.ClassicalCPLEX" />

`ClassicalCPLEX(operator, timelimit=600, thread=1, display=2)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/algorithms/minimum_eigen_solvers/cplex/classical_cplex.py "view source code")

The Classical CPLEX algorithm (classical).

This algorithm uses the IBM ILOG CPLEX Optimization Studio along with its separately installed Python API to solve optimization problems modeled as an Ising Hamiltonian.

See these `installation instructions` if you need more information in that regard.

**Parameters**

*   **operator** (`WeightedPauliOperator`) – The Ising Hamiltonian as an Operator
*   **timelimit** (`int`) – A time limit in seconds for the execution
*   **thread** (`int`) – The number of threads that CPLEX uses. Setting this 0 lets CPLEX decide the number of threads to allocate, but this may not be ideal for small problems for which the default of 1 is more suitable.
*   **display** (`int`) – Decides what CPLEX reports to the screen and records in a log during mixed integer optimization. This value must be between 0 and 5 where the amount of information displayed increases with increasing values of this parameter.

### \_\_init\_\_

<span id="qiskit.aqua.algorithms.ClassicalCPLEX.__init__" />

`__init__(operator, timelimit=600, thread=1, display=2)`

**Parameters**

*   **operator** (`WeightedPauliOperator`) – The Ising Hamiltonian as an Operator
*   **timelimit** (`int`) – A time limit in seconds for the execution
*   **thread** (`int`) – The number of threads that CPLEX uses. Setting this 0 lets CPLEX decide the number of threads to allocate, but this may not be ideal for small problems for which the default of 1 is more suitable.
*   **display** (`int`) – Decides what CPLEX reports to the screen and records in a log during mixed integer optimization. This value must be between 0 and 5 where the amount of information displayed increases with increasing values of this parameter.

## Methods

|                                                                                                                                                         |                                          |
| ------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------- |
| [`__init__`](#qiskit.aqua.algorithms.ClassicalCPLEX.__init__ "qiskit.aqua.algorithms.ClassicalCPLEX.__init__")(operator\[, timelimit, thread, display]) | **type operator**`WeightedPauliOperator` |
| [`run`](#qiskit.aqua.algorithms.ClassicalCPLEX.run "qiskit.aqua.algorithms.ClassicalCPLEX.run")()                                                       | Execute the classical algorithm.         |

## Attributes

|                                                                                                                |                        |
| -------------------------------------------------------------------------------------------------------------- | ---------------------- |
| [`random`](#qiskit.aqua.algorithms.ClassicalCPLEX.random "qiskit.aqua.algorithms.ClassicalCPLEX.random")       | Return a numpy random. |
| [`solution`](#qiskit.aqua.algorithms.ClassicalCPLEX.solution "qiskit.aqua.algorithms.ClassicalCPLEX.solution") | return solution        |

### random

<span id="qiskit.aqua.algorithms.ClassicalCPLEX.random" />

`property random`

Return a numpy random.

### run

<span id="qiskit.aqua.algorithms.ClassicalCPLEX.run" />

`run()`

Execute the classical algorithm.

**Returns**

results of an algorithm.

**Return type**

dict

### solution

<span id="qiskit.aqua.algorithms.ClassicalCPLEX.solution" />

`property solution`

return solution

