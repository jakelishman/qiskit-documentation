---
title: RuntimeJob
description: API reference for qiskit.providers.ibmq.runtime.RuntimeJob
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.ibmq.runtime.RuntimeJob
---

# RuntimeJob

<span id="qiskit.providers.ibmq.runtime.RuntimeJob" />

`RuntimeJob(backend, api_client, credentials, job_id, program_id, params=None, creation_date=None, user_callback=None, result_decoder=<class 'qiskit.providers.ibmq.runtime.program.result_decoder.ResultDecoder'>, image='')`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/runtime/runtime_job.py "view source code")

Bases: `object`

Representation of a runtime program execution.

A new `RuntimeJob` instance is returned when you call [`IBMRuntimeService.run`](qiskit.providers.ibmq.runtime.IBMRuntimeService#run "qiskit.providers.ibmq.runtime.IBMRuntimeService.run") to execute a runtime program, or [`IBMRuntimeService.job`](qiskit.providers.ibmq.runtime.IBMRuntimeService#job "qiskit.providers.ibmq.runtime.IBMRuntimeService.job") to retrieve a previously executed job.

If the program execution is successful, you can inspect the job’s status by calling [`status()`](qiskit.providers.ibmq.runtime.RuntimeJob#status "qiskit.providers.ibmq.runtime.RuntimeJob.status"). Job status can be one of the [`JobStatus`](qiskit.providers.JobStatus "qiskit.providers.JobStatus") members.

Some of the methods in this class are blocking, which means control may not be returned immediately. [`result()`](qiskit.providers.ibmq.runtime.RuntimeJob#result "qiskit.providers.ibmq.runtime.RuntimeJob.result") is an example of a blocking method:

```python
job = provider.runtime.run(...)

try:
    job_result = job.result()  # It will block until the job finishes.
    print("The job finished with result {}".format(job_result))
except RuntimeJobFailureError as ex:
    print("Job failed!: {}".format(ex))
```

If the program has any interim results, you can use the `callback` parameter of the [`run()`](qiskit.providers.ibmq.runtime.IBMRuntimeService#run "qiskit.providers.ibmq.runtime.IBMRuntimeService.run") method to stream the interim results. Alternatively, you can use the [`stream_results()`](qiskit.providers.ibmq.runtime.RuntimeJob#stream_results "qiskit.providers.ibmq.runtime.RuntimeJob.stream_results") method to stream the results at a later time, but before the job finishes.

RuntimeJob constructor.

**Parameters**

*   **backend** (`Backend`) – The backend instance used to run this job.
*   **api\_client** (`RuntimeClient`) – Object for connecting to the server.
*   **credentials** (`Credentials`) – Account credentials.
*   **job\_id** (`str`) – Job ID.
*   **program\_id** (`str`) – ID of the program this job is for.
*   **params** (`Optional`\[`Dict`]) – Job parameters.
*   **creation\_date** (`Optional`\[`str`]) – Job creation date, in UTC.
*   **user\_callback** (`Optional`\[`Callable`]) – User callback function.
*   **result\_decoder** (`Type`\[`ResultDecoder`]) – A [`ResultDecoder`](qiskit.providers.ibmq.runtime.ResultDecoder "qiskit.providers.ibmq.runtime.ResultDecoder") subclass used to decode job results.
*   **image** (`Optional`\[`str`]) – Runtime image used for this job: image\_name:tag.

## Methods

### backend

<span id="qiskit.providers.ibmq.runtime.RuntimeJob.backend" />

`RuntimeJob.backend()`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/runtime/runtime_job.py "view source code")

Return the backend where this job was executed.

**Return type**

`Backend`

**Returns**

Backend used for the job.

### cancel

<span id="qiskit.providers.ibmq.runtime.RuntimeJob.cancel" />

`RuntimeJob.cancel()`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/runtime/runtime_job.py "view source code")

Cancel the job.

**Raises**

*   **RuntimeInvalidStateError** – If the job is in a state that cannot be cancelled.
*   **QiskitRuntimeError** – If unable to cancel job.

**Return type**

`None`

### cancel\_result\_streaming

<span id="qiskit.providers.ibmq.runtime.RuntimeJob.cancel_result_streaming" />

`RuntimeJob.cancel_result_streaming()`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/runtime/runtime_job.py "view source code")

Cancel result streaming.

**Return type**

`None`

### error\_message

<span id="qiskit.providers.ibmq.runtime.RuntimeJob.error_message" />

`RuntimeJob.error_message()`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/runtime/runtime_job.py "view source code")

