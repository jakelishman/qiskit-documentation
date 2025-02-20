---
title: active_backend
description: API reference for qiskit.pulse.builder.active_backend
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.pulse.builder.active_backend
---

# qiskit.pulse.builder.active\_backend

<span id="qiskit.pulse.builder.active_backend" />

`active_backend()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/pulse/builder.py "view source code")

Get the backend of the currently active builder context.

**Returns**

**The active backend in the currently active**

builder context.

**Return type**

Union\[[Backend](qiskit.providers.Backend "qiskit.providers.Backend"), [BaseBackend](qiskit.providers.BaseBackend "qiskit.providers.BaseBackend")]

**Raises**

**exceptions.BackendNotSet** – If the builder does not have a backend set.

