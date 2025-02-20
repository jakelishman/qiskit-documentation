---
title: IBMQJob
description: API reference for qiskit.providers.ibmq.job.IBMQJob
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.ibmq.job.IBMQJob
---

# IBMQJob

<span id="qiskit.providers.ibmq.job.IBMQJob" />

`IBMQJob(backend, api_client, job_id, creation_date, status, kind=None, name=None, time_per_step=None, result=None, qobj=None, error=None, tags=None, run_mode=None, share_level=None, client_info=None, experiment_id=None, **kwargs)`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/job/ibmqjob.py "view source code")

Bases: `qiskit.providers.job.JobV1`

Representation of a job that executes on an IBM Quantum Experience backend.

The job may be executed on a simulator or a real device. A new `IBMQJob` instance is returned when you call `IBMQBackend.run()` to submit a job to a particular backend.

If the job is successfully submitted, you can inspect the job’s status by calling [`status()`](qiskit.providers.ibmq.job.IBMQJob#status "qiskit.providers.ibmq.job.IBMQJob.status"). Job status can be one of the [`JobStatus`](qiskit.providers.JobStatus "qiskit.providers.JobStatus") members. For example:

```python
from qiskit.providers.jobstatus import JobStatus

job = backend.run(...)

try:
    job_status = job.status()  # Query the backend server for job status.
    if job_status is JobStatus.RUNNING:
        print("The job is still running")
except IBMQJobApiError as ex:
    print("Something wrong happened!: {}".format(ex))
```

<Admonition title="Note" type="note">
  An error may occur when querying the remote server to get job information. The most common errors are temporary network failures and server errors, in which case an [`IBMQJobApiError`](qiskit.providers.ibmq.job.IBMQJobApiError "qiskit.providers.ibmq.job.IBMQJobApiError") is raised. These errors usually clear quickly, so retrying the operation is likely to succeed.
</Admonition>

Some of the methods in this class are blocking, which means control may not be returned immediately. [`result()`](qiskit.providers.ibmq.job.IBMQJob#result "qiskit.providers.ibmq.job.IBMQJob.result") is an example of a blocking method:

```python
job = backend.run(...)

try:
    job_result = job.result()  # It will block until the job finishes.
    print("The job finished with result {}".format(job_result))
except JobError as ex:
    print("Something wrong happened!: {}".format(ex))
```

Job information retrieved from the server is attached to the `IBMQJob` instance as attributes. Given that Qiskit and the server can be updated independently, some of these attributes might be deprecated or experimental. Supported attributes can be retrieved via methods. For example, you can use [`creation_date()`](qiskit.providers.ibmq.job.IBMQJob#creation_date "qiskit.providers.ibmq.job.IBMQJob.creation_date") to retrieve the job creation date, which is a supported attribute.

IBMQJob constructor.

**Parameters**

*   **backend** (`IBMQBackend`) – The backend instance used to run this job.
*   **api\_client** (`AccountClient`) – Object for connecting to the server.
*   **job\_id** (`str`) – Job ID.
*   **creation\_date** (`str`) – Job creation date.
*   **status** (`str`) – Job status returned by the server.
*   **kind** (`Optional`\[`str`]) – Job type.
*   **name** (`Optional`\[`str`]) – Job name.
*   **time\_per\_step** (`Optional`\[`dict`]) – Time spent for each processing step.
*   **result** (`Optional`\[`dict`]) – Job result.
*   **qobj** (`Union`\[`dict`, `QasmQobj`, `PulseQobj`, `None`]) – Qobj for this job.
*   **error** (`Optional`\[`dict`]) – Job error.
*   **tags** (`Optional`\[`List`\[`str`]]) – Job tags.
*   **run\_mode** (`Optional`\[`str`]) – Scheduling mode the job runs in.
*   **share\_level** (`Optional`\[`str`]) – Level the job can be shared with.
*   **client\_info** (`Optional`\[`Dict`\[`str`, `str`]]) – Client version.
*   **experiment\_id** (`Optional`\[`str`]) – ID of the experiment this job is part of.
*   **kwargs** (`Any`) – Additional job attributes.

## Methods

### backend

<span id="qiskit.providers.ibmq.job.IBMQJob.backend" />

`IBMQJob.backend()`

Return the backend where this job was executed.

**Return type**

`Backend`

### backend\_options

<span id="qiskit.providers.ibmq.job.IBMQJob.backend_options" />

`IBMQJob.backend_options()`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/job/ibmqjob.py "view source code")

Return the backend configuration options used for this job.

Options that are not applicable to the job execution are not returned. Some but not all of the options with default values are returned. You can use [`qiskit.providers.ibmq.IBMQBackend.options`](qiskit.providers.ibmq.IBMQBackend#options "qiskit.providers.ibmq.IBMQBackend.options") to see all backend options.

**Return type**

`Dict`\[`str`, `Any`]

**Returns**

Backend options used for this job. An empty dictionary is returned if the options cannot be retrieved.

### cancel

<span id="qiskit.providers.ibmq.job.IBMQJob.cancel" />

`IBMQJob.cancel()`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/job/ibmqjob.py "view source code")

Attempt to cancel the job.

<Admonition title="Note" type="note">
  Depending on the state the job is in, it might be impossible to cancel the job.
</Admonition>

**Return type**

`bool`

**Returns**

`True` if the job is cancelled, else `False`.

**Raises**

[**IBMQJobApiError**](qiskit.providers.ibmq.job.IBMQJobApiError "qiskit.providers.ibmq.job.IBMQJobApiError") – If an unexpected error occurred when communicating with the server.

### cancelled

<span id="qiskit.providers.ibmq.job.IBMQJob.cancelled" />

`IBMQJob.cancelled()`

Return whether the job has been cancelled.

**Return type**

`bool`

### circuits

<span id="qiskit.providers.ibmq.job.IBMQJob.circuits" />

`IBMQJob.circuits()`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/job/ibmqjob.py "view source code")

Return the circuits or pulse schedules for this job.

**Return type**

`List`\[`Union`\[`QuantumCircuit`, `Schedule`]]

**Returns**

The circuits or pulse schedules for this job. An empty list is returned if the circuits cannot be retrieved (for example, if the job uses an old format that is no longer supported).

### creation\_date

<span id="qiskit.providers.ibmq.job.IBMQJob.creation_date" />

`IBMQJob.creation_date()`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/job/ibmqjob.py "view source code")

