---
title: SnapshotDensityMatrix
description: API reference for qiskit.providers.aer.extensions.SnapshotDensityMatrix
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.aer.extensions.SnapshotDensityMatrix
---

# SnapshotDensityMatrix

<span id="qiskit.providers.aer.extensions.SnapshotDensityMatrix" />

`SnapshotDensityMatrix(label, num_qubits)`[GitHub](https://github.com/qiskit/qiskit-aer/tree/stable/0.5/qiskit/providers/aer/extensions/snapshot_density_matrix.py "view source code")

Snapshot instruction for density matrix method of Qasm simulator.

Create a density matrix state snapshot instruction.

**Parameters**

*   **label** (*str*) – the snapshot label.
*   **num\_qubits** (*int*) – the number of qubits to snapshot.

**Raises**

**ExtensionError** – if snapshot is invalid.

## Attributes

### decompositions

Get the decompositions of the instruction from the SessionEquivalenceLibrary.

### definition

Return definition in terms of other basic gates.

### label

Return snapshot label

### params

return instruction params.

### snapshot\_type

Return snapshot type

## Methods

### add\_decomposition

<span id="qiskit.providers.aer.extensions.SnapshotDensityMatrix.add_decomposition" />

`SnapshotDensityMatrix.add_decomposition(decomposition)`

Add a decomposition of the instruction to the SessionEquivalenceLibrary.

### assemble

<span id="qiskit.providers.aer.extensions.SnapshotDensityMatrix.assemble" />

`SnapshotDensityMatrix.assemble()`

Assemble a QasmQobjInstruction

### broadcast\_arguments

<span id="qiskit.providers.aer.extensions.SnapshotDensityMatrix.broadcast_arguments" />

`SnapshotDensityMatrix.broadcast_arguments(qargs, cargs)`

Validation of the arguments.

**Parameters**

*   **qargs** (*List*) – List of quantum bit arguments.
*   **cargs** (*List*) – List of classical bit arguments.

**Yields**

*Tuple(List, List)* – A tuple with single arguments.

**Raises**

**CircuitError** – If the input is not valid. For example, the number of arguments does not match the gate expectation.

### c\_if

<span id="qiskit.providers.aer.extensions.SnapshotDensityMatrix.c_if" />

`SnapshotDensityMatrix.c_if(classical, val)`

Add classical condition on register classical and value val.

### copy

<span id="qiskit.providers.aer.extensions.SnapshotDensityMatrix.copy" />

`SnapshotDensityMatrix.copy(name=None)`

Copy of the instruction.

**Parameters**

**name** (*str*) – name to be given to the copied circuit, if None then the name stays the same.

**Returns**

**a copy of the current instruction, with the name**

updated if it was provided

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

### define\_snapshot\_register

<span id="qiskit.providers.aer.extensions.SnapshotDensityMatrix.define_snapshot_register" />

`static SnapshotDensityMatrix.define_snapshot_register(circuit, label, qubits=None)`

Defines qubits to snapshot for all snapshot methods

### inverse

<span id="qiskit.providers.aer.extensions.SnapshotDensityMatrix.inverse" />

`SnapshotDensityMatrix.inverse()`

Special case. Return self.

### is\_parameterized

<span id="qiskit.providers.aer.extensions.SnapshotDensityMatrix.is_parameterized" />

`SnapshotDensityMatrix.is_parameterized()`

Return True .IFF. instruction is parameterized else False

### mirror

<span id="qiskit.providers.aer.extensions.SnapshotDensityMatrix.mirror" />

`SnapshotDensityMatrix.mirror()`

For a composite instruction, reverse the order of sub-gates.

This is done by recursively mirroring all sub-instructions. It does not invert any gate.

**Returns**

a fresh gate with sub-gates reversed

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

### qasm

<span id="qiskit.providers.aer.extensions.SnapshotDensityMatrix.qasm" />

`SnapshotDensityMatrix.qasm()`

Return a default OpenQASM string for the instruction.

Derived instructions may override this to print in a different format (e.g. measure q\[0] -> c\[0];).

### repeat

<span id="qiskit.providers.aer.extensions.SnapshotDensityMatrix.repeat" />

`SnapshotDensityMatrix.repeat(n)`

Creates an instruction with gate repeated n amount of times.

**Parameters**

**n** (*int*) – Number of times to repeat the instruction

**Returns**

Containing the definition.

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

**Raises**

**CircuitError** – If n \< 1.

