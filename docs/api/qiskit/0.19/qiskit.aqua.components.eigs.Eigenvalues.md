---
title: Eigenvalues
description: API reference for qiskit.aqua.components.eigs.Eigenvalues
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.components.eigs.Eigenvalues
---

# Eigenvalues

<span id="qiskit.aqua.components.eigs.Eigenvalues" />

`Eigenvalues`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/components/eigs/eigs.py "view source code")

Base class for eigenvalue estimation.

This method should initialize the module and use an exception if a component of the module is not available.

## Methods

### construct\_circuit

<span id="qiskit.aqua.components.eigs.Eigenvalues.construct_circuit" />

`abstract Eigenvalues.construct_circuit(mode, register=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/components/eigs/eigs.py "view source code")

Construct the eigenvalue estimation quantum circuit.

**Parameters**

*   **mode** (*str*) – ‘matrix’ or ‘circuit’
*   **register** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")) – register for circuit construction where eigenvalues will be stored.

**Returns**

object for the eigenvalue estimation circuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**NotImplementedError** – not implemented

### construct\_inverse

<span id="qiskit.aqua.components.eigs.Eigenvalues.construct_inverse" />

`Eigenvalues.construct_inverse(mode, circuit)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/components/eigs/eigs.py "view source code")

Construct the inverse eigenvalue estimation quantum circuit.

**Parameters**

*   **mode** (*str*) – construction mode, ‘matrix’ not supported
*   **circuit** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – the quantum circuit to invert

**Returns**

**object for of the inverted eigenvalue estimation**

circuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

*   **NotImplementedError** – not implemented for matrix mode
*   **ValueError** – Circuit was not constructed beforehand

### get\_register\_sizes

<span id="qiskit.aqua.components.eigs.Eigenvalues.get_register_sizes" />

`abstract Eigenvalues.get_register_sizes()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/components/eigs/eigs.py "view source code")

get register sizes

### get\_scaling

<span id="qiskit.aqua.components.eigs.Eigenvalues.get_scaling" />

`abstract Eigenvalues.get_scaling()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/components/eigs/eigs.py "view source code")

get scaling

