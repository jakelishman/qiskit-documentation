---
title: EvolutionResult
description: API reference for qiskit.algorithms.EvolutionResult
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.EvolutionResult
---

# EvolutionResult

<span id="qiskit.algorithms.EvolutionResult" />

`EvolutionResult(evolved_state, aux_ops_evaluated=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/evolvers/evolution_result.py "view source code")

Bases: `qiskit.algorithms.algorithm_result.AlgorithmResult`

Pending deprecation: Class for holding evolution result.

The EvolutionResult class has been superseded by the `qiskit.algorithms.time_evolvers.TimeEvolutionResult` class. This class will be deprecated in a future release and subsequently removed after that.

**Parameters**

*   **evolved\_state** (`Union`\[[`StateFn`](qiskit.opflow.state_fns.StateFn "qiskit.opflow.state_fns.state_fn.StateFn"), [`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit"), [`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")]) – An evolved quantum state.
*   **aux\_ops\_evaluated** (`Union`\[`List`\[`Optional`\[`Tuple`\[`complex`, `complex`]]], `Dict`\[`str`, `Tuple`\[`complex`, `complex`]], `None`]) – Optional list of observables for which expected values on an evolved state are calculated. These values are in fact tuples formatted as (mean, standard deviation).

## Methods

### combine

<span id="qiskit.algorithms.EvolutionResult.combine" />

`EvolutionResult.combine(result)`

Any property from the argument that exists in the receiver is updated. :type result: `AlgorithmResult` :param result: Argument result with properties to be set.

**Raises**

**TypeError** – Argument is None

**Return type**

`None`

