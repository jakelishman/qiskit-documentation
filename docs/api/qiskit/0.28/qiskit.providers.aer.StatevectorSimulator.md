---
title: StatevectorSimulator
description: API reference for qiskit.providers.aer.StatevectorSimulator
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.aer.StatevectorSimulator
---

# qiskit.providers.aer.StatevectorSimulator

<span id="qiskit.providers.aer.StatevectorSimulator" />

`StatevectorSimulator(configuration=None, properties=None, provider=None, **backend_options)`[GitHub](https://github.com/qiskit/qiskit-aer/tree/stable/0.8/qiskit/providers/aer/backends/statevector_simulator.py "view source code")

Ideal quantum circuit statevector simulator

**Configurable Options**

The StatevectorSimulator supports CPU and GPU simulation methods and additional configurable options. These may be set using the appropriate kwargs during initialization. They can also be set of updated using the [`set_options()`](#qiskit.providers.aer.StatevectorSimulator.set_options "qiskit.providers.aer.StatevectorSimulator.set_options") method.

Run-time options may also be specified as kwargs using the [`run()`](#qiskit.providers.aer.StatevectorSimulator.run "qiskit.providers.aer.StatevectorSimulator.run") method. These will not be stored in the backend and will only apply to that execution. They will also override any previously set options.

For example, to configure a a single-precision simulator

```python
backend = StatevectorSimulator(precision='single')
```

**Backend Options**

The following configurable backend options are supported

*   `method` (str): Set the simulation method supported methods are `"statevector"` for CPU simulation, and `"statevector_gpu"` for GPU simulation (Default: `"statevector"`).
*   `precision` (str): Set the floating point precision for certain simulation methods to either `"single"` or `"double"` precision (default: `"double"`).
*   `zero_threshold` (double): Sets the threshold for truncating small values to zero in the result data (Default: 1e-10).
*   `validation_threshold` (double): Sets the threshold for checking if the initial statevector is valid (Default: 1e-8).
*   `max_parallel_threads` (int): Sets the maximum number of CPU cores used by OpenMP for parallelization. If set to 0 the maximum will be set to the number of CPU cores (Default: 0).
*   `max_parallel_experiments` (int): Sets the maximum number of qobj experiments that may be executed in parallel up to the max\_parallel\_threads value. If set to 1 parallel circuit execution will be disabled. If set to 0 the maximum will be automatically set to max\_parallel\_threads (Default: 1).
*   `max_memory_mb` (int): Sets the maximum size of memory to store a state vector. If a state vector needs more, an error is thrown. In general, a state vector of n-qubits uses 2^n complex values (16 Bytes). If set to 0, the maximum will be automatically set to the system memory size (Default: 0).
*   `statevector_parallel_threshold` (int): Sets the threshold that “n\_qubits” must be greater than to enable OpenMP parallelization for matrix multiplication during execution of an experiment. If parallel circuit or shot execution is enabled this will only use unallocated CPU cores up to max\_parallel\_threads. Note that setting this too low can reduce performance (Default: 14).

These backend options apply in circuit optimization passes:

*   `fusion_enable` (bool): Enable fusion optimization in circuit optimization passes \[Default: True]
*   `fusion_verbose` (bool): Output gates generated in fusion optimization into metadata \[Default: False]
*   `fusion_max_qubit` (int): Maximum number of qubits for a operation generated in a fusion optimization \[Default: 5]
*   `fusion_threshold` (int): Threshold that number of qubits must be greater than or equal to enable fusion optimization \[Default: 14]

Aer class for backends.

This method should initialize the module and its configuration, and raise an exception if a component of the module is not available.

**Parameters**

*   **configuration** ([*BackendConfiguration*](qiskit.providers.models.BackendConfiguration "qiskit.providers.models.BackendConfiguration")) – backend configuration.
*   **properties** ([*BackendProperties*](qiskit.providers.models.BackendProperties "qiskit.providers.models.BackendProperties") *or None*) – Optional, backend properties.
*   **defaults** ([*PulseDefaults*](qiskit.providers.models.PulseDefaults "qiskit.providers.models.PulseDefaults") *or None*) – Optional, backend pulse defaults.
*   **available\_methods** (*list or None*) – Optional, the available simulation methods if backend supports multiple methods.
*   **provider** ([*Provider*](qiskit.providers.Provider "qiskit.providers.Provider")) – Optional, provider responsible for this backend.
*   **backend\_options** (*dict or None*) – Optional set custom backend options.

**Raises**

[**AerError**](qiskit.providers.aer.AerError "qiskit.providers.aer.AerError") – if there is no name in the configuration

### \_\_init\_\_

<span id="qiskit.providers.aer.StatevectorSimulator.__init__" />

`__init__(configuration=None, properties=None, provider=None, **backend_options)`

Aer class for backends.

This method should initialize the module and its configuration, and raise an exception if a component of the module is not available.

**Parameters**

*   **configuration** ([*BackendConfiguration*](qiskit.providers.models.BackendConfiguration "qiskit.providers.models.BackendConfiguration")) – backend configuration.
*   **properties** ([*BackendProperties*](qiskit.providers.models.BackendProperties "qiskit.providers.models.BackendProperties") *or None*) – Optional, backend properties.
*   **defaults** ([*PulseDefaults*](qiskit.providers.models.PulseDefaults "qiskit.providers.models.PulseDefaults") *or None*) – Optional, backend pulse defaults.
*   **available\_methods** (*list or None*) – Optional, the available simulation methods if backend supports multiple methods.
*   **provider** ([*Provider*](qiskit.providers.Provider "qiskit.providers.Provider")) – Optional, provider responsible for this backend.
*   **backend\_options** (*dict or None*) – Optional set custom backend options.

**Raises**

[**AerError**](qiskit.providers.aer.AerError "qiskit.providers.aer.AerError") – if there is no name in the configuration

## Methods

|                                                                                                                                                                |                                                 |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------- |
| [`__init__`](#qiskit.providers.aer.StatevectorSimulator.__init__ "qiskit.providers.aer.StatevectorSimulator.__init__")(\[configuration, properties, provider]) | Aer class for backends.                         |
| [`available_methods`](#qiskit.providers.aer.StatevectorSimulator.available_methods "qiskit.providers.aer.StatevectorSimulator.available_methods")()            | Return the available simulation methods.        |
| [`clear_options`](#qiskit.providers.aer.StatevectorSimulator.clear_options "qiskit.providers.aer.StatevectorSimulator.clear_options")()                        | Reset the simulator options to default values.  |
| [`configuration`](#qiskit.providers.aer.StatevectorSimulator.configuration "qiskit.providers.aer.StatevectorSimulator.configuration")()                        | Return the simulator backend configuration.     |
| [`defaults`](#qiskit.providers.aer.StatevectorSimulator.defaults "qiskit.providers.aer.StatevectorSimulator.defaults")()                                       | Return the simulator backend pulse defaults.    |
| [`name`](#qiskit.providers.aer.StatevectorSimulator.name "qiskit.providers.aer.StatevectorSimulator.name")()                                                   | Return the backend name.                        |
| [`properties`](#qiskit.providers.aer.StatevectorSimulator.properties "qiskit.providers.aer.StatevectorSimulator.properties")()                                 | Return the simulator backend properties if set. |
| [`provider`](#qiskit.providers.aer.StatevectorSimulator.provider "qiskit.providers.aer.StatevectorSimulator.provider")()                                       | Return the backend Provider.                    |
| [`run`](#qiskit.providers.aer.StatevectorSimulator.run "qiskit.providers.aer.StatevectorSimulator.run")(circuits\[, backend\_options, validate])               | Run a qobj on the backend.                      |
| [`set_option`](#qiskit.providers.aer.StatevectorSimulator.set_option "qiskit.providers.aer.StatevectorSimulator.set_option")(key, value)                       | Special handling for setting backend options.   |
| [`set_options`](#qiskit.providers.aer.StatevectorSimulator.set_options "qiskit.providers.aer.StatevectorSimulator.set_options")(\*\*fields)                    | Set the options fields for the backend          |
| [`status`](#qiskit.providers.aer.StatevectorSimulator.status "qiskit.providers.aer.StatevectorSimulator.status")()                                             | Return backend status.                          |

## Attributes

|                                                                                                                     |                                    |
| ------------------------------------------------------------------------------------------------------------------- | ---------------------------------- |
| [`options`](#qiskit.providers.aer.StatevectorSimulator.options "qiskit.providers.aer.StatevectorSimulator.options") | Return the options for the backend |
| `version`                                                                                                           |                                    |

### available\_methods

<span id="qiskit.providers.aer.StatevectorSimulator.available_methods" />

`available_methods()`

Return the available simulation methods.

### clear\_options

<span id="qiskit.providers.aer.StatevectorSimulator.clear_options" />

`clear_options()`

Reset the simulator options to default values.

### configuration

<span id="qiskit.providers.aer.StatevectorSimulator.configuration" />

`configuration()`

Return the simulator backend configuration.

**Returns**

the configuration for the backend.

**Return type**

[BackendConfiguration](qiskit.providers.models.BackendConfiguration "qiskit.providers.models.BackendConfiguration")

### defaults

<span id="qiskit.providers.aer.StatevectorSimulator.defaults" />

`defaults()`

Return the simulator backend pulse defaults.

**Returns**

**The backend pulse defaults or `None` if the**

backend does not support pulse.

**Return type**

[PulseDefaults](qiskit.providers.models.PulseDefaults "qiskit.providers.models.PulseDefaults")

### name

<span id="qiskit.providers.aer.StatevectorSimulator.name" />

`name()`

Return the backend name.

**Returns**

the name of the backend.

**Return type**

str

### options

<span id="qiskit.providers.aer.StatevectorSimulator.options" />

`property options`

Return the options for the backend

The options of a backend are the dynamic parameters defining how the backend is used. These are used to control the [`run()`](#qiskit.providers.aer.StatevectorSimulator.run "qiskit.providers.aer.StatevectorSimulator.run") method.

### properties

<span id="qiskit.providers.aer.StatevectorSimulator.properties" />

`properties()`

Return the simulator backend properties if set.

**Returns**

**The backend properties or `None` if the**

backend does not have properties set.

**Return type**

[BackendProperties](qiskit.providers.models.BackendProperties "qiskit.providers.models.BackendProperties")

### provider

<span id="qiskit.providers.aer.StatevectorSimulator.provider" />

`provider()`

Return the backend Provider.

**Returns**

the Provider responsible for the backend.

**Return type**

[Provider](qiskit.providers.Provider "qiskit.providers.Provider")

### run

<span id="qiskit.providers.aer.StatevectorSimulator.run" />

`run(circuits, backend_options=None, validate=False, **run_options)`

Run a qobj on the backend.

**Parameters**

*   **circuits** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit") *or list*) – The QuantumCircuit (or list of QuantumCircuit objects) to run
*   **backend\_options** (*dict or None*) – DEPRECATED dictionary of backend options for the execution (default: None).
*   **validate** (*bool*) – validate the Qobj before running (default: False).
*   **run\_options** (*kwargs*) – additional run time backend options.

**Returns**

The simulation job.

**Return type**

[AerJob](qiskit.providers.aer.AerJob "qiskit.providers.aer.AerJob")

**Additional Information:**

*   kwarg options specified in `run_options` will temporarily override any set options of the same name for the current run.
*   The entries in the `backend_options` will be combined with the `Qobj.config` dictionary with the values of entries in `backend_options` taking precedence. This kwarg is deprecated and direct kwarg’s should be used for options to pass them to `run_options`.

### set\_option

<span id="qiskit.providers.aer.StatevectorSimulator.set_option" />

`set_option(key, value)`

Special handling for setting backend options.

This method should be extended by sub classes to update special option values.

**Parameters**

*   **key** (*str*) – key to update
*   **value** (*any*) – value to update.

**Raises**

[**AerError**](qiskit.providers.aer.AerError "qiskit.providers.aer.AerError") – if key is ‘method’ and val isn’t in available methods.

### set\_options

<span id="qiskit.providers.aer.StatevectorSimulator.set_options" />

`set_options(**fields)`

Set the options fields for the backend

This method is used to update the options of a backend. If you need to change any of the options prior to running just pass in the kwarg with the new value for the options.

**Parameters**

**fields** – The fields to update the options

**Raises**

**AttributeError** – If the field passed in is not part of the options

### status

<span id="qiskit.providers.aer.StatevectorSimulator.status" />

`status()`

Return backend status.

**Returns**

the status of the backend.

**Return type**

[BackendStatus](qiskit.providers.models.BackendStatus "qiskit.providers.models.BackendStatus")

