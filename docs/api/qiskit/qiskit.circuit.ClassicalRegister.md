---
title: ClassicalRegister
description: API reference for qiskit.circuit.ClassicalRegister
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.ClassicalRegister
---

# ClassicalRegister

<span id="qiskit.circuit.ClassicalRegister" />

`qiskit.circuit.ClassicalRegister(size=None, name=None, bits=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/circuit/classicalregister.py "view source code")

Bases: [`Register`](qiskit.circuit.Register "qiskit.circuit.register.Register")

Implement a classical register.

Create a new generic register.

Either the `size` or the `bits` argument must be provided. If `size` is not None, the register will be pre-populated with bits of the correct type.

**Parameters**

*   **size** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – Optional. The number of bits to include in the register.
*   **name** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")) – Optional. The name of the register. If not provided, a unique name will be auto-generated from the register type.
*   **bits** ([*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")*\[*[*Bit*](qiskit.circuit.Bit "qiskit.circuit.Bit")*]*) – Optional. A list of Bit() instances to be used to populate the register.

**Raises**

*   [**CircuitError**](circuit#qiskit.circuit.CircuitError "qiskit.circuit.CircuitError") – if both the `size` and `bits` arguments are provided, or if neither are.
*   [**CircuitError**](circuit#qiskit.circuit.CircuitError "qiskit.circuit.CircuitError") – if `size` is not valid.
*   [**CircuitError**](circuit#qiskit.circuit.CircuitError "qiskit.circuit.CircuitError") – if `name` is not a valid name according to the OpenQASM spec.
*   [**CircuitError**](circuit#qiskit.circuit.CircuitError "qiskit.circuit.CircuitError") – if `bits` contained duplicated bits.
*   [**CircuitError**](circuit#qiskit.circuit.CircuitError "qiskit.circuit.CircuitError") – if `bits` contained bits of an incorrect type.

## Attributes

<span id="qiskit.circuit.ClassicalRegister.instances_counter" />

### instances\_counter

`= count(0)`

<span id="qiskit.circuit.ClassicalRegister.name" />

### name

Get the register name.

<span id="qiskit.circuit.ClassicalRegister.name_format" />

### name\_format

`= re.compile('[a-z][a-zA-Z0-9_]*')`

<span id="qiskit.circuit.ClassicalRegister.prefix" />

### prefix

`= 'c'`

<span id="qiskit.circuit.ClassicalRegister.size" />

### size

Get the register size.

## Methods

### index

<span id="qiskit.circuit.ClassicalRegister.index" />

`index(bit)`

Find the index of the provided bit within this register.

### qasm

<span id="qiskit.circuit.ClassicalRegister.qasm" />

`qasm()`

Return OPENQASM string for this register.

<Admonition title="Deprecated since version 0.23.0" type="danger">
  The method `qiskit.circuit.classicalregister.ClassicalRegister.qasm()` is deprecated as of qiskit-terra 0.23.0. It will be removed no earlier than 3 months after the release date. Correct exporting to OpenQASM 2 is the responsibility of a larger exporter; it cannot safely be done on an object-by-object basis without context. No replacement will be provided, because the premise is wrong.
</Admonition>

