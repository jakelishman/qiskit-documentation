---
title: remove_trivial_barriers
description: API reference for qiskit.pulse.transforms.remove_trivial_barriers
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.pulse.transforms.remove_trivial_barriers
---

# qiskit.pulse.transforms.remove\_trivial\_barriers

<span id="qiskit.pulse.transforms.remove_trivial_barriers" />

`remove_trivial_barriers(schedule)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/pulse/transforms/canonicalization.py "view source code")

Remove trivial barriers with 0 or 1 channels.

**Parameters**

**schedule** (`Schedule`) – A schedule to remove trivial barriers.

**Returns**

A schedule without trivial barriers

**Return type**

schedule