Return job creation date, in local time.

**Return type**

`datetime`

**Returns**

The job creation date as a datetime object, in local time.

### done

<span id="qiskit.providers.ibmq.job.IBMQJob.done" />

`IBMQJob.done()`

Return whether the job has successfully run.

**Return type**

`bool`

### error\_message

<span id="qiskit.providers.ibmq.job.IBMQJob.error_message" />

`IBMQJob.error_message()`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/job/ibmqjob.py "view source code")

Provide details about the reason of failure.

**Return type**

`Optional`\[`str`]

**Returns**

An error report if the job failed or `None` otherwise.

### header

<span id="qiskit.providers.ibmq.job.IBMQJob.header" />

`IBMQJob.header()`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/job/ibmqjob.py "view source code")

Return the user header specified for this job.

**Return type**

`Dict`

**Returns**

User header specified for this job. An empty dictionary is returned if the header cannot be retrieved.

### in\_final\_state

<span id="qiskit.providers.ibmq.job.IBMQJob.in_final_state" />

`IBMQJob.in_final_state()`

Return whether the job is in a final job state such as `DONE` or `ERROR`.

**Return type**

`bool`

### job\_id

<span id="qiskit.providers.ibmq.job.IBMQJob.job_id" />

`IBMQJob.job_id()`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/job/ibmqjob.py "view source code")

Return the job ID assigned by the server.

**Return type**

`str`

**Returns**

Job ID.

### name

<span id="qiskit.providers.ibmq.job.IBMQJob.name" />

`IBMQJob.name()`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/job/ibmqjob.py "view source code")

Return the name assigned to this job.

**Return type**

`Optional`\[`str`]

**Returns**

Job name or `None` if no name was assigned to this job.

### properties

<span id="qiskit.providers.ibmq.job.IBMQJob.properties" />

`IBMQJob.properties()`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/job/ibmqjob.py "view source code")

Return the backend properties for this job.

**Return type**

`Optional`\[`BackendProperties`]

**Returns**

The backend properties used for this job, or `None` if properties are not available.

**Raises**

[**IBMQJobApiError**](qiskit.providers.ibmq.job.IBMQJobApiError "qiskit.providers.ibmq.job.IBMQJobApiError") – If an unexpected error occurred when communicating with the server.

### qobj

<span id="qiskit.providers.ibmq.job.IBMQJob.qobj" />

`IBMQJob.qobj()`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/job/ibmqjob.py "view source code")

Return the Qobj for this job.

**Return type**

`Union`\[`QasmQobj`, `PulseQobj`, `None`]

