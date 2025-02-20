---
title: U3Gate
description: API reference for qiskit.circuit.library.U3Gate
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.U3Gate
---

# U3Gate

<span id="qiskit.circuit.library.U3Gate" />

`U3Gate(theta, phi, lam, label=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/circuit/library/standard_gates/u3.py "view source code")

Bases: `qiskit.circuit.gate.Gate`

Generic single-qubit rotation gate with 3 Euler angles.

Implemented using two X90 pulses on IBM Quantum systems:

$$
U3(\theta, \phi, \lambda) =
    RZ(\phi) RX(-\pi/2) RZ(\theta) RX(\pi/2) RZ(\lambda)
$$

**Circuit symbol:**

```python
     ┌───────────┐
q_0: ┤ U3(ϴ,φ,λ) ├
     └───────────┘
```

**Matrix Representation:**

$$
 \begin{align}\begin{aligned}\newcommand{\th}{\frac{\theta}{2}}\\\begin{split}U3(\theta, \phi, \lambda) =
    \begin{pmatrix}
        \cos(\th)          & -e^{i\lambda}\sin(\th) \\
        e^{i\phi}\sin(\th) & e^{i(\phi+\lambda)}\cos(\th)
    \end{pmatrix}\end{split}\end{aligned}\end{align} 
$$

**Examples:**

$$
U3(\theta, -\frac{\pi}{2}, \frac{\pi}{2}) = RX(\theta)
$$

$$
U3(\theta, 0, 0) = RY(\theta)
$$

Create new U3 gate.

## Methods Defined Here

### control

<span id="qiskit.circuit.library.U3Gate.control" />

`U3Gate.control(num_ctrl_qubits=1, label=None, ctrl_state=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/circuit/library/standard_gates/u3.py "view source code")

Return a (multi-)controlled-U3 gate.

**Parameters**

*   **num\_ctrl\_qubits** (*int*) – number of control qubits.
*   **label** (*str or None*) – An optional label for the gate \[Default: None]
*   **ctrl\_state** (*int or str or None*) – control state expressed as integer, string (e.g. ‘110’), or None. If None, use all 1s.

**Returns**

controlled version of this gate.

**Return type**

[ControlledGate](qiskit.circuit.ControlledGate "qiskit.circuit.ControlledGate")

### inverse

<span id="qiskit.circuit.library.U3Gate.inverse" />

`U3Gate.inverse()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/circuit/library/standard_gates/u3.py "view source code")

Return inverted U3 gate.

$U3(\theta,\phi,\lambda)^{\dagger} =U3(-\theta,-\lambda,-\phi)$)

## Attributes

<span id="qiskit.circuit.library.U3Gate.condition_bits" />

### condition\_bits

Get Clbits in condition.

**Return type**

`List`\[`Clbit`]

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

**Return type**

`str`

<span id="qiskit.circuit.library.U3Gate.params" />

### params

return instruction params.

<span id="qiskit.circuit.library.U3Gate.unit" />

### unit

Get the time unit of duration.

