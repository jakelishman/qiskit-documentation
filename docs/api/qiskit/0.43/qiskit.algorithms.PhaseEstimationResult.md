---
title: PhaseEstimationResult
description: API reference for qiskit.algorithms.PhaseEstimationResult
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.PhaseEstimationResult
---

# PhaseEstimationResult

<span id="qiskit.algorithms.PhaseEstimationResult" />

`PhaseEstimationResult(num_evaluation_qubits, circuit_result, phases)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/algorithms/phase_estimators/phase_estimation_result.py "view source code")

Bases: `PhaseEstimatorResult`

Store and manipulate results from running PhaseEstimation.

This class is instantiated by the `PhaseEstimation` class, not via user code. The `PhaseEstimation` class generates a list of phases and corresponding weights. Upon completion it returns the results as an instance of this class. The main method for accessing the results is filter\_phases.

The canonical phase satisfying the `PhaseEstimator` interface, returned by the attribute phase, is the most likely phase.

**Parameters**

*   **num\_evaluation\_qubits** (*int*) – number of qubits in phase-readout register.
*   **circuit\_result** ([*Result*](qiskit.result.Result "qiskit.result.Result")) – result object returned by method running circuit.
*   **phases** ([*numpy.ndarray*](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.25)") *| dict\[str, float]*) – ndarray or dict of phases and frequencies determined by QPE.

## Methods

<span id="qiskit-algorithms-phaseestimationresult-combine" />

### combine

<span id="qiskit.algorithms.PhaseEstimationResult.combine" />

`PhaseEstimationResult.combine(result)`

Any property from the argument that exists in the receiver is updated. :param result: Argument result with properties to be set.

**Raises**

**TypeError** – Argument is None

<span id="qiskit-algorithms-phaseestimationresult-filter-phases" />

### filter\_phases

<span id="qiskit.algorithms.PhaseEstimationResult.filter_phases" />

`PhaseEstimationResult.filter_phases(cutoff=0.0, as_float=True)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/algorithms/phase_estimators/phase_estimation_result.py "view source code")

Return a filtered dict of phases (keys) and frequencies (values).

Only phases with frequencies (counts) larger than cutoff are included. It is assumed that the run method has been called so that the phases have been computed. When using a noiseless, shot-based simulator to read a single phase that can be represented exactly by num\_evaluation\_qubits, all the weight will be concentrated on a single phase. In all other cases, many, or all, bit strings will have non-zero weight. This method is useful for filtering out these uninteresting bit strings.

**Parameters**

*   **cutoff** (*float*) – Minimum weight of number of counts required to keep a bit string. The default value is 0.0.
*   **as\_float** (*bool*) – If True, returned keys are floats in $[0.0, 1.0)$. If False returned keys are bit strings.

**Returns**

A filtered dict of phases (keys) and frequencies (values).

**Return type**

dict

## Attributes

<span id="qiskit.algorithms.PhaseEstimationResult.circuit_result" />

### circuit\_result

Return the result object returned by running the QPE circuit (on hardware or simulator).

This is useful for inspecting and troubleshooting the QPE algorithm.

<span id="qiskit.algorithms.PhaseEstimationResult.most_likely_phase" />

### most\_likely\_phase

DEPRECATED - Return the most likely phase as a number in $[0.0, 1.0)$.

1.0 corresponds to a phase of $2\pi$. This selects the phase corresponding to the bit string with the highesest probability. This is the most likely phase.

<Admonition title="Deprecated since version 0.18.0" type="danger">
  The property `qiskit.algorithms.phase_estimators.phase_estimation_result.PhaseEstimationResult.most_likely_phase` is deprecated as of qiskit-terra 0.18.0. It will be removed no earlier than 3 months after the release date. Instead, use the property `phase`, which behaves the same.
</Admonition>

<span id="qiskit.algorithms.PhaseEstimationResult.phase" />

### phase

Return the most likely phase as a number in $[0.0, 1.0)$.

1.0 corresponds to a phase of $2\pi$. This selects the phase corresponding to the bit string with the highesest probability. This is the most likely phase.

<span id="qiskit.algorithms.PhaseEstimationResult.phases" />

### phases

Return all phases and their frequencies computed by QPE.

This is an array or dict whose values correspond to weights on bit strings.

