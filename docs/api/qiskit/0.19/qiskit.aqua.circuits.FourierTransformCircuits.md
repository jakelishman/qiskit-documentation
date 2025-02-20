---
title: FourierTransformCircuits
description: API reference for qiskit.aqua.circuits.FourierTransformCircuits
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.circuits.FourierTransformCircuits
---

# FourierTransformCircuits

<span id="qiskit.aqua.circuits.FourierTransformCircuits" />

`FourierTransformCircuits`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/circuits/fourier_transform_circuits.py "view source code")

DEPRECATED. Quantum Fourier Transform Circuit.

## Methods

### construct\_circuit

<span id="qiskit.aqua.circuits.FourierTransformCircuits.construct_circuit" />

`static FourierTransformCircuits.construct_circuit(circuit=None, qubits=None, inverse=False, approximation_degree=0, do_swaps=True)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/circuits/fourier_transform_circuits.py "view source code")

Construct the circuit representing the desired state vector.

**Parameters**

*   **circuit** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – The optional circuit to extend from.
*   **qubits** (*Union(*[*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*, list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*])*) – The optional qubits to construct the circuit with.
*   **approximation\_degree** (*int*) – degree of approximation for the desired circuit
*   **inverse** (*bool*) – Boolean flag to indicate Inverse Quantum Fourier Transform
*   **do\_swaps** (*bool*) – Boolean flag to specify if swaps should be included to align the qubit order of input and output. The output qubits would be in reversed order without the swaps.

**Returns**

quantum circuit

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – invalid input

