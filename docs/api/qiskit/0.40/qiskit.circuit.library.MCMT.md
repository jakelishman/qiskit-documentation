---
title: MCMT
description: API reference for qiskit.circuit.library.MCMT
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.MCMT
---

# MCMT

<span id="qiskit.circuit.library.MCMT" />

`MCMT(gate, num_ctrl_qubits, num_target_qubits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/circuit/library/generalized_gates/mcmt.py "view source code")

Bases: [`qiskit.circuit.quantumcircuit.QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit")

The multi-controlled multi-target gate, for an arbitrary singly controlled target gate.

For example, the H gate controlled on 3 qubits and acting on 2 target qubit is represented as:

```python
───■────
   │
───■────
   │
───■────
┌──┴───┐
┤0     ├
│  2-H │
┤1     ├
└──────┘
```

This default implementations requires no ancilla qubits, by broadcasting the target gate to the number of target qubits and using Qiskit’s generic control routine to control the broadcasted target on the control qubits. If ancilla qubits are available, a more efficient variant using the so-called V-chain decomposition can be used. This is implemented in [`MCMTVChain`](qiskit.circuit.library.MCMTVChain "qiskit.circuit.library.MCMTVChain").

Create a new multi-control multi-target gate.

**Parameters**

*   **gate** (`Union`\[[`Gate`](qiskit.circuit.Gate "qiskit.circuit.gate.Gate"), `Callable`\[\[[`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit"), [`Qubit`](qiskit.circuit.Qubit "qiskit.circuit.quantumregister.Qubit"), [`Qubit`](qiskit.circuit.Qubit "qiskit.circuit.quantumregister.Qubit")], [`Instruction`](qiskit.circuit.Instruction "qiskit.circuit.instruction.Instruction")]]) – The gate to be applied controlled on the control qubits and applied to the target qubits. Can be either a Gate or a circuit method. If it is a callable, it will be casted to a Gate.
*   **num\_ctrl\_qubits** (`int`) – The number of control qubits.
*   **num\_target\_qubits** (`int`) – The number of target qubits.

**Raises**

*   **AttributeError** – If the gate cannot be casted to a controlled gate.
*   **AttributeError** – If the number of controls or targets is 0.

## Methods Defined Here

### control

<span id="qiskit.circuit.library.MCMT.control" />

`MCMT.control(num_ctrl_qubits=1, label=None, ctrl_state=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/circuit/library/generalized_gates/mcmt.py "view source code")

Return the controlled version of the MCMT circuit.

### inverse

<span id="qiskit.circuit.library.MCMT.inverse" />

`MCMT.inverse()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/circuit/library/generalized_gates/mcmt.py "view source code")

Return the inverse MCMT circuit, which is itself.

## Attributes

<span id="qiskit.circuit.library.MCMT.ancillas" />

### ancillas

Returns a list of ancilla bits in the order that the registers were added.

**Return type**

`List`\[[`AncillaQubit`](qiskit.circuit.AncillaQubit "qiskit.circuit.quantumregister.AncillaQubit")]

<span id="qiskit.circuit.library.MCMT.calibrations" />

### calibrations

Return calibration dictionary.

The custom pulse definition of a given gate is of the form `{'gate_name': {(qubits, params): schedule}}`

**Return type**

`dict`

<span id="qiskit.circuit.library.MCMT.clbits" />

### clbits

Returns a list of classical bits in the order that the registers were added.

**Return type**

`List`\[[`Clbit`](qiskit.circuit.Clbit "qiskit.circuit.classicalregister.Clbit")]

<span id="qiskit.circuit.library.MCMT.data" />

### data

Return the circuit data (instructions and context).

**Returns**

a list-like object containing the [`CircuitInstruction`](qiskit.circuit.CircuitInstruction "qiskit.circuit.CircuitInstruction")s for each instruction.

**Return type**

QuantumCircuitData

<span id="qiskit.circuit.library.MCMT.extension_lib" />

### extension\_lib

`= 'include "qelib1.inc";'`

<span id="qiskit.circuit.library.MCMT.global_phase" />

### global\_phase

Return the global phase of the circuit in radians.

**Return type**

`Union`\[[`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression"), `float`]

<span id="qiskit.circuit.library.MCMT.header" />

### header

`= 'OPENQASM 2.0;'`

<span id="qiskit.circuit.library.MCMT.instances" />

### instances

`= 2368`

<span id="qiskit.circuit.library.MCMT.metadata" />

### metadata

The user provided metadata associated with the circuit

The metadata for the circuit is a user provided `dict` of metadata for the circuit. It will not be used to influence the execution or operation of the circuit, but it is expected to be passed between all transforms of the circuit (ie transpilation) and that providers will associate any circuit metadata with the results it returns from execution of that circuit.

**Return type**

`dict`

<span id="qiskit.circuit.library.MCMT.num_ancilla_qubits" />

### num\_ancilla\_qubits

Return the number of ancillas.

<span id="qiskit.circuit.library.MCMT.num_ancillas" />

### num\_ancillas

Return the number of ancilla qubits.

**Return type**

`int`

<span id="qiskit.circuit.library.MCMT.num_clbits" />

### num\_clbits

Return number of classical bits.

**Return type**

`int`

<span id="qiskit.circuit.library.MCMT.num_parameters" />

### num\_parameters

The number of parameter objects in the circuit.

**Return type**

`int`

<span id="qiskit.circuit.library.MCMT.num_qubits" />

### num\_qubits

Return number of qubits.

**Return type**

`int`

<span id="qiskit.circuit.library.MCMT.op_start_times" />

### op\_start\_times

Return a list of operation start times.

This attribute is enabled once one of scheduling analysis passes runs on the quantum circuit.

**Return type**

`List`\[`int`]

**Returns**

List of integers representing instruction start times. The index corresponds to the index of instruction in `QuantumCircuit.data`.

**Raises**

**AttributeError** – When circuit is not scheduled.

<span id="qiskit.circuit.library.MCMT.parameters" />

### parameters

The parameters defined in the circuit.

This attribute returns the [`Parameter`](qiskit.circuit.Parameter "qiskit.circuit.Parameter") objects in the circuit sorted alphabetically. Note that parameters instantiated with a [`ParameterVector`](qiskit.circuit.ParameterVector "qiskit.circuit.ParameterVector") are still sorted numerically.

## Examples

The snippet below shows that insertion order of parameters does not matter.

```python
>>> from qiskit.circuit import QuantumCircuit, Parameter
>>> a, b, elephant = Parameter("a"), Parameter("b"), Parameter("elephant")
>>> circuit = QuantumCircuit(1)
>>> circuit.rx(b, 0)
>>> circuit.rz(elephant, 0)
>>> circuit.ry(a, 0)
>>> circuit.parameters  # sorted alphabetically!
ParameterView([Parameter(a), Parameter(b), Parameter(elephant)])
```

Bear in mind that alphabetical sorting might be unituitive when it comes to numbers. The literal “10” comes before “2” in strict alphabetical sorting.

```python
>>> from qiskit.circuit import QuantumCircuit, Parameter
>>> angles = [Parameter("angle_1"), Parameter("angle_2"), Parameter("angle_10")]
>>> circuit = QuantumCircuit(1)
>>> circuit.u(*angles, 0)
>>> circuit.draw()
   ┌─────────────────────────────┐
q: ┤ U(angle_1,angle_2,angle_10) ├
   └─────────────────────────────┘
>>> circuit.parameters
ParameterView([Parameter(angle_1), Parameter(angle_10), Parameter(angle_2)])
```

To respect numerical sorting, a [`ParameterVector`](qiskit.circuit.ParameterVector "qiskit.circuit.ParameterVector") can be used.

```python
```

```python
>>> from qiskit.circuit import QuantumCircuit, Parameter, ParameterVector
>>> x = ParameterVector("x", 12)
>>> circuit = QuantumCircuit(1)
>>> for x_i in x:
...     circuit.rx(x_i, 0)
>>> circuit.parameters
ParameterView([
    ParameterVectorElement(x[0]), ParameterVectorElement(x[1]),
    ParameterVectorElement(x[2]), ParameterVectorElement(x[3]),
    ..., ParameterVectorElement(x[11])
])
```

**Return type**

`ParameterView`

**Returns**

The sorted [`Parameter`](qiskit.circuit.Parameter "qiskit.circuit.Parameter") objects in the circuit.

<span id="qiskit.circuit.library.MCMT.prefix" />

### prefix

`= 'circuit'`

<span id="qiskit.circuit.library.MCMT.qubits" />

### qubits

Returns a list of quantum bits in the order that the registers were added.

**Return type**

`List`\[[`Qubit`](qiskit.circuit.Qubit "qiskit.circuit.quantumregister.Qubit")]

