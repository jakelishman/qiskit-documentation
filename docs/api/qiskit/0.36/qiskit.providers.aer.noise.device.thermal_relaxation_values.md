---
title: thermal_relaxation_values
description: API reference for qiskit.providers.aer.noise.device.thermal_relaxation_values
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.providers.aer.noise.device.thermal_relaxation_values
---

# qiskit.providers.aer.noise.device.thermal\_relaxation\_values

<span id="qiskit.providers.aer.noise.device.thermal_relaxation_values" />

`thermal_relaxation_values(properties)`[GitHub](https://github.com/qiskit/qiskit-aer/tree/stable/0.10/qiskit/providers/aer/noise/device/parameters.py "view source code")

Return T1, T2 and frequency values from a devices BackendProperties.

**Parameters**

**properties** ([*BackendProperties*](qiskit.providers.models.BackendProperties "qiskit.providers.models.BackendProperties")) – device backend properties

**Returns**

A list of tuples `(T1, T2, freq)` for each qubit in the device. If $T_1$, $T_2$, or frequency cannot be found for qubit a value of `Numpy.inf` will be used.

**Return type**

list

## Additional Information:

$T_1$ and $T_2$ values are returned in microsecond (µs) units. Frequency is returned in gigahertz (GHz) units.

