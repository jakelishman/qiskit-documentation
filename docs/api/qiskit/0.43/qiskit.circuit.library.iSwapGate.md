---
title: iSwapGate
description: API reference for qiskit.circuit.library.iSwapGate
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.iSwapGate
---

# iSwapGate

<span id="qiskit.circuit.library.iSwapGate" />

`iSwapGate(label=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/circuit/library/standard_gates/iswap.py "view source code")

Bases: [`Gate`](qiskit.circuit.Gate "qiskit.circuit.gate.Gate")

iSWAP gate.

A 2-qubit XX+YY interaction. This is a Clifford and symmetric gate. Its action is to swap two qubit states and phase the $|01\rangle$ and $|10\rangle$ amplitudes by i.

Can be applied to a [`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit") with the [`iswap()`](qiskit.circuit.QuantumCircuit#iswap "qiskit.circuit.QuantumCircuit.iswap") method.

**Circuit Symbol:**

```python
q_0: ─⨂─
      │
q_1: ─⨂─
```

**Reference Implementation:**

```python
     ┌───┐┌───┐     ┌───┐
q_0: ┤ S ├┤ H ├──■──┤ X ├─────
     ├───┤└───┘┌─┴─┐└─┬─┘┌───┐
q_1: ┤ S ├─────┤ X ├──■──┤ H ├
     └───┘     └───┘     └───┘
```

**Matrix Representation:**

$$
\begin{split}iSWAP = R_{XX+YY}\left(-\frac{\pi}{2}\right)
  = \exp\left(i \frac{\pi}{4} \left(X{\otimes}X+Y{\otimes}Y\right)\right) =
    \begin{pmatrix}
        1 & 0 & 0 & 0 \\
        0 & 0 & i & 0 \\
        0 & i & 0 & 0 \\
        0 & 0 & 0 & 1
    \end{pmatrix}\end{split}
$$

This gate is equivalent to a SWAP up to a diagonal.

$$
\begin{split}iSWAP =
   \begin{pmatrix}
       1 & 0 & 0 & 0 \\
       0 & 0 & 1 & 0 \\
       0 & 1 & 0 & 0 \\
       0 & 0 & 0 & 1
   \end{pmatrix}
.  \begin{pmatrix}
       1 & 0 & 0 & 0 \\
       0 & i & 0 & 0 \\
       0 & 0 & i & 0 \\
       0 & 0 & 0 & 1
   \end{pmatrix}\end{split}
$$

Create new iSwap gate.

## Methods Defined Here

<span id="qiskit-circuit-library-iswapgate-power" />

### power

<span id="qiskit.circuit.library.iSwapGate.power" />

`iSwapGate.power(exponent)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/circuit/library/standard_gates/iswap.py "view source code")

Raise gate to a power.

## Attributes

<span id="qiskit.circuit.library.iSwapGate.condition_bits" />

### condition\_bits

Get Clbits in condition.

<span id="qiskit.circuit.library.iSwapGate.decompositions" />

### decompositions

Get the decompositions of the instruction from the SessionEquivalenceLibrary.

<span id="qiskit.circuit.library.iSwapGate.definition" />

### definition

Return definition in terms of other basic gates.

<span id="qiskit.circuit.library.iSwapGate.duration" />

### duration

Get the duration.

<span id="qiskit.circuit.library.iSwapGate.label" />

### label

Return instruction label

<span id="qiskit.circuit.library.iSwapGate.name" />

### name

Return the name.

<span id="qiskit.circuit.library.iSwapGate.num_clbits" />

### num\_clbits

Return the number of clbits.

<span id="qiskit.circuit.library.iSwapGate.num_qubits" />

### num\_qubits

Return the number of qubits.

<span id="qiskit.circuit.library.iSwapGate.params" />

### params

return instruction params.

<span id="qiskit.circuit.library.iSwapGate.unit" />

### unit

Get the time unit of duration.

