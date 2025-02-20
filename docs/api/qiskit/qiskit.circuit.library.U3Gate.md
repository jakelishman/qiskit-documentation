---
title: U3Gate
description: API reference for qiskit.circuit.library.U3Gate
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.U3Gate
---

# U3Gate

<span id="qiskit.circuit.library.U3Gate" />

`qiskit.circuit.library.U3Gate(theta, phi, lam, label=None, *, duration=None, unit='dt')`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/circuit/library/standard_gates/u3.py "view source code")

Bases: [`Gate`](qiskit.circuit.Gate "qiskit.circuit.gate.Gate")

Generic single-qubit rotation gate with 3 Euler angles.

<Admonition title="Warning" type="caution">
  This gate is deprecated. Instead, the following replacements should be used

  $$
  U3(\theta, \phi, \lambda) =  U(\theta, \phi, \lambda)
  $$

  ```python
  circuit = QuantumCircuit(1)
  circuit.u(theta, phi, lambda)
  ```
</Admonition>

**Circuit symbol:**

```python
     ┌───────────┐
q_0: ┤ U3(ϴ,φ,λ) ├
     └───────────┘
```

**Matrix Representation:**

$$
\newcommand{\rotationangle}{\frac{\theta}{2}}

U3(\theta, \phi, \lambda) =
    \begin{pmatrix}
        \cos\left(\rotationangle\right) & -e^{i\lambda}\sin\left(\rotationangle\right) \\
        e^{i\phi}\sin\left(\rotationangle\right) &
        e^{i(\phi+\lambda)}\cos\left(\rotationangle\right)
    \end{pmatrix}
$$

<Admonition title="Note" type="note">
  The matrix representation shown here differs from the [OpenQASM 2.0 specification](https://doi.org/10.48550/arXiv.1707.03429) by a global phase of $e^{i(\phi+\lambda)/2}$.
</Admonition>

**Examples:**

$$
U3(\theta, \phi, \lambda) = e^{-i \frac{\pi + \theta}{2}} P(\phi + \pi) \sqrt{X}
P(\theta + \pi) \sqrt{X} P(\lambda)
$$

$$
U3\left(\theta, -\frac{\pi}{2}, \frac{\pi}{2}\right) = RX(\theta)
$$

$$
U3(\theta, 0, 0) = RY(\theta)
$$

Create new U3 gate.

## Attributes

<span id="qiskit.circuit.library.U3Gate.base_class" />

### base\_class

Get the base class of this instruction. This is guaranteed to be in the inheritance tree of `self`.

The “base class” of an instruction is the lowest class in its inheritance tree that the object should be considered entirely compatible with for \_all\_ circuit applications. This typically means that the subclass is defined purely to offer some sort of programmer convenience over the base class, and the base class is the “true” class for a behavioural perspective. In particular, you should *not* override [`base_class`](#qiskit.circuit.library.U3Gate.base_class "qiskit.circuit.library.U3Gate.base_class") if you are defining a custom version of an instruction that will be implemented differently by hardware, such as an alternative measurement strategy, or a version of a parametrised gate with a particular set of parameters for the purposes of distinguishing it in a [`Target`](qiskit.transpiler.Target "qiskit.transpiler.Target") from the full parametrised gate.

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

<span id="qiskit.circuit.library.U3Gate.condition" />

### condition

The classical condition on the instruction.

<span id="qiskit.circuit.library.U3Gate.condition_bits" />

### condition\_bits

Get Clbits in condition.

<span id="qiskit.circuit.library.U3Gate.decompositions" />

### decompositions

Get the decompositions of the instruction from the SessionEquivalenceLibrary.

<span id="qiskit.circuit.library.U3Gate.definition" />

### definition

Return definition in terms of other basic gates.

<span id="qiskit.circuit.library.U3Gate.duration" />

### duration

Get the duration.

<span id="qiskit.circuit.library.U3Gate.label" />

### label

Return instruction label

<span id="qiskit.circuit.library.U3Gate.mutable" />

### mutable

Is this instance is a mutable unique instance or not.

If this attribute is `False` the gate instance is a shared singleton and is not mutable.

<span id="qiskit.circuit.library.U3Gate.name" />

### name

Return the name.

<span id="qiskit.circuit.library.U3Gate.num_clbits" />

### num\_clbits

Return the number of clbits.

<span id="qiskit.circuit.library.U3Gate.num_qubits" />

### num\_qubits

Return the number of qubits.

<span id="qiskit.circuit.library.U3Gate.params" />

### params

return instruction params.

<span id="qiskit.circuit.library.U3Gate.unit" />

### unit

Get the time unit of duration.

## Methods

### control

<span id="qiskit.circuit.library.U3Gate.control" />

`control(num_ctrl_qubits=1, label=None, ctrl_state=None)`

Return a (multi-)controlled-U3 gate.

**Parameters**

*   **num\_ctrl\_qubits** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – number of control qubits.
*   **label** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)") *or None*) – An optional label for the gate \[Default: None]
*   **ctrl\_state** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")  *or*[*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)") *or None*) – control state expressed as integer, string (e.g. ‘110’), or None. If None, use all 1s.

**Returns**

controlled version of this gate.

**Return type**

[ControlledGate](qiskit.circuit.ControlledGate "qiskit.circuit.ControlledGate")

### inverse

<span id="qiskit.circuit.library.U3Gate.inverse" />

`inverse()`

Return inverted U3 gate.

$U3(\theta,\phi,\lambda)^{\dagger} =U3(-\theta,-\lambda,-\phi)$)

