---
title: tools
description: API reference for qiskit.tools
in_page_toc_min_heading_level: 1
python_api_type: module
python_api_name: qiskit.tools
---

<span id="module-qiskit.tools" />

<span id="qiskit-tools-qiskit-tools" />

# Qiskit Tools

<span id="module-qiskit.tools" />

`qiskit.tools`

## Parallel Routines

A helper function for calling a custom function with python `ProcessPoolExecutor`. Tasks can be executed in parallel using this function. It has a built-in event publisher to show the progress of the parallel tasks.

<span id="qiskit.tools.parallel_map" />

`qiskit.tools.parallel_map(task, values, task_args=(), task_kwargs={}, num_processes=2)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.25/qiskit/tools/parallel.py "view source code")

Parallel execution of a mapping of values to the function task. This is functionally equivalent to:

```python
result = [task(value, *task_args, **task_kwargs) for value in values]
```

On Windows this function defaults to a serial implementation to avoid the overhead from spawning processes in Windows.

**Parameters**

*   **task** (*func*) – Function that is to be called for each value in `values`.
*   **values** (*array\_like*) – List or array of values for which the `task` function is to be evaluated.
*   **task\_args** ([*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")) – Optional additional arguments to the `task` function.
*   **task\_kwargs** ([*dict*](https://docs.python.org/3/library/stdtypes.html#dict "(in Python v3.12)")) – Optional additional keyword argument to the `task` function.
*   **num\_processes** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – Number of processes to spawn.

**Returns**

**The result list contains the value of**

**`task(value, *task_args, **task_kwargs)` for**

each value in `values`.

**Return type**

result

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – If user interrupts via keyboard.

**Events:**

terra.parallel.start: The collection of parallel tasks are about to start. terra.parallel.update: One of the parallel task has finished. terra.parallel.finish: All the parallel tasks have finished.

## Examples

```python
import time
from qiskit.tools.parallel import parallel_map
def func(_):
        time.sleep(0.1)
        return 0
parallel_map(func, list(range(10)));
```

## Monitoring

A helper module to get IBM backend information and submitted job status.

<span id="qiskit.tools.job_monitor" />

`qiskit.tools.job_monitor(job, interval=None, quiet=False, output=<_io.TextIOWrapper name='<stdout>' mode='w' encoding='utf-8'>, line_discipline='\r')`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.25/qiskit/tools/monitor/job_monitor.py "view source code")

Monitor the status of a IBMQJob instance.

**Parameters**

*   **job** (*BaseJob*) – Job to monitor.
*   **interval** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – Time interval between status queries.
*   **quiet** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – If True, do not print status messages.
*   **output** (*file*) – The file like object to write status messages to.
*   **sys.stdout.** (*By default this is*) –
*   **line\_discipline** (*string*) – character emitted at start of a line of job monitor output,
*   **r.** (*This defaults to*) –

## Examples

```python
from qiskit import BasicAer, transpile
from qiskit.circuit import QuantumCircuit
from qiskit.tools.monitor import job_monitor
sim_backend = BasicAer.get_backend("qasm_simulator")
qc = QuantumCircuit(2, 2)
qc.h(0)
qc.cx(0, 1)
qc.measure_all()
tqc = transpile(qc, sim_backend)
job_sim = sim_backend.run(tqc)
job_monitor(job_sim)
```

<span id="qiskit.tools.backend_monitor" />

`qiskit.tools.backend_monitor(backend)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.25/qiskit/tools/monitor/overview.py "view source code")

Monitor a single IBMQ backend.

**Parameters**

**backend** (*IBMQBackend*) – Backend to monitor.

**Raises**

*   [**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – Input is not a IBMQ backend.
*   [**MissingOptionalLibraryError**](exceptions#qiskit.exceptions.MissingOptionalLibraryError "qiskit.exceptions.MissingOptionalLibraryError") – If qiskit-ibmq-provider is not installed

Examples: .. code-block:: python

> from qiskit.providers.ibmq import IBMQ from qiskit.tools.monitor import backend\_monitor provider = IBMQ.get\_provider(hub=’ibm-q’) backend\_monitor(provider.backends.ibmq\_lima)

<span id="qiskit.tools.backend_overview" />

`qiskit.tools.backend_overview()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.25/qiskit/tools/monitor/overview.py "view source code")

Gives overview information on all the IBMQ backends that are available.

## Examples

```python
from qiskit.providers.ibmq import IBMQ
from qiskit.tools.monitor import backend_overview
provider = IBMQ.get_provider(hub='ibm-q')
backend_overview()
```

<span id="module-qiskit.tools.events" />

<span id="events-qiskit-tools-events" />

### Events ([`qiskit.tools.events`](#module-qiskit.tools.events "qiskit.tools.events"))

A helper component for publishing and subscribing to events.

<span id="qiskit.tools.events.TextProgressBar" />

`qiskit.tools.events.TextProgressBar(output_handler=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.25/qiskit/tools/events/progressbar.py "view source code")

A simple text-based progress bar.

**output\_handlerthe handler the progress bar should be written to, default**

is sys.stdout, another option is sys.stderr

## Examples

The progress bar can be used to track the progress of a parallel\_map.

```python
import numpy as np
import qiskit.tools.jupyter
from qiskit.tools.parallel import parallel_map
from qiskit.tools.events import TextProgressBar

TextProgressBar()
%qiskit_progress_bar -t text
parallel_map(np.sin, np.linspace(0,10,100));
```

And it can also be used individually.

```python
from qiskit.tools.events import TextProgressBar

iterations = 100
t = TextProgressBar()
t.start(iterations=iterations)
for i in range(iterations):
    # step i of heavy calculation ...
    t.update(i + 1)  # update progress bar
```

