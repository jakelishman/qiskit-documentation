---
title: DraperQFTAdder
description: API reference for qiskit.circuit.library.DraperQFTAdder
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.DraperQFTAdder
---

# DraperQFTAdder

<span id="qiskit.circuit.library.DraperQFTAdder" />

`qiskit.circuit.library.DraperQFTAdder(num_state_qubits, kind='fixed', name='DraperQFTAdder')`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/circuit/library/arithmetic/adders/draper_qft_adder.py "view source code")

Bases: `Adder`

A circuit that uses QFT to perform in-place addition on two qubit registers.

For registers with $n$ qubits, the QFT adder can perform addition modulo $2^n$ (with `kind="fixed"`) or ordinary addition by adding a carry qubits (with `kind="half"`).

As an example, a non-fixed\_point QFT adder circuit that performs addition on two 2-qubit sized registers is as follows:

```python
 a_0:   ─────────■──────■────────────────────────■────────────────
                 │      │                        │
 a_1:   ─────────┼──────┼────────■──────■────────┼────────────────
        ┌──────┐ │P(π)  │        │      │        │       ┌───────┐
 b_0:   ┤0     ├─■──────┼────────┼──────┼────────┼───────┤0      ├
        │      │        │P(π/2)  │P(π)  │        │       │       │
 b_1:   ┤1 qft ├────────■────────■──────┼────────┼───────┤1 iqft ├
        │      │                        │P(π/2)  │P(π/4) │       │
cout_0: ┤2     ├────────────────────────■────────■───────┤2      ├
        └──────┘                                         └───────┘
```

**References:**

\[1] T. G. Draper, Addition on a Quantum Computer, 2000. [arXiv:quant-ph/0008033](https://arxiv.org/pdf/quant-ph/0008033.pdf)

\[2] Ruiz-Perez et al., Quantum arithmetic with the Quantum Fourier Transform, 2017. [arXiv:1411.5949](https://arxiv.org/pdf/1411.5949.pdf)

\[3] Vedral et al., Quantum Networks for Elementary Arithmetic Operations, 1995. [arXiv:quant-ph/9511018](https://arxiv.org/pdf/quant-ph/9511018.pdf)

**Parameters**

*   **num\_state\_qubits** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – The number of qubits in either input register for state $|a\rangle$ or $|b\rangle$. The two input registers must have the same number of qubits.
*   **kind** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")) – The kind of adder, can be `'half'` for a half adder or `'fixed'` for a fixed-sized adder. A half adder contains a carry-out to represent the most-significant bit, but the fixed-sized adder doesn’t and hence performs addition modulo `2 ** num_state_qubits`.
*   **name** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")) – The name of the circuit object.

**Raises**

[**ValueError**](https://docs.python.org/3/library/exceptions.html#ValueError "(in Python v3.12)") – If `num_state_qubits` is lower than 1.

## Attributes

<span id="qiskit.circuit.library.DraperQFTAdder.ancillas" />

### ancillas

Returns a list of ancilla bits in the order that the registers were added.

<span id="qiskit.circuit.library.DraperQFTAdder.calibrations" />

### calibrations

Return calibration dictionary.

The custom pulse definition of a given gate is of the form `{'gate_name': {(qubits, params): schedule}}`

<span id="qiskit.circuit.library.DraperQFTAdder.clbits" />

### clbits

Returns a list of classical bits in the order that the registers were added.

<span id="qiskit.circuit.library.DraperQFTAdder.data" />

### data

Return the circuit data (instructions and context).

**Returns**

a list-like object containing the [`CircuitInstruction`](qiskit.circuit.CircuitInstruction "qiskit.circuit.CircuitInstruction")s for each instruction.

**Return type**

QuantumCircuitData

<span id="qiskit.circuit.library.DraperQFTAdder.extension_lib" />

### extension\_lib

`= 'include "qelib1.inc";'`

<span id="qiskit.circuit.library.DraperQFTAdder.global_phase" />

### global\_phase

Return the global phase of the current circuit scope in radians.

<span id="qiskit.circuit.library.DraperQFTAdder.header" />

### header

`= 'OPENQASM 2.0;'`

<span id="qiskit.circuit.library.DraperQFTAdder.instances" />

### instances

`= 167`

<span id="qiskit.circuit.library.DraperQFTAdder.layout" />

### layout

Return any associated layout information about the circuit

This attribute contains an optional [`TranspileLayout`](qiskit.transpiler.TranspileLayout "qiskit.transpiler.TranspileLayout") object. This is typically set on the output from [`transpile()`](compiler#qiskit.compiler.transpile "qiskit.compiler.transpile") or [`PassManager.run()`](qiskit.transpiler.PassManager#run "qiskit.transpiler.PassManager.run") to retain information about the permutations caused on the input circuit by transpilation.

There are two types of permutations caused by the [`transpile()`](compiler#qiskit.compiler.transpile "qiskit.compiler.transpile") function, an initial layout which permutes the qubits based on the selected physical qubits on the [`Target`](qiskit.transpiler.Target "qiskit.transpiler.Target"), and a final layout which is an output permutation caused by [`SwapGate`](qiskit.circuit.library.SwapGate "qiskit.circuit.library.SwapGate")s inserted during routing.

<span id="qiskit.circuit.library.DraperQFTAdder.metadata" />

### metadata

The user provided metadata associated with the circuit.

The metadata for the circuit is a user provided `dict` of metadata for the circuit. It will not be used to influence the execution or operation of the circuit, but it is expected to be passed between all transforms of the circuit (ie transpilation) and that providers will associate any circuit metadata with the results it returns from execution of that circuit.

<span id="qiskit.circuit.library.DraperQFTAdder.num_ancillas" />

### num\_ancillas

Return the number of ancilla qubits.

<span id="qiskit.circuit.library.DraperQFTAdder.num_clbits" />

### num\_clbits

Return number of classical bits.

<span id="qiskit.circuit.library.DraperQFTAdder.num_parameters" />

### num\_parameters

The number of parameter objects in the circuit.

<span id="qiskit.circuit.library.DraperQFTAdder.num_qubits" />

### num\_qubits

Return number of qubits.

<span id="qiskit.circuit.library.DraperQFTAdder.num_state_qubits" />

### num\_state\_qubits

The number of state qubits, i.e. the number of bits in each input register.

**Returns**

The number of state qubits.

<span id="qiskit.circuit.library.DraperQFTAdder.op_start_times" />

### op\_start\_times

Return a list of operation start times.

This attribute is enabled once one of scheduling analysis passes runs on the quantum circuit.

**Returns**

List of integers representing instruction start times. The index corresponds to the index of instruction in `QuantumCircuit.data`.

**Raises**

[**AttributeError**](https://docs.python.org/3/library/exceptions.html#AttributeError "(in Python v3.12)") – When circuit is not scheduled.

<span id="qiskit.circuit.library.DraperQFTAdder.parameters" />

### parameters

The parameters defined in the circuit.

This attribute returns the [`Parameter`](qiskit.circuit.Parameter "qiskit.circuit.Parameter") objects in the circuit sorted alphabetically. Note that parameters instantiated with a [`ParameterVector`](qiskit.circuit.ParameterVector "qiskit.circuit.ParameterVector") are still sorted numerically.

**Examples**

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

<span id="qiskit.circuit.library.DraperQFTAdder.prefix" />

### prefix

`= 'circuit'`

<span id="qiskit.circuit.library.DraperQFTAdder.qubits" />

### qubits

Returns a list of quantum bits in the order that the registers were added.

