---
title: set_unitary
description: API reference for qiskit.providers.aer.library.set_unitary
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.providers.aer.library.set_unitary
---

# qiskit.providers.aer.library.set\_unitary

<span id="qiskit.providers.aer.library.set_unitary" />

`set_unitary(self, state)`[GitHub](https://github.com/qiskit/qiskit-aer/tree/stable/0.8/qiskit/providers/aer/library/set_instructions/set_unitary.py "view source code")

Set the state state of the simulator.

**Parameters**

**state** ([*Operator*](qiskit.quantum_info.Operator "qiskit.quantum_info.Operator")) – A state matrix.

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

*   **ExtensionError** – If the state is the incorrect size for the current circuit.
*   **ExtensionError** – if the input matrix is not unitary.

