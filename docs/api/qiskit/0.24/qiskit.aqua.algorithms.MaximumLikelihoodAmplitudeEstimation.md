---
title: MaximumLikelihoodAmplitudeEstimation
description: API reference for qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation
---

<span id="qiskit-aqua-algorithms-maximumlikelihoodamplitudeestimation" />

# qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation

<span id="qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation" />

`MaximumLikelihoodAmplitudeEstimation(num_oracle_circuits, state_preparation=None, grover_operator=None, objective_qubits=None, post_processing=None, a_factory=None, q_factory=None, i_objective=None, likelihood_evals=None, quantum_instance=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.8/qiskit/aqua/algorithms/amplitude_estimators/mlae.py "view source code")

The Maximum Likelihood Amplitude Estimation algorithm.

This class implements the quantum amplitude estimation (QAE) algorithm without phase estimation, as introduced in \[1]. In comparison to the original QAE algorithm \[2], this implementation relies solely on different powers of the Grover operator and does not require additional evaluation qubits. Finally, the estimate is determined via a maximum likelihood estimation, which is why this class in named `MaximumLikelihoodAmplitudeEstimation`.

## References

**\[1]: Suzuki, Y., Uno, S., Raymond, R., Tanaka, T., Onodera, T., & Yamamoto, N. (2019).**

Amplitude Estimation without Phase Estimation. [arXiv:1904.10246](https://arxiv.org/abs/1904.10246).

**\[2]: Brassard, G., Hoyer, P., Mosca, M., & Tapp, A. (2000).**

Quantum Amplitude Amplification and Estimation. [arXiv:quant-ph/0005055](http://arxiv.org/abs/quant-ph/0005055).

**Parameters**

*   **num\_oracle\_circuits** (`int`) – The number of circuits applying different powers of the Grover oracle Q. The (num\_oracle\_circuits + 1) executed circuits will be \[id, Q^2^0, …, Q^2^\{num\_oracle\_circuits-1}] A |0>, where A is the problem unitary encoded in the argument a\_factory. Has a minimum value of 1.
*   **state\_preparation** (`Union`\[`QuantumCircuit`, `CircuitFactory`, `None`]) – A circuit preparing the input state, referred to as $\mathcal{A}$.
*   **grover\_operator** (`Union`\[`QuantumCircuit`, `CircuitFactory`, `None`]) – The Grover operator $\mathcal{Q}$ used as unitary in the phase estimation circuit.
*   **objective\_qubits** (`Optional`\[`List`\[`int`]]) – A list of qubit indices. A measurement outcome is classified as ‘good’ state if all objective qubits are in state $|1\rangle$, otherwise it is classified as ‘bad’.
*   **post\_processing** (`Optional`\[`Callable`\[\[`float`], `float`]]) – A mapping applied to the estimate of $0 \leq a \leq 1$, usually used to map the estimate to a target interval.
*   **a\_factory** (`Optional`\[`CircuitFactory`]) – The CircuitFactory subclass object representing the problem unitary.
*   **q\_factory** (`Optional`\[`CircuitFactory`]) – The CircuitFactory subclass object representing. an amplitude estimation sample (based on a\_factory)
*   **i\_objective** (`Optional`\[`int`]) – The index of the objective qubit, i.e. the qubit marking ‘good’ solutions with the state |1> and ‘bad’ solutions with the state |0>
*   **likelihood\_evals** (`Optional`\[`int`]) – The number of gridpoints for the maximum search of the likelihood function
*   **quantum\_instance** (`Union`\[`QuantumInstance`, `Backend`, `BaseBackend`, `None`]) – Quantum Instance or Backend

### \_\_init\_\_

<span id="qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.__init__" />

`__init__(num_oracle_circuits, state_preparation=None, grover_operator=None, objective_qubits=None, post_processing=None, a_factory=None, q_factory=None, i_objective=None, likelihood_evals=None, quantum_instance=None)`

**Parameters**

*   **num\_oracle\_circuits** (`int`) – The number of circuits applying different powers of the Grover oracle Q. The (num\_oracle\_circuits + 1) executed circuits will be \[id, Q^2^0, …, Q^2^\{num\_oracle\_circuits-1}] A |0>, where A is the problem unitary encoded in the argument a\_factory. Has a minimum value of 1.
*   **state\_preparation** (`Union`\[`QuantumCircuit`, `CircuitFactory`, `None`]) – A circuit preparing the input state, referred to as $\mathcal{A}$.
*   **grover\_operator** (`Union`\[`QuantumCircuit`, `CircuitFactory`, `None`]) – The Grover operator $\mathcal{Q}$ used as unitary in the phase estimation circuit.
*   **objective\_qubits** (`Optional`\[`List`\[`int`]]) – A list of qubit indices. A measurement outcome is classified as ‘good’ state if all objective qubits are in state $|1\rangle$, otherwise it is classified as ‘bad’.
*   **post\_processing** (`Optional`\[`Callable`\[\[`float`], `float`]]) – A mapping applied to the estimate of $0 \leq a \leq 1$, usually used to map the estimate to a target interval.
*   **a\_factory** (`Optional`\[`CircuitFactory`]) – The CircuitFactory subclass object representing the problem unitary.
*   **q\_factory** (`Optional`\[`CircuitFactory`]) – The CircuitFactory subclass object representing. an amplitude estimation sample (based on a\_factory)
*   **i\_objective** (`Optional`\[`int`]) – The index of the objective qubit, i.e. the qubit marking ‘good’ solutions with the state |1> and ‘bad’ solutions with the state |0>
*   **likelihood\_evals** (`Optional`\[`int`]) – The number of gridpoints for the maximum search of the likelihood function
*   **quantum\_instance** (`Union`\[`QuantumInstance`, `Backend`, `BaseBackend`, `None`]) – Quantum Instance or Backend

## Methods

|                                                                                                                                                                                                             |                                                                           |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| [`__init__`](#qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.__init__ "qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.__init__")(num\_oracle\_circuits\[, …])                     | **type num\_oracle\_circuits**`int`                                       |
| [`confidence_interval`](#qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.confidence_interval "qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.confidence_interval")(alpha\[, kind]) | Compute the alpha confidence interval using the method kind.              |
| [`construct_circuits`](#qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.construct_circuits "qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.construct_circuits")(\[measurement])    | Construct the Amplitude Estimation w/o QPE quantum circuits.              |
| [`is_good_state`](#qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.is_good_state "qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.is_good_state")(measurement)                      | Determine whether a given state is a good state.                          |
| [`post_processing`](#qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.post_processing "qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.post_processing")(value)                      | Post processing of the raw amplitude estimation output $0 \leq a \leq 1$. |
| [`run`](#qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.run "qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.run")(\[quantum\_instance])                                           | Execute the algorithm with selected backend.                              |
| [`set_backend`](#qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.set_backend "qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.set_backend")(backend, \*\*kwargs)                    | Sets backend with configuration.                                          |

## Attributes

|                                                                                                                                                                                       |                                                                                     |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| [`a_factory`](#qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.a_factory "qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.a_factory")                         | Get the A operator encoding the amplitude a that’s approximated, i.e.               |
| [`backend`](#qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.backend "qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.backend")                               | Returns backend.                                                                    |
| [`grover_operator`](#qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.grover_operator "qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.grover_operator")       | Get the $\mathcal{Q}$ operator, or Grover operator.                                 |
| [`i_objective`](#qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.i_objective "qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.i_objective")                   | Get the index of the objective qubit.                                               |
| [`objective_qubits`](#qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.objective_qubits "qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.objective_qubits")    | Get the criterion for a measurement outcome to be in a ‘good’ state.                |
| [`q_factory`](#qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.q_factory "qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.q_factory")                         | Get the Q operator, or Grover-operator for the Amplitude Estimation algorithm, i.e. |
| [`quantum_instance`](#qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.quantum_instance "qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.quantum_instance")    | Returns quantum instance.                                                           |
| [`random`](#qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.random "qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.random")                                  | Return a numpy random.                                                              |
| [`state_preparation`](#qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.state_preparation "qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.state_preparation") | Get the $\mathcal{A}$ operator encoding the amplitude $a$.                          |

### a\_factory

<span id="qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.a_factory" />

`property a_factory`

Get the A operator encoding the amplitude a that’s approximated, i.e.

> A |0>\_n |0> = sqrt\{1 - a} |psi\_0>\_n |0> + sqrt\{a} |psi\_1>\_n |1>

see the original Brassard paper ([https://arxiv.org/abs/quant-ph/0005055](https://arxiv.org/abs/quant-ph/0005055)) for more detail.

**Returns**

the A operator as CircuitFactory

**Return type**

[CircuitFactory](qiskit.aqua.utils.CircuitFactory "qiskit.aqua.utils.CircuitFactory")

### backend

<span id="qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.backend" />

`property backend`

Returns backend.

**Return type**

`Union`\[`Backend`, `BaseBackend`]

### confidence\_interval

<span id="qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.confidence_interval" />

`confidence_interval(alpha, kind='fisher')`

Compute the alpha confidence interval using the method kind.

The confidence level is (1 - alpha) and supported kinds are ‘fisher’, ‘likelihood\_ratio’ and ‘observed\_fisher’ with shorthand notations ‘fi’, ‘lr’ and ‘oi’, respectively.

**Parameters**

*   **alpha** (`float`) – The confidence level.
*   **kind** (`str`) – The method to compute the confidence interval. Defaults to ‘fisher’, which computes the theoretical Fisher information.

**Return type**

`List`\[`float`]

**Returns**

The specified confidence interval.

**Raises**

*   [**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – If run() hasn’t been called yet.
*   **NotImplementedError** – If the method kind is not supported.

### construct\_circuits

<span id="qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.construct_circuits" />

`construct_circuits(measurement=False)`

Construct the Amplitude Estimation w/o QPE quantum circuits.

**Parameters**

**measurement** (`bool`) – Boolean flag to indicate if measurement should be included in the circuits.

**Return type**

`List`\[`QuantumCircuit`]

**Returns**

A list with the QuantumCircuit objects for the algorithm.

### grover\_operator

<span id="qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.grover_operator" />

`property grover_operator`

Get the $\mathcal{Q}$ operator, or Grover operator.

If the Grover operator is not set, we try to build it from the $\mathcal{A}$ operator and objective\_qubits. This only works if objective\_qubits is a list of integers.

**Return type**

`Optional`\[`QuantumCircuit`]

**Returns**

The Grover operator, or None if neither the Grover operator nor the $\mathcal{A}$ operator is set.

### i\_objective

<span id="qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.i_objective" />

`property i_objective`

Get the index of the objective qubit. The objective qubit marks the |psi\_0> state (called ‘bad states’ in [https://arxiv.org/abs/quant-ph/0005055](https://arxiv.org/abs/quant-ph/0005055)) with |0> and |psi\_1> (‘good’ states) with |1>. If the A operator performs the mapping

> A |0>\_n |0> = sqrt\{1 - a} |psi\_0>\_n |0> + sqrt\{a} |psi\_1>\_n |1>

then, the objective qubit is the last one (which is either |0> or |1>).

If the objective qubit (i\_objective) is not set, we check if the Q operator (q\_factory) is set and return the index specified there. If the q\_factory is not defined, the index equals the number of qubits of the A operator (a\_factory) minus one. If also the a\_factory is not set, return None.

**Returns**

the index of the objective qubit

**Return type**

int

### is\_good\_state

<span id="qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.is_good_state" />

`is_good_state(measurement)`

Determine whether a given state is a good state.

**Parameters**

**measurement** (`str`) – A measurement as bitstring, e.g. ‘01100’.

**Return type**

`bool`

**Returns**

True if the measurement corresponds to a good state, False otherwise.

**Raises**

**ValueError** – If `self.objective_qubits` is not set.

### objective\_qubits

<span id="qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.objective_qubits" />

`property objective_qubits`

Get the criterion for a measurement outcome to be in a ‘good’ state.

**Return type**

`Optional`\[`List`\[`int`]]

**Returns**

The criterion as list of qubit indices.

### post\_processing

<span id="qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.post_processing" />

`post_processing(value)`

Post processing of the raw amplitude estimation output $0 \leq a \leq 1$.

**Parameters**

**value** (`float`) – The estimation value $a$.

**Return type**

`float`

**Returns**

The value after post processing, usually mapping the interval $[0, 1]$ to the target interval.

### q\_factory

<span id="qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.q_factory" />

`property q_factory`

Get the Q operator, or Grover-operator for the Amplitude Estimation algorithm, i.e.

$$
\mathcal{Q} = \mathcal{A} \mathcal{S}_0 \mathcal{A}^\dagger \mathcal{S}_f,
$$

where $\mathcal{S}_0$ reflects about the |0>\_n state and S\_psi0 reflects about $|\Psi_0\rangle_n$. See [https://arxiv.org/abs/quant-ph/0005055](https://arxiv.org/abs/quant-ph/0005055) for more detail.

If the Q operator is not set, we try to build it from the A operator. If neither the A operator is set, None is returned.

**Returns**

returns the current Q factory of the algorithm

**Return type**

QFactory

### quantum\_instance

<span id="qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.quantum_instance" />

`property quantum_instance`

Returns quantum instance.

**Return type**

`Optional`\[`QuantumInstance`]

### random

<span id="qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.random" />

`property random`

Return a numpy random.

### run

<span id="qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.run" />

`run(quantum_instance=None, **kwargs)`

Execute the algorithm with selected backend.

**Parameters**

*   **quantum\_instance** (`Union`\[`QuantumInstance`, `Backend`, `BaseBackend`, `None`]) – the experimental setting.
*   **kwargs** (*dict*) – kwargs

**Returns**

results of an algorithm.

**Return type**

dict

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – If a quantum instance or backend has not been provided

### set\_backend

<span id="qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.set_backend" />

`set_backend(backend, **kwargs)`

Sets backend with configuration.

**Return type**

`None`

### state\_preparation

<span id="qiskit.aqua.algorithms.MaximumLikelihoodAmplitudeEstimation.state_preparation" />

`property state_preparation`

Get the $\mathcal{A}$ operator encoding the amplitude $a$.

**Return type**

`QuantumCircuit`

**Returns**

The $\mathcal{A}$ operator as QuantumCircuit.

