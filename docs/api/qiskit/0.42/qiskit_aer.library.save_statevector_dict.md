---
title: save_statevector_dict
description: API reference for qiskit_aer.library.save_statevector_dict
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit_aer.library.save_statevector_dict
---

# qiskit\_aer.library.save\_statevector\_dict

<span id="qiskit_aer.library.save_statevector_dict" />

`save_statevector_dict(self, label='statevector', pershot=False, conditional=False)`[GitHub](https://github.com/qiskit/qiskit-aer/tree/stable/0.12/qiskit_aer/library/save_instructions/save_statevector.py "view source code")

Save the current simulator quantum state as a statevector as a dict.

**Parameters**

*   **label** (*str*) – the key for retrieving saved data from results.
*   **pershot** (*bool*) – if True save a list of statevectors for each shot of the simulation \[Default: False].
*   **conditional** (*bool*) – if True save pershot data conditional on the current classical register values \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

<Admonition title="Note" type="note">
  This instruction is always defined across all qubits in a circuit.
</Admonition>

