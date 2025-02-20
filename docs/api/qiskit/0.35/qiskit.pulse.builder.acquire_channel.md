---
title: acquire_channel
description: API reference for qiskit.pulse.builder.acquire_channel
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.pulse.builder.acquire_channel
---

# qiskit.pulse.builder.acquire\_channel

<span id="qiskit.pulse.builder.acquire_channel" />

`acquire_channel(qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/pulse/builder.py "view source code")

Return `AcquireChannel` for `qubit` on the active builder backend.

Examples:

```python
from qiskit import pulse
from qiskit.test.mock import FakeOpenPulse2Q

backend = FakeOpenPulse2Q()

with pulse.build(backend):
    assert pulse.acquire_channel(0) == pulse.AcquireChannel(0)
```

<Admonition title="Note" type="note">
  Requires the active builder context to have a backend set.
</Admonition>

**Return type**

[`AcquireChannel`](qiskit.pulse.channels.AcquireChannel "qiskit.pulse.channels.AcquireChannel")

