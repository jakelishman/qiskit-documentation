---
title: XXDecomposer
description: API reference for qiskit.quantum_info.XXDecomposer
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.quantum_info.XXDecomposer
---

# XXDecomposer

<span id="qiskit.quantum_info.XXDecomposer" />

`XXDecomposer(euler_basis='U', embodiments=None, backup_optimizer=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/quantum_info/synthesis/xx_decompose/decomposer.py "view source code")

Bases: `object`

A class for optimal decomposition of 2-qubit unitaries into 2-qubit basis gates of XX type (i.e., each locally equivalent to CAN(alpha, 0, 0) for a possibly varying alpha).

**Parameters**

*   **euler\_basis** (`str`) – Basis string provided to OneQubitEulerDecomposer for 1Q synthesis. Defaults to “U”.
*   **embodiments** (`Optional`\[`dict`]) – A dictionary mapping interaction strengths alpha to native circuits which embody the gate CAN(alpha, 0, 0). Strengths are taken so that pi/2 represents the class of a full CX.
*   **backup\_optimizer** (`Optional`\[`Callable`]) – If supplied, defers synthesis to this callable when XXDecomposer has no efficient decomposition of its own. Useful for special cases involving 2 or 3 applications of XX(pi/2), in which case standard synthesis methods provide lower 1Q gate count.

<Admonition title="Note" type="note">
  If `embodiments` is not passed, or if an entry is missing, it will be populated as needed using the method `_default_embodiment`.
</Admonition>

## Methods

### num\_basis\_gates

<span id="qiskit.quantum_info.XXDecomposer.num_basis_gates" />

`XXDecomposer.num_basis_gates(unitary)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/quantum_info/synthesis/xx_decompose/decomposer.py "view source code")

Counts the number of gates that would be emitted during re-synthesis.

NOTE: Used by ConsolidateBlocks.

