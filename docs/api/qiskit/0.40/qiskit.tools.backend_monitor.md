---
title: backend_monitor
description: API reference for qiskit.tools.backend_monitor
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.tools.backend_monitor
---

# qiskit.tools.backend\_monitor

<span id="qiskit.tools.backend_monitor" />

`backend_monitor(backend)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/tools/monitor/overview.py "view source code")

Monitor a single IBMQ backend.

**Parameters**

**backend** ([*IBMQBackend*](qiskit.providers.ibmq.IBMQBackend "qiskit.providers.ibmq.IBMQBackend")) – Backend to monitor.

**Raises**

*   **QiskitError** – Input is not a IBMQ backend.
*   **MissingOptionalLibraryError** – If qiskit-ibmq-provider is not installed

Examples: .. code-block:: python

> from qiskit.providers.ibmq import IBMQ from qiskit.tools.monitor import backend\_monitor provider = IBMQ.get\_provider(hub=’ibm-q’) backend\_monitor(provider.backends.ibmq\_lima)

