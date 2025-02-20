---
title: synth_cz_depth_line_mr
description: API reference for qiskit.synthesis.synth_cz_depth_line_mr
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.synthesis.synth_cz_depth_line_mr
---

<span id="qiskit-synthesis-synth-cz-depth-line-mr" />

# qiskit.synthesis.synth\_cz\_depth\_line\_mr

<span id="qiskit.synthesis.synth_cz_depth_line_mr" />

`synth_cz_depth_line_mr(mat)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/synthesis/linear_phase/cz_depth_lnn.py "view source code")

Synthesis of a CZ circuit for linear nearest neighbour (LNN) connectivity, based on Maslov and Roetteler.

Note that this method *reverts* the order of qubits in the circuit, and returns a circuit containing CX and phase (S, Sdg or Z) gates.

**Parameters**

**mat** ([*ndarray*](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.25)")) – an upper-diagonal matrix representing the CZ circuit. mat\[i]\[j]=1 for i\<j represents a CZ(i,j) gate

**Returns**

a circuit implementation of the CZ circuit of depth 2\*n+2 for LNN connectivity.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

## Reference:

1.  Dmitri Maslov, Martin Roetteler, *Shorter stabilizer circuits via Bruhat decomposition and quantum circuit transformations*, [arXiv:1705.09176](https://arxiv.org/abs/1705.09176).

