---
title: StateVectorCircuit
description: API reference for qiskit.aqua.circuits.StateVectorCircuit
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.circuits.StateVectorCircuit
---

# StateVectorCircuit

<span id="qiskit.aqua.circuits.StateVectorCircuit" />

`StateVectorCircuit(state_vector)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/circuits/statevector_circuit.py "view source code")

Bases: `object`

Arbitrary State-Vector Circuit.

Constructor.

**Parameters**

**state\_vector** (*numpy.ndarray*) – vector representation of the desired quantum state

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – invalid input

## Methods

### construct\_circuit

<span id="qiskit.aqua.circuits.StateVectorCircuit.construct_circuit" />

`StateVectorCircuit.construct_circuit(circuit=None, register=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/circuits/statevector_circuit.py "view source code")

Construct the circuit representing the desired state vector.

**Parameters**

*   **circuit** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – The optional circuit to extend from.
*   **register** (*Union(*[*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister") *, list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*])*) – The optional qubits to construct the circuit with.

**Returns**

quantum circuit

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – invalid input

