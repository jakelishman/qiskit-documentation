---
title: set_frequency
description: API reference for qiskit.pulse.builder.set_frequency
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.pulse.builder.set_frequency
---

<span id="qiskit-pulse-builder-set-frequency" />

# qiskit.pulse.builder.set\_frequency

<span id="qiskit.pulse.builder.set_frequency" />

`set_frequency(frequency, channel)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.16/qiskit/pulse/builder.py "view source code")

Set the `frequency` of a pulse `channel`.

Examples:

```python
from qiskit import pulse

d0 = pulse.DriveChannel(0)

with pulse.build() as pulse_prog:
    pulse.set_frequency(1e9, d0)
```

**Parameters**

*   **frequency** (`float`) – Frequency in Hz to set channel to.
*   **channel** ([`PulseChannel`](qiskit.pulse.channels#pulsechannel "qiskit.pulse.channels.PulseChannel")) – Channel to set frequency of.

