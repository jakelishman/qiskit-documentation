---
title: Result
description: API reference for qiskit.result.Result
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.result.Result
---

# Result

<span id="qiskit.result.Result" />

`Result(backend_name, backend_version, qobj_id, job_id, success, results, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/result/result.py "view source code")

Model for Results.

Please note that this class only describes the required fields. For the full description of the model, please check `ResultSchema`.

<span id="qiskit.result.Result.backend_name" />

### backend\_name

backend name.

**Type**

str

<span id="qiskit.result.Result.backend_version" />

### backend\_version

backend version, in the form X.Y.Z.

**Type**

str

<span id="qiskit.result.Result.qobj_id" />

### qobj\_id

user-generated Qobj id.

**Type**

str

<span id="qiskit.result.Result.job_id" />

### job\_id

unique execution id from the backend.

**Type**

str

<span id="qiskit.result.Result.success" />

### success

True if complete input qobj executed correctly. (Implies each experiment success)

**Type**

bool

<span id="qiskit.result.Result.results" />

### results

corresponding results for array of experiments of the input qobj

**Type**

list\[ExperimentResult]

BaseModel initializer.

<Admonition title="Note" type="note">
  The `validate` argument is used for controlling the behavior of the schema binding, and will not be present on the created object.
</Admonition>

## Attributes

### schema

<span id="qiskit.result.Result.schema" />

`=`

### shallow\_schema

<span id="qiskit.result.Result.shallow_schema" />

`=`

## Methods

### data

<span id="qiskit.result.Result.data" />

`Result.data(experiment=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/result/result.py "view source code")

Get the raw data for an experiment.

Note this data will be a single classical and quantum register and in a format required by the results schema. We recommend that most users use the get\_xxx method, and the data will be post-processed for the data type.

**Parameters**

**experiment** (*str or* [*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")  *or*[*Schedule*](qiskit.pulse.Schedule "qiskit.pulse.Schedule") *or int or None*) – the index of the experiment. Several types are accepted for convenience:: \* str: the name of the experiment. \* QuantumCircuit: the name of the circuit instance will be used. \* Schedule: the name of the schedule instance will be used. \* int: the position of the experiment. \* None: if there is only one experiment, returns it.

**Returns**

A dictionary of results data for an experiment. The data depends on the backend it ran on and the settings of meas\_level, meas\_return and memory.

QASM backends return a dictionary of dictionary with the key ‘counts’ and with the counts, with the second dictionary keys containing a string in hex format (`0x123`) and values equal to the number of times this outcome was measured.

Statevector backends return a dictionary with key ‘statevector’ and values being a list\[list\[complex components]] list of 2^num\_qubits complex amplitudes. Where each complex number is represented as a 2 entry list for each component. For example, a list of \[0.5+1j, 0-1j] would be represented as \[\[0.5, 1], \[0, -1]].

Unitary backends return a dictionary with key ‘unitary’ and values being a list\[list\[list\[complex components]]] list of 2^num\_qubits x 2^num\_qubits complex amplitudes in a two entry list for each component. For example if the amplitude is \[\[0.5+0j, 0-1j], …] the value returned will be \[\[\[0.5, 0], \[0, -1]], …].

The simulator backends also have an optional key ‘snapshots’ which returns a dict of snapshots specified by the simulator backend. The value is of the form dict\[slot: dict\[str: array]] where the keys are the requested snapshot slots, and the values are a dictionary of the snapshots.

**Return type**

dict

**Raises**

**QiskitError** – if data for the experiment could not be retrieved.

### from\_dict

<span id="qiskit.result.Result.from_dict" />

`classmethod Result.from_dict(dict_)`

Deserialize a dict of simple types into an instance of this class.

Note that this method requires that the model is bound with `@bind_schema`.

### get\_counts

<span id="qiskit.result.Result.get_counts" />

`Result.get_counts(experiment=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/result/result.py "view source code")

Get the histogram data of an experiment.

**Parameters**

**experiment** (*str or* [*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")  *or*[*Schedule*](qiskit.pulse.Schedule "qiskit.pulse.Schedule") *or int or None*) – the index of the experiment, as specified by `get_data()`.

**Returns**

**int] or list\[dict\[str:int]]: a dictionary or a list of**

dictionaries. A dictionary has the counts for each qubit with the keys containing a string in binary format and separated according to the registers in circuit (e.g. `0100 1110`). The string is little-endian (cr\[0] on the right hand side).

**Return type**

dict\[str

**Raises**

**QiskitError** – if there are no counts for the experiment.

### get\_memory

<span id="qiskit.result.Result.get_memory" />

`Result.get_memory(experiment=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/result/result.py "view source code")

Get the sequence of memory states (readouts) for each shot The data from the experiment is a list of format \[‘00000’, ‘01000’, ‘10100’, ‘10100’, ‘11101’, ‘11100’, ‘00101’, …, ‘01010’]

**Parameters**

**experiment** (*str or* [*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")  *or*[*Schedule*](qiskit.pulse.Schedule "qiskit.pulse.Schedule") *or int or None*) – the index of the experiment, as specified by `data()`.

**Returns**

**Either the list of each outcome, formatted according to**

registers in circuit or a complex numpy np.darray with shape:

| meas\_level | meas\_return | shape                                                 |
| ----------- | ------------ | ----------------------------------------------------- |
| 0           | single       | np.ndarray\[shots, memory\_slots, memory\_slot\_size] |
| 0           | avg          | np.ndarray\[memory\_slots, memory\_slot\_size]        |
| 1           | single       | np.ndarray\[shots, memory\_slots]                     |
| 1           | avg          | np.ndarray\[memory\_slots]                            |
| 2           | memory=True  | list                                                  |

**Return type**

List\[str] or np.ndarray

**Raises**

**QiskitError** – if there is no memory data for the circuit.

### get\_statevector

<span id="qiskit.result.Result.get_statevector" />

`Result.get_statevector(experiment=None, decimals=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/result/result.py "view source code")

Get the final statevector of an experiment.

**Parameters**

*   **experiment** (*str or* [*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")  *or*[*Schedule*](qiskit.pulse.Schedule "qiskit.pulse.Schedule") *or int or None*) – the index of the experiment, as specified by `data()`.
*   **decimals** (*int*) – the number of decimals in the statevector. If None, does not round.

**Returns**

list of 2^num\_qubits complex amplitudes.

**Return type**

list\[complex]

**Raises**

**QiskitError** – if there is no statevector for the experiment.

### get\_unitary

<span id="qiskit.result.Result.get_unitary" />

`Result.get_unitary(experiment=None, decimals=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/result/result.py "view source code")

Get the final unitary of an experiment.

**Parameters**

*   **experiment** (*str or* [*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")  *or*[*Schedule*](qiskit.pulse.Schedule "qiskit.pulse.Schedule") *or int or None*) – the index of the experiment, as specified by `data()`.
*   **decimals** (*int*) – the number of decimals in the unitary. If None, does not round.

**Returns**

**list of 2^num\_qubits x 2^num\_qubits complex**

amplitudes.

**Return type**

list\[list\[complex]]

**Raises**

**QiskitError** – if there is no unitary for the experiment.

### to\_dict

<span id="qiskit.result.Result.to_dict" />

`Result.to_dict()`

Serialize the model into a Python dict of simple types.

Note that this method requires that the model is bound with `@bind_schema`.

