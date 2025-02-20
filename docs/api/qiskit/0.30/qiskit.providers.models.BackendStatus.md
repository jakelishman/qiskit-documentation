---
title: BackendStatus
description: API reference for qiskit.providers.models.BackendStatus
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.models.BackendStatus
---

# BackendStatus

<span id="qiskit.providers.models.BackendStatus" />

`BackendStatus(backend_name, backend_version, operational, pending_jobs, status_msg)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/providers/models/backendstatus.py "view source code")

Bases: `object`

Class representing Backend Status.

Initialize a BackendStatus object

**Parameters**

*   **backend\_name** (`str`) – The backend’s name
*   **backend\_version** (`str`) – The backend’s version of the form X.Y.Z
*   **operational** (`bool`) – True if the backend is operational
*   **pending\_jobs** (`int`) – The number of pending jobs on the backend
*   **status\_msg** (`str`) – The status msg for the backend

**Raises**

**QiskitError** – If the backend version is in an invalid format

## Methods

### from\_dict

<span id="qiskit.providers.models.BackendStatus.from_dict" />

`classmethod BackendStatus.from_dict(data)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/providers/models/backendstatus.py "view source code")

Create a new BackendStatus object from a dictionary.

**Parameters**

**data** (*dict*) – A dictionary representing the BaseBakend to create. It will be in the same format as output by [`to_dict()`](qiskit.providers.models.BackendStatus#to_dict "qiskit.providers.models.BackendStatus.to_dict").

**Returns**

The BackendStatus from the input dictionary.

**Return type**

[BackendStatus](qiskit.providers.models.BackendStatus "qiskit.providers.models.BackendStatus")

### to\_dict

<span id="qiskit.providers.models.BackendStatus.to_dict" />

`BackendStatus.to_dict()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/providers/models/backendstatus.py "view source code")

Return a dictionary format representation of the BackendStatus.

**Returns**

The dictionary form of the QobjHeader.

**Return type**

dict

