---
title: RGate
description: API reference for qiskit.circuit.library.RGate
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.RGate
---

# RGate

<span id="qiskit.circuit.library.RGate" />

`RGate(theta, phi)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/circuit/library/standard_gates/r.py "view source code")

Bases: `qiskit.circuit.gate.Gate`

Rotation θ around the cos(φ)x + sin(φ)y axis.

**Circuit symbol:**

```python
     ┌──────┐
q_0: ┤ R(ϴ) ├
     └──────┘
```

**Matrix Representation:**

$$
 \begin{align}\begin{aligned}\newcommand{\th}{\frac{\theta}{2}}\\\begin{split}R(\theta, \phi) = e^{-i \th (\cos{\phi} x + \sin{\phi} y)} =
    \begin{pmatrix}
        \cos{\th} & -i e^{-i \phi} \sin{\th} \\
        -i e^{i \phi} \sin{\th} & \cos{\th}
    \end{pmatrix}\end{split}\end{aligned}\end{align} 
$$

Create new r single-qubit gate.

## Methods Defined Here

### inverse

<span id="qiskit.circuit.library.RGate.inverse" />

`RGate.inverse()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/circuit/library/standard_gates/r.py "view source code")

Invert this gate.

r(θ, φ)^dagger = r(-θ, φ)

## Attributes

<span id="qiskit.circuit.library.RGate.decompositions" />

### decompositions

Get the decompositions of the instruction from the SessionEquivalenceLibrary.

<span id="qiskit.circuit.library.RGate.definition" />

### definition

Return definition in terms of other basic gates.

<span id="qiskit.circuit.library.RGate.duration" />

### duration

Get the duration.

<span id="qiskit.circuit.library.RGate.label" />

### label

Return instruction label

**Return type**

`str`

<span id="qiskit.circuit.library.RGate.params" />

### params

return instruction params.

<span id="qiskit.circuit.library.RGate.unit" />

### unit

Get the time unit of duration.

