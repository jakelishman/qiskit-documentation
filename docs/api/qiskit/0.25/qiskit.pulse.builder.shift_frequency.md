---
title: shift_frequency
description: API reference for qiskit.pulse.builder.shift_frequency
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.pulse.builder.shift_frequency
---

# qiskit.pulse.builder.shift\_frequency

<span id="qiskit.pulse.builder.shift_frequency" />

`shift_frequency(frequency, channel, name=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.17/qiskit/pulse/builder.py "view source code")

Shift the `frequency` of a pulse `channel`.

Examples:

```python
from qiskit import pulse

d0 = pulse.DriveChannel(0)

with pulse.build() as pulse_prog:
    pulse.shift_frequency(1e9, d0)
```

**Parameters**

*   **frequency** (`float`) – Frequency in Hz to shift channel frequency by.
*   **channel** ([`PulseChannel`](qiskit.pulse.channels#qiskit.pulse.channels.PulseChannel "qiskit.pulse.channels.PulseChannel")) – Channel to shift frequency of.
*   **name** (`Optional`\[`str`]) – Name of the instruction.

