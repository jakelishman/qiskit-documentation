---
title: RawFeatureVector
description: API reference for qiskit.aqua.components.feature_maps.RawFeatureVector
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.components.feature_maps.RawFeatureVector
---

# RawFeatureVector

<span id="qiskit.aqua.components.feature_maps.RawFeatureVector" />

`RawFeatureVector(feature_dimension=2)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/components/feature_maps/raw_feature_vector.py "view source code")

Bases: `qiskit.aqua.components.feature_maps.feature_map.FeatureMap`

Raw Feature Vector feature map.

The Raw Feature Vector can be directly used as a feature map, where the raw feature vectors will be automatically padded with ending 0s as necessary, to make sure vector length is a power of 2, and normalized such that it can be treated and used as an initial quantum state vector.

**Parameters**

**feature\_dimension** (`int`) – The feature dimension, has a minimum value of 1.

## Methods

### construct\_circuit

<span id="qiskit.aqua.components.feature_maps.RawFeatureVector.construct_circuit" />

`RawFeatureVector.construct_circuit(x, qr=None, inverse=False)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/components/feature_maps/raw_feature_vector.py "view source code")

Construct the second order expansion based on given data.

**Parameters**

*   **x** (*numpy.ndarray*) – 1-D to-be-encoded data.
*   **qr** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")) – the QuantumRegister object for the circuit, if None, generate new registers with name q.
*   **inverse** (*bool*) – inverse

**Returns**

a quantum circuit transform data x.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

*   **TypeError** – invalid input
*   **ValueError** – invalid input

### get\_entangler\_map

<span id="qiskit.aqua.components.feature_maps.RawFeatureVector.get_entangler_map" />

`static RawFeatureVector.get_entangler_map(map_type, num_qubits)`

get entangle map

### validate\_entangler\_map

<span id="qiskit.aqua.components.feature_maps.RawFeatureVector.validate_entangler_map" />

`static RawFeatureVector.validate_entangler_map(entangler_map, num_qubits)`

validate entangler map

## Attributes

<span id="qiskit.aqua.components.feature_maps.RawFeatureVector.feature_dimension" />

### feature\_dimension

returns feature dimension

<span id="qiskit.aqua.components.feature_maps.RawFeatureVector.num_qubits" />

### num\_qubits

returns number of qubits

<span id="qiskit.aqua.components.feature_maps.RawFeatureVector.support_parameterized_circuit" />

### support\_parameterized\_circuit

returns whether or not the sub-class support parameterized circuit

