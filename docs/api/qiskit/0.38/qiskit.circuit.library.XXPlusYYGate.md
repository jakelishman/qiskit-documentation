---
title: XXPlusYYGate
description: API reference for qiskit.circuit.library.XXPlusYYGate
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.XXPlusYYGate
---

# XXPlusYYGate

<span id="qiskit.circuit.library.XXPlusYYGate" />

`XXPlusYYGate(theta, beta=0, label='{XX+YY}')`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/circuit/library/standard_gates/xx_plus_yy.py "view source code")

Bases: [`qiskit.circuit.gate.Gate`](qiskit.circuit.Gate "qiskit.circuit.gate.Gate")

XX+YY interaction gate.

A 2-qubit parameterized XX+YY interaction, also known as an XY gate. Its action is to induce a coherent rotation by some angle between $|01\rangle$ and $|10\rangle$.

**Circuit Symbol:**

```python
     ┌───────────────┐
q_0: ┤0              ├
     │  {XX+YY}(θ,β) │
q_1: ┤1              ├
     └───────────────┘
```

**Matrix Representation:**

$$
 \begin{align}\begin{aligned}\newcommand{\th}{\frac{\theta}{2}}\\\begin{split}R_{XX+YY}(\theta, \beta)\ q_0, q_1 =
  RZ_0(-\beta) \cdot \exp\left(-i \frac{\theta}{2} \frac{XX+YY}{2}\right) \cdot RZ_0(\beta) =
    \begin{pmatrix}
        1 & 0                     & 0                    & 0  \\
        0 & \cos\left(\th\right)             & -i\sin\left(\th\right)e^{-i\beta} & 0  \\
        0 & -i\sin\left(\th\right)e^{i\beta} & \cos\left(\th\right)            & 0  \\
        0 & 0                     & 0                    & 1
    \end{pmatrix}\end{split}\end{aligned}\end{align} 
$$

<Admonition title="Note" type="note">
  In Qiskit’s convention, higher qubit indices are more significant (little endian convention). In the above example we apply the gate on (q\_0, q\_1) which results in adding the (optional) phase defined by $beta$ on q\_0. Instead, if we apply it on (q\_1, q\_0), the phase is added on q\_1. If $beta$ is set to its default value of $0$, the gate is equivalent in big and little endian.

  ```python
       ┌───────────────┐
  q_0: ┤1              ├
       │  {XX+YY}(θ,β) │
  q_1: ┤0              ├
       └───────────────┘
  ```
</Admonition>

$$
 \begin{align}\begin{aligned}\newcommand{\th}{\frac{\theta}{2}}\\\begin{split}R_{XX+YY}(\theta, \beta)\ q_0, q_1 =
  RZ_1(-\beta) \cdot \exp\left(-i \frac{\theta}{2} \frac{XX+YY}{2}\right) \cdot RZ_1(\beta) =
    \begin{pmatrix}
        1 & 0                     & 0                    & 0  \\
        0 & \cos\left(\th\right)             & -i\sin\left(\th\right)e^{i\beta} & 0  \\
        0 & -i\sin\left(\th\right)e^{-i\beta} & \cos\left(\th\right)            & 0  \\
        0 & 0                     & 0                    & 1
    \end{pmatrix}\end{split}\end{aligned}\end{align} 
$$

Create new XX+YY gate.

**Parameters**

*   **theta** (`Union`\[[`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression"), `float`]) – The rotation angle.
*   **beta** (`Union`\[[`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression"), `float`]) – The phase angle.
*   **label** (`Optional`\[`str`]) – The label of the gate.

## Methods Defined Here

### inverse

<span id="qiskit.circuit.library.XXPlusYYGate.inverse" />

`XXPlusYYGate.inverse()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/circuit/library/standard_gates/xx_plus_yy.py "view source code")

Return inverse XX+YY gate (i.e. with the negative rotation angle and same phase angle).

## Attributes

<span id="qiskit.circuit.library.XXPlusYYGate.condition_bits" />

### condition\_bits

Get Clbits in condition.

**Return type**

`List`\[[`Clbit`](qiskit.circuit.Clbit "qiskit.circuit.classicalregister.Clbit")]

<span id="qiskit.circuit.library.XXPlusYYGate.decompositions" />

### decompositions

Get the decompositions of the instruction from the SessionEquivalenceLibrary.

<span id="qiskit.circuit.library.XXPlusYYGate.definition" />

### definition

Return definition in terms of other basic gates.

<span id="qiskit.circuit.library.XXPlusYYGate.duration" />

### duration

Get the duration.

<span id="qiskit.circuit.library.XXPlusYYGate.label" />

### label

Return instruction label

**Return type**

`str`

<span id="qiskit.circuit.library.XXPlusYYGate.name" />

### name

Return the name.

<span id="qiskit.circuit.library.XXPlusYYGate.num_clbits" />

### num\_clbits

Return the number of clbits.

<span id="qiskit.circuit.library.XXPlusYYGate.num_qubits" />

### num\_qubits

Return the number of qubits.

<span id="qiskit.circuit.library.XXPlusYYGate.params" />

### params

return instruction params.

<span id="qiskit.circuit.library.XXPlusYYGate.unit" />

### unit

Get the time unit of duration.

