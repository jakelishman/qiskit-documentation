---
title: ManagedJob
description: API reference for qiskit.providers.ibmq.managed.ManagedJob
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.ibmq.managed.ManagedJob
---

# qiskit.providers.ibmq.managed.ManagedJob

<span id="qiskit.providers.ibmq.managed.ManagedJob" />

`ManagedJob(start_index, experiments_count, job=None)`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.15/qiskit/providers/ibmq/managed/managedjob.py "view source code")

Job managed by the Job Manager.

ManagedJob constructor.

**Parameters**

*   **start\_index** (`int`) – Starting index of the experiment set.
*   **experiments\_count** (`int`) – Number of experiments.
*   **job** (`Optional`\[`IBMQJob`]) – Job to be managed, or `None` if not already known.

### \_\_init\_\_

<span id="qiskit.providers.ibmq.managed.ManagedJob.__init__" />

`__init__(start_index, experiments_count, job=None)`

ManagedJob constructor.

**Parameters**

*   **start\_index** (`int`) – Starting index of the experiment set.
*   **experiments\_count** (`int`) – Number of experiments.
*   **job** (`Optional`\[`IBMQJob`]) – Job to be managed, or `None` if not already known.

## Methods

|                                                                                                                                                                |                                              |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------- |
| [`__init__`](#qiskit.providers.ibmq.managed.ManagedJob.__init__ "qiskit.providers.ibmq.managed.ManagedJob.__init__")(start\_index, experiments\_count\[, job]) | ManagedJob constructor.                      |
| [`cancel`](#qiskit.providers.ibmq.managed.ManagedJob.cancel "qiskit.providers.ibmq.managed.ManagedJob.cancel")()                                               | Attempt to cancel the job.                   |
| [`error_message`](#qiskit.providers.ibmq.managed.ManagedJob.error_message "qiskit.providers.ibmq.managed.ManagedJob.error_message")()                          | Provide details about the reason of failure. |
| [`qobj`](#qiskit.providers.ibmq.managed.ManagedJob.qobj "qiskit.providers.ibmq.managed.ManagedJob.qobj")()                                                     | Return the Qobj for this job.                |
| [`result`](#qiskit.providers.ibmq.managed.ManagedJob.result "qiskit.providers.ibmq.managed.ManagedJob.result")(\[timeout, partial, refresh])                   | Return the result of the job.                |
| [`status`](#qiskit.providers.ibmq.managed.ManagedJob.status "qiskit.providers.ibmq.managed.ManagedJob.status")()                                               | Query the server for job status.             |
| [`submit`](#qiskit.providers.ibmq.managed.ManagedJob.submit "qiskit.providers.ibmq.managed.ManagedJob.submit")(circuits, job\_name, backend, …\[, …])          | Submit the job.                              |

### cancel

<span id="qiskit.providers.ibmq.managed.ManagedJob.cancel" />

`cancel()`

Attempt to cancel the job.

**Return type**

`None`

### error\_message

<span id="qiskit.providers.ibmq.managed.ManagedJob.error_message" />

`error_message()`

Provide details about the reason of failure.

**Return type**

`Optional`\[`str`]

**Returns**

An error report if the job failed or `None` otherwise.

### qobj

<span id="qiskit.providers.ibmq.managed.ManagedJob.qobj" />

`qobj()`

Return the Qobj for this job.

**Return type**

`Union`\[`QasmQobj`, `PulseQobj`, `None`]

**Returns**

The Qobj for this job or `None` if the Qobj could not be retrieved.

### result

<span id="qiskit.providers.ibmq.managed.ManagedJob.result" />

`result(timeout=None, partial=False, refresh=False)`

Return the result of the job.

**Parameters**

*   **timeout** (`Optional`\[`float`]) – Number of seconds to wait for job.
*   **partial** (`bool`) – If `True`, attempt to retrieve partial job results.
*   **refresh** (`bool`) – If `True`, re-query the server for the result. Otherwise return the cached value.

**Return type**

`Optional`\[`Result`]

**Returns**

Job result or `None` if result could not be retrieved.

**Raises**

[**IBMQJobTimeoutError**](qiskit.providers.ibmq.job.IBMQJobTimeoutError "qiskit.providers.ibmq.job.IBMQJobTimeoutError") – If the job does not return results before a specified timeout.

### status

<span id="qiskit.providers.ibmq.managed.ManagedJob.status" />

`status()`

Query the server for job status.

**Return type**

`Optional`\[`JobStatus`]

**Returns**

Current job status, or `None` if an error occurred.

### submit

<span id="qiskit.providers.ibmq.managed.ManagedJob.submit" />

`submit(circuits, job_name, backend, executor, submit_lock, job_share_level=None, job_tags=None, **run_config)`

Submit the job.

**Parameters**

*   **circuits** (`Union`\[`QuantumCircuit`, `Schedule`, `List`\[`Union`\[`QuantumCircuit`, `Schedule`]]]) – Circuits to run.
*   **job\_name** (`str`) – Name of the job.
*   **backend** (`IBMQBackend`) – Backend to execute the experiments on.
*   **executor** (`ThreadPoolExecutor`) – The thread pool used to submit the job.
*   **submit\_lock** (`allocate_lock`) – Lock used to synchronize job submission.
*   **job\_share\_level** (`Optional`\[`ApiJobShareLevel`]) – Job share level.
*   **job\_tags** (`Optional`\[`List`\[`str`]]) – Tags to be assigned to the job.
*   **\*\*run\_config** – Extra arguments used to configure the run.

**Return type**

`None`

