---
title: save_stabilizer
description: API reference for qiskit.providers.aer.library.save_stabilizer
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.providers.aer.library.save_stabilizer
---

# qiskit.providers.aer.library.save\_stabilizer

<span id="qiskit.providers.aer.library.save_stabilizer" />

`save_stabilizer(self, label='stabilizer', pershot=False, conditional=False)`[GitHub](https://github.com/qiskit/qiskit-aer/tree/stable/0.9/qiskit/providers/aer/library/save_instructions/save_stabilizer.py "view source code")

Save the current stabilizer simulator quantum state as a Clifford.

**Parameters**

*   **label** (*str*) – the key for retrieving saved data from results.
*   **pershot** (*bool*) – if True save a list of Cliffords for each shot of the simulation \[Default: False].
*   **conditional** (*bool*) – if True save pershot data conditional on the current classical register values \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

<Admonition title="Note" type="note">
  This instruction is always defined across all qubits in a circuit.
</Admonition>