Returns the reason if the job failed.

**Return type**

`Optional`\[`str`]

**Returns**

Error message string or `None`.

### job\_id

<span id="qiskit.providers.ibmq.runtime.RuntimeJob.job_id" />

`RuntimeJob.job_id()`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/runtime/runtime_job.py "view source code")

Return a unique ID identifying the job.

**Return type**

`str`

**Returns**

Job ID.

### logs

<span id="qiskit.providers.ibmq.runtime.RuntimeJob.logs" />

`RuntimeJob.logs()`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/runtime/runtime_job.py "view source code")

Return job logs.

<Admonition title="Note" type="note">
  Job logs are only available after the job finishes.
</Admonition>

**Return type**

`str`

**Returns**

Job logs, including standard output and error.

**Raises**

**QiskitRuntimeError** – If a network error occurred.

### result

<span id="qiskit.providers.ibmq.runtime.RuntimeJob.result" />

`RuntimeJob.result(timeout=None, wait=5, decoder=None)`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/runtime/runtime_job.py "view source code")

Return the results of the job.

**Parameters**

*   **timeout** (`Optional`\[`float`]) – Number of seconds to wait for job.
*   **wait** (`float`) – Seconds between queries.
*   **decoder** (`Optional`\[`Type`\[`ResultDecoder`]]) – A [`ResultDecoder`](qiskit.providers.ibmq.runtime.ResultDecoder "qiskit.providers.ibmq.runtime.ResultDecoder") subclass used to decode job results.

**Return type**

`Any`

**Returns**

Runtime job result.

**Raises**

**RuntimeJobFailureError** – If the job failed.

### status

<span id="qiskit.providers.ibmq.runtime.RuntimeJob.status" />

`RuntimeJob.status()`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/runtime/runtime_job.py "view source code")

Return the status of the job.

**Return type**

`JobStatus`

**Returns**

Status of this job.

### stream\_results

<span id="qiskit.providers.ibmq.runtime.RuntimeJob.stream_results" />

`RuntimeJob.stream_results(callback, decoder=None)`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/runtime/runtime_job.py "view source code")

Start streaming job results.

**Parameters**

*   **callback** (`Callable`) –

    Callback function to be invoked for any interim results. The callback function will receive 2 positional parameters:

    > 1.  Job ID
    > 2.  Job interim result.

*   **decoder** (`Optional`\[`Type`\[`ResultDecoder`]]) – A [`ResultDecoder`](qiskit.providers.ibmq.runtime.ResultDecoder "qiskit.providers.ibmq.runtime.ResultDecoder") subclass used to decode job results.

**Raises**

**RuntimeInvalidStateError** – If a callback function is already streaming results or if the job already finished.

**Return type**

`None`

### wait\_for\_final\_state

<span id="qiskit.providers.ibmq.runtime.RuntimeJob.wait_for_final_state" />

`RuntimeJob.wait_for_final_state(timeout=None, wait=5)`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/runtime/runtime_job.py "view source code")

Poll the job status until it progresses to a final state such as `DONE` or `ERROR`.

**Parameters**

*   **timeout** (`Optional`\[`float`]) – Seconds to wait for the job. If `None`, wait indefinitely.
*   **wait** (`float`) – Seconds between queries.

**Raises**

[**JobTimeoutError**](qiskit.providers.JobTimeoutError "qiskit.providers.JobTimeoutError") – If the job does not reach a final state before the specified timeout.

**Return type**

`None`

## Attributes

<span id="qiskit.providers.ibmq.runtime.RuntimeJob.creation_date" />

### creation\_date

Job creation date in local time.

**Return type**

`Optional`\[`datetime`]

**Returns**

The job creation date as a datetime object, in local time, or `None` if creation date is not available.

<span id="qiskit.providers.ibmq.runtime.RuntimeJob.image" />

### image

Return the runtime image used for the job.

**Returns**

image\_name:tag or “” if the default image is used.

**Return type**

Runtime image

<span id="qiskit.providers.ibmq.runtime.RuntimeJob.inputs" />

### inputs

Job input parameters.

**Return type**

`Dict`

**Returns**

Input parameters used in this job.

<span id="qiskit.providers.ibmq.runtime.RuntimeJob.program_id" />

### program\_id

Program ID.

**Return type**

`str`

**Returns**

ID of the program this job is for.

