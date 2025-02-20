---
title: RC3XGate
description: API reference for qiskit.circuit.library.RC3XGate
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.RC3XGate
---

# RC3XGate

<span id="qiskit.circuit.library.RC3XGate" />

`qiskit.circuit.library.RC3XGate(*args, _force_mutable=False, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/circuit/library/standard_gates/x.py "view source code")

Bases: [`SingletonGate`](circuit_singleton#qiskit.circuit.singleton.SingletonGate "qiskit.circuit.singleton.SingletonGate")

The simplified 3-controlled Toffoli gate.

The simplified Toffoli gate implements the Toffoli gate up to relative phases. Note, that the simplified Toffoli is not equivalent to the Toffoli. But can be used in places where the Toffoli gate is uncomputed again.

This concrete implementation is from [https://arxiv.org/abs/1508.03273](https://arxiv.org/abs/1508.03273), the complete circuit of Fig. 4.

Can be applied to a [`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit") with the [`rcccx()`](qiskit.circuit.QuantumCircuit#rcccx "qiskit.circuit.QuantumCircuit.rcccx") method.

Create a new RC3X gate.

## Attributes

<span id="qiskit.circuit.library.RC3XGate.base_class" />

### base\_class

Get the base class of this instruction. This is guaranteed to be in the inheritance tree of `self`.

The “base class” of an instruction is the lowest class in its inheritance tree that the object should be considered entirely compatible with for \_all\_ circuit applications. This typically means that the subclass is defined purely to offer some sort of programmer convenience over the base class, and the base class is the “true” class for a behavioural perspective. In particular, you should *not* override [`base_class`](#qiskit.circuit.library.RC3XGate.base_class "qiskit.circuit.library.RC3XGate.base_class") if you are defining a custom version of an instruction that will be implemented differently by hardware, such as an alternative measurement strategy, or a version of a parametrised gate with a particular set of parameters for the purposes of distinguishing it in a [`Target`](qiskit.transpiler.Target "qiskit.transpiler.Target") from the full parametrised gate.

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

<span id="qiskit.circuit.library.RC3XGate.condition" />

### condition

The classical condition on the instruction.

<span id="qiskit.circuit.library.RC3XGate.condition_bits" />

### condition\_bits

Get Clbits in condition.

<span id="qiskit.circuit.library.RC3XGate.decompositions" />

### decompositions

Get the decompositions of the instruction from the SessionEquivalenceLibrary.

<span id="qiskit.circuit.library.RC3XGate.definition" />

### definition

Return definition in terms of other basic gates.

<span id="qiskit.circuit.library.RC3XGate.duration" />

### duration

Get the duration.

<span id="qiskit.circuit.library.RC3XGate.label" />

### label

Return instruction label

<span id="qiskit.circuit.library.RC3XGate.mutable" />

### mutable

Is this instance is a mutable unique instance or not.

If this attribute is `False` the gate instance is a shared singleton and is not mutable.

<span id="qiskit.circuit.library.RC3XGate.name" />

### name

Return the name.

<span id="qiskit.circuit.library.RC3XGate.num_clbits" />

### num\_clbits

Return the number of clbits.

<span id="qiskit.circuit.library.RC3XGate.num_qubits" />

### num\_qubits

Return the number of qubits.

<span id="qiskit.circuit.library.RC3XGate.params" />

### params

return instruction params.

<span id="qiskit.circuit.library.RC3XGate.unit" />

### unit

Get the time unit of duration.

