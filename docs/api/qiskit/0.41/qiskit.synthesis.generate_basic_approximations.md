---
title: generate_basic_approximations
description: API reference for qiskit.synthesis.generate_basic_approximations
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.synthesis.generate_basic_approximations
---

# qiskit.synthesis.generate\_basic\_approximations

<span id="qiskit.synthesis.generate_basic_approximations" />

`generate_basic_approximations(basis_gates, depth, filename=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/synthesis/discrete_basis/generate_basis_approximations.py "view source code")

Generates a list of `GateSequence``s with the gates in ``basic_gates`.

**Parameters**

*   **basis\_gates** (*list\[str |* [*Gate*](qiskit.circuit.Gate "qiskit.circuit.Gate")*]*) – The gates from which to create the sequences of gates.
*   **depth** (*int*) – The maximum depth of the approximations.
*   **filename** (*str | None*) – If provided, the basic approximations are stored in this file.

**Return type**

list\[GateSequence]

**Returns**

List of `GateSequences` using the gates in `basic_gates`.

**Raises**

**ValueError** – If `basis_gates` contains an invalid gate identifier.

