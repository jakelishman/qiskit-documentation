---
title: phase_offset
description: API reference for qiskit.pulse.builder.phase_offset
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.pulse.builder.phase_offset
---

# qiskit.pulse.builder.phase\_offset

<span id="qiskit.pulse.builder.phase_offset" />

`phase_offset(phase, *channels)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.17/qiskit/pulse/builder.py "view source code")

Shift the phase of input channels on entry into context and undo on exit.

Examples:

```python
import math

from qiskit import pulse

d0 = pulse.DriveChannel(0)

with pulse.build() as pulse_prog:
    with pulse.phase_offset(math.pi, d0):
        pulse.play(pulse.Constant(10, 1.0), d0)

assert len(pulse_prog.instructions) == 3
```

**Parameters**

*   **phase** (`float`) – Amount of phase offset in radians.
*   **channels** ([`PulseChannel`](qiskit.pulse.channels#qiskit.pulse.channels.PulseChannel "qiskit.pulse.channels.PulseChannel")) – Channels to offset phase of.

**Yields**

None

**Return type**

`AbstractContextManager`\[`None`]

