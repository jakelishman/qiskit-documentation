---
title: QasmSimulatorPy
description: API reference for qiskit.providers.basicaer.QasmSimulatorPy
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.basicaer.QasmSimulatorPy
---

# QasmSimulatorPy

<span id="qiskit.providers.basicaer.QasmSimulatorPy" />

`QasmSimulatorPy(configuration=None, provider=None, **fields)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/providers/basicaer/qasm_simulator.py "view source code")

Bases: `qiskit.providers.backend.BackendV1`

Python implementation of a qasm simulator.

Initialize a backend class

**Parameters**

*   **configuration** ([*BackendConfiguration*](qiskit.providers.models.BackendConfiguration "qiskit.providers.models.BackendConfiguration")) – A backend configuration object for the backend object.
*   **provider** ([*qiskit.providers.Provider*](qiskit.providers.Provider "qiskit.providers.Provider")) – Optionally, the provider object that this Backend comes from.
*   **fields** – kwargs for the values to use to override the default options.

**Raises**

**AttributeError** – if input field not a valid options

In addition to the public abstract methods, subclasses should also implement the following private methods:

### \_default\_options

<span id="qiskit.providers.basicaer.QasmSimulatorPy._default_options" />

`classmethod _default_options()`

Return the default options

This method will return a [`qiskit.providers.Options`](qiskit.providers.Options "qiskit.providers.Options") subclass object that will be used for the default options. These should be the default parameters to use for the options of the backend.

**Returns**

**A options object with**

default values set

**Return type**

[qiskit.providers.Options](qiskit.providers.Options "qiskit.providers.Options")

## Methods

### configuration

<span id="qiskit.providers.basicaer.QasmSimulatorPy.configuration" />

`QasmSimulatorPy.configuration()`

Return the backend configuration.

**Returns**

the configuration for the backend.

**Return type**

[BackendConfiguration](qiskit.providers.models.BackendConfiguration "qiskit.providers.models.BackendConfiguration")

### name

<span id="qiskit.providers.basicaer.QasmSimulatorPy.name" />

`QasmSimulatorPy.name()`

Return the backend name.

**Returns**

the name of the backend.

**Return type**

str

### properties

<span id="qiskit.providers.basicaer.QasmSimulatorPy.properties" />

`QasmSimulatorPy.properties()`

Return the backend properties.

**Returns**

the configuration for the backend. If the backend does not support properties, it returns `None`.

**Return type**

[BackendProperties](qiskit.providers.models.BackendProperties "qiskit.providers.models.BackendProperties")

### provider

<span id="qiskit.providers.basicaer.QasmSimulatorPy.provider" />

`QasmSimulatorPy.provider()`

Return the backend Provider.

**Returns**

the Provider responsible for the backend.

**Return type**

[Provider](qiskit.providers.Provider "qiskit.providers.Provider")

### run

<span id="qiskit.providers.basicaer.QasmSimulatorPy.run" />

`QasmSimulatorPy.run(qobj, **backend_options)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/providers/basicaer/qasm_simulator.py "view source code")

Run qobj asynchronously.

**Parameters**

*   **qobj** ([*Qobj*](qiskit.qobj.Qobj "qiskit.qobj.Qobj")) – payload of the experiment
*   **backend\_options** (*dict*) – backend options

**Returns**

derived from BaseJob

**Return type**

[BasicAerJob](qiskit.providers.basicaer.BasicAerJob "qiskit.providers.basicaer.BasicAerJob")

#### Additional Information:

#### backend\_options: Is a dict of options for the backend. It may contain

*   “initial\_statevector”: vector\_like

The “initial\_statevector” option specifies a custom initial initial statevector for the simulator to be used instead of the all zero state. This size of this vector must be correct for the number of qubits in all experiments in the qobj.

Example:

```python
backend_options = {
    "initial_statevector": np.array([1, 0, 0, 1j]) / np.sqrt(2),
}
```

### run\_experiment

<span id="qiskit.providers.basicaer.QasmSimulatorPy.run_experiment" />

