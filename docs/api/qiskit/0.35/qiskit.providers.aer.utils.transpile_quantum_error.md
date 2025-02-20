---
title: transpile_quantum_error
description: API reference for qiskit.providers.aer.utils.transpile_quantum_error
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.providers.aer.utils.transpile_quantum_error
---

# qiskit.providers.aer.utils.transpile\_quantum\_error

<span id="qiskit.providers.aer.utils.transpile_quantum_error" />

`transpile_quantum_error(error, **transpile_kwargs)`[GitHub](https://github.com/qiskit/qiskit-aer/tree/stable/0.10/qiskit/providers/aer/utils/noise_transformation.py "view source code")

Return a new quantum error containin transpiled circuits.

This returns a new QuantumError containing the circuits resulting from transpiling all error circuits using `qiskit.transpile()` with the passed keyword agruments.

**Parameters**

*   **error** (`QuantumError`) – the quantum error to be transformed.
*   **transpile\_kwargs** – kwargs for passing to qiskit transpile function.

**Return type**

`QuantumError`

**Returns**

The transformed quantum error.

**Raises**

**NoiseError** – if the transformation failed.

