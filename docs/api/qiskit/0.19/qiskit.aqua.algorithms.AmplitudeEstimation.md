---
title: AmplitudeEstimation
description: API reference for qiskit.aqua.algorithms.AmplitudeEstimation
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.algorithms.AmplitudeEstimation
---

# AmplitudeEstimation

<span id="qiskit.aqua.algorithms.AmplitudeEstimation" />

`AmplitudeEstimation(num_eval_qubits, a_factory=None, q_factory=None, i_objective=None, iqft=None, quantum_instance=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/amplitude_estimators/ae.py "view source code")

The Quantum Phase Estimation-based Amplitude Estimation algorithm.

This class implements the original Quantum Amplitude Estimation (QAE) algorithm, introduced by [https://arxiv.org/abs/quant-ph/0005055](https://arxiv.org/abs/quant-ph/0005055). This (original) version uses quantum phase estimation along with a set of m ancilla qubits to find an estimate, that is restricted to the grid

> \{sin^2(pi y / 2^m) : y = 0, …, 2^\{m-1}}.

Using a maximum likelihood post processing, this grid constraint can be circumvented. This improved estimator is implemented as well, see [https://arxiv.org/abs/1912.05559](https://arxiv.org/abs/1912.05559) Appendix A for more detail.

**Parameters**

*   **num\_eval\_qubits** (`int`) – Number of evaluation qubits, has a min. value of 1.
*   **a\_factory** (`Optional`\[[`CircuitFactory`](qiskit.aqua.utils.CircuitFactory "qiskit.aqua.utils.circuit_factory.CircuitFactory")]) – The CircuitFactory subclass object representing the problem unitary.
*   **q\_factory** (`Optional`\[[`CircuitFactory`](qiskit.aqua.utils.CircuitFactory "qiskit.aqua.utils.circuit_factory.CircuitFactory")]) – The CircuitFactory subclass object representing an amplitude estimation sample (based on a\_factory).
*   **i\_objective** (`Optional`\[`int`]) – The index of the objective qubit, i.e. the qubit marking ‘good’ solutions with the state |1> and ‘bad’ solutions with the state |0>.
*   **iqft** (`Union`\[[`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit"), [`IQFT`](qiskit.aqua.components.iqfts.IQFT "qiskit.aqua.components.iqfts.iqft.IQFT"), `None`]) – The Inverse Quantum Fourier Transform component, defaults to using a standard IQFT when None
*   **quantum\_instance** (`Union`\[[`QuantumInstance`](qiskit.aqua.QuantumInstance "qiskit.aqua.quantum_instance.QuantumInstance"), [`BaseBackend`](qiskit.providers.BaseBackend "qiskit.providers.basebackend.BaseBackend"), `None`]) – Quantum Instance or Backend

## Attributes

### a\_factory

Get the A operator encoding the amplitude a that’s approximated, i.e.

> A |0>\_n |0> = sqrt\{1 - a} |psi\_0>\_n |0> + sqrt\{a} |psi\_1>\_n |1>

