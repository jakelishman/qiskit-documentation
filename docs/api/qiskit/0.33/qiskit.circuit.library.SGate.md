---
title: SGate
description: API reference for qiskit.circuit.library.SGate
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.SGate
---

# SGate

<span id="qiskit.circuit.library.SGate" />

`SGate(label=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/circuit/library/standard_gates/s.py "view source code")

Bases: `qiskit.circuit.gate.Gate`

Single qubit S gate (Z\*\*0.5).

It induces a $\pi/2$ phase, and is sometimes called the P gate (phase).

This is a Clifford gate and a square-root of Pauli-Z.

**Matrix Representation:**

$$
\begin{split}S = \begin{pmatrix}
        1 & 0 \\
        0 & i
    \end{pmatrix}\end{split}
$$

**Circuit symbol:**

```python
     ┌───┐
q_0: ┤ S ├
     └───┘
```

Equivalent to a $\pi/2$ radian rotation about the Z axis.

Create new S gate.

## Methods Defined Here

### inverse

<span id="qiskit.circuit.library.SGate.inverse" />

`SGate.inverse()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/circuit/library/standard_gates/s.py "view source code")

Return inverse of S (SdgGate).

## Attributes

<span id="qiskit.circuit.library.SGate.condition_bits" />

### condition\_bits

Get Clbits in condition.

**Return type**

`List`\[`Clbit`]

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

**Return type**

`str`

<span id="qiskit.circuit.library.SGate.params" />

### params

return instruction params.

<span id="qiskit.circuit.library.SGate.unit" />

### unit

Get the time unit of duration.

