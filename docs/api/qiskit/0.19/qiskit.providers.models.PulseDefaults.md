---
title: PulseDefaults
description: API reference for qiskit.providers.models.PulseDefaults
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.models.PulseDefaults
---

# PulseDefaults

<span id="qiskit.providers.models.PulseDefaults" />

`PulseDefaults(qubit_freq_est, meas_freq_est, buffer, pulse_library, cmd_def, meas_kernel=None, discriminator=None, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/providers/models/pulsedefaults.py "view source code")

Description of default settings for Pulse systems. These are instructions or settings that may be good starting points for the Pulse user. The user may modify these defaults for custom scheduling.

Validate and reformat transport layer inputs to initialize.

**Parameters**

*   **qubit\_freq\_est** (`List`\[`float`]) – Estimated qubit frequencies in GHz.
*   **meas\_freq\_est** (`List`\[`float`]) – Estimated measurement cavity frequencies in GHz.
*   **buffer** (`int`) – Default buffer time (in units of dt) between pulses.
*   **pulse\_library** (`List`\[[`PulseLibraryItem`](qiskit.qobj.PulseLibraryItem "qiskit.qobj.pulse_qobj.PulseLibraryItem")]) – Pulse name and sample definitions.
*   **cmd\_def** (`List`\[[`Command`](qiskit.providers.models.Command "qiskit.providers.models.pulsedefaults.Command")]) – Operation name and definition in terms of Commands.
*   **meas\_kernel** (`Optional`\[`MeasurementKernel`]) – The measurement kernels
*   **discriminator** (`Optional`\[`Discriminator`]) – The discriminators
*   **\*\*kwargs** – Other attributes for the super class.

## Attributes

### circuit\_instruction\_map

Deprecated property, use `instruction_schedule_map` instead.

### meas\_freq\_est

Measurement frequencies in Hertz.

### qubit\_freq\_est

Qubit frequencies in Hertz.

## Methods

### from\_dict

<span id="qiskit.providers.models.PulseDefaults.from_dict" />

`classmethod PulseDefaults.from_dict(data)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/providers/models/pulsedefaults.py "view source code")

Create a new PulseDefaults object from a dictionary.

**Parameters**

**data** (*dict*) – A dictionary representing the PulseDefaults to create. It will be in the same format as output by [`to_dict()`](qiskit.providers.models.PulseDefaults#to_dict "qiskit.providers.models.PulseDefaults.to_dict").

**Returns**

The PulseDefaults from the input dictionary.

**Return type**

[PulseDefaults](qiskit.providers.models.PulseDefaults "qiskit.providers.models.PulseDefaults")

### to\_dict

<span id="qiskit.providers.models.PulseDefaults.to_dict" />

`PulseDefaults.to_dict()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/providers/models/pulsedefaults.py "view source code")

Return a dictionary format representation of the PulseDefaults.

**Returns**

The dictionary form of the PulseDefaults.

**Return type**

dict

