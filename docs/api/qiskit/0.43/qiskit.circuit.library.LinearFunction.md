---
title: LinearFunction
description: API reference for qiskit.circuit.library.LinearFunction
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.LinearFunction
---

# LinearFunction

<span id="qiskit.circuit.library.LinearFunction" />

`LinearFunction(linear, validate_input=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/circuit/library/generalized_gates/linear_function.py "view source code")

Bases: [`Gate`](qiskit.circuit.Gate "qiskit.circuit.gate.Gate")

A linear reversible circuit on n qubits.

Internally, a linear function acting on n qubits is represented as a n x n matrix of 0s and 1s in numpy array format.

A linear function can be synthesized into CX and SWAP gates using the Patel–Markov–Hayes algorithm, as implemented in `cnot_synth()` based on reference \[1].

For efficiency, the internal n x n matrix is stored in the format expected by cnot\_synth, which is the big-endian (and not the little-endian) bit-ordering convention.

**Example:** the circuit

```python
q_0: ──■──
     ┌─┴─┐
q_1: ┤ X ├
     └───┘
q_2: ─────
```

is represented by a 3x3 linear matrix

$$
\begin{split}\begin{pmatrix}
    1 & 0 & 0 \\
    1 & 1 & 0 \\
    0 & 0 & 1
\end{pmatrix}\end{split}
$$

**References:**

\[1] Ketan N. Patel, Igor L. Markov, and John P. Hayes, Optimal synthesis of linear reversible circuits, Quantum Inf. Comput. 8(3) (2008). [Online at umich.edu.](https://web.eecs.umich.edu/~imarkov/pubs/jour/qic08-cnot.pdf)

Create a new linear function.

**Parameters**

*   **linear** (*list\[list] or ndarray\[bool] or* [*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – either an n x n matrix, describing the linear function, or a quantum circuit composed of linear gates only (currently supported gates are CX and SWAP).
*   **validate\_input** (*bool | None*) – if True, performs more expensive input validation checks, such as checking that a given n x n matrix is invertible.

**Raises**

**CircuitError** – if the input is invalid: either a matrix is non \{square, invertible}, or a quantum circuit contains non-linear gates.

## Methods Defined Here

<span id="qiskit-circuit-library-linearfunction-is-permutation" />

### is\_permutation

<span id="qiskit.circuit.library.LinearFunction.is_permutation" />

`LinearFunction.is_permutation()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/circuit/library/generalized_gates/linear_function.py "view source code")

Returns whether this linear function is a permutation, that is whether every row and every column of the n x n matrix has exactly one 1.

**Return type**

bool

<span id="qiskit-circuit-library-linearfunction-permutation-pattern" />

### permutation\_pattern

<span id="qiskit.circuit.library.LinearFunction.permutation_pattern" />

`LinearFunction.permutation_pattern()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/circuit/library/generalized_gates/linear_function.py "view source code")

This method first checks if a linear function is a permutation and raises a qiskit.circuit.exceptions.CircuitError if not. In the case that this linear function is a permutation, returns the permutation pattern.

<span id="qiskit-circuit-library-linearfunction-synthesize" />

### synthesize

<span id="qiskit.circuit.library.LinearFunction.synthesize" />

`LinearFunction.synthesize()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/circuit/library/generalized_gates/linear_function.py "view source code")

Synthesizes the linear function into a quantum circuit.

**Returns**

A circuit implementing the evolution.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

<span id="qiskit-circuit-library-linearfunction-validate-parameter" />

### validate\_parameter

<span id="qiskit.circuit.library.LinearFunction.validate_parameter" />

`LinearFunction.validate_parameter(parameter)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/circuit/library/generalized_gates/linear_function.py "view source code")

Parameter validation

## Attributes

<span id="qiskit.circuit.library.LinearFunction.condition_bits" />

### condition\_bits

Get Clbits in condition.

<span id="qiskit.circuit.library.LinearFunction.decompositions" />

### decompositions

Get the decompositions of the instruction from the SessionEquivalenceLibrary.

<span id="qiskit.circuit.library.LinearFunction.definition" />

### definition

Return definition in terms of other basic gates.

<span id="qiskit.circuit.library.LinearFunction.duration" />

### duration

Get the duration.

<span id="qiskit.circuit.library.LinearFunction.label" />

### label

Return instruction label

<span id="qiskit.circuit.library.LinearFunction.linear" />

### linear

Returns the n x n matrix representing this linear function

<span id="qiskit.circuit.library.LinearFunction.name" />

### name

Return the name.

<span id="qiskit.circuit.library.LinearFunction.num_clbits" />

### num\_clbits

Return the number of clbits.

<span id="qiskit.circuit.library.LinearFunction.num_qubits" />

### num\_qubits

Return the number of qubits.

<span id="qiskit.circuit.library.LinearFunction.original_circuit" />

### original\_circuit

Returns the original circuit used to construct this linear function (including None, when the linear function is not constructed from a circuit).

<span id="qiskit.circuit.library.LinearFunction.params" />

### params

return instruction params.

<span id="qiskit.circuit.library.LinearFunction.unit" />

### unit

Get the time unit of duration.

