---
title: FasterAmplitudeEstimation
description: API reference for qiskit.algorithms.FasterAmplitudeEstimation
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.FasterAmplitudeEstimation
---

# FasterAmplitudeEstimation

<span id="qiskit.algorithms.FasterAmplitudeEstimation" />

`FasterAmplitudeEstimation(delta, maxiter, rescale=True, quantum_instance=None, sampler=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/amplitude_estimators/fae.py "view source code")

Bases: [`qiskit.algorithms.amplitude_estimators.amplitude_estimator.AmplitudeEstimator`](qiskit.algorithms.AmplitudeEstimator "qiskit.algorithms.amplitude_estimators.amplitude_estimator.AmplitudeEstimator")

The Faster Amplitude Estimation algorithm.

The Faster Amplitude Estimation (FAE) \[1] algorithm is a variant of Quantum Amplitude Estimation (QAE), where the Quantum Phase Estimation (QPE) by an iterative Grover search, similar to \[2].

Due to the iterative version of the QPE, this algorithm does not require any additional qubits, as the originally proposed QAE \[3] and thus the resulting circuits are less complex.

## References

**\[1]: K. Nakaji. Faster Amplitude Estimation, 2020;**

[arXiv:2002.02417](https://arxiv.org/pdf/2003.02417.pdf)

**\[2]: D. Grinko et al. Iterative Amplitude Estimation, 2019;**

[arXiv:1912.05559](http://arxiv.org/abs/1912.05559)

**\[3]: G. Brassard et al. Quantum Amplitude Amplification and Estimation, 2000;**

[arXiv:quant-ph/0005055](http://arxiv.org/abs/quant-ph/0005055)

**Parameters**

*   **delta** (*float*) – The probability that the true value is outside of the final confidence interval.
*   **maxiter** (*int*) – The number of iterations, the maximal power of Q is 2 \*\* (maxiter - 1).
*   **rescale** (*bool*) – Whether to rescale the problem passed to estimate.
*   **quantum\_instance** ([*QuantumInstance*](qiskit.utils.QuantumInstance "qiskit.utils.QuantumInstance")  *|*[*Backend*](qiskit.providers.Backend "qiskit.providers.Backend") *| None*) – Pending deprecation: The quantum instance or backend to run the circuits.
*   **sampler** ([*BaseSampler*](qiskit.primitives.BaseSampler "qiskit.primitives.BaseSampler") *| None*) – A sampler primitive to evaluate the circuits.

<Admonition title="Note" type="note">
  This algorithm overwrites the number of shots set in the `quantum_instance` argument, but will reset them to the initial number after running.
</Admonition>

## Methods

### construct\_circuit

<span id="qiskit.algorithms.FasterAmplitudeEstimation.construct_circuit" />

`FasterAmplitudeEstimation.construct_circuit(estimation_problem, k, measurement=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/amplitude_estimators/fae.py "view source code")

Construct the circuit $Q^k X |0\rangle>$.

The A operator is the unitary specifying the QAE problem and Q the associated Grover operator.

**Parameters**

*   **estimation\_problem** – The estimation problem for which to construct the circuit.
*   **k** – The power of the Q operator.
*   **measurement** – Boolean flag to indicate if measurements should be included in the circuits.

**Returns**

The circuit $Q^k X |0\rangle$.

### estimate

<span id="qiskit.algorithms.FasterAmplitudeEstimation.estimate" />

`FasterAmplitudeEstimation.estimate(estimation_problem)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/amplitude_estimators/fae.py "view source code")

Run the amplitude estimation algorithm on provided estimation problem.

**Parameters**

**estimation\_problem** ([`EstimationProblem`](qiskit.algorithms.EstimationProblem "qiskit.algorithms.amplitude_estimators.estimation_problem.EstimationProblem")) – The estimation problem.

**Return type**

[FasterAmplitudeEstimationResult](qiskit.algorithms.FasterAmplitudeEstimationResult "qiskit.algorithms.FasterAmplitudeEstimationResult")

**Returns**

An amplitude estimation results object.

**Raises**

*   **ValueError** – A quantum instance or Sampler must be provided.
*   [**AlgorithmError**](qiskit.algorithms.AlgorithmError "qiskit.algorithms.AlgorithmError") – Sampler run error.

## Attributes

<span id="qiskit.algorithms.FasterAmplitudeEstimation.quantum_instance" />

### quantum\_instance

Pending deprecation; Get the quantum instance.

**Return type**

[QuantumInstance](qiskit.utils.QuantumInstance "qiskit.utils.QuantumInstance") | None

**Returns**

The quantum instance used to run this algorithm.

<span id="qiskit.algorithms.FasterAmplitudeEstimation.sampler" />

### sampler

Get the sampler primitive.

**Return type**

[BaseSampler](qiskit.primitives.BaseSampler "qiskit.primitives.BaseSampler") | None

**Returns**

The sampler primitive to evaluate the circuits.

