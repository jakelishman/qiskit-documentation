---
title: snapshot
description: API reference for qiskit.pulse.builder.snapshot
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.pulse.builder.snapshot
---

# qiskit.pulse.builder.snapshot

<span id="qiskit.pulse.builder.snapshot" />

`snapshot(label, snapshot_type='statevector')`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.17/qiskit/pulse/builder.py "view source code")

Simulator snapshot.

Examples:

```python
from qiskit import pulse

with pulse.build() as pulse_prog:
    pulse.snapshot('first', 'statevector')
```

**Parameters**

*   **label** (`str`) – Label for snapshot.
*   **snapshot\_type** (`str`) – Type of snapshot.

