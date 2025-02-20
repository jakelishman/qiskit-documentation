---
title: MSGate
description: API reference for qiskit.circuit.library.MSGate
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.MSGate
---

# MSGate

<span id="qiskit.circuit.library.MSGate" />

`MSGate(num_qubits, theta, label=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/circuit/library/standard_gates/ms.py "view source code")

Bases: `qiskit.circuit.gate.Gate`

MSGate has been deprecated. Please use `GMS` in `qiskit.circuit.generalized_gates` instead.

Global Mølmer–Sørensen gate.

The Mølmer–Sørensen gate is native to ion-trap systems. The global MS can be applied to multiple ions to entangle multiple qubits simultaneously.

In the two-qubit case, this is equivalent to an XX(theta) interaction, and is thus reduced to the RXXGate.

Create new MS gate.

## Attributes

<span id="qiskit.circuit.library.MSGate.decompositions" />

### decompositions

Get the decompositions of the instruction from the SessionEquivalenceLibrary.

<span id="qiskit.circuit.library.MSGate.definition" />

### definition

Return definition in terms of other basic gates.

<span id="qiskit.circuit.library.MSGate.duration" />

### duration

Get the duration.

<span id="qiskit.circuit.library.MSGate.label" />

### label

Return instruction label

**Return type**

`str`

<span id="qiskit.circuit.library.MSGate.params" />

### params

return instruction params.

<span id="qiskit.circuit.library.MSGate.unit" />

### unit

Get the time unit of duration.