**Returns**

The Qobj for this job, or `None` if the job does not have a Qobj.

**Raises**

[**IBMQJobApiError**](qiskit.providers.ibmq.job.IBMQJobApiError "qiskit.providers.ibmq.job.IBMQJobApiError") – If an unexpected error occurred when retrieving job information from the server.

### queue\_info

<span id="qiskit.providers.ibmq.job.IBMQJob.queue_info" />

`IBMQJob.queue_info()`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/job/ibmqjob.py "view source code")

Return queue information for this job.

The queue information may include queue position, estimated start and end time, and dynamic priorities for the hub, group, and project. See [`QueueInfo`](qiskit.providers.ibmq.job.QueueInfo "qiskit.providers.ibmq.job.QueueInfo") for more information.

<Admonition title="Note" type="note">
  The queue information is calculated after the job enters the queue. Therefore, some or all of the information may not be immediately available, and this method may return `None`.
</Admonition>

**Return type**

`Optional`\[`QueueInfo`]

**Returns**

A [`QueueInfo`](qiskit.providers.ibmq.job.QueueInfo "qiskit.providers.ibmq.job.QueueInfo") instance that contains queue information for this job, or `None` if queue information is unknown or not applicable.

### queue\_position

<span id="qiskit.providers.ibmq.job.IBMQJob.queue_position" />

`IBMQJob.queue_position(refresh=False)`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/job/ibmqjob.py "view source code")

Return the position of the job in the server queue.

<Admonition title="Note" type="note">
  The position returned is within the scope of the provider and may differ from the global queue position.
</Admonition>

**Parameters**

**refresh** (`bool`) – If `True`, re-query the server to get the latest value. Otherwise return the cached value.

**Return type**

`Optional`\[`int`]

**Returns**

Position in the queue or `None` if position is unknown or not applicable.

### refresh

<span id="qiskit.providers.ibmq.job.IBMQJob.refresh" />

`IBMQJob.refresh()`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/job/ibmqjob.py "view source code")

Obtain the latest job information from the server.

This method may add additional attributes to this job instance, if new information becomes available.

**Raises**

[**IBMQJobApiError**](qiskit.providers.ibmq.job.IBMQJobApiError "qiskit.providers.ibmq.job.IBMQJobApiError") – If an unexpected error occurred when communicating with the server.

**Return type**

`None`

### result

<span id="qiskit.providers.ibmq.job.IBMQJob.result" />

`IBMQJob.result(timeout=None, wait=5, partial=False, refresh=False)`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/job/ibmqjob.py "view source code")

Return the result of the job.

<Admonition title="Note" type="note">
  Some IBM Quantum Experience job results can only be read once. A second attempt to query the server for the same job will fail, since the job has already been “consumed”.

  The first call to this method in an `IBMQJob` instance will query the server and consume any available job results. Subsequent calls to that instance’s `result()` will also return the results, since they are cached. However, attempting to retrieve the results again in another instance or session might fail due to the job results having been consumed.
</Admonition>

<Admonition title="Note" type="note">
  When partial=True, this method will attempt to retrieve partial results of failed jobs. In this case, precaution should be taken when accessing individual experiments, as doing so might cause an exception. The `success` attribute of the returned [`Result`](qiskit.result.Result "qiskit.result.Result") instance can be used to verify whether it contains partial results.

  For example, if one of the experiments in the job failed, trying to get the counts of the unsuccessful experiment would raise an exception since there are no counts to return:

  ```python
  try:
      counts = result.get_counts("failed_experiment")
  except QiskitError:
      print("Experiment failed!")
  ```
</Admonition>

If the job failed, you can use [`error_message()`](qiskit.providers.ibmq.job.IBMQJob#error_message "qiskit.providers.ibmq.job.IBMQJob.error_message") to get more information.

**Parameters**

*   **timeout** (`Optional`\[`float`]) – Number of seconds to wait for job.
*   **wait** (`float`) – Time in seconds between queries.
*   **partial** (`bool`) – If `True`, return partial results if possible.
*   **refresh** (`bool`) – If `True`, re-query the server for the result. Otherwise return the cached value.

**Return type**

`Result`

**Returns**

Job result.

**Raises**

*   [**IBMQJobInvalidStateError**](qiskit.providers.ibmq.job.IBMQJobInvalidStateError "qiskit.providers.ibmq.job.IBMQJobInvalidStateError") – If the job was cancelled.
*   [**IBMQJobFailureError**](qiskit.providers.ibmq.job.IBMQJobFailureError "qiskit.providers.ibmq.job.IBMQJobFailureError") – If the job failed.
*   [**IBMQJobApiError**](qiskit.providers.ibmq.job.IBMQJobApiError "qiskit.providers.ibmq.job.IBMQJobApiError") – If an unexpected error occurred when communicating with the server.

### running

<span id="qiskit.providers.ibmq.job.IBMQJob.running" />

`IBMQJob.running()`

Return whether the job is actively running.

**Return type**

`bool`

### scheduling\_mode

<span id="qiskit.providers.ibmq.job.IBMQJob.scheduling_mode" />

`IBMQJob.scheduling_mode()`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/job/ibmqjob.py "view source code")