see the original Brassard paper ([https://arxiv.org/abs/quant-ph/0005055](https://arxiv.org/abs/quant-ph/0005055)) for more detail.

**Returns**

the A operator as CircuitFactory

**Return type**

[CircuitFactory](qiskit.aqua.utils.CircuitFactory "qiskit.aqua.utils.CircuitFactory")

### backend

<span id="qiskit.aqua.algorithms.AmplitudeEstimation.backend" />

`qiskit.providers.basebackend.BaseBackend`

Returns backend.

**Return type**

[`BaseBackend`](qiskit.providers.BaseBackend "qiskit.providers.basebackend.BaseBackend")

### i\_objective

Get the index of the objective qubit. The objective qubit marks the |psi\_0> state (called ‘bad states’ in [https://arxiv.org/abs/quant-ph/0005055](https://arxiv.org/abs/quant-ph/0005055)) with |0> and |psi\_1> (‘good’ states) with |1>. If the A operator performs the mapping

> A |0>\_n |0> = sqrt\{1 - a} |psi\_0>\_n |0> + sqrt\{a} |psi\_1>\_n |1>

then, the objective qubit is the last one (which is either |0> or |1>).

If the objective qubit (i\_objective) is not set, we check if the Q operator (q\_factory) is set and return the index specified there. If the q\_factory is not defined, the index equals the number of qubits of the A operator (a\_factory) minus one. If also the a\_factory is not set, return None.

**Returns**

the index of the objective qubit

**Return type**

int

### q\_factory

Get the Q operator, or Grover-operator for the Amplitude Estimation algorithm, i.e.

> Q = -A S\_0 A^\{-1} S\_psi0,

where S\_0 reflects about the |0>\_n state and S\_psi0 reflects about |psi\_0>\_n. See [https://arxiv.org/abs/quant-ph/0005055](https://arxiv.org/abs/quant-ph/0005055) for more detail.

If the Q operator is not set, we try to build it from the A operator. If neither the A operator is set, None is returned.

**Returns**

returns the current Q factory of the algorithm

**Return type**

QFactory

### quantum\_instance

<span id="qiskit.aqua.algorithms.AmplitudeEstimation.quantum_instance" />

`Union[None, qiskit.aqua.quantum_instance.QuantumInstance]`

Returns quantum instance.

**Return type**

`Optional`\[[`QuantumInstance`](qiskit.aqua.QuantumInstance "qiskit.aqua.quantum_instance.QuantumInstance")]

### random

Return a numpy random.

## Methods

### confidence\_interval

<span id="qiskit.aqua.algorithms.AmplitudeEstimation.confidence_interval" />

`AmplitudeEstimation.confidence_interval(alpha, kind='likelihood_ratio')`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/amplitude_estimators/ae.py "view source code")

Compute the (1 - alpha) confidence interval.

**Parameters**

*   **alpha** (`float`) – Confidence level: compute the (1 - alpha) confidence interval.
*   **kind** (`str`) – The method to compute the confidence interval, can be ‘fisher’, ‘observed\_fisher’ or ‘likelihood\_ratio’ (default)

**Return type**

`List`\[`float`]

**Returns**

The (1 - alpha) confidence interval of the specified kind.

**Raises**

*   [**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – If ‘mle’ is not in self.\_ret.keys() (i.e. run was not called yet).
*   **NotImplementedError** – If the confidence interval method kind is not implemented.

### construct\_circuit

<span id="qiskit.aqua.algorithms.AmplitudeEstimation.construct_circuit" />

`AmplitudeEstimation.construct_circuit(measurement=False)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/amplitude_estimators/ae.py "view source code")

Construct the Amplitude Estimation quantum circuit.

**Parameters**

**measurement** (`bool`) – Boolean flag to indicate if measurements should be included in the circuit.

**Return type**

[`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit")

**Returns**

The QuantumCircuit object for the constructed circuit.

### run

<span id="qiskit.aqua.algorithms.AmplitudeEstimation.run" />

`AmplitudeEstimation.run(quantum_instance=None, **kwargs)`

Execute the algorithm with selected backend.

**Parameters**

*   **quantum\_instance** (`Union`\[[`QuantumInstance`](qiskit.aqua.QuantumInstance "qiskit.aqua.quantum_instance.QuantumInstance"), [`BaseBackend`](qiskit.providers.BaseBackend "qiskit.providers.basebackend.BaseBackend"), `None`]) – the experimental setting.
*   **kwargs** (*dict*) – kwargs

**Returns**

results of an algorithm.

**Return type**

dict

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – If a quantum instance or backend has not been provided

### set\_backend

<span id="qiskit.aqua.algorithms.AmplitudeEstimation.set_backend" />

`AmplitudeEstimation.set_backend(backend, **kwargs)`

Sets backend with configuration.

**Return type**

`None`

