---
title: SetMatrixProductState
description: API reference for qiskit.providers.aer.library.SetMatrixProductState
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.aer.library.SetMatrixProductState
---

# SetMatrixProductState

<span id="qiskit.providers.aer.library.SetMatrixProductState" />

`SetMatrixProductState(state)`[GitHub](https://github.com/qiskit/qiskit-aer/tree/stable/0.8/qiskit/providers/aer/library/set_instructions/set_matrix_product_state.py "view source code")

Bases: `qiskit.circuit.instruction.Instruction`

Set the matrix product state of the simulator

Create new instruction to set the matrix product state of the simulator.

**Parameters**

**state** (*Tuple\[List\[Tuple\[np.array\[complex\_t]]]], List\[List\[float]]*) – A matrix\_product\_state.

<Admonition title="Note" type="note">
  This set instruction must always be performed on the full width of qubits in a circuit. The matrix\_product\_state consists of a pair of vectors. The first is a vector of pairs of matrices of complex numbers. The second is a vector of vectors of double.
</Admonition>

## Methods

### add\_decomposition

<span id="qiskit.providers.aer.library.SetMatrixProductState.add_decomposition" />

`SetMatrixProductState.add_decomposition(decomposition)`

Add a decomposition of the instruction to the SessionEquivalenceLibrary.

### assemble

<span id="qiskit.providers.aer.library.SetMatrixProductState.assemble" />

`SetMatrixProductState.assemble()`

Assemble a QasmQobjInstruction

### broadcast\_arguments

<span id="qiskit.providers.aer.library.SetMatrixProductState.broadcast_arguments" />

`SetMatrixProductState.broadcast_arguments(qargs, cargs)`

Validation of the arguments.

**Parameters**

*   **qargs** (*List*) – List of quantum bit arguments.
*   **cargs** (*List*) – List of classical bit arguments.

**Yields**

*Tuple(List, List)* – A tuple with single arguments.

**Raises**

**CircuitError** – If the input is not valid. For example, the number of arguments does not match the gate expectation.

### c\_if

<span id="qiskit.providers.aer.library.SetMatrixProductState.c_if" />

`SetMatrixProductState.c_if(classical, val)`

Add classical condition on register or cbit classical and value val.

### copy

<span id="qiskit.providers.aer.library.SetMatrixProductState.copy" />

`SetMatrixProductState.copy(name=None)`

Copy of the instruction.

**Parameters**

**name** (*str*) – name to be given to the copied circuit, if None then the name stays the same.

**Returns**

**a copy of the current instruction, with the name**

updated if it was provided

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

### inverse

<span id="qiskit.providers.aer.library.SetMatrixProductState.inverse" />

`SetMatrixProductState.inverse()`

Invert this instruction.

If the instruction is composite (i.e. has a definition), then its definition will be recursively inverted.

Special instructions inheriting from Instruction can implement their own inverse (e.g. T and Tdg, Barrier, etc.)

**Returns**

a fresh instruction for the inverse

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

**Raises**

**CircuitError** – if the instruction is not composite and an inverse has not been implemented for it.

### is\_parameterized

<span id="qiskit.providers.aer.library.SetMatrixProductState.is_parameterized" />

`SetMatrixProductState.is_parameterized()`

Return True .IFF. instruction is parameterized else False

### mirror

<span id="qiskit.providers.aer.library.SetMatrixProductState.mirror" />

`SetMatrixProductState.mirror()`

DEPRECATED: use instruction.reverse\_ops().

**Returns**

**a new instruction with sub-instructions**

reversed.

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

### qasm

<span id="qiskit.providers.aer.library.SetMatrixProductState.qasm" />

`SetMatrixProductState.qasm()`

Return a default OpenQASM string for the instruction.

Derived instructions may override this to print in a different format (e.g. measure q\[0] -> c\[0];).

### repeat

<span id="qiskit.providers.aer.library.SetMatrixProductState.repeat" />

`SetMatrixProductState.repeat(n)`

Creates an instruction with gate repeated n amount of times.

**Parameters**

**n** (*int*) – Number of times to repeat the instruction

**Returns**

Containing the definition.

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

**Raises**

**CircuitError** – If n \< 1.

### reverse\_ops

<span id="qiskit.providers.aer.library.SetMatrixProductState.reverse_ops" />

`SetMatrixProductState.reverse_ops()`

For a composite instruction, reverse the order of sub-instructions.

This is done by recursively reversing all sub-instructions. It does not invert any gate.

**Returns**

**a new instruction with**

sub-instructions reversed.

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

### soft\_compare

<span id="qiskit.providers.aer.library.SetMatrixProductState.soft_compare" />

`SetMatrixProductState.soft_compare(other)`

Soft comparison between gates. Their names, number of qubits, and classical bit numbers must match. The number of parameters must match. Each parameter is compared. If one is a ParameterExpression then it is not taken into account.

**Parameters**

**other** (*instruction*) – other instruction.

**Returns**

are self and other equal up to parameter expressions.

**Return type**

bool

### validate\_parameter

<span id="qiskit.providers.aer.library.SetMatrixProductState.validate_parameter" />

`SetMatrixProductState.validate_parameter(parameter)`

Instruction parameters has no validation or normalization.

## Attributes

<span id="qiskit.providers.aer.library.SetMatrixProductState.decompositions" />

### decompositions

Get the decompositions of the instruction from the SessionEquivalenceLibrary.

<span id="qiskit.providers.aer.library.SetMatrixProductState.definition" />

### definition

Return definition in terms of other basic gates.

<span id="qiskit.providers.aer.library.SetMatrixProductState.duration" />

### duration

Get the duration.

<span id="qiskit.providers.aer.library.SetMatrixProductState.label" />

### label

Return instruction label

**Return type**

`str`

<span id="qiskit.providers.aer.library.SetMatrixProductState.params" />

### params

return instruction params.

<span id="qiskit.providers.aer.library.SetMatrixProductState.unit" />

### unit

Get the time unit of duration.