`QasmSimulatorPy.run_experiment(experiment)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/providers/basicaer/qasm_simulator.py "view source code")

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

### set\_options

<span id="qiskit.providers.basicaer.QasmSimulatorPy.set_options" />

`QasmSimulatorPy.set_options(**fields)`

Set the options fields for the backend

This method is used to update the options of a backend. If you need to change any of the options prior to running just pass in the kwarg with the new value for the options.

**Parameters**

**fields** – The fields to update the options

**Raises**

**AttributeError** – If the field passed in is not part of the options

### status

<span id="qiskit.providers.basicaer.QasmSimulatorPy.status" />

`QasmSimulatorPy.status()`

Return the backend status.

**Returns**

the status of the backend.

**Return type**

[BackendStatus](qiskit.providers.models.BackendStatus "qiskit.providers.models.BackendStatus")

## Attributes

<span id="qiskit.providers.basicaer.QasmSimulatorPy.DEFAULT_CONFIGURATION" />

### DEFAULT\_CONFIGURATION = \{'backend\_name'

`= {'backend_name':`

`= {'backend_name': 'qasm_simulator', 'backend_version': '2.1.0', 'basis_gates': ['u1', 'u2', 'u3', 'rz', 'sx', 'x', 'cx', 'id', 'unitary'], 'conditional': True, 'coupling_map': None, 'description': 'A python simulator for qasm experiments', 'gates': [{'name': 'u1', 'parameters': ['lambda'], 'qasm_def': 'gate u1(lambda) q { U(0,0,lambda) q; }'}, {'name': 'u2', 'parameters': ['phi', 'lambda'], 'qasm_def': 'gate u2(phi,lambda) q { U(pi/2,phi,lambda) q; }'}, {'name': 'u3', 'parameters': ['theta', 'phi', 'lambda'], 'qasm_def': 'gate u3(theta,phi,lambda) q { U(theta,phi,lambda) q; }'}, {'name': 'rz', 'parameters': ['phi'], 'qasm_def': 'gate rz(phi) q { U(0,0,phi) q; }'}, {'name': 'sx', 'parameters': [], 'qasm_def': 'gate sx(phi) q { U(pi/2,7*pi/2,pi/2) q; }'}, {'name': 'x', 'parameters': [], 'qasm_def': 'gate x q { U(pi,7*pi/2,pi/2) q; }'}, {'name': 'cx', 'parameters': [], 'qasm_def': 'gate cx c,t { CX c,t; }'}, {'name': 'id', 'parameters': [], 'qasm_def': 'gate id a { U(0,0,0) a; }'}, {'name': 'unitary', 'parameters': ['matrix'], 'qasm_def': 'unitary(matrix) q1, q2,...'}], 'local': True, 'max_shots': 65536, 'memory': True, 'n_qubits': 24, 'open_pulse': False, 'simulator': True, 'url': 'https://github.com/Qiskit/qiskit-terra'}`

<span id="qiskit.providers.basicaer.QasmSimulatorPy.DEFAULT_OPTIONS" />

### DEFAULT\_OPTIONS = \{'chop\_threshold'

`= {'chop_threshold':`

`= {'chop_threshold': 1e-15, 'initial_statevector': None}`

<span id="qiskit.providers.basicaer.QasmSimulatorPy.MAX_QUBITS_MEMORY" />

### MAX\_QUBITS\_MEMORY

`= 32`

<span id="qiskit.providers.basicaer.QasmSimulatorPy.SHOW_FINAL_STATE" />

### SHOW\_FINAL\_STATE

`= False`

<span id="qiskit.providers.basicaer.QasmSimulatorPy.options" />

### options

Return the options for the backend

The options of a backend are the dynamic parameters defining how the backend is used. These are used to control the [`run()`](qiskit.providers.basicaer.QasmSimulatorPy#run "qiskit.providers.basicaer.QasmSimulatorPy.run") method.

<span id="qiskit.providers.basicaer.QasmSimulatorPy.version" />

### version

`= 1`

