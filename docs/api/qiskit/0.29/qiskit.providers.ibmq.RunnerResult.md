---
title: RunnerResult
description: API reference for qiskit.providers.ibmq.RunnerResult
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.ibmq.RunnerResult
---

# RunnerResult

<span id="qiskit.providers.ibmq.RunnerResult" />

`RunnerResult(backend_name, backend_version, qobj_id, job_id, success, results, date=None, status=None, header=None, **kwargs)`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.16/qiskit/providers/ibmq/runner_result.py "view source code")

Bases: `qiskit.result.result.Result`, `qiskit.providers.ibmq.runtime.program.result_decoder.ResultDecoder`

Result class for Qiskit Runtime program circuit-runner.

## Methods

### data

<span id="qiskit.providers.ibmq.RunnerResult.data" />

`RunnerResult.data(experiment=None)`

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

### decode

<span id="qiskit.providers.ibmq.RunnerResult.decode" />

`classmethod RunnerResult.decode(data)`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.16/qiskit/providers/ibmq/runner_result.py "view source code")

Decoding for results from Qiskit runtime jobs.

**Return type**

`RunnerResult`

### from\_dict

<span id="qiskit.providers.ibmq.RunnerResult.from_dict" />

`classmethod RunnerResult.from_dict(data)`

Create a new ExperimentResultData object from a dictionary.

**Parameters**

**data** (*dict*) – A dictionary representing the Result to create. It will be in the same format as output by [`to_dict()`](qiskit.providers.ibmq.RunnerResult#to_dict "qiskit.providers.ibmq.RunnerResult.to_dict").

**Returns**

The `Result` object from the input dictionary.

**Return type**

[Result](qiskit.result.Result "qiskit.result.Result")

### get\_counts

<span id="qiskit.providers.ibmq.RunnerResult.get_counts" />

`RunnerResult.get_counts(experiment=None)`

Get the histogram data of an experiment.

**Parameters**

**experiment** (*str or* [*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")  *or*[*Schedule*](qiskit.pulse.Schedule "qiskit.pulse.Schedule") *or int or None*) – the index of the experiment, as specified by `data([experiment])`.

**Returns**

a dictionary or a list of dictionaries. A dictionary has the counts for each qubit with the keys containing a string in binary format and separated according to the registers in circuit (e.g. `0100 1110`). The string is little-endian (cr\[0] on the right hand side).

**Return type**

dict\[str, int] or list\[dict\[str, int]]

**Raises**

**QiskitError** – if there are no counts for the experiment.

### get\_memory

<span id="qiskit.providers.ibmq.RunnerResult.get_memory" />

`RunnerResult.get_memory(experiment=None)`

Get the sequence of memory states (readouts) for each shot The data from the experiment is a list of format \[‘00000’, ‘01000’, ‘10100’, ‘10100’, ‘11101’, ‘11100’, ‘00101’, …, ‘01010’]

**Parameters**

**experiment** (*str or* [*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")  *or*[*Schedule*](qiskit.pulse.Schedule "qiskit.pulse.Schedule") *or int or None*) – the index of the experiment, as specified by `data()`.

**Returns**

Either the list of each outcome, formatted according to registers in circuit or a complex numpy np.ndarray with shape:

> | meas\_level | meas\_return | shape                                                 |
> | ----------- | ------------ | ----------------------------------------------------- |
> | 0           | single       | np.ndarray\[shots, memory\_slots, memory\_slot\_size] |
> | 0           | avg          | np.ndarray\[memory\_slots, memory\_slot\_size]        |
> | 1           | single       | np.ndarray\[shots, memory\_slots]                     |
> | 1           | avg          | np.ndarray\[memory\_slots]                            |
> | 2           | memory=True  | list                                                  |

**Return type**

List\[str] or np.ndarray

**Raises**

**QiskitError** – if there is no memory data for the circuit.

### get\_quasiprobabilities

<span id="qiskit.providers.ibmq.RunnerResult.get_quasiprobabilities" />

`RunnerResult.get_quasiprobabilities(experiment=None)`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.16/qiskit/providers/ibmq/runner_result.py "view source code")

Get quasiprobabilites associated with one or more experiments.

**Parameters**

**experiment** (`Union`\[`int`, `List`, `None`]) – Indices of experiments to grab quasiprobabilities from.

**Return type**

`Union`\[`QuasiDistribution`, `List`\[`QuasiDistribution`]]

**Returns**

A single distribution or a list of distributions.

**Raises**

**QiskitError** – If experiment result doesn’t contain quasiprobabilities.

### get\_statevector

<span id="qiskit.providers.ibmq.RunnerResult.get_statevector" />

`RunnerResult.get_statevector(experiment=None, decimals=None)`

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

<span id="qiskit.providers.ibmq.RunnerResult.get_unitary" />

`RunnerResult.get_unitary(experiment=None, decimals=None)`

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

<span id="qiskit.providers.ibmq.RunnerResult.to_dict" />

`RunnerResult.to_dict()`

Return a dictionary format representation of the Result

**Returns**

The dictionary form of the Result

**Return type**

dict

