---
title: StatevectorSimulatorPy
description: API reference for qiskit.providers.basicaer.StatevectorSimulatorPy
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.basicaer.StatevectorSimulatorPy
---

# StatevectorSimulatorPy

<span id="qiskit.providers.basicaer.StatevectorSimulatorPy" />

`StatevectorSimulatorPy(configuration=None, provider=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/providers/basicaer/statevector_simulator.py "view source code")

Python statevector simulator.

Base class for backends.

This method should initialize the module and its configuration, and raise an exception if a component of the module is not available.

**Parameters**

*   **configuration** ([*BackendConfiguration*](qiskit.providers.models.BackendConfiguration "qiskit.providers.models.BackendConfiguration")) – backend configuration
*   **provider** ([*BaseProvider*](qiskit.providers.BaseProvider "qiskit.providers.BaseProvider")) – provider responsible for this backend

**Raises**

**QiskitError** – if an error occurred when instantiating the backend.

## Attributes

### DEFAULT\_CONFIGURATION

<span id="qiskit.providers.basicaer.StatevectorSimulatorPy.DEFAULT_CONFIGURATION" />

`= {'backend_name': 'statevector_simulator', 'backend_version': '1.0.0', 'basis_gates': ['u1', 'u2', 'u3', 'cx', 'id', 'unitary'], 'conditional': True, 'coupling_map': None, 'description': 'A Python statevector simulator for qobj files', 'gates': [{'name': 'u1', 'parameters': ['lambda'], 'qasm_def': 'gate u1(lambda) q { U(0,0,lambda) q; }'}, {'name': 'u2', 'parameters': ['phi', 'lambda'], 'qasm_def': 'gate u2(phi,lambda) q { U(pi/2,phi,lambda) q; }'}, {'name': 'u3', 'parameters': ['theta', 'phi', 'lambda'], 'qasm_def': 'gate u3(theta,phi,lambda) q { U(theta,phi,lambda) q; }'}, {'name': 'cx', 'parameters': ['c', 't'], 'qasm_def': 'gate cx c,t { CX c,t; }'}, {'name': 'id', 'parameters': ['a'], 'qasm_def': 'gate id a { U(0,0,0) a; }'}, {'name': 'unitary', 'parameters': ['matrix'], 'qasm_def': 'unitary(matrix) q1, q2,...'}], 'local': True, 'max_shots': 65536, 'memory': True, 'n_qubits': 24, 'open_pulse': False, 'simulator': True, 'url': 'https://github.com/Qiskit/qiskit-terra'}`

### DEFAULT\_OPTIONS

<span id="qiskit.providers.basicaer.StatevectorSimulatorPy.DEFAULT_OPTIONS" />

`= {'chop_threshold': 1e-15, 'initial_statevector': None}`

### MAX\_QUBITS\_MEMORY

<span id="qiskit.providers.basicaer.StatevectorSimulatorPy.MAX_QUBITS_MEMORY" />

`= 32`

### SHOW\_FINAL\_STATE

<span id="qiskit.providers.basicaer.StatevectorSimulatorPy.SHOW_FINAL_STATE" />

`= True`

## Methods

### configuration

<span id="qiskit.providers.basicaer.StatevectorSimulatorPy.configuration" />

`StatevectorSimulatorPy.configuration()`

Return the backend configuration.

**Returns**

the configuration for the backend.

**Return type**

[BackendConfiguration](qiskit.providers.models.BackendConfiguration "qiskit.providers.models.BackendConfiguration")

### name

<span id="qiskit.providers.basicaer.StatevectorSimulatorPy.name" />

`StatevectorSimulatorPy.name()`

Return the backend name.

**Returns**

the name of the backend.

**Return type**

str

### properties

<span id="qiskit.providers.basicaer.StatevectorSimulatorPy.properties" />

`StatevectorSimulatorPy.properties()`

Return the backend properties.

**Returns**

the configuration for the backend. If the backend does not support properties, it returns `None`.

**Return type**

[BackendProperties](qiskit.providers.models.BackendProperties "qiskit.providers.models.BackendProperties")

### provider

<span id="qiskit.providers.basicaer.StatevectorSimulatorPy.provider" />

`StatevectorSimulatorPy.provider()`

Return the backend Provider.

**Returns**

the Provider responsible for the backend.

**Return type**

[BaseProvider](qiskit.providers.BaseProvider "qiskit.providers.BaseProvider")

### run

<span id="qiskit.providers.basicaer.StatevectorSimulatorPy.run" />

`StatevectorSimulatorPy.run(qobj, backend_options=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/providers/basicaer/statevector_simulator.py "view source code")

Run qobj asynchronously.

**Parameters**

*   **qobj** ([*Qobj*](qiskit.qobj.Qobj "qiskit.qobj.Qobj")) – payload of the experiment
*   **backend\_options** (*dict*) – backend options

**Returns**

derived from BaseJob

**Return type**

[BasicAerJob](qiskit.providers.basicaer.BasicAerJob "qiskit.providers.basicaer.BasicAerJob")

Additional Information:

```python
backend_options: Is a dict of options for the backend. It may contain
    * "initial_statevector": vector_like
    * "chop_threshold": double

The "initial_statevector" option specifies a custom initial
initial statevector for the simulator to be used instead of the all
zero state. This size of this vector must be correct for the number
of qubits in all experiments in the qobj.

The "chop_threshold" option specifies a truncation value for
setting small values to zero in the output statevector. The default
value is 1e-15.

Example::

    backend_options = {
        "initial_statevector": np.array([1, 0, 0, 1j]) / np.sqrt(2),
        "chop_threshold": 1e-15
    }
```

### run\_experiment

<span id="qiskit.providers.basicaer.StatevectorSimulatorPy.run_experiment" />

`StatevectorSimulatorPy.run_experiment(experiment)`

Run an experiment (circuit) and return a single experiment result.

**Parameters**

**experiment** (*QobjExperiment*) – experiment from qobj experiments list

**Returns**

A result dictionary which looks something like:

```python
{
"name": name of this experiment (obtained from qobj.experiment header)
"seed": random seed used for simulation
"shots": number of shots used in the simulation
"data":
    {
    "counts": {'0x9: 5, ...},
    "memory": ['0x9', '0xF', '0x1D', ..., '0x9']
    },
"status": status string for the simulation
"success": boolean
"time_taken": simulation time of this single experiment
}
```

**Return type**

dict

**Raises**

[**BasicAerError**](qiskit.providers.basicaer.BasicAerError "qiskit.providers.basicaer.BasicAerError") – if an error occurred.

### status

<span id="qiskit.providers.basicaer.StatevectorSimulatorPy.status" />

`StatevectorSimulatorPy.status()`

Return the backend status.

**Returns**

the status of the backend.

**Return type**

[BackendStatus](qiskit.providers.models.BackendStatus "qiskit.providers.models.BackendStatus")

### version

<span id="qiskit.providers.basicaer.StatevectorSimulatorPy.version" />

`StatevectorSimulatorPy.version()`

Return the backend version.

**Returns**

the X.X.X version of the backend.

**Return type**

str

