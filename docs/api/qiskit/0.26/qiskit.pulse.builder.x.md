---
title: x
description: API reference for qiskit.pulse.builder.x
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.pulse.builder.x
---

# qiskit.pulse.builder.x

<span id="qiskit.pulse.builder.x" />

`x(qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.17/qiskit/pulse/builder.py "view source code")

Call a `XGate` on the input physical qubit.

<Admonition title="Note" type="note">
  Calling gates directly within the pulse builder namespace will be deprecated in the future in favor of tight integration with a circuit builder interface which is under development.
</Admonition>

Examples:

```python
from qiskit import pulse
from qiskit.test.mock import FakeOpenPulse2Q

backend = FakeOpenPulse2Q()

with pulse.build(backend) as pulse_prog:
    pulse.x(0)
```

