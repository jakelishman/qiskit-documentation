---
title: TrotterQRTE
description: API reference for qiskit.algorithms.time_evolvers.trotterization.TrotterQRTE
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.time_evolvers.trotterization.TrotterQRTE
---

# TrotterQRTE

<span id="qiskit.algorithms.time_evolvers.trotterization.TrotterQRTE" />

`TrotterQRTE(product_formula=None, estimator=None, num_timesteps=1)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/algorithms/time_evolvers/trotterization/trotter_qrte.py "view source code")

Bases: [`RealTimeEvolver`](qiskit.algorithms.RealTimeEvolver "qiskit.algorithms.time_evolvers.real_time_evolver.RealTimeEvolver")

Quantum Real Time Evolution using Trotterization. Type of Trotterization is defined by a `ProductFormula` provided.

## Examples

```python
from qiskit.opflow import PauliSumOp
from qiskit.quantum_info import Pauli, SparsePauliOp
from qiskit import QuantumCircuit
from qiskit.algorithms import TimeEvolutionProblem
from qiskit.algorithms.time_evolvers import TrotterQRTE
from qiskit.primitives import Estimator

operator = PauliSumOp(SparsePauliOp([Pauli("X"), Pauli("Z")]))
initial_state = QuantumCircuit(1)
time = 1
evolution_problem = TimeEvolutionProblem(operator, time, initial_state)
# LieTrotter with 1 rep
estimator = Estimator()
trotter_qrte = TrotterQRTE(estimator=estimator)
evolved_state = trotter_qrte.evolve(evolution_problem).evolved_state
```

**Parameters**

*   **product\_formula** ([*ProductFormula*](qiskit.synthesis.ProductFormula "qiskit.synthesis.ProductFormula") *| None*) – A Lie-Trotter-Suzuki product formula. If `None` provided, the Lie-Trotter first order product formula with a single repetition is used. `reps` should be 1 to obtain a number of time-steps equal to `num_timesteps` and an evaluation of [`TimeEvolutionProblem.aux_operators`](qiskit.algorithms.TimeEvolutionProblem#aux_operators "qiskit.algorithms.TimeEvolutionProblem.aux_operators") at every time-step. If `reps` is larger than 1, the true number of time-steps will be `num_timesteps * reps`.
*   **num\_timesteps** (*int*) – The number of time-steps the full evolution time is devided into (repetitions of `product_formula`)
*   **estimator** ([*BaseEstimator*](qiskit.primitives.BaseEstimator "qiskit.primitives.BaseEstimator") *| None*) – An estimator primitive used for calculating expectation values of `TimeEvolutionProblem.aux_operators`.

## Methods

<span id="qiskit-algorithms-time-evolvers-trotterization-trotterqrte-evolve" />

### evolve

<span id="qiskit.algorithms.time_evolvers.trotterization.TrotterQRTE.evolve" />

`TrotterQRTE.evolve(evolution_problem)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/algorithms/time_evolvers/trotterization/trotter_qrte.py "view source code")

Evolves a quantum state for a given time using the Trotterization method based on a product formula provided. The result is provided in the form of a quantum circuit. If auxiliary operators are included in the `evolution_problem`, they are evaluated on the `init_state` and on the evolved state at every step (`num_timesteps` times) using an estimator primitive provided.

**Parameters**

**evolution\_problem** ([*TimeEvolutionProblem*](qiskit.algorithms.TimeEvolutionProblem "qiskit.algorithms.time_evolvers.time_evolution_problem.TimeEvolutionProblem")) – Instance defining evolution problem. For the included Hamiltonian, `Pauli` or `PauliSumOp` are supported by TrotterQRTE.

**Returns**

Evolution result that includes an evolved state as a quantum circuit and, optionally, auxiliary operators evaluated for a resulting state on an estimator primitive.

**Raises**

*   **ValueError** – If `t_param` is not set to `None` in the `TimeEvolutionProblem` (feature not currently supported).
*   **ValueError** – If `aux_operators` provided in the time evolution problem but no estimator provided to the algorithm.
*   **ValueError** – If the `initial_state` is not provided in the `TimeEvolutionProblem`.
*   **ValueError** – If an unsupported Hamiltonian type is provided.

**Return type**

[*TimeEvolutionResult*](qiskit.algorithms.TimeEvolutionResult "qiskit.algorithms.time_evolvers.time_evolution_result.TimeEvolutionResult")

<span id="qiskit-algorithms-time-evolvers-trotterization-trotterqrte-supports-aux-operators" />

### supports\_aux\_operators

<span id="qiskit.algorithms.time_evolvers.trotterization.TrotterQRTE.supports_aux_operators" />

`classmethod TrotterQRTE.supports_aux_operators()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/algorithms/time_evolvers/trotterization/trotter_qrte.py "view source code")

Whether computing the expectation value of auxiliary operators is supported.

**Returns**

`True` if `aux_operators` expectations in the `TimeEvolutionProblem` can be evaluated, `False` otherwise.

**Return type**

bool

## Attributes

<span id="qiskit.algorithms.time_evolvers.trotterization.TrotterQRTE.estimator" />

### estimator

Returns an estimator.

<span id="qiskit.algorithms.time_evolvers.trotterization.TrotterQRTE.num_timesteps" />

### num\_timesteps

Returns the number of timesteps.

<span id="qiskit.algorithms.time_evolvers.trotterization.TrotterQRTE.product_formula" />

### product\_formula

Returns a product formula.

