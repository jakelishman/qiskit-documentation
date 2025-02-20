---
title: get_graph_solution
description: API reference for qiskit.optimization.applications.ising.max_cut.get_graph_solution
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.optimization.applications.ising.max_cut.get_graph_solution
---

<span id="qiskit-optimization-applications-ising-max-cut" />

# qiskit.optimization.applications.ising.max\_cut

Convert max-cut instances into Pauli list Deal with Gset format. See [https://web.stanford.edu/\~yyye/yyye/Gset/](https://web.stanford.edu/~yyye/yyye/Gset/) Design the max-cut object w as a two-dimensional np.array e.g., w\[i, j] = x means that the weight of a edge between i and j is x Note that the weights are symmetric, i.e., w\[j, i] = x always holds.

## Functions

|                                                                                                                                                                   |                                                          |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------- |
| [`get_graph_solution`](#qiskit.optimization.applications.ising.max_cut.get_graph_solution "qiskit.optimization.applications.ising.max_cut.get_graph_solution")(x) | Get graph solution from binary string.                   |
| [`get_operator`](#qiskit.optimization.applications.ising.max_cut.get_operator "qiskit.optimization.applications.ising.max_cut.get_operator")(weight\_matrix)      | Generate Hamiltonian for the max-cut problem of a graph. |
| [`max_cut_value`](#qiskit.optimization.applications.ising.max_cut.max_cut_value "qiskit.optimization.applications.ising.max_cut.max_cut_value")(x, w)             | Compute the value of a cut.                              |

<span id="qiskit.optimization.applications.ising.max_cut.get_graph_solution" />

`get_graph_solution(x)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/optimization/applications/ising/max_cut.py "view source code")

Get graph solution from binary string.

**Parameters**

**x** (*numpy.ndarray*) – binary string as numpy array.

**Returns**

graph solution as binary numpy array.

**Return type**

numpy.ndarray

<span id="qiskit.optimization.applications.ising.max_cut.get_operator" />

`get_operator(weight_matrix)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/optimization/applications/ising/max_cut.py "view source code")

Generate Hamiltonian for the max-cut problem of a graph.

**Parameters**

**weight\_matrix** (*numpy.ndarray*) – adjacency matrix.

**Returns**

operator for the Hamiltonian float: a constant shift for the obj function.

**Return type**

[WeightedPauliOperator](qiskit.aqua.operators.legacy.WeightedPauliOperator "qiskit.aqua.operators.legacy.WeightedPauliOperator")

<span id="qiskit.optimization.applications.ising.max_cut.max_cut_value" />

`max_cut_value(x, w)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/optimization/applications/ising/max_cut.py "view source code")

Compute the value of a cut.

**Parameters**

*   **x** (*numpy.ndarray*) – binary string as numpy array.
*   **w** (*numpy.ndarray*) – adjacency matrix.

**Returns**

value of the cut.

**Return type**

float

