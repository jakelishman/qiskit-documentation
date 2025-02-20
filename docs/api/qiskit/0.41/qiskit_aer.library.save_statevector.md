---
title: save_statevector
description: API reference for qiskit_aer.library.save_statevector
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit_aer.library.save_statevector
---

# qiskit\_aer.library.save\_statevector

<span id="qiskit_aer.library.save_statevector" />

`save_statevector(self, label='statevector', pershot=False, conditional=False)`[GitHub](https://github.com/qiskit/qiskit-aer/tree/stable/0.11/qiskit_aer/library/save_instructions/save_statevector.py "view source code")

Save the current simulator quantum state as a statevector.

**Parameters**

*   **pershot** (*bool*) – if True save a list of statevectors for each shot of the simulation \[Default: False].
*   **label** (*str*) – the key for retrieving saved data from results.
*   **conditional** (*bool*) – if True save pershot data conditional on the current classical register values \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

<Admonition title="Note" type="note">
  This instruction is always defined across all qubits in a circuit.
</Admonition>

