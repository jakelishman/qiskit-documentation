---
title: Exporter
description: API reference for qiskit.qasm3.Exporter
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.qasm3.Exporter
---

# Exporter

<span id="qiskit.qasm3.Exporter" />

`Exporter(includes=('stdgates.inc',), basis_gates=('U',), disable_constants=False, alias_classical_registers=False, indent='  ')`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/qasm3/exporter.py "view source code")

Bases: `object`

QASM3 exporter main class.

**Parameters**

*   **includes** (`Sequence`\[`str`]) – the filenames that should be emitted as includes. These files will be parsed for gates, and any objects dumped from this exporter will use those definitions where possible.
*   **basis\_gates** (`Sequence`\[`str`]) – the basic defined gate set of the backend.
*   **disable\_constants** (`bool`) – if `True`, always emit floating-point constants for numeric parameter values. If `False` (the default), then values close to multiples of QASM 3 constants (`pi`, `euler`, and `tau`) will be emitted in terms of those constants instead, potentially improving accuracy in the output.
*   **alias\_classical\_registers** (`bool`) – If `True`, then classical bit and classical register declarations will look similar to quantum declarations, where the whole set of bits will be declared in a flat array, and the registers will just be aliases to collections of these bits. This is inefficient for running OpenQASM 3 programs, however, and may not be well supported on backends. Instead, the default behaviour of `False` means that individual classical registers will gain their own `bit[size] register;` declarations, and loose [`Clbit`](qiskit.circuit.Clbit "qiskit.circuit.Clbit")s will go onto their own declaration. In this form, each [`Clbit`](qiskit.circuit.Clbit "qiskit.circuit.Clbit") must be in either zero or one [`ClassicalRegister`](qiskit.circuit.ClassicalRegister "qiskit.circuit.ClassicalRegister")s.
*   **indent** (`str`) – the indentation string to use for each level within an indented block. Can be set to the empty string to disable indentation.

## Methods

### dump

<span id="qiskit.qasm3.Exporter.dump" />

`Exporter.dump(circuit, stream)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/qasm3/exporter.py "view source code")

Convert the circuit to QASM 3, dumping the result to a file or text stream.

### dumps

<span id="qiskit.qasm3.Exporter.dumps" />

`Exporter.dumps(circuit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/qasm3/exporter.py "view source code")

Convert the circuit to QASM 3, returning the result as a string.

