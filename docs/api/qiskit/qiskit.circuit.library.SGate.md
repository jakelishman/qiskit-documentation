---
title: SGate
description: API reference for qiskit.circuit.library.SGate
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.SGate
---

# SGate

<span id="qiskit.circuit.library.SGate" />

`qiskit.circuit.library.SGate(*args, _force_mutable=False, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/circuit/library/standard_gates/s.py "view source code")

Bases: [`SingletonGate`](circuit_singleton#qiskit.circuit.singleton.SingletonGate "qiskit.circuit.singleton.SingletonGate")

Single qubit S gate (Z\*\*0.5).

It induces a $\pi/2$ phase, and is sometimes called the P gate (phase).

This is a Clifford gate and a square-root of Pauli-Z.

Can be applied to a [`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit") with the [`s()`](qiskit.circuit.QuantumCircuit#s "qiskit.circuit.QuantumCircuit.s") method.

**Matrix Representation:**

$$
S = \begin{pmatrix}
        1 & 0 \\
        0 & i
    \end{pmatrix}
$$

**Circuit symbol:**

```python
     ┌───┐
q_0: ┤ S ├
     └───┘
```

Equivalent to a $\pi/2$ radian rotation about the Z axis.

Create new S gate.

## Attributes

<span id="qiskit.circuit.library.SGate.base_class" />

### base\_class

Get the base class of this instruction. This is guaranteed to be in the inheritance tree of `self`.

The “base class” of an instruction is the lowest class in its inheritance tree that the object should be considered entirely compatible with for \_all\_ circuit applications. This typically means that the subclass is defined purely to offer some sort of programmer convenience over the base class, and the base class is the “true” class for a behavioural perspective. In particular, you should *not* override [`base_class`](#qiskit.circuit.library.SGate.base_class "qiskit.circuit.library.SGate.base_class") if you are defining a custom version of an instruction that will be implemented differently by hardware, such as an alternative measurement strategy, or a version of a parametrised gate with a particular set of parameters for the purposes of distinguishing it in a [`Target`](qiskit.transpiler.Target "qiskit.transpiler.Target") from the full parametrised gate.

This is often exactly equivalent to `type(obj)`, except in the case of singleton instances of standard-library instructions. These singleton instances are special subclasses of their base class, and this property will return that base. For example:

```python
>>> isinstance(XGate(), XGate)
True
>>> type(XGate()) is XGate
False
>>> XGate().base_class is XGate
True
```

In general, you should not rely on the precise class of an instruction; within a given circuit, it is expected that `Instruction.name` should be a more suitable discriminator in most situations.

<span id="qiskit.circuit.library.SGate.condition" />

### condition

The classical condition on the instruction.

<span id="qiskit.circuit.library.SGate.condition_bits" />

### condition\_bits

Get Clbits in condition.

<span id="qiskit.circuit.library.SGate.decompositions" />

### decompositions

Get the decompositions of the instruction from the SessionEquivalenceLibrary.

<span id="qiskit.circuit.library.SGate.definition" />

### definition

Return definition in terms of other basic gates.

<span id="qiskit.circuit.library.SGate.duration" />

### duration

Get the duration.

<span id="qiskit.circuit.library.SGate.label" />

### label

Return instruction label

<span id="qiskit.circuit.library.SGate.mutable" />

### mutable

Is this instance is a mutable unique instance or not.

If this attribute is `False` the gate instance is a shared singleton and is not mutable.

<span id="qiskit.circuit.library.SGate.name" />

### name

Return the name.

<span id="qiskit.circuit.library.SGate.num_clbits" />

### num\_clbits

Return the number of clbits.

<span id="qiskit.circuit.library.SGate.num_qubits" />

### num\_qubits

Return the number of qubits.

<span id="qiskit.circuit.library.SGate.params" />

### params

return instruction params.

<span id="qiskit.circuit.library.SGate.unit" />

### unit

Get the time unit of duration.

## Methods

### inverse

<span id="qiskit.circuit.library.SGate.inverse" />

`inverse()`

Return inverse of S (SdgGate).

### power

<span id="qiskit.circuit.library.SGate.power" />

`power(exponent)`

Raise gate to a power.

