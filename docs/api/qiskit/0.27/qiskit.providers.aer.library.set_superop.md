---
title: set_superop
description: API reference for qiskit.providers.aer.library.set_superop
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.providers.aer.library.set_superop
---

# qiskit.providers.aer.library.set\_superop

<span id="qiskit.providers.aer.library.set_superop" />

`set_superop(self, state)`[GitHub](https://github.com/qiskit/qiskit-aer/tree/stable/0.8/qiskit/providers/aer/library/set_instructions/set_superop.py "view source code")

Set the superop state of the simulator.

**Parameters**

**state** (*QuantumChannel*) – A CPTP quantum channel.

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

*   **ExtensionError** – If the state is the incorrect size for the current circuit.
*   **ExtensionError** – if the input QuantumChannel is not CPTP.

