---
title: shift_phase
description: API reference for qiskit.pulse.builder.shift_phase
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.pulse.builder.shift_phase
---

# qiskit.pulse.builder.shift\_phase

<span id="qiskit.pulse.builder.shift_phase" />

`shift_phase(phase, channel, name=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/pulse/builder.py "view source code")

Shift the `phase` of a pulse `channel`.

Examples:

```python
import math

from qiskit import pulse

d0 = pulse.DriveChannel(0)

with pulse.build() as pulse_prog:
    pulse.shift_phase(math.pi, d0)
```

**Parameters**

*   **phase** (`float`) – Phase in radians to shift channel carrier signal by.
*   **channel** (`PulseChannel`) – Channel to shift phase of.
*   **name** (`Optional`\[`str`]) – Name of the instruction.

