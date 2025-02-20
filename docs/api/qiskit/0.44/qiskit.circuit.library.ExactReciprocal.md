---
title: ExactReciprocal
description: API reference for qiskit.circuit.library.ExactReciprocal
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.ExactReciprocal
---

# ExactReciprocal

<span id="qiskit.circuit.library.ExactReciprocal" />

`qiskit.circuit.library.ExactReciprocal(num_state_qubits, scaling, neg_vals=False, name='1/x')`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.25/qiskit/circuit/library/arithmetic/exact_reciprocal.py "view source code")

Bases: [`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit")

Exact reciprocal

$$
|x\rangle |0\rangle \mapsto \cos(1/x)|x\rangle|0\rangle + \sin(1/x)|x\rangle |1\rangle
$$

**Parameters**

*   **num\_state\_qubits** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – The number of qubits representing the value to invert.
*   **scaling** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")) – Scaling factor $s$ of the reciprocal function, i.e. to compute $s / x$.
*   **neg\_vals** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – Whether $x$ might represent negative values. In this case the first qubit is the sign, with $|1\rangle$ for negative and $|0\rangle$ for positive. For the negative case it is assumed that the remaining string represents $1 - x$. This is because $e^{-2 \pi i x} = e^{2 \pi i (1 - x)}$ for $x \in [0,1)$.
*   **name** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")) – The name of the object.

<Admonition title="Note" type="note">
  It is assumed that the binary string $x$ represents a number \< 1.
</Admonition>

## Attributes

<span id="qiskit.circuit.library.ExactReciprocal.ancillas" />

### ancillas

Returns a list of ancilla bits in the order that the registers were added.

<span id="qiskit.circuit.library.ExactReciprocal.calibrations" />

### calibrations

Return calibration dictionary.

The custom pulse definition of a given gate is of the form `{'gate_name': {(qubits, params): schedule}}`

<span id="qiskit.circuit.library.ExactReciprocal.clbits" />

### clbits

Returns a list of classical bits in the order that the registers were added.

<span id="qiskit.circuit.library.ExactReciprocal.data" />

### data

Return the circuit data (instructions and context).

**Returns**

a list-like object containing the [`CircuitInstruction`](qiskit.circuit.CircuitInstruction "qiskit.circuit.CircuitInstruction")s for each instruction.

**Return type**

QuantumCircuitData

<span id="qiskit.circuit.library.ExactReciprocal.extension_lib" />

### extension\_lib

`= 'include "qelib1.inc";'`

<span id="qiskit.circuit.library.ExactReciprocal.global_phase" />

### global\_phase

Return the global phase of the circuit in radians.

<span id="qiskit.circuit.library.ExactReciprocal.header" />

### header

`= 'OPENQASM 2.0;'`

<span id="qiskit.circuit.library.ExactReciprocal.instances" />

### instances

`= 127`

<span id="qiskit.circuit.library.ExactReciprocal.layout" />

### layout

Return any associated layout information about the circuit

This attribute contains an optional [`TranspileLayout`](qiskit.transpiler.TranspileLayout "qiskit.transpiler.TranspileLayout") object. This is typically set on the output from [`transpile()`](compiler#qiskit.compiler.transpile "qiskit.compiler.transpile") or [`PassManager.run()`](qiskit.transpiler.PassManager#run "qiskit.transpiler.PassManager.run") to retain information about the permutations caused on the input circuit by transpilation.

There are two types of permutations caused by the [`transpile()`](compiler#qiskit.compiler.transpile "qiskit.compiler.transpile") function, an initial layout which permutes the qubits based on the selected physical qubits on the [`Target`](qiskit.transpiler.Target "qiskit.transpiler.Target"), and a final layout which is an output permutation caused by [`SwapGate`](qiskit.circuit.library.SwapGate "qiskit.circuit.library.SwapGate")s inserted during routing.

<span id="qiskit.circuit.library.ExactReciprocal.metadata" />

### metadata

The user provided metadata associated with the circuit.

The metadata for the circuit is a user provided `dict` of metadata for the circuit. It will not be used to influence the execution or operation of the circuit, but it is expected to be passed between all transforms of the circuit (ie transpilation) and that providers will associate any circuit metadata with the results it returns from execution of that circuit.

<span id="qiskit.circuit.library.ExactReciprocal.num_ancillas" />

### num\_ancillas

Return the number of ancilla qubits.

<span id="qiskit.circuit.library.ExactReciprocal.num_clbits" />

### num\_clbits

Return number of classical bits.

<span id="qiskit.circuit.library.ExactReciprocal.num_parameters" />

### num\_parameters

The number of parameter objects in the circuit.

<span id="qiskit.circuit.library.ExactReciprocal.num_qubits" />

### num\_qubits

Return number of qubits.

<span id="qiskit.circuit.library.ExactReciprocal.op_start_times" />

### op\_start\_times

Return a list of operation start times.

This attribute is enabled once one of scheduling analysis passes runs on the quantum circuit.

**Returns**

List of integers representing instruction start times. The index corresponds to the index of instruction in `QuantumCircuit.data`.

**Raises**

[**AttributeError**](https://docs.python.org/3/library/exceptions.html#AttributeError "(in Python v3.12)") – When circuit is not scheduled.

<span id="qiskit.circuit.library.ExactReciprocal.parameters" />

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

Bear in mind that alphabetical sorting might be unintuitive when it comes to numbers. The literal “10” comes before “2” in strict alphabetical sorting.

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

**Returns**

The sorted [`Parameter`](qiskit.circuit.Parameter "qiskit.circuit.Parameter") objects in the circuit.

<span id="qiskit.circuit.library.ExactReciprocal.prefix" />

### prefix

`= 'circuit'`

<span id="qiskit.circuit.library.ExactReciprocal.qubits" />

### qubits

Returns a list of quantum bits in the order that the registers were added.

