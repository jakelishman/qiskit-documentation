---
title: set_phase
description: API reference for qiskit.pulse.builder.set_phase
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.pulse.builder.set_phase
---

<span id="qiskit-pulse-builder-set-phase" />

# qiskit.pulse.builder.set\_phase

<span id="qiskit.pulse.builder.set_phase" />

`set_phase(phase, channel, name=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/pulse/builder.py "view source code")

Set the `phase` of a pulse `channel`.

Examples:

```python
import math

from qiskit import pulse

d0 = pulse.DriveChannel(0)

with pulse.build() as pulse_prog:
    pulse.set_phase(math.pi, d0)
```

**Parameters**

*   **phase** (*float*) – Phase in radians to set channel carrier signal to.
*   **channel** (*PulseChannel*) – Channel to set phase of.
*   **name** (*str | None*) – Name of the instruction.

