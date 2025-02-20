---
title: RealVariationalPrinciple
description: API reference for qiskit.algorithms.time_evolvers.variational.RealVariationalPrinciple
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.time_evolvers.variational.RealVariationalPrinciple
---

# RealVariationalPrinciple

<span id="qiskit.algorithms.time_evolvers.variational.RealVariationalPrinciple" />

`RealVariationalPrinciple(qgt, gradient)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/algorithms/time_evolvers/variational/variational_principles/real_variational_principle.py "view source code")

Bases: [`VariationalPrinciple`](qiskit.algorithms.time_evolvers.variational.VariationalPrinciple "qiskit.algorithms.time_evolvers.variational.variational_principles.variational_principle.VariationalPrinciple"), `ABC`

Class for a Real Variational Principle. The real variant means that we consider real time dynamics.

**Parameters**

*   **qgt** ([*BaseQGT*](qiskit.algorithms.gradients.BaseQGT "qiskit.algorithms.gradients.BaseQGT")) – Instance of a class used to compute the GQT.
*   **gradient** ([*BaseEstimatorGradient*](qiskit.algorithms.gradients.BaseEstimatorGradient "qiskit.algorithms.gradients.BaseEstimatorGradient")) – Instance of a class used to compute the state gradient.