Return the scheduling mode the job is in.

The scheduling mode indicates how the job is scheduled to run. For example, `fairshare` indicates the job is scheduled using a fairshare algorithm.

This information is only available if the job status is `RUNNING` or `DONE`.

**Return type**

`Optional`\[`str`]

**Returns**

The scheduling mode the job is in or `None` if the information is not available.

### share\_level

<span id="qiskit.providers.ibmq.job.IBMQJob.share_level" />

`IBMQJob.share_level()`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/job/ibmqjob.py "view source code")

Return the share level of the job.

The share level is one of `global`, `hub`, `group`, `project`, and `none`.

**Return type**

`str`

**Returns**

The share level of the job.

### status

<span id="qiskit.providers.ibmq.job.IBMQJob.status" />

`IBMQJob.status()`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/job/ibmqjob.py "view source code")

Query the server for the latest job status.

<Admonition title="Note" type="note">
  This method is not designed to be invoked repeatedly in a loop for an extended period of time. Doing so may cause the server to reject your request. Use [`wait_for_final_state()`](qiskit.providers.ibmq.job.IBMQJob#wait_for_final_state "qiskit.providers.ibmq.job.IBMQJob.wait_for_final_state") if you want to wait for the job to finish.
</Admonition>

<Admonition title="Note" type="note">
  If the job failed, you can use [`error_message()`](qiskit.providers.ibmq.job.IBMQJob#error_message "qiskit.providers.ibmq.job.IBMQJob.error_message") to get more information.
</Admonition>

**Return type**

`JobStatus`

**Returns**

The status of the job.

**Raises**

[**IBMQJobApiError**](qiskit.providers.ibmq.job.IBMQJobApiError "qiskit.providers.ibmq.job.IBMQJobApiError") – If an unexpected error occurred when communicating with the server.

### submit

<span id="qiskit.providers.ibmq.job.IBMQJob.submit" />

`IBMQJob.submit()`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/job/ibmqjob.py "view source code")

Unsupported method.

<Admonition title="Note" type="note">
  This method is not supported, please use `run()` to submit a job.
</Admonition>

**Raises**

**NotImplementedError** – Upon invocation.

**Return type**

`None`

### tags

<span id="qiskit.providers.ibmq.job.IBMQJob.tags" />

`IBMQJob.tags()`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/job/ibmqjob.py "view source code")

Return the tags assigned to this job.

**Return type**

`List`\[`str`]

**Returns**

Tags assigned to this job.

### time\_per\_step

<span id="qiskit.providers.ibmq.job.IBMQJob.time_per_step" />

`IBMQJob.time_per_step()`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/job/ibmqjob.py "view source code")

Return the date and time information on each step of the job processing.

The output dictionary contains the date and time information on each step of the job processing, in local time. The keys of the dictionary are the names of the steps, and the values are the date and time data, as a datetime object with local timezone info. For example:

```python
{'CREATING': datetime(2020, 2, 13, 15, 19, 25, 717000, tzinfo=tzlocal(),
 'CREATED': datetime(2020, 2, 13, 15, 19, 26, 467000, tzinfo=tzlocal(),
 'VALIDATING': datetime(2020, 2, 13, 15, 19, 26, 527000, tzinfo=tzlocal()}
```

**Return type**

`Optional`\[`Dict`]

**Returns**

Date and time information on job processing steps, in local time, or `None` if the information is not yet available.

### update\_name

<span id="qiskit.providers.ibmq.job.IBMQJob.update_name" />

`IBMQJob.update_name(name)`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/job/ibmqjob.py "view source code")

Update the name associated with this job.

**Parameters**

**name** (`str`) – The new name for this job.

**Return type**

`str`

**Returns**

The new name associated with this job.

**Raises**

