---
title: IterativePhaseEstimation
description: API reference for qiskit.algorithms.IterativePhaseEstimation
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.IterativePhaseEstimation
---

# IterativePhaseEstimation

<span id="qiskit.algorithms.IterativePhaseEstimation" />

`IterativePhaseEstimation(num_iterations, quantum_instance=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/algorithms/phase_estimators/ipe.py "view source code")

Bases: `qiskit.algorithms.phase_estimators.phase_estimator.PhaseEstimator`

Run the Iterative quantum phase estimation (QPE) algorithm.

Given a unitary circuit and a circuit preparing an eigenstate, return the phase of the eigenvalue as a number in $[0,1)$ using the iterative phase estimation algorithm.

**\[1]: Dobsicek et al. (2006), Arbitrary accuracy iterative phase estimation algorithm as a two**

qubit benchmark, [arxiv/quant-ph/0610214](https://arxiv.org/abs/quant-ph/0610214)

**Parameters**

*   **num\_iterations** (`int`) – The number of iterations (rounds) of the phase estimation to run.
*   **quantum\_instance** (`Union`\[`Backend`, `BaseBackend`, `QuantumInstance`, `None`]) – The quantum instance on which the circuit will be run.

**Raises**

**ValueError** – if num\_iterations is not greater than zero.

## Methods

### construct\_circuit

<span id="qiskit.algorithms.IterativePhaseEstimation.construct_circuit" />

`IterativePhaseEstimation.construct_circuit(unitary, state_preparation, k, omega=0, measurement=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/algorithms/phase_estimators/ipe.py "view source code")

Construct the kth iteration Quantum Phase Estimation circuit.

For details of parameters, see Fig. 2 in [https://arxiv.org/pdf/quant-ph/0610214.pdf](https://arxiv.org/pdf/quant-ph/0610214.pdf).

**Parameters**

*   **unitary** (`QuantumCircuit`) – The circuit representing the unitary operator whose eigenvalue (via phase) will be measured.
*   **state\_preparation** (`QuantumCircuit`) – The circuit that prepares the state whose eigenphase will be measured. If this parameter is omitted, no preparation circuit will be run and input state will be the all-zero state in the computational basis.
*   **k** (`int`) – the iteration idx.
*   **omega** (`float`) – the feedback angle.
*   **measurement** (`bool`) – Boolean flag to indicate if measurement should be included in the circuit.

**Returns**

the quantum circuit per iteration

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### estimate

<span id="qiskit.algorithms.IterativePhaseEstimation.estimate" />

`IterativePhaseEstimation.estimate(unitary, state_preparation)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/algorithms/phase_estimators/ipe.py "view source code")

Estimate the eigenphase of the input unitary and initial-state pair.

**Parameters**

*   **unitary** (`QuantumCircuit`) – The circuit representing the unitary operator whose eigenvalue (via phase) will be measured.
*   **state\_preparation** (`QuantumCircuit`) – The circuit that prepares the state whose eigenphase will be measured. If this parameter is omitted, no preparation circuit will be run and input state will be the all-zero state in the computational basis.

**Return type**

`IterativePhaseEstimationResult`

**Returns**

Estimated phase in an IterativePhaseEstimationResult object.

