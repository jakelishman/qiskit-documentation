---
title: set_packing
description: API reference for qiskit.optimization.applications.ising.set_packing
in_page_toc_min_heading_level: 1
python_api_type: module
python_api_name: qiskit.optimization.applications.ising.set_packing
---

<span id="module-qiskit.optimization.applications.ising.set_packing" />

<span id="qiskit-optimization-applications-ising-set-packing" />

# qiskit.optimization.applications.ising.set\_packing

set packing module

## Functions

|                                                                                                                                                                                    |                                                |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------- |
| [`check_disjoint`](#qiskit.optimization.applications.ising.set_packing.check_disjoint "qiskit.optimization.applications.ising.set_packing.check_disjoint")(sol, list\_of\_subsets) | check disjoint                                 |
| [`get_operator`](#qiskit.optimization.applications.ising.set_packing.get_operator "qiskit.optimization.applications.ising.set_packing.get_operator")(list\_of\_subsets)            | Construct the Hamiltonian for the set packing. |
| [`get_solution`](#qiskit.optimization.applications.ising.set_packing.get_solution "qiskit.optimization.applications.ising.set_packing.get_solution")(x)                            | **param x**binary string as numpy array.       |

<span id="qiskit.optimization.applications.ising.set_packing.check_disjoint" />

`check_disjoint(sol, list_of_subsets)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.8/qiskit/optimization/applications/ising/set_packing.py "view source code")

check disjoint

<span id="qiskit.optimization.applications.ising.set_packing.get_operator" />

`get_operator(list_of_subsets)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.8/qiskit/optimization/applications/ising/set_packing.py "view source code")

Construct the Hamiltonian for the set packing.

## Notes

find the maximal number of subsets which are disjoint pairwise.

Hamiltonian: H = A Ha + B Hb Ha = sum\_\{Si and Sj overlaps}\{XiXj} Hb = -sum\_\{i}\{Xi}

Ha is to ensure the disjoint condition, while Hb is to achieve the maximal number. Ha is hard constraint that must be satisfied. Therefore A >> B. In the following, we set A=10 and B = 1

where Xi = (Zi + 1)/2

**Parameters**

**list\_of\_subsets** (*list*) – list of lists (i.e., subsets)

**Returns**

**operator for the Hamiltonian,**

a constant shift for the obj function.

**Return type**

tuple([WeightedPauliOperator](qiskit.aqua.operators.legacy.WeightedPauliOperator "qiskit.aqua.operators.legacy.WeightedPauliOperator"), float)

<span id="qiskit.optimization.applications.ising.set_packing.get_solution" />

`get_solution(x)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.8/qiskit/optimization/applications/ising/set_packing.py "view source code")

**Parameters**

**x** (*numpy.ndarray*) – binary string as numpy array.

**Returns**

graph solution as binary numpy array.

**Return type**

numpy.ndarray