*   [**IBMQJobApiError**](qiskit.providers.ibmq.job.IBMQJobApiError "qiskit.providers.ibmq.job.IBMQJobApiError") – If an unexpected error occurred when communicating with the server or updating the job name.
*   [**IBMQJobInvalidStateError**](qiskit.providers.ibmq.job.IBMQJobInvalidStateError "qiskit.providers.ibmq.job.IBMQJobInvalidStateError") – If the input job name is not a string.

### update\_tags

<span id="qiskit.providers.ibmq.job.IBMQJob.update_tags" />

`IBMQJob.update_tags(replacement_tags=None, additional_tags=None, removal_tags=None)`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/job/ibmqjob.py "view source code")

Update the tags associated with this job.

When multiple parameters are specified, the parameters are processed in the following order:

> 1.  replacement\_tags
> 2.  additional\_tags
> 3.  removal\_tags

For example, if ‘new\_tag’ is specified for both additional\_tags and removal\_tags, then it is added and subsequently removed from the tags list, making it a “do nothing” operation.

<Admonition title="Note" type="note">
  *   Some tags, such as those starting with `ibmq_jobset`, are used internally by ibmq-provider and therefore cannot be modified.
  *   When removing tags, if the job does not have a specified tag, it will be ignored.
</Admonition>

**Parameters**

*   **replacement\_tags** (`Optional`\[`List`\[`str`]]) – The tags that should replace the current tags associated with this job.
*   **additional\_tags** (`Optional`\[`List`\[`str`]]) – The new tags that should be added to the current tags associated with this job.
*   **removal\_tags** (`Optional`\[`List`\[`str`]]) – The tags that should be removed from the current tags associated with this job.

**Return type**

`List`\[`str`]

**Returns**

The new tags associated with this job.

**Raises**

*   [**IBMQJobApiError**](qiskit.providers.ibmq.job.IBMQJobApiError "qiskit.providers.ibmq.job.IBMQJobApiError") – If an unexpected error occurred when communicating with the server or updating the job tags.
*   [**IBMQJobInvalidStateError**](qiskit.providers.ibmq.job.IBMQJobInvalidStateError "qiskit.providers.ibmq.job.IBMQJobInvalidStateError") – If none of the input parameters are specified or if any of the input parameters are invalid.

### wait\_for\_final\_state

<span id="qiskit.providers.ibmq.job.IBMQJob.wait_for_final_state" />

`IBMQJob.wait_for_final_state(timeout=None, wait=None, callback=None)`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.17/qiskit/providers/ibmq/job/ibmqjob.py "view source code")

Wait until the job progresses to a final state such as `DONE` or `ERROR`.

**Parameters**

*   **timeout** (`Optional`\[`float`]) – Seconds to wait for the job. If `None`, wait indefinitely.

*   **wait** (`Optional`\[`float`]) – Seconds to wait between invoking the callback function. If `None`, the callback function is invoked only if job status or queue position has changed.

*   **callback** (`Optional`\[`Callable`]) –

    Callback function invoked after each querying iteration. The following positional arguments are provided to the callback function:

    > *   job\_id: Job ID
    > *   job\_status: Status of the job from the last query.
    > *   job: This `IBMQJob` instance.

    In addition, the following keyword arguments are also provided:

    > *   queue\_info: A [`QueueInfo`](qiskit.providers.ibmq.job.QueueInfo "qiskit.providers.ibmq.job.QueueInfo") instance with job queue information, or `None` if queue information is unknown or not applicable. You can use the `to_dict()` method to convert the [`QueueInfo`](qiskit.providers.ibmq.job.QueueInfo "qiskit.providers.ibmq.job.QueueInfo") instance to a dictionary, if desired.

**Raises**

[**IBMQJobTimeoutError**](qiskit.providers.ibmq.job.IBMQJobTimeoutError "qiskit.providers.ibmq.job.IBMQJobTimeoutError") – if the job does not reach a final state before the specified timeout.

**Return type**

`None`

## Attributes

<span id="qiskit.providers.ibmq.job.IBMQJob.client_version" />

### client\_version

Return version of the client used for this job.

**Return type**

`Dict`\[`str`, `str`]

**Returns**

**Client version in dictionary format, where the key is the name**

of the client and the value is the version.

<span id="qiskit.providers.ibmq.job.IBMQJob.experiment_id" />

### experiment\_id

Return the experiment ID.

**Return type**

`str`

**Returns**

ID of the experiment this job is part of.

<span id="qiskit.providers.ibmq.job.IBMQJob.version" />

### version

`= 1`

