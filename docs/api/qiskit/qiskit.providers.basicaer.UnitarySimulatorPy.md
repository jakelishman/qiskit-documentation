---
title: UnitarySimulatorPy
description: API reference for qiskit.providers.basicaer.UnitarySimulatorPy
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.basicaer.UnitarySimulatorPy
---

# UnitarySimulatorPy

<span id="qiskit.providers.basicaer.UnitarySimulatorPy" />

`qiskit.providers.basicaer.UnitarySimulatorPy(configuration=None, provider=None, **fields)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/providers/basicaer/unitary_simulator.py "view source code")

Bases: [`BackendV1`](qiskit.providers.BackendV1 "qiskit.providers.backend.BackendV1")

Python implementation of a unitary simulator.

Initialize a backend class

**Parameters**

*   **configuration** ([*BackendConfiguration*](qiskit.providers.models.BackendConfiguration "qiskit.providers.models.BackendConfiguration")) – A backend configuration object for the backend object.
*   **provider** ([*qiskit.providers.Provider*](qiskit.providers.Provider "qiskit.providers.Provider")) – Optionally, the provider object that this Backend comes from.
*   **fields** – kwargs for the values to use to override the default options.

**Raises**

[**AttributeError**](https://docs.python.org/3/library/exceptions.html#AttributeError "(in Python v3.12)") – if input field not a valid options

In addition to the public abstract methods, subclasses should also implement the following private methods:

`classmethod _default_options()`

Return the default options

This method will return a [`qiskit.providers.Options`](qiskit.providers.Options "qiskit.providers.Options") subclass object that will be used for the default options. These should be the default parameters to use for the options of the backend.

**Returns**

**A options object with**

default values set

**Return type**

[qiskit.providers.Options](qiskit.providers.Options "qiskit.providers.Options")

## Attributes

<span id="qiskit.providers.basicaer.UnitarySimulatorPy.DEFAULT_CONFIGURATION" />

### DEFAULT\_CONFIGURATION = \{'backend\_name'

`= {'backend_name':`

`= {'backend_name': 'unitary_simulator', 'backend_version': '1.1.0', 'basis_gates': ['u1', 'u2', 'u3', 'rz', 'sx', 'x', 'cx', 'id', 'unitary'], 'conditional': False, 'coupling_map': None, 'description': 'A python simulator for unitary matrix corresponding to a circuit', 'gates': [{'name': 'u1', 'parameters': ['lambda'], 'qasm_def': 'gate u1(lambda) q { U(0,0,lambda) q; }'}, {'name': 'u2', 'parameters': ['phi', 'lambda'], 'qasm_def': 'gate u2(phi,lambda) q { U(pi/2,phi,lambda) q; }'}, {'name': 'u3', 'parameters': ['theta', 'phi', 'lambda'], 'qasm_def': 'gate u3(theta,phi,lambda) q { U(theta,phi,lambda) q; }'}, {'name': 'rz', 'parameters': ['phi'], 'qasm_def': 'gate rz(phi) q { U(0,0,phi) q; }'}, {'name': 'sx', 'parameters': [], 'qasm_def': 'gate sx(phi) q { U(pi/2,7*pi/2,pi/2) q; }'}, {'name': 'x', 'parameters': [], 'qasm_def': 'gate x q { U(pi,7*pi/2,pi/2) q; }'}, {'name': 'cx', 'parameters': [], 'qasm_def': 'gate cx c,t { CX c,t; }'}, {'name': 'id', 'parameters': [], 'qasm_def': 'gate id a { U(0,0,0) a; }'}, {'name': 'unitary', 'parameters': ['matrix'], 'qasm_def': 'unitary(matrix) q1, q2,...'}], 'local': True, 'max_shots': 0, 'memory': False, 'n_qubits': 14, 'open_pulse': False, 'simulator': True, 'url': 'https://github.com/Qiskit/qiskit-terra'}`

<span id="qiskit.providers.basicaer.UnitarySimulatorPy.DEFAULT_OPTIONS" />

### DEFAULT\_OPTIONS = \{'chop\_threshold'

`= {'chop_threshold':`

`= {'chop_threshold': 1e-15, 'initial_unitary': None}`

<span id="qiskit.providers.basicaer.UnitarySimulatorPy.MAX_QUBITS_MEMORY" />

### MAX\_QUBITS\_MEMORY

`= 14`

<span id="qiskit.providers.basicaer.UnitarySimulatorPy.options" />

### options

Return the options for the backend

The options of a backend are the dynamic parameters defining how the backend is used. These are used to control the [`run()`](#qiskit.providers.basicaer.UnitarySimulatorPy.run "qiskit.providers.basicaer.UnitarySimulatorPy.run") method.

<span id="qiskit.providers.basicaer.UnitarySimulatorPy.version" />

### version

`= 1`

## Methods

### configuration

<span id="qiskit.providers.basicaer.UnitarySimulatorPy.configuration" />

`configuration()`

Return the backend configuration.

**Returns**

the configuration for the backend.

**Return type**

[BackendConfiguration](qiskit.providers.models.BackendConfiguration "qiskit.providers.models.BackendConfiguration")

### name

<span id="qiskit.providers.basicaer.UnitarySimulatorPy.name" />

`name()`

Return the backend name.

**Returns**

the name of the backend.

**Return type**

[str](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")

### properties

<span id="qiskit.providers.basicaer.UnitarySimulatorPy.properties" />

`properties()`

Return the backend properties.

**Returns**

the configuration for the backend. If the backend does not support properties, it returns `None`.

**Return type**

[BackendProperties](qiskit.providers.models.BackendProperties "qiskit.providers.models.BackendProperties")

### provider

<span id="qiskit.providers.basicaer.UnitarySimulatorPy.provider" />

`provider()`

Return the backend Provider.

**Returns**

the Provider responsible for the backend.

**Return type**

[Provider](qiskit.providers.Provider "qiskit.providers.Provider")

### run

<span id="qiskit.providers.basicaer.UnitarySimulatorPy.run" />

`run(qobj, **backend_options)`

Run qobj asynchronously.

**Parameters**

*   **qobj** (*Qobj*) – payload of the experiment
*   **backend\_options** ([*dict*](https://docs.python.org/3/library/stdtypes.html#dict "(in Python v3.12)")) – backend options

**Returns**

derived from BaseJob

**Return type**

[BasicAerJob](qiskit.providers.basicaer.BasicAerJob "qiskit.providers.basicaer.BasicAerJob")

Additional Information:

```python
backend_options: Is a dict of options for the backend. It may contain
    * "initial_unitary": matrix_like
    * "chop_threshold": double

The "initial_unitary" option specifies a custom initial unitary
matrix for the simulator to be used instead of the identity
matrix. This size of this matrix must be correct for the number
of qubits inall experiments in the qobj.

The "chop_threshold" option specifies a truncation value for
setting small values to zero in the output unitary. The default
value is 1e-15.

Example::

    backend_options = {
        "initial_unitary": np.array([[1, 0, 0, 0],
                                     [0, 0, 0, 1],
                                     [0, 0, 1, 0],
                                     [0, 1, 0, 0]])
        "chop_threshold": 1e-15
    }
```

### run\_experiment

<span id="qiskit.providers.basicaer.UnitarySimulatorPy.run_experiment" />

`run_experiment(experiment)`

Run an experiment (circuit) and return a single experiment result.

**Parameters**

**experiment** ([*QasmQobjExperiment*](qiskit.qobj.QasmQobjExperiment "qiskit.qobj.QasmQobjExperiment")) – experiment from qobj experiments list

**Returns**

A result dictionary which looks something like:

```python
{
"name": name of this experiment (obtained from qobj.experiment header)
"seed": random seed used for simulation
"shots": number of shots used in the simulation
"data":
    {
    "unitary": [[[0.0, 0.0], [1.0, 0.0]],
                [[1.0, 0.0], [0.0, 0.0]]]
    },
"status": status string for the simulation
"success": boolean
"time taken": simulation time of this single experiment
}
```

**Return type**

[dict](https://docs.python.org/3/library/stdtypes.html#dict "(in Python v3.12)")

**Raises**

[**BasicAerError**](qiskit.providers.basicaer.BasicAerError "qiskit.providers.basicaer.BasicAerError") – if the number of qubits in the circuit is greater than 24. Note that the practical qubit limit is much lower than 24.

### set\_options

<span id="qiskit.providers.basicaer.UnitarySimulatorPy.set_options" />

`set_options(**fields)`

Set the options fields for the backend

This method is used to update the options of a backend. If you need to change any of the options prior to running just pass in the kwarg with the new value for the options.

**Parameters**

**fields** – The fields to update the options

**Raises**

[**AttributeError**](https://docs.python.org/3/library/exceptions.html#AttributeError "(in Python v3.12)") – If the field passed in is not part of the options

### status

<span id="qiskit.providers.basicaer.UnitarySimulatorPy.status" />

`status()`

Return the backend status.

**Returns**

the status of the backend.

**Return type**

[BackendStatus](qiskit.providers.models.BackendStatus "qiskit.providers.models.BackendStatus")

