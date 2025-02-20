---
title: Clbit
description: API reference for qiskit.circuit.Clbit
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.Clbit
---

# Clbit

<span id="qiskit.circuit.Clbit" />

`Clbit(register=None, index=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/circuit/classicalregister.py "view source code")

Bases: `qiskit.circuit.bit.Bit`

Implement a classical bit.

Creates a classical bit.

**Parameters**

*   **register** ([*ClassicalRegister*](qiskit.circuit.ClassicalRegister "qiskit.circuit.ClassicalRegister")) – Optional. A classical register containing the bit.
*   **index** (*int*) – Optional. The index of the bit in its containing register.

**Raises**

**CircuitError** – if the provided register is not a valid [`ClassicalRegister`](qiskit.circuit.ClassicalRegister "qiskit.circuit.ClassicalRegister")

## Attributes

<span id="qiskit.circuit.Clbit.index" />

### index

Get bit’s index.

<span id="qiskit.circuit.Clbit.register" />

### register

Get bit’s register.

