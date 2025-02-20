---
title: save_amplitudes_squared
description: API reference for qiskit.providers.aer.library.save_amplitudes_squared
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.providers.aer.library.save_amplitudes_squared
---

# qiskit.providers.aer.library.save\_amplitudes\_squared

<span id="qiskit.providers.aer.library.save_amplitudes_squared" />

`save_amplitudes_squared(self, params, label='amplitudes_squared', unnormalized=False, pershot=False, conditional=False)`[GitHub](https://github.com/qiskit/qiskit-aer/tree/stable/0.9/qiskit/providers/aer/library/save_instructions/save_amplitudes.py "view source code")

Save squared statevector amplitudes (probabilities).

**Parameters**

*   **params** (*List\[int] or List\[str]*) – the basis states to return amplitudes for.
*   **label** (*str*) – the key for retrieving saved data from results.
*   **unnormalized** (*bool*) – If True return save the unnormalized accumulated probabilities over all shots \[Default: False].
*   **pershot** (*bool*) – if True save a list of probability vectors for each shot of the simulation rather than the a single amplitude vector \[Default: False].
*   **conditional** (*bool*) – if True save the probability vector conditional on the current classical register values \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – if params is invalid for the specified number of qubits.

