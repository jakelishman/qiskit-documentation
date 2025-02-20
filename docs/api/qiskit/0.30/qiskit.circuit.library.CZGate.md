---
title: CZGate
description: API reference for qiskit.circuit.library.CZGate
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.CZGate
---

# CZGate

<span id="qiskit.circuit.library.CZGate" />

`CZGate(label=None, ctrl_state=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/circuit/library/standard_gates/z.py "view source code")

Bases: `qiskit.circuit.controlledgate.ControlledGate`

Controlled-Z gate.

This is a Clifford and symmetric gate.

**Circuit symbol:**

```python
q_0: ─■─
      │
q_1: ─■─
```

**Matrix representation:**

$$
\begin{split}CZ\ q_1, q_0 =
    |0\rangle\langle 0| \otimes I + |1\rangle\langle 1| \otimes Z =
    \begin{pmatrix}
        1 & 0 & 0 & 0 \\
        0 & 1 & 0 & 0 \\
        0 & 0 & 1 & 0 \\
        0 & 0 & 0 & -1
    \end{pmatrix}\end{split}
$$

In the computational basis, this gate flips the phase of the target qubit if the control qubit is in the $|1\rangle$ state.

Create new CZ gate.

## Methods Defined Here

### inverse

<span id="qiskit.circuit.library.CZGate.inverse" />

`CZGate.inverse()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/circuit/library/standard_gates/z.py "view source code")

Return inverted CZ gate (itself).

## Attributes

<span id="qiskit.circuit.library.CZGate.ctrl_state" />

### ctrl\_state

Return the control state of the gate as a decimal integer.

**Return type**

`int`

<span id="qiskit.circuit.library.CZGate.decompositions" />

### decompositions

Get the decompositions of the instruction from the SessionEquivalenceLibrary.

<span id="qiskit.circuit.library.CZGate.definition" />

### definition

Return definition in terms of other basic gates. If the gate has open controls, as determined from self.ctrl\_state, the returned definition is conjugated with X without changing the internal \_definition.

**Return type**

`List`

<span id="qiskit.circuit.library.CZGate.duration" />

### duration

Get the duration.

<span id="qiskit.circuit.library.CZGate.label" />

### label

Return instruction label

**Return type**

`str`

<span id="qiskit.circuit.library.CZGate.name" />

### name

Get name of gate. If the gate has open controls the gate name will become:

> \<original\_name\_o\<ctrl\_state>

where \<original\_name> is the gate name for the default case of closed control qubits and \<ctrl\_state> is the integer value of the control state for the gate.

**Return type**

`str`

<span id="qiskit.circuit.library.CZGate.num_ctrl_qubits" />

### num\_ctrl\_qubits

Get number of control qubits.

**Returns**

The number of control qubits for the gate.

**Return type**

int

<span id="qiskit.circuit.library.CZGate.params" />

### params

Get parameters from base\_gate.

**Returns**

List of gate parameters.

**Return type**

list

**Raises**

**CircuitError** – Controlled gate does not define a base gate

<span id="qiskit.circuit.library.CZGate.unit" />

### unit

Get the time unit of duration.

