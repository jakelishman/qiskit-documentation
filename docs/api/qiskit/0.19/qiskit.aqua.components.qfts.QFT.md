---
title: QFT
description: API reference for qiskit.aqua.components.qfts.QFT
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.components.qfts.QFT
---

# QFT

<span id="qiskit.aqua.components.qfts.QFT" />

`QFT`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/components/qfts/qft.py "view source code")

DEPRECATED. Base class for QFT.

## Methods

### construct\_circuit

<span id="qiskit.aqua.components.qfts.QFT.construct_circuit" />

`QFT.construct_circuit(mode='circuit', qubits=None, circuit=None, do_swaps=True)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/components/qfts/qft.py "view source code")

Construct the circuit.

**Parameters**

*   **mode** (*str*) – ‘matrix’ or ‘circuit’
*   **qubits** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister") *or qubits*) – register or qubits to build the circuit on.
*   **circuit** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – circuit for construction.
*   **do\_swaps** (*bool*) – include the swaps.

**Returns**

The matrix or circuit depending on the specified mode.

**Return type**

numpy.ndarray

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – ‘Unrecognized mode

