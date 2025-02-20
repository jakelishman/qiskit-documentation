---
title: delay
description: API reference for qiskit.pulse.builder.delay
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.pulse.builder.delay
---

# qiskit.pulse.builder.delay

<span id="qiskit.pulse.builder.delay" />

`delay(duration, channel, name=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.17/qiskit/pulse/builder.py "view source code")

Delay on a `channel` for a `duration`.

Examples:

```python
from qiskit import pulse

d0 = pulse.DriveChannel(0)

with pulse.build() as pulse_prog:
    pulse.delay(10, d0)
```

**Parameters**

*   **duration** (`int`) – Number of cycles to delay for on `channel`.
*   **channel** ([`Channel`](qiskit.pulse.channels#qiskit.pulse.channels.Channel "qiskit.pulse.channels.Channel")) – Channel to delay on.
*   **name** (`Optional`\[`str`]) – Name of the instruction.

