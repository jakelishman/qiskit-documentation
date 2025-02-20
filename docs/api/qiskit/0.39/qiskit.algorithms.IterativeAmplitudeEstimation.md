---
title: IterativeAmplitudeEstimation
description: API reference for qiskit.algorithms.IterativeAmplitudeEstimation
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.IterativeAmplitudeEstimation
---

# IterativeAmplitudeEstimation

<span id="qiskit.algorithms.IterativeAmplitudeEstimation" />

`IterativeAmplitudeEstimation(epsilon_target, alpha, confint_method='beta', min_ratio=2, quantum_instance=None, sampler=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/algorithms/amplitude_estimators/iae.py "view source code")

Bases: [`qiskit.algorithms.amplitude_estimators.amplitude_estimator.AmplitudeEstimator`](qiskit.algorithms.AmplitudeEstimator "qiskit.algorithms.amplitude_estimators.amplitude_estimator.AmplitudeEstimator")

The Iterative Amplitude Estimation algorithm.

This class implements the Iterative Quantum Amplitude Estimation (IQAE) algorithm, proposed in \[1]. The output of the algorithm is an estimate that, with at least probability $1 - \alpha$, differs by epsilon to the target value, where both alpha and epsilon can be specified.

It differs from the original QAE algorithm proposed by Brassard \[2] in that it does not rely on Quantum Phase Estimation, but is only based on Grover’s algorithm. IQAE iteratively applies carefully selected Grover iterations to find an estimate for the target amplitude.

## References

**\[1]: Grinko, D., Gacon, J., Zoufal, C., & Woerner, S. (2019).**

Iterative Quantum Amplitude Estimation. [arXiv:1912.05559](https://arxiv.org/abs/1912.05559).

**\[2]: Brassard, G., Hoyer, P., Mosca, M., & Tapp, A. (2000).**

Quantum Amplitude Amplification and Estimation. [arXiv:quant-ph/0005055](http://arxiv.org/abs/quant-ph/0005055).

The output of the algorithm is an estimate for the amplitude a, that with at least probability 1 - alpha has an error of epsilon. The number of A operator calls scales linearly in 1/epsilon (up to a logarithmic factor).

**Parameters**

*   **epsilon\_target** (*float*) – Target precision for estimation target a, has values between 0 and 0.5
*   **alpha** (*float*) – Confidence level, the target probability is 1 - alpha, has values between 0 and 1
*   **confint\_method** (*str*) – Statistical method used to estimate the confidence intervals in each iteration, can be ‘chernoff’ for the Chernoff intervals or ‘beta’ for the Clopper-Pearson intervals (default)
*   **min\_ratio** (*float*) – Minimal q-ratio ($K_{i+1} / K_i$) for FindNextK
*   **quantum\_instance** ([*QuantumInstance*](qiskit.utils.QuantumInstance "qiskit.utils.QuantumInstance")  *|*[*Backend*](qiskit.providers.Backend "qiskit.providers.Backend") *| None*) – Pending deprecation: Quantum Instance or Backend
*   **sampler** ([*BaseSampler*](qiskit.primitives.BaseSampler "qiskit.primitives.BaseSampler") *| None*) – A sampler primitive to evaluate the circuits.

**Raises**

*   [**AlgorithmError**](qiskit.algorithms.AlgorithmError "qiskit.algorithms.AlgorithmError") – if the method to compute the confidence intervals is not supported
*   **ValueError** – If the target epsilon is not in (0, 0.5]
*   **ValueError** – If alpha is not in (0, 1)
*   **ValueError** – If confint\_method is not supported

## Methods

### construct\_circuit

<span id="qiskit.algorithms.IterativeAmplitudeEstimation.construct_circuit" />

`IterativeAmplitudeEstimation.construct_circuit(estimation_problem, k=0, measurement=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/algorithms/amplitude_estimators/iae.py "view source code")

Construct the circuit $\mathcal{Q}^k \mathcal{A} |0\rangle$.

The A operator is the unitary specifying the QAE problem and Q the associated Grover operator.

**Parameters**

*   **estimation\_problem** ([`EstimationProblem`](qiskit.algorithms.EstimationProblem "qiskit.algorithms.amplitude_estimators.estimation_problem.EstimationProblem")) – The estimation problem for which to construct the QAE circuit.
*   **k** (`int`) – The power of the Q operator.
*   **measurement** (`bool`) – Boolean flag to indicate if measurements should be included in the circuits.

**Return type**

[`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit")

**Returns**

The circuit implementing $\mathcal{Q}^k \mathcal{A} |0\rangle$.

### estimate

<span id="qiskit.algorithms.IterativeAmplitudeEstimation.estimate" />

`IterativeAmplitudeEstimation.estimate(estimation_problem)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/algorithms/amplitude_estimators/iae.py "view source code")

Run the amplitude estimation algorithm on provided estimation problem.

**Parameters**

**estimation\_problem** ([`EstimationProblem`](qiskit.algorithms.EstimationProblem "qiskit.algorithms.amplitude_estimators.estimation_problem.EstimationProblem")) – The estimation problem.

**Return type**

[IterativeAmplitudeEstimationResult](qiskit.algorithms.IterativeAmplitudeEstimationResult "qiskit.algorithms.IterativeAmplitudeEstimationResult")

**Returns**

An amplitude estimation results object.

**Raises**

*   **ValueError** – A quantum instance or Sampler must be provided.
*   [**AlgorithmError**](qiskit.algorithms.AlgorithmError "qiskit.algorithms.AlgorithmError") – Sampler job run error.

## Attributes

<span id="qiskit.algorithms.IterativeAmplitudeEstimation.epsilon_target" />

### epsilon\_target

Returns the target precision `epsilon_target` of the algorithm.

**Return type**

`float`

**Returns**

The target precision (which is half the width of the confidence interval).

<span id="qiskit.algorithms.IterativeAmplitudeEstimation.quantum_instance" />

### quantum\_instance

Pending deprecation; Get the quantum instance.

**Return type**

[QuantumInstance](qiskit.utils.QuantumInstance "qiskit.utils.QuantumInstance") | None

**Returns**

The quantum instance used to run this algorithm.

<span id="qiskit.algorithms.IterativeAmplitudeEstimation.sampler" />

### sampler

Get the sampler primitive.

**Return type**

[BaseSampler](qiskit.primitives.BaseSampler "qiskit.primitives.BaseSampler") | None

**Returns**

The sampler primitive to evaluate the circuits.

