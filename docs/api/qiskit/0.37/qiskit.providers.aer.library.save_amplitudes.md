---
title: save_amplitudes
description: API reference for qiskit.providers.aer.library.save_amplitudes
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.providers.aer.library.save_amplitudes
---

# qiskit.providers.aer.library.save\_amplitudes

<span id="qiskit.providers.aer.library.save_amplitudes" />

`save_amplitudes(self, params, label='amplitudes', pershot=False, conditional=False)`[GitHub](https://github.com/qiskit/qiskit-aer/tree/stable/0.10/qiskit/providers/aer/library/save_instructions/save_amplitudes.py "view source code")

Save complex statevector amplitudes.

**Parameters**

*   **params** (*List\[int] or List\[str]*) – the basis states to return amplitudes for.
*   **label** (*str*) – the key for retrieving saved data from results.
*   **pershot** (*bool*) – if True save a list of amplitudes vectors for each shot of the simulation rather than the a single amplitude vector \[Default: False].
*   **conditional** (*bool*) – if True save the amplitudes vector conditional on the current classical register values \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – if params is invalid for the specified number of qubits.

