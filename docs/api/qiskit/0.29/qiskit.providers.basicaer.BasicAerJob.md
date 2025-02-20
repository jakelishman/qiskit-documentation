---
title: BasicAerJob
description: API reference for qiskit.providers.basicaer.BasicAerJob
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.basicaer.BasicAerJob
---

# BasicAerJob

<span id="qiskit.providers.basicaer.BasicAerJob" />

`BasicAerJob(backend, job_id, result)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/providers/basicaer/basicaerjob.py "view source code")

Bases: `qiskit.providers.job.JobV1`

BasicAerJob class.

Initializes the asynchronous job.

**Parameters**

*   **backend** – the backend used to run the job.
*   **job\_id** – a unique id in the context of the backend used to run the job.
*   **kwargs** – Any key value metadata to associate with this job.

## Methods

### backend

<span id="qiskit.providers.basicaer.BasicAerJob.backend" />

`BasicAerJob.backend()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/providers/basicaer/basicaerjob.py "view source code")

Return the instance of the backend used for this job.

### cancel

<span id="qiskit.providers.basicaer.BasicAerJob.cancel" />

`BasicAerJob.cancel()`

Attempt to cancel the job.

### cancelled

<span id="qiskit.providers.basicaer.BasicAerJob.cancelled" />

`BasicAerJob.cancelled()`

Return whether the job has been cancelled.

**Return type**

`bool`

### done

<span id="qiskit.providers.basicaer.BasicAerJob.done" />

`BasicAerJob.done()`

Return whether the job has successfully run.

**Return type**

`bool`

### in\_final\_state

<span id="qiskit.providers.basicaer.BasicAerJob.in_final_state" />

`BasicAerJob.in_final_state()`

Return whether the job is in a final job state such as `DONE` or `ERROR`.

**Return type**

`bool`

### job\_id

<span id="qiskit.providers.basicaer.BasicAerJob.job_id" />

`BasicAerJob.job_id()`

Return a unique id identifying the job.

**Return type**

`str`

### result

<span id="qiskit.providers.basicaer.BasicAerJob.result" />

`BasicAerJob.result(timeout=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/providers/basicaer/basicaerjob.py "view source code")

Get job result .

**Returns**

Result object

**Return type**

qiskit.Result

### running

<span id="qiskit.providers.basicaer.BasicAerJob.running" />

`BasicAerJob.running()`

Return whether the job is actively running.

**Return type**

`bool`

### status

<span id="qiskit.providers.basicaer.BasicAerJob.status" />

`BasicAerJob.status()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/providers/basicaer/basicaerjob.py "view source code")

Gets the status of the job by querying the Python’s future

**Returns**

The current JobStatus

**Return type**

[qiskit.providers.JobStatus](qiskit.providers.JobStatus "qiskit.providers.JobStatus")

### submit

<span id="qiskit.providers.basicaer.BasicAerJob.submit" />

`BasicAerJob.submit()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/providers/basicaer/basicaerjob.py "view source code")

Submit the job to the backend for execution.

**Raises**

[**JobError**](qiskit.providers.JobError "qiskit.providers.JobError") – if trying to re-submit the job.

### wait\_for\_final\_state

<span id="qiskit.providers.basicaer.BasicAerJob.wait_for_final_state" />

`BasicAerJob.wait_for_final_state(timeout=None, wait=5, callback=None)`

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

<span id="qiskit.providers.basicaer.BasicAerJob.version" />

### version

`= 1`

