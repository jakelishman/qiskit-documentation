---
title: QasmQobjInstruction
description: API reference for qiskit.qobj.QasmQobjInstruction
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.qobj.QasmQobjInstruction
---

# QasmQobjInstruction

<span id="qiskit.qobj.QasmQobjInstruction" />

`QasmQobjInstruction(name, params=None, qubits=None, register=None, memory=None, condition=None, conditional=None, label=None, mask=None, relation=None, val=None, snapshot_type=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/qobj/qasm_qobj.py "view source code")

Bases: `object`

A class representing a single instruction in an QasmQobj Experiment.

Instantiate a new QasmQobjInstruction object.

**Parameters**

*   **name** (*str*) – The name of the instruction
*   **params** (*list*) – The list of parameters for the gate
*   **qubits** (*list*) – A list of `int` representing the qubits the instruction operates on
*   **register** (*list*) – If a `measure` instruction this is a list of `int` containing the list of register slots in which to store the measurement results (must be the same length as qubits). If a `bfunc` instruction this is a single `int` of the register slot in which to store the result.
*   **memory** (*list*) – If a `measure` instruction this is a list of `int` containing the list of memory slots to store the measurement results in (must be the same length as qubits). If a `bfunc` instruction this is a single `int` of the memory slot to store the boolean function result in.
*   **condition** (*tuple*) – A tuple of the form `(int, int)` where the first `int` is the control register and the second `int` is the control value if the gate has a condition.
*   **conditional** (*int*) – The register index of the condition
*   **label** (*str*) – An optional label assigned to the instruction
*   **mask** (*int*) – For a `bfunc` instruction the hex value which is applied as an `AND` to the register bits.
*   **relation** (*str*) – Relational operator for comparing the masked register to the `val` kwarg. Can be either `==` (equals) or `!=` (not equals).
*   **val** (*int*) – Value to which to compare the masked register. In other words, the output of the function is `(register AND mask)`
*   **snapshot\_type** (*str*) – For snapshot instructions the type of snapshot to use

## Methods

### from\_dict

<span id="qiskit.qobj.QasmQobjInstruction.from_dict" />

`classmethod QasmQobjInstruction.from_dict(data)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/qobj/qasm_qobj.py "view source code")

Create a new QasmQobjInstruction object from a dictionary.

**Parameters**

**data** (*dict*) – A dictionary for the experiment config

**Returns**

The object from the input dictionary.

**Return type**

[QasmQobjInstruction](qiskit.qobj.QasmQobjInstruction "qiskit.qobj.QasmQobjInstruction")

### to\_dict

<span id="qiskit.qobj.QasmQobjInstruction.to_dict" />

`QasmQobjInstruction.to_dict()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/qobj/qasm_qobj.py "view source code")

Return a dictionary format representation of the Instruction.

**Returns**

The dictionary form of the QasmQobjInstruction.

**Return type**

dict

