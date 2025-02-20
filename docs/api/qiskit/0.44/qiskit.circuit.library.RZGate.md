---
title: RZGate
description: API reference for qiskit.circuit.library.RZGate
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.RZGate
---

# RZGate

<span id="qiskit.circuit.library.RZGate" />

`qiskit.circuit.library.RZGate(phi, label=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.25/qiskit/circuit/library/standard_gates/rz.py "view source code")

Bases: [`Gate`](qiskit.circuit.Gate "qiskit.circuit.gate.Gate")

Single-qubit rotation about the Z axis.

This is a diagonal gate. It can be implemented virtually in hardware via framechanges (i.e. at zero error and duration).

Can be applied to a [`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit") with the [`rz()`](qiskit.circuit.QuantumCircuit#rz "qiskit.circuit.QuantumCircuit.rz") method.

**Circuit symbol:**

```python
     ┌───────┐
q_0: ┤ Rz(λ) ├
     └───────┘
```

**Matrix Representation:**

$$
\begin{split}RZ(\lambda) = \exp\left(-i\frac{\lambda}{2}Z\right) =
    \begin{pmatrix}
        e^{-i\frac{\lambda}{2}} & 0 \\
        0 & e^{i\frac{\lambda}{2}}
    \end{pmatrix}\end{split}
$$

<Admonition title="See also" type="note">
  `U1Gate` This gate is equivalent to U1 up to a phase factor.

  > $$
  > U1(\lambda) = e^{i{\lambda}/2}RZ(\lambda)
  > $$

  Reference for virtual Z gate implementation: [1612.00858](https://arxiv.org/abs/1612.00858)
</Admonition>

Create new RZ gate.

## Attributes

<span id="qiskit.circuit.library.RZGate.condition_bits" />

### condition\_bits

Get Clbits in condition.

<span id="qiskit.circuit.library.RZGate.decompositions" />

### decompositions

Get the decompositions of the instruction from the SessionEquivalenceLibrary.

<span id="qiskit.circuit.library.RZGate.definition" />

### definition

Return definition in terms of other basic gates.

<span id="qiskit.circuit.library.RZGate.duration" />

### duration

Get the duration.

<span id="qiskit.circuit.library.RZGate.label" />

### label

Return instruction label

<span id="qiskit.circuit.library.RZGate.name" />

### name

Return the name.

<span id="qiskit.circuit.library.RZGate.num_clbits" />

### num\_clbits

Return the number of clbits.

<span id="qiskit.circuit.library.RZGate.num_qubits" />

### num\_qubits

Return the number of qubits.

<span id="qiskit.circuit.library.RZGate.params" />

### params

return instruction params.

<span id="qiskit.circuit.library.RZGate.unit" />

### unit

Get the time unit of duration.

## Methods

### control

<span id="qiskit.circuit.library.RZGate.control" />

`control(num_ctrl_qubits=1, label=None, ctrl_state=None)`

Return a (multi-)controlled-RZ gate.

**Parameters**

*   **num\_ctrl\_qubits** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – number of control qubits.
*   **label** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)") *or None*) – An optional label for the gate \[Default: None]
*   **ctrl\_state** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")  *or*[*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)") *or None*) – control state expressed as integer, string (e.g. ‘110’), or None. If None, use all 1s.

**Returns**

controlled version of this gate.

**Return type**

[ControlledGate](qiskit.circuit.ControlledGate "qiskit.circuit.ControlledGate")

### inverse

<span id="qiskit.circuit.library.RZGate.inverse" />

`inverse()`

Return inverted RZ gate

$RZ(\lambda)^{\dagger} = RZ(-\lambda)$

### power

<span id="qiskit.circuit.library.RZGate.power" />

`power(exponent)`

Raise gate to a power.

