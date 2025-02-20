---
title: circuit_scheduler_settings
description: API reference for qiskit.pulse.builder.circuit_scheduler_settings
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.pulse.builder.circuit_scheduler_settings
---

<span id="qiskit-pulse-builder-circuit-scheduler-settings" />

# qiskit.pulse.builder.circuit\_scheduler\_settings

<span id="qiskit.pulse.builder.circuit_scheduler_settings" />

`circuit_scheduler_settings(**settings)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.16/qiskit/pulse/builder.py "view source code")

Set the currently active circuit scheduler settings for this context.

Examples:

```python
from qiskit import pulse
from qiskit.test.mock import FakeOpenPulse2Q

backend = FakeOpenPulse2Q()

with pulse.build(backend):
    print(pulse.active_circuit_scheduler_settings())
    with pulse.circuit_scheduler_settings(method='alap'):
        print(pulse.active_circuit_scheduler_settings())
```

```python
{}
{'method': 'alap'}
```

**Return type**

`AbstractContextManager`\[`None`]

