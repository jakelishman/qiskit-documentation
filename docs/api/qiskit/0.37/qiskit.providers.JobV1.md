---
title: JobV1
description: API reference for qiskit.providers.JobV1
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.JobV1
---

# JobV1

<span id="qiskit.providers.JobV1" />

`JobV1(backend, job_id, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/providers/job.py "view source code")

Bases: [`qiskit.providers.job.Job`](qiskit.providers.Job "qiskit.providers.job.Job"), `abc.ABC`

Class to handle jobs

This first version of the Backend abstract class is written to be mostly backwards compatible with the legacy providers interface. This was done to ease the transition for users and provider maintainers to the new versioned providers. Expect, future versions of this abstract class to change the data model and interface.

Initializes the asynchronous job.

**Parameters**

*   **backend** ([`Backend`](qiskit.providers.Backend "qiskit.providers.backend.Backend")) – the backend used to run the job.
*   **job\_id** (`str`) – a unique id in the context of the backend used to run the job.
*   **kwargs** – Any key value metadata to associate with this job.

## Methods

### backend

<span id="qiskit.providers.JobV1.backend" />

`JobV1.backend()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/providers/job.py "view source code")

Return the backend where this job was executed.

**Return type**

[`Backend`](qiskit.providers.Backend "qiskit.providers.backend.Backend")

### cancel

<span id="qiskit.providers.JobV1.cancel" />

`JobV1.cancel()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/providers/job.py "view source code")

Attempt to cancel the job.

### cancelled

<span id="qiskit.providers.JobV1.cancelled" />

`JobV1.cancelled()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/providers/job.py "view source code")

Return whether the job has been cancelled.

**Return type**

`bool`

### done

<span id="qiskit.providers.JobV1.done" />

`JobV1.done()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/providers/job.py "view source code")

Return whether the job has successfully run.

**Return type**

`bool`

### in\_final\_state

<span id="qiskit.providers.JobV1.in_final_state" />

`JobV1.in_final_state()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/providers/job.py "view source code")

Return whether the job is in a final job state such as `DONE` or `ERROR`.

**Return type**

`bool`

### job\_id

<span id="qiskit.providers.JobV1.job_id" />

`JobV1.job_id()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/providers/job.py "view source code")

Return a unique id identifying the job.

**Return type**

`str`

### result

<span id="qiskit.providers.JobV1.result" />

`abstract JobV1.result()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/providers/job.py "view source code")

Return the results of the job.

### running

<span id="qiskit.providers.JobV1.running" />

`JobV1.running()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/providers/job.py "view source code")

Return whether the job is actively running.

**Return type**

`bool`

### status

<span id="qiskit.providers.JobV1.status" />

`abstract JobV1.status()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/providers/job.py "view source code")

Return the status of the job, among the values of `JobStatus`.

### submit

<span id="qiskit.providers.JobV1.submit" />

`abstract JobV1.submit()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/providers/job.py "view source code")

Submit the job to the backend for execution.

### wait\_for\_final\_state

<span id="qiskit.providers.JobV1.wait_for_final_state" />

`JobV1.wait_for_final_state(timeout=None, wait=5, callback=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/providers/job.py "view source code")

Poll the job status until it progresses to a final state such as `DONE` or `ERROR`.

**Parameters**

*   **timeout** (`Optional`\[`float`]) – Seconds to wait for the job. If `None`, wait indefinitely.

*   **wait** (`float`) – Seconds between queries.

*   **callback** (`Optional`\[`Callable`]) –

    Callback function invoked after each query. The following positional arguments are provided to the callback function:

    *   job\_id: Job ID
    *   job\_status: Status of the job from the last query
    *   job: This BaseJob instance

    Note: different subclass might provide different arguments to the callback function.

**Raises**

[**JobTimeoutError**](qiskit.providers.JobTimeoutError "qiskit.providers.JobTimeoutError") – If the job does not reach a final state before the specified timeout.

**Return type**

`None`

## Attributes

<span id="qiskit.providers.JobV1.version" />

### version

`= 1`

