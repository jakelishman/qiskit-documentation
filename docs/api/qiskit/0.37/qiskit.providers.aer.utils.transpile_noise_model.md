---
title: transpile_noise_model
description: API reference for qiskit.providers.aer.utils.transpile_noise_model
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.providers.aer.utils.transpile_noise_model
---

# qiskit.providers.aer.utils.transpile\_noise\_model

<span id="qiskit.providers.aer.utils.transpile_noise_model" />

`transpile_noise_model(noise_model, **transpile_kwargs)`[GitHub](https://github.com/qiskit/qiskit-aer/tree/stable/0.10/qiskit/providers/aer/utils/noise_transformation.py "view source code")

Return a new noise model with transpiled QuantumErrors.

This returns a new noise model containing the resulting errors from transpiling all QuantumErrors in the noise model using [`transpile_quantum_error()`](qiskit.providers.aer.utils.transpile_quantum_error "qiskit.providers.aer.utils.transpile_quantum_error") function with the passed keyword agruments.

**Parameters**

*   **noise\_model** ([`NoiseModel`](qiskit.providers.aer.noise.NoiseModel "qiskit.providers.aer.noise.noise_model.NoiseModel")) – the noise model to be transformed.
*   **transpile\_kwargs** – kwargs for passing to qiskit transpile function.

**Return type**

[`NoiseModel`](qiskit.providers.aer.noise.NoiseModel "qiskit.providers.aer.noise.noise_model.NoiseModel")

**Returns**

The transpiled noise model.

**Raises**

**NoiseError** – if the transformation failed.

