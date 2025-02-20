---
title: Session
description: API reference for qiskit_ibm_provider.Session
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit_ibm_provider.Session
---

# Session

<span id="qiskit_ibm_provider.Session" />

`Session(max_time=None)`[GitHub](https://github.com/qiskit/qiskit-ibm-provider/tree/stable/0.7/qiskit_ibm_provider/session.py "view source code")

Class for creating a flexible Qiskit Runtime session.

A Qiskit Runtime `session` allows you to group a collection of iterative calls to the quantum computer. A session is started when the first job within the session is started. Subsequent jobs within the session are prioritized by the scheduler. Data used within a session, such as transpiled circuits, is also cached to avoid unnecessary overhead.

You can open a Qiskit Runtime session using this `Session` class and submit one or more jobs.

For example:

```python
from qiskit.test.reference_circuits import ReferenceCircuits
from qiskit_ibm_provider import IBMProvider

circ = ReferenceCircuits.bell()
backend = IBMProvider().get_backend("ibmq_qasm_simulator")
backend.open_session()
job = backend.run(circ)
print(f"Job ID: {job.job_id()}")
print(f"Result: {job.result()}")
# Close the session only if all jobs are finished and
# you don't need to run more in the session.
backend.cancel_session()
```

Session can also be used as a context manager:

```python
with backend.open_session() as session:
    job = backend.run(ReferenceCircuits.bell())
    assert job.job_id() == session.session_id
```

Session constructor.

**Parameters**

**max\_time** (`Union`\[`int`, `str`, `None`]) – (EXPERIMENTAL setting, can break between releases without warning) Maximum amount of time, a runtime session can be open before being forcibly closed. Can be specified as seconds (int) or a string like “2h 30m 40s”. This value must be in between 300 seconds and the [system imposed maximum](https://qiskit.org/documentation/partners/qiskit_ibm_runtime/faqs/max_execution_time.html).

**Raises**

**ValueError** – If an input value is invalid.

## Attributes

<span id="session-active" />

### active

<span id="qiskit_ibm_provider.Session.active" />

`bool`

Return the status of the session.

**Return type**

`bool`

**Returns**

True if the session is active, False otherwise.

<span id="session-session-id" />

### session\_id

<span id="qiskit_ibm_provider.Session.session_id" />

`str`

Return the session ID.

**Return type**

`str`

**Returns**

Session ID. None until a job runs in the session.

## Methods

<span id="session-cancel" />

### cancel

<span id="qiskit_ibm_provider.Session.cancel" />

`Session.cancel()`[GitHub](https://github.com/qiskit/qiskit-ibm-provider/tree/stable/0.7/qiskit_ibm_provider/session.py "view source code")

Set the session.\_active status to False

**Return type**

`None`

