---
title: approximate_noise_model
description: API reference for qiskit.providers.aer.utils.approximate_noise_model
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.providers.aer.utils.approximate_noise_model
---

# qiskit.providers.aer.utils.approximate\_noise\_model

<span id="qiskit.providers.aer.utils.approximate_noise_model" />

`approximate_noise_model(model, *, operator_string=None, operator_dict=None, operator_list=None)`[GitHub](https://github.com/qiskit/qiskit-aer/tree/stable/0.8/qiskit/providers/aer/utils/noise_transformation.py "view source code")

Return an approximate noise model.

**Parameters**

*   **model** ([*NoiseModel*](qiskit.providers.aer.noise.NoiseModel "qiskit.providers.aer.noise.NoiseModel")) – the noise model to be approximated.
*   **operator\_string** (*string or None*) – a name for a pre-made set of building blocks for the output channel (Default: None).
*   **operator\_dict** (*dict or None*) – a dictionary whose values are the building blocks for the output channel (Default: None).
*   **operator\_list** (*dict or None*) – list of building blocks for the output channel (Default: None).

**Returns**

the approximate noise model.

**Return type**

[NoiseModel](qiskit.providers.aer.noise.NoiseModel "qiskit.providers.aer.noise.NoiseModel")

**Raises**

*   **NoiseError** – if number of qubits is not supported or approximation
*   **failed.** –

## Additional Information:

The operator input precedence is: `list` \< `dict` \< `str`. If a string is given, dict is overwritten; if a dict is given, list is overwritten. Oossible values for string are `'pauli'`, `'reset'`, `'clifford'`. For further information see `NoiseTransformer.named_operators()`.

