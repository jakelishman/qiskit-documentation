---
title: Custom
description: API reference for qiskit.aqua.components.initial_states.Custom
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.components.initial_states.Custom
---

# Custom

<span id="qiskit.aqua.components.initial_states.Custom" />

`Custom(num_qubits, state='zero', state_vector=None, circuit=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/components/initial_states/custom.py "view source code")

The custom initial state.

A custom initial state can be created with this component. It allows a state to be defined in the form of custom probability distribution with the *state\_vector*, or by providing a desired *circuit* to set the state.

Also *state* can be used having a few pre-defined initial states for convenience:

*   ‘zero’: configures the state vector with the zero probability distribution, and is effectively equivalent to the [`Zero`](qiskit.aqua.components.initial_states.Zero "qiskit.aqua.components.initial_states.Zero") initial state.
*   ‘uniform’: This setting configures the state vector with the uniform probability distribution. All the qubits are set in superposition, each of them being initialized with a Hadamard gate, which means that a measurement will have equal probabilities to become $1$ or $0$.
*   ‘random’: This setting assigns the elements of the state vector according to a random probability distribution.

The custom initial state will be set from the *circuit*, the *state\_vector*, or *state*, in that order. For *state\_vector* the provided custom probability distribution will be internally normalized so the total probability represented is $1.0$.

**Parameters**

*   **num\_qubits** (`int`) – Number of qubits, has a minimum value of 1.
*   **state** (`str`) – Use a predefined state of (‘zero’ | ‘uniform’ | ‘random’)
*   **state\_vector** (`Union`\[`ndarray`, [`StateFn`](qiskit.aqua.operators.state_fns.StateFn "qiskit.aqua.operators.state_fns.state_fn.StateFn"), `None`]) – An optional vector of `complex` or `float` representing the state as a probability distribution which will be normalized to a total probability of 1 when initializing the qubits. The length of the vector must be $2^q$, where $q$ is the *num\_qubits* value. When provided takes precedence over *state*.
*   **circuit** (`Optional`\[[`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit")]) – A quantum circuit for the desired initial state. When provided takes precedence over both *state\_vector* and *state*.

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – invalid input

## Attributes

### bitstr

## Methods

### construct\_circuit

<span id="qiskit.aqua.components.initial_states.Custom.construct_circuit" />

`Custom.construct_circuit(mode='circuit', register=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/components/initial_states/custom.py "view source code")

Construct the statevector of desired initial state.

**Parameters**

*   **mode** – vector or circuit. The vector mode produces the vector. While the circuit constructs the quantum circuit corresponding that vector.
*   **register** – qubits for circuit construction.

**Returns**

statevector.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit") or numpy.ndarray

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – when mode is not ‘vector’ or ‘circuit’.

