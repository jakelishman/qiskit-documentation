---
title: AdaptVQE
description: API reference for qiskit.algorithms.minimum_eigensolvers.AdaptVQE
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.minimum_eigensolvers.AdaptVQE
---

# AdaptVQE

<span id="qiskit.algorithms.minimum_eigensolvers.AdaptVQE" />

`AdaptVQE(solver, *, gradient_threshold=1e-05, eigenvalue_threshold=1e-05, max_iterations=None, threshold=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/algorithms/minimum_eigensolvers/adapt_vqe.py "view source code")

Bases: `VariationalAlgorithm`, [`MinimumEigensolver`](qiskit.algorithms.minimum_eigensolvers.MinimumEigensolver "qiskit.algorithms.minimum_eigensolvers.minimum_eigensolver.MinimumEigensolver")

The Adaptive Variational Quantum Eigensolver algorithm.

[AdaptVQE](https://arxiv.org/abs/1812.11173) is a quantum algorithm which creates a compact ansatz from a set of evolution operators. It iteratively extends the ansatz circuit, by selecting the building block that leads to the largest gradient from a set of candidates. In chemistry, this is usually a list of orbital excitations. Thus, a common choice of ansatz to be used with this algorithm is the Unitary Coupled Cluster ansatz implemented in Qiskit Nature. This results in a wavefunction ansatz which is uniquely adapted to the operator whose minimum eigenvalue is being determined. This class relies on a supplied instance of [`VQE`](qiskit.algorithms.minimum_eigensolvers.VQE "qiskit.algorithms.minimum_eigensolvers.VQE") to find the minimum eigenvalue. The performance of AdaptVQE significantly depends on the minimization routine.

```python
from qiskit.algorithms.minimum_eigensolvers import AdaptVQE, VQE
from qiskit.algorithms.optimizers import SLSQP
from qiskit.primitives import Estimator
from qiskit.circuit.library import EvolvedOperatorAnsatz

# get your Hamiltonian
hamiltonian = ...

# construct your ansatz
ansatz = EvolvedOperatorAnsatz(...)

vqe = VQE(Estimator(), ansatz, SLSQP())

adapt_vqe = AdaptVQE(vqe)

eigenvalue, _ = adapt_vqe.compute_minimum_eigenvalue(hamiltonian)
```

The following attributes can be set via the initializer but can also be read and updated once the AdaptVQE object has been constructed.

<span id="qiskit.algorithms.minimum_eigensolvers.AdaptVQE.solver" />

### solver

a [`VQE`](qiskit.algorithms.minimum_eigensolvers.VQE "qiskit.algorithms.minimum_eigensolvers.VQE") instance used internally to compute the minimum eigenvalues. It is a requirement that the [`ansatz`](qiskit.algorithms.minimum_eigensolvers.VQE#ansatz "qiskit.algorithms.minimum_eigensolvers.VQE.ansatz") of this solver is of type [`EvolvedOperatorAnsatz`](qiskit.circuit.library.EvolvedOperatorAnsatz "qiskit.circuit.library.EvolvedOperatorAnsatz").

<span id="qiskit.algorithms.minimum_eigensolvers.AdaptVQE.gradient_threshold" />

### gradient\_threshold

once all gradients have an absolute value smaller than this threshold, the algorithm has converged and terminates.

<span id="qiskit.algorithms.minimum_eigensolvers.AdaptVQE.eigenvalue_threshold" />

### eigenvalue\_threshold

once the eigenvalue has changed by less than this threshold from one iteration to the next, the algorithm has converged and terminates. When this case occurs, the excitation included in the final iteration did not result in a significant improvement of the eigenvalue and, thus, the results from this iteration are not considered.

<span id="qiskit.algorithms.minimum_eigensolvers.AdaptVQE.max_iterations" />

### max\_iterations

the maximum number of iterations for the adaptive loop. If `None`, the algorithm is not bound in its number of iterations.

<Admonition title="Deprecated since version 0.24.0_pending" type="danger">
  `qiskit.algorithms.minimum_eigensolvers.adapt_vqe.AdaptVQE.__init__()`’s argument `threshold` is pending deprecation as of qiskit-terra 0.24.0. It will be marked deprecated in a future release, and then removed no earlier than 3 months after the release date. Instead, use the argument `gradient_threshold`, which behaves identically.
</Admonition>

**Parameters**

*   **solver** ([*VQE*](qiskit.algorithms.minimum_eigensolvers.VQE "qiskit.algorithms.minimum_eigensolvers.VQE")) – a [`VQE`](qiskit.algorithms.minimum_eigensolvers.VQE "qiskit.algorithms.minimum_eigensolvers.VQE") instance used internally to compute the minimum eigenvalues. It is a requirement that the [`ansatz`](qiskit.algorithms.minimum_eigensolvers.VQE#ansatz "qiskit.algorithms.minimum_eigensolvers.VQE.ansatz") of this solver is of type [`EvolvedOperatorAnsatz`](qiskit.circuit.library.EvolvedOperatorAnsatz "qiskit.circuit.library.EvolvedOperatorAnsatz").
*   **gradient\_threshold** (*float*) – once all gradients have an absolute value smaller than this threshold, the algorithm has converged and terminates.
*   **eigenvalue\_threshold** (*float*) – once the eigenvalue has changed by less than this threshold from one iteration to the next, the algorithm has converged and terminates. When this case occurs, the excitation included in the final iteration did not result in a significant improvement of the eigenvalue and, thus, the results from this iteration are not considered.
*   **max\_iterations** (*int | None*) – the maximum number of iterations for the adaptive loop. If `None`, the algorithm is not bound in its number of iterations.
*   **threshold** (*float | None*) – once all gradients have an absolute value smaller than this threshold, the algorithm has converged and terminates. Defaults to `1e-5`.

## Methods

<span id="qiskit-algorithms-minimum-eigensolvers-adaptvqe-compute-minimum-eigenvalue" />

### compute\_minimum\_eigenvalue

<span id="qiskit.algorithms.minimum_eigensolvers.AdaptVQE.compute_minimum_eigenvalue" />

`AdaptVQE.compute_minimum_eigenvalue(operator, aux_operators=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/algorithms/minimum_eigensolvers/adapt_vqe.py "view source code")

