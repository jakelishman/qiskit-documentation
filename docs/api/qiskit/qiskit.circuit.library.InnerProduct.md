---
title: InnerProduct
description: API reference for qiskit.circuit.library.InnerProduct
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.InnerProduct
---

# InnerProduct

<span id="qiskit.circuit.library.InnerProduct" />

`qiskit.circuit.library.InnerProduct(num_qubits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/circuit/library/boolean_logic/inner_product.py "view source code")

Bases: [`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit")

A 2n-qubit Boolean function that computes the inner product of two n-qubit vectors over $F_2$.

This implementation is a phase oracle which computes the following transform.

$$
\mathcal{IP}_{2n} : F_2^{2n} \rightarrow {-1, 1}
\mathcal{IP}_{2n}(x_1, \cdots, x_n, y_1, \cdots, y_n) = (-1)^{x.y}
$$

The corresponding unitary is a diagonal, which induces a -1 phase on any inputs where the inner product of the top and bottom registers is 1. Otherwise it keeps the input intact.

```python
q0_0: ─■──────────
       │
q0_1: ─┼──■───────
       │  │
q0_2: ─┼──┼──■────
       │  │  │
q0_3: ─┼──┼──┼──■─
       │  │  │  │
q1_0: ─■──┼──┼──┼─
          │  │  │
q1_1: ────■──┼──┼─
             │  │
q1_2: ───────■──┼─
                │
q1_3: ──────────■─
```

**Reference Circuit:**

![../\_images/qiskit-circuit-library-InnerProduct-1.png](/images/api/qiskit/qiskit-circuit-library-InnerProduct-1.png)

Return a circuit to compute the inner product of 2 n-qubit registers.

**Parameters**

**num\_qubits** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – width of top and bottom registers (half total circuit width)

## Attributes

<span id="qiskit.circuit.library.InnerProduct.ancillas" />

### ancillas

Returns a list of ancilla bits in the order that the registers were added.

<span id="qiskit.circuit.library.InnerProduct.calibrations" />

### calibrations

Return calibration dictionary.

The custom pulse definition of a given gate is of the form `{'gate_name': {(qubits, params): schedule}}`

<span id="qiskit.circuit.library.InnerProduct.clbits" />

### clbits

Returns a list of classical bits in the order that the registers were added.

<span id="qiskit.circuit.library.InnerProduct.data" />

### data

Return the circuit data (instructions and context).

**Returns**

a list-like object containing the [`CircuitInstruction`](qiskit.circuit.CircuitInstruction "qiskit.circuit.CircuitInstruction")s for each instruction.

**Return type**

QuantumCircuitData

<span id="qiskit.circuit.library.InnerProduct.extension_lib" />

### extension\_lib

`= 'include "qelib1.inc";'`

<span id="qiskit.circuit.library.InnerProduct.global_phase" />

### global\_phase

Return the global phase of the current circuit scope in radians.

<span id="qiskit.circuit.library.InnerProduct.header" />

### header

`= 'OPENQASM 2.0;'`

<span id="qiskit.circuit.library.InnerProduct.instances" />

### instances

`= 179`

<span id="qiskit.circuit.library.InnerProduct.layout" />

### layout

Return any associated layout information about the circuit

This attribute contains an optional [`TranspileLayout`](qiskit.transpiler.TranspileLayout "qiskit.transpiler.TranspileLayout") object. This is typically set on the output from [`transpile()`](compiler#qiskit.compiler.transpile "qiskit.compiler.transpile") or [`PassManager.run()`](qiskit.transpiler.PassManager#run "qiskit.transpiler.PassManager.run") to retain information about the permutations caused on the input circuit by transpilation.

There are two types of permutations caused by the [`transpile()`](compiler#qiskit.compiler.transpile "qiskit.compiler.transpile") function, an initial layout which permutes the qubits based on the selected physical qubits on the [`Target`](qiskit.transpiler.Target "qiskit.transpiler.Target"), and a final layout which is an output permutation caused by [`SwapGate`](qiskit.circuit.library.SwapGate "qiskit.circuit.library.SwapGate")s inserted during routing.

<span id="qiskit.circuit.library.InnerProduct.metadata" />

### metadata

The user provided metadata associated with the circuit.

The metadata for the circuit is a user provided `dict` of metadata for the circuit. It will not be used to influence the execution or operation of the circuit, but it is expected to be passed between all transforms of the circuit (ie transpilation) and that providers will associate any circuit metadata with the results it returns from execution of that circuit.

<span id="qiskit.circuit.library.InnerProduct.num_ancillas" />

### num\_ancillas

Return the number of ancilla qubits.

<span id="qiskit.circuit.library.InnerProduct.num_clbits" />

### num\_clbits

Return number of classical bits.

<span id="qiskit.circuit.library.InnerProduct.num_parameters" />

### num\_parameters

The number of parameter objects in the circuit.

<span id="qiskit.circuit.library.InnerProduct.num_qubits" />

### num\_qubits

Return number of qubits.

<span id="qiskit.circuit.library.InnerProduct.op_start_times" />

### op\_start\_times

Return a list of operation start times.

This attribute is enabled once one of scheduling analysis passes runs on the quantum circuit.

**Returns**

List of integers representing instruction start times. The index corresponds to the index of instruction in `QuantumCircuit.data`.

**Raises**

[**AttributeError**](https://docs.python.org/3/library/exceptions.html#AttributeError "(in Python v3.12)") – When circuit is not scheduled.

<span id="qiskit.circuit.library.InnerProduct.parameters" />

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

<span id="qiskit.circuit.library.InnerProduct.prefix" />

### prefix

`= 'circuit'`

<span id="qiskit.circuit.library.InnerProduct.qubits" />

### qubits

Returns a list of quantum bits in the order that the registers were added.

