---
title: QasmSimulatorPy
description: API reference for qiskit.providers.basicaer.QasmSimulatorPy
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.basicaer.QasmSimulatorPy
---

# QasmSimulatorPy

<span id="qiskit.providers.basicaer.QasmSimulatorPy" />

`QasmSimulatorPy(configuration=None, provider=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/providers/basicaer/qasm_simulator.py "view source code")

Python implementation of a qasm simulator.

Base class for backends.

This method should initialize the module and its configuration, and raise an exception if a component of the module is not available.

**Parameters**

*   **configuration** ([*BackendConfiguration*](qiskit.providers.models.BackendConfiguration "qiskit.providers.models.BackendConfiguration")) – backend configuration
*   **provider** ([*BaseProvider*](qiskit.providers.BaseProvider "qiskit.providers.BaseProvider")) – provider responsible for this backend

**Raises**

**QiskitError** – if an error occurred when instantiating the backend.

## Attributes

### DEFAULT\_CONFIGURATION

<span id="qiskit.providers.basicaer.QasmSimulatorPy.DEFAULT_CONFIGURATION" />

`= {'backend_name': 'qasm_simulator', 'backend_version': '2.0.0', 'basis_gates': ['u1', 'u2', 'u3', 'cx', 'id', 'unitary'], 'conditional': True, 'coupling_map': None, 'description': 'A python simulator for qasm experiments', 'gates': [{'name': 'u1', 'parameters': ['lambda'], 'qasm_def': 'gate u1(lambda) q { U(0,0,lambda) q; }'}, {'name': 'u2', 'parameters': ['phi', 'lambda'], 'qasm_def': 'gate u2(phi,lambda) q { U(pi/2,phi,lambda) q; }'}, {'name': 'u3', 'parameters': ['theta', 'phi', 'lambda'], 'qasm_def': 'gate u3(theta,phi,lambda) q { U(theta,phi,lambda) q; }'}, {'name': 'cx', 'parameters': ['c', 't'], 'qasm_def': 'gate cx c,t { CX c,t; }'}, {'name': 'id', 'parameters': ['a'], 'qasm_def': 'gate id a { U(0,0,0) a; }'}, {'name': 'unitary', 'parameters': ['matrix'], 'qasm_def': 'unitary(matrix) q1, q2,...'}], 'local': True, 'max_shots': 65536, 'memory': True, 'n_qubits': 24, 'open_pulse': False, 'simulator': True, 'url': 'https://github.com/Qiskit/qiskit-terra'}`

### DEFAULT\_OPTIONS

<span id="qiskit.providers.basicaer.QasmSimulatorPy.DEFAULT_OPTIONS" />

`= {'chop_threshold': 1e-15, 'initial_statevector': None}`

### MAX\_QUBITS\_MEMORY

<span id="qiskit.providers.basicaer.QasmSimulatorPy.MAX_QUBITS_MEMORY" />

`= 32`

### SHOW\_FINAL\_STATE

<span id="qiskit.providers.basicaer.QasmSimulatorPy.SHOW_FINAL_STATE" />

`= False`

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

[BaseProvider](qiskit.providers.BaseProvider "qiskit.providers.BaseProvider")

### run

<span id="qiskit.providers.basicaer.QasmSimulatorPy.run" />

`QasmSimulatorPy.run(qobj, backend_options=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/providers/basicaer/qasm_simulator.py "view source code")

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

`QasmSimulatorPy.run_experiment(experiment)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/providers/basicaer/qasm_simulator.py "view source code")

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

<span id="qiskit.providers.basicaer.QasmSimulatorPy.status" />

`QasmSimulatorPy.status()`

Return the backend status.

**Returns**

the status of the backend.

**Return type**

[BackendStatus](qiskit.providers.models.BackendStatus "qiskit.providers.models.BackendStatus")

### version

<span id="qiskit.providers.basicaer.QasmSimulatorPy.version" />

`QasmSimulatorPy.version()`

Return the backend version.

**Returns**

the X.X.X version of the backend.

**Return type**

str

