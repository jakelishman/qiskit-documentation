---
title: Zero
description: API reference for qiskit.aqua.components.initial_states.Zero
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.components.initial_states.Zero
---

# Zero

<span id="qiskit.aqua.components.initial_states.Zero" />

`Zero(num_qubits)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/components/initial_states/zero.py "view source code")

The zero (null/vacuum) state.

This is suitable for those situations in which the all-zeros state is the desired state. This is the case for a *vacuum state* in physics or chemistry

**Parameters**

**num\_qubits** (`int`) – Number of qubits, has a minimum value of 1.

## Attributes

### bitstr

## Methods

### construct\_circuit

<span id="qiskit.aqua.components.initial_states.Zero.construct_circuit" />

`Zero.construct_circuit(mode='circuit', register=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/components/initial_states/zero.py "view source code")

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

