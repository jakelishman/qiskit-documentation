---
title: MaximumLikelihoodAmplitudeEstimation
description: API reference for qiskit.algorithms.MaximumLikelihoodAmplitudeEstimation
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.MaximumLikelihoodAmplitudeEstimation
---

# MaximumLikelihoodAmplitudeEstimation

<span id="qiskit.algorithms.MaximumLikelihoodAmplitudeEstimation" />

`MaximumLikelihoodAmplitudeEstimation(evaluation_schedule, minimizer=None, quantum_instance=None, sampler=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/algorithms/amplitude_estimators/mlae.py "view source code")

Bases: [`AmplitudeEstimator`](qiskit.algorithms.AmplitudeEstimator "qiskit.algorithms.amplitude_estimators.amplitude_estimator.AmplitudeEstimator")

The Maximum Likelihood Amplitude Estimation algorithm.

This class implements the quantum amplitude estimation (QAE) algorithm without phase estimation, as introduced in \[1]. In comparison to the original QAE algorithm \[2], this implementation relies solely on different powers of the Grover operator and does not require additional evaluation qubits. Finally, the estimate is determined via a maximum likelihood estimation, which is why this class in named `MaximumLikelihoodAmplitudeEstimation`.

## References

**\[1]: Suzuki, Y., Uno, S., Raymond, R., Tanaka, T., Onodera, T., & Yamamoto, N. (2019).**

Amplitude Estimation without Phase Estimation. [arXiv:1904.10246](https://arxiv.org/abs/1904.10246).

**\[2]: Brassard, G., Hoyer, P., Mosca, M., & Tapp, A. (2000).**

Quantum Amplitude Amplification and Estimation. [arXiv:quant-ph/0005055](http://arxiv.org/abs/quant-ph/0005055).

<Admonition title="Deprecated since version 0.24.0" type="danger">
  `qiskit.algorithms.amplitude_estimators.mlae.MaximumLikelihoodAmplitudeEstimation.__init__()`’s argument `quantum_instance` is deprecated as of qiskit-terra 0.24.0. It will be removed no earlier than 3 months after the release date. Instead, use the `sampler` argument. See [https://qisk.it/algo\_migration](https://qisk.it/algo_migration) for a migration guide.
</Admonition>

**Parameters**

*   **evaluation\_schedule** (*list\[int] | int*) – If a list, the powers applied to the Grover operator. The list element must be non-negative. If a non-negative integer, an exponential schedule is used where the highest power is 2 to the integer minus 1: \[id, Q^2^0, …, Q^2^(evaluation\_schedule-1)].
*   **minimizer** (*MINIMIZER | None*) – A minimizer used to find the minimum of the likelihood function. Defaults to a brute search where the number of evaluation points is determined according to `evaluation_schedule`. The minimizer takes a function as first argument and a list of (float, float) tuples (as bounds) as second argument and returns a single float which is the found minimum.
*   **quantum\_instance** ([*QuantumInstance*](qiskit.utils.QuantumInstance "qiskit.utils.QuantumInstance")  *|*[*Backend*](qiskit.providers.Backend "qiskit.providers.Backend") *| None*) – Deprecated: Quantum Instance or Backend
*   **sampler** ([*BaseSampler*](qiskit.primitives.BaseSampler "qiskit.primitives.BaseSampler") *| None*) – A sampler primitive to evaluate the circuits.

**Raises**

**ValueError** – If the number of oracle circuits is smaller than 1.

## Methods

<span id="qiskit-algorithms-maximumlikelihoodamplitudeestimation-compute-confidence-interval" />

### compute\_confidence\_interval

<span id="qiskit.algorithms.MaximumLikelihoodAmplitudeEstimation.compute_confidence_interval" />

`static MaximumLikelihoodAmplitudeEstimation.compute_confidence_interval(result, alpha, kind='fisher', apply_post_processing=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/algorithms/amplitude_estimators/mlae.py "view source code")

Compute the alpha confidence interval using the method kind.

The confidence level is (1 - alpha) and supported kinds are ‘fisher’, ‘likelihood\_ratio’ and ‘observed\_fisher’ with shorthand notations ‘fi’, ‘lr’ and ‘oi’, respectively.

**Parameters**

*   **result** ([*MaximumLikelihoodAmplitudeEstimationResult*](qiskit.algorithms.MaximumLikelihoodAmplitudeEstimationResult "qiskit.algorithms.MaximumLikelihoodAmplitudeEstimationResult")) – A maximum likelihood amplitude estimation result.
*   **alpha** (*float*) – The confidence level.
*   **kind** (*str*) – The method to compute the confidence interval. Defaults to ‘fisher’, which computes the theoretical Fisher information.
*   **apply\_post\_processing** (*bool*) – If True, apply post-processing to the confidence interval.

