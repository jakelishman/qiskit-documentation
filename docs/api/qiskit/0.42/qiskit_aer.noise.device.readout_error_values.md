---
title: readout_error_values
description: API reference for qiskit_aer.noise.device.readout_error_values
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit_aer.noise.device.readout_error_values
---

# qiskit\_aer.noise.device.readout\_error\_values

<span id="qiskit_aer.noise.device.readout_error_values" />

`readout_error_values(properties)`[GitHub](https://github.com/qiskit/qiskit-aer/tree/stable/0.12/qiskit_aer/noise/device/parameters.py "view source code")

Return readout error values from a devices BackendProperties.

**Parameters**

**properties** ([*BackendProperties*](qiskit.providers.models.BackendProperties "qiskit.providers.models.BackendProperties")) – device backend properties

**Returns**

A list of readout error values for qubits. If readout error information is not available None will be returned for value.

**Return type**

list