Computes the minimum eigenvalue.

**Parameters**

*   **operator** (*BaseOperator |* [*PauliSumOp*](qiskit.opflow.primitive_ops.PauliSumOp "qiskit.opflow.primitive_ops.PauliSumOp")) – Operator whose minimum eigenvalue we want to find.
*   **aux\_operators** (*ListOrDict\[BaseOperator |* [*PauliSumOp*](qiskit.opflow.primitive_ops.PauliSumOp "qiskit.opflow.primitive_ops.PauliSumOp")*] | None*) – Additional auxiliary operators to evaluate.

**Raises**

*   **TypeError** – If an ansatz other than [`EvolvedOperatorAnsatz`](qiskit.circuit.library.EvolvedOperatorAnsatz "qiskit.circuit.library.EvolvedOperatorAnsatz") is provided.
*   **QiskitError** – If all evaluated gradients lie below the convergence threshold in the first iteration of the algorithm.

**Returns**

An [`AdaptVQEResult`](qiskit.algorithms.minimum_eigensolvers.AdaptVQEResult "qiskit.algorithms.minimum_eigensolvers.AdaptVQEResult") which is a [`VQEResult`](qiskit.algorithms.minimum_eigensolvers.VQEResult "qiskit.algorithms.minimum_eigensolvers.VQEResult") but also but also includes runtime information about the AdaptVQE algorithm like the number of iterations, termination criterion, and the final maximum gradient.

**Return type**

[AdaptVQEResult](qiskit.algorithms.minimum_eigensolvers.AdaptVQEResult "qiskit.algorithms.minimum_eigensolvers.AdaptVQEResult")

<span id="qiskit-algorithms-minimum-eigensolvers-adaptvqe-supports-aux-operators" />

### supports\_aux\_operators

<span id="qiskit.algorithms.minimum_eigensolvers.AdaptVQE.supports_aux_operators" />

`classmethod AdaptVQE.supports_aux_operators()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/algorithms/minimum_eigensolvers/adapt_vqe.py "view source code")

Whether computing the expectation value of auxiliary operators is supported.

If the minimum eigensolver computes an eigenvalue of the main `operator` then it can compute the expectation value of the `aux_operators` for that state. Otherwise they will be ignored.

**Returns**

True if aux\_operator expectations can be evaluated, False otherwise

**Return type**

bool

## Attributes

<span id="qiskit.algorithms.minimum_eigensolvers.AdaptVQE.initial_point" />

### initial\_point

Returns the initial point of the internal [`VQE`](qiskit.algorithms.minimum_eigensolvers.VQE "qiskit.algorithms.minimum_eigensolvers.VQE") solver.

<span id="qiskit.algorithms.minimum_eigensolvers.AdaptVQE.threshold" />

### threshold

The threshold for the gradients.

Once all gradients have an absolute value smaller than this threshold, the algorithm has converged and terminates.

<Admonition title="Deprecated since version 0.24.0_pending" type="danger">
  The property `qiskit.algorithms.minimum_eigensolvers.adapt_vqe.AdaptVQE.threshold` is pending deprecation as of qiskit-terra 0.24.0. It will be marked deprecated in a future release, and then removed no earlier than 3 months after the release date. Instead, use the gradient\_threshold attribute.
</Admonition>