**Returns**

The specified confidence interval.

**Raises**

*   [**AlgorithmError**](qiskit.algorithms.AlgorithmError "qiskit.algorithms.AlgorithmError") – If run() hasn’t been called yet.
*   **NotImplementedError** – If the method kind is not supported.

**Return type**

tuple\[float, float]

<span id="qiskit-algorithms-maximumlikelihoodamplitudeestimation-compute-mle" />

### compute\_mle

<span id="qiskit.algorithms.MaximumLikelihoodAmplitudeEstimation.compute_mle" />

`MaximumLikelihoodAmplitudeEstimation.compute_mle(circuit_results, estimation_problem, num_state_qubits=None, return_counts=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/algorithms/amplitude_estimators/mlae.py "view source code")

Compute the MLE via a grid-search.

This is a stable approach if sufficient gridpoints are used.

**Parameters**

*   **circuit\_results** (*list\[dict\[str, int] | np.ndarray]*) – A list of circuit outcomes. Can be counts or statevectors.
*   **estimation\_problem** ([*EstimationProblem*](qiskit.algorithms.EstimationProblem "qiskit.algorithms.EstimationProblem")) – The estimation problem containing the evaluation schedule and the number of likelihood function evaluations used to find the minimum.
*   **num\_state\_qubits** (*int | None*) – The number of state qubits, required for statevector simulations.
*   **return\_counts** (*bool*) – If True, returns the good counts.

**Returns**

The MLE for the provided result object.

**Return type**

float | tuple\[float, list\[float]]

<span id="qiskit-algorithms-maximumlikelihoodamplitudeestimation-construct-circuits" />

### construct\_circuits

<span id="qiskit.algorithms.MaximumLikelihoodAmplitudeEstimation.construct_circuits" />

`MaximumLikelihoodAmplitudeEstimation.construct_circuits(estimation_problem, measurement=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/algorithms/amplitude_estimators/mlae.py "view source code")

Construct the Amplitude Estimation w/o QPE quantum circuits.

**Parameters**

*   **estimation\_problem** ([*EstimationProblem*](qiskit.algorithms.EstimationProblem "qiskit.algorithms.EstimationProblem")) – The estimation problem for which to construct the QAE circuit.
*   **measurement** (*bool*) – Boolean flag to indicate if measurement should be included in the circuits.

**Returns**

A list with the QuantumCircuit objects for the algorithm.

**Return type**

list\[[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")]

<span id="qiskit-algorithms-maximumlikelihoodamplitudeestimation-estimate" />

### estimate

<span id="qiskit.algorithms.MaximumLikelihoodAmplitudeEstimation.estimate" />

`MaximumLikelihoodAmplitudeEstimation.estimate(estimation_problem)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/algorithms/amplitude_estimators/mlae.py "view source code")

Run the amplitude estimation algorithm on provided estimation problem.

**Parameters**

**estimation\_problem** ([*EstimationProblem*](qiskit.algorithms.EstimationProblem "qiskit.algorithms.amplitude_estimators.estimation_problem.EstimationProblem")) – The estimation problem.

**Returns**

An amplitude estimation results object.

**Raises**

*   **ValueError** – A quantum instance or Sampler must be provided.
*   [**AlgorithmError**](qiskit.algorithms.AlgorithmError "qiskit.algorithms.AlgorithmError") – If state\_preparation is not set in estimation\_problem.
*   [**AlgorithmError**](qiskit.algorithms.AlgorithmError "qiskit.algorithms.AlgorithmError") – Sampler job run error

**Return type**

[MaximumLikelihoodAmplitudeEstimationResult](qiskit.algorithms.MaximumLikelihoodAmplitudeEstimationResult "qiskit.algorithms.MaximumLikelihoodAmplitudeEstimationResult")

## Attributes

<span id="qiskit.algorithms.MaximumLikelihoodAmplitudeEstimation.quantum_instance" />

### quantum\_instance

Deprecated. Get the quantum instance.

<Admonition title="Deprecated since version 0.24.0" type="danger">
  The property `qiskit.algorithms.amplitude_estimators.mlae.MaximumLikelihoodAmplitudeEstimation.quantum_instance` is deprecated as of qiskit-terra 0.24.0. It will be removed no earlier than 3 months after the release date. See [https://qisk.it/algo\_migration](https://qisk.it/algo_migration) for a migration guide.
</Admonition>

**Returns**

The quantum instance used to run this algorithm.

<span id="qiskit.algorithms.MaximumLikelihoodAmplitudeEstimation.sampler" />

### sampler

Get the sampler primitive.

**Returns**

The sampler primitive to evaluate the circuits.

