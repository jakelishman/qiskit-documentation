---
title: BosonicBasis
description: API reference for qiskit.chemistry.components.bosonic_bases.BosonicBasis
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.chemistry.components.bosonic_bases.BosonicBasis
---

# BosonicBasis

<span id="qiskit.chemistry.components.bosonic_bases.BosonicBasis" />

`BosonicBasis`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/chemistry/components/bosonic_bases/bosonic_basis.py "view source code")

Bases: `object`

Basis to express a second quantization Bosonic Hamiltonian.

## Methods

### convert

<span id="qiskit.chemistry.components.bosonic_bases.BosonicBasis.convert" />

`BosonicBasis.convert(threshold=1e-06)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/chemistry/components/bosonic_bases/bosonic_basis.py "view source code")

This prepares an array object representing a bosonic hamiltonian expressed in the harmonic basis. This object can directly be given to the BosonicOperator class to be mapped to a qubit hamiltonian.

**Parameters**

**threshold** (`float`) – the matrix elements of value below this threshold are discarded

**Return type**

`List`\[`List`\[`Tuple`\[`List`\[`List`\[`int`]], `float`]]]

**Returns**

List of modes for input to creation of a bosonic hamiltonian in the harmonic basis

**Raises**

**ValueError** – If problem with order value from computed modes

