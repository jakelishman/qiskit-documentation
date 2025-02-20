---
title: VariationalPrinciple
description: API reference for qiskit.algorithms.time_evolvers.variational.VariationalPrinciple
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.time_evolvers.variational.VariationalPrinciple
---

# VariationalPrinciple

<span id="qiskit.algorithms.time_evolvers.variational.VariationalPrinciple" />

`VariationalPrinciple(qgt, gradient)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/time_evolvers/variational/variational_principles/variational_principle.py "view source code")

Bases: `abc.ABC`

A Variational Principle class. It determines the time propagation of parameters in a quantum state provided as a parametrized quantum circuit (ansatz).

<span id="qiskit.algorithms.time_evolvers.variational.VariationalPrinciple.qgt" />

### qgt

Instance of a class used to compute the GQT.

**Type**

[BaseQGT](qiskit.algorithms.gradients.BaseQGT "qiskit.algorithms.gradients.BaseQGT")

<span id="qiskit.algorithms.time_evolvers.variational.VariationalPrinciple.gradient" />

### gradient

Instance of a class used to compute the state gradient.

**Type**

[BaseEstimatorGradient](qiskit.algorithms.gradients.BaseEstimatorGradient "qiskit.algorithms.gradients.BaseEstimatorGradient")

**Parameters**

*   **qgt** ([`BaseQGT`](qiskit.algorithms.gradients.BaseQGT "qiskit.algorithms.gradients.base_qgt.BaseQGT")) – Instance of a class used to compute the GQT.
*   **gradient** ([`BaseEstimatorGradient`](qiskit.algorithms.gradients.BaseEstimatorGradient "qiskit.algorithms.gradients.base_estimator_gradient.BaseEstimatorGradient")) – Instance of a class used to compute the state gradient.

## Methods Defined Here

### evolution\_gradient

<span id="qiskit.algorithms.time_evolvers.variational.VariationalPrinciple.evolution_gradient" />

`abstract VariationalPrinciple.evolution_gradient(hamiltonian, ansatz, param_values, gradient_params=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/time_evolvers/variational/variational_principles/variational_principle.py "view source code")

Calculates an evolution gradient according to the rules of this variational principle.

**Parameters**

*   **hamiltonian** – Operator used for Variational Quantum Time Evolution.
*   **ansatz** – Quantum state in the form of a parametrized quantum circuit.
*   **param\_values** – Values of parameters to be bound.
*   **gradient\_params** – List of parameters with respect to which gradients should be computed. If `None` given, gradients w\.r.t. all parameters will be computed.

**Returns**

An evolution gradient.

### metric\_tensor

<span id="qiskit.algorithms.time_evolvers.variational.VariationalPrinciple.metric_tensor" />

`VariationalPrinciple.metric_tensor(ansatz, param_values)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/time_evolvers/variational/variational_principles/variational_principle.py "view source code")

Calculates a metric tensor according to the rules of this variational principle.

**Parameters**

*   **ansatz** – Quantum state in the form of a parametrized quantum circuit.
*   **param\_values** – Values of parameters to be bound.

**Returns**

Metric tensor.

**Raises**

[**AlgorithmError**](qiskit.algorithms.AlgorithmError "qiskit.algorithms.AlgorithmError") – If a QFI job fails.

