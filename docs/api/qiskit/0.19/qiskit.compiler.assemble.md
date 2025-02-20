---
title: assemble
description: API reference for qiskit.compiler.assemble
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.compiler.assemble
---

# assemble

<span id="qiskit.compiler.assemble" />

`assemble(experiments, backend=None, qobj_id=None, qobj_header=None, shots=None, memory=False, max_credits=None, seed_simulator=None, qubit_lo_freq=None, meas_lo_freq=None, qubit_lo_range=None, meas_lo_range=None, schedule_los=None, meas_level=MeasLevel.CLASSIFIED, meas_return=MeasReturnType.AVERAGE, meas_map=None, memory_slot_size=100, rep_time=None, parameter_binds=None, parametric_pulses=None, **run_config)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/compiler/assemble.py "view source code")

Assemble a list of circuits or pulse schedules into a `Qobj`.

This function serializes the payloads, which could be either circuits or schedules, to create `Qobj` “experiments”. It further annotates the experiment payload with header and configurations.

**Parameters**

*   **experiments** (`Union`\[[`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit"), `List`\[[`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit")], [`Schedule`](qiskit.pulse.Schedule "qiskit.pulse.schedule.Schedule"), `List`\[[`Schedule`](qiskit.pulse.Schedule "qiskit.pulse.schedule.Schedule")]]) – Circuit(s) or pulse schedule(s) to execute

*   **backend** (`Optional`\[[`BaseBackend`](qiskit.providers.BaseBackend "qiskit.providers.basebackend.BaseBackend")]) – If set, some runtime options are automatically grabbed from `backend.configuration()` and `backend.defaults()`. If any other option is explicitly set (e.g., `rep_time`), it will override the backend’s. If any other options is set in the run\_config, it will also override the backend’s.

*   **qobj\_id** (`Optional`\[`str`]) – String identifier to annotate the `Qobj`

*   **qobj\_header** (`Union`\[[`QobjHeader`](qiskit.qobj.QobjHeader "qiskit.qobj.qasm_qobj.QobjHeader"), `Dict`, `None`]) – User input that will be inserted in `Qobj` header, and will also be copied to the corresponding Result header. Headers do not affect the run.

*   **shots** (`Optional`\[`int`]) – Number of repetitions of each circuit, for sampling. Default: 1024 or `max_shots` from the backend configuration, whichever is smaller

*   **memory** (`Optional`\[`bool`]) – If `True`, per-shot measurement bitstrings are returned as well (provided the backend supports it). For OpenPulse jobs, only measurement level 2 supports this option.

*   **max\_credits** (`Optional`\[`int`]) – Maximum credits to spend on job. Default: 10

*   **seed\_simulator** (`Optional`\[`int`]) – Random seed to control sampling, for when backend is a simulator

*   **qubit\_lo\_freq** (`Optional`\[`List`\[`int`]]) – List of default qubit LO frequencies in Hz. Will be overridden by `schedule_los` if set.

*   **meas\_lo\_freq** (`Optional`\[`List`\[`int`]]) – List of default measurement LO frequencies in Hz. Will be overridden by `schedule_los` if set.

*   **qubit\_lo\_range** (`Optional`\[`List`\[`int`]]) – List of drive LO ranges each of form `[range_min, range_max]` in Hz. Used to validate the supplied qubit frequencies.

*   **meas\_lo\_range** (`Optional`\[`List`\[`int`]]) – List of measurement LO ranges each of form `[range_min, range_max]` in Hz. Used to validate the supplied qubit frequencies.

*   **schedule\_los** (`Union`\[`List`\[`Union`\[`Dict`\[[`PulseChannel`](qiskit.pulse.channels#qiskit.pulse.channels.PulseChannel "qiskit.pulse.channels.PulseChannel"), `float`], `LoConfig`]], `Dict`\[[`PulseChannel`](qiskit.pulse.channels#qiskit.pulse.channels.PulseChannel "qiskit.pulse.channels.PulseChannel"), `float`], `LoConfig`, `None`]) – Experiment LO configurations, frequencies are given in Hz.

*   **meas\_level** (`Union`\[`int`, `MeasLevel`]) – Set the appropriate level of the measurement output for pulse experiments.

*   **meas\_return** (`Union`\[`str`, `MeasReturnType`]) –

    Level of measurement data for the backend to return.

    **For `meas_level` 0 and 1:**

    *   `single` returns information from every shot.
    *   `avg` returns average measurement output (averaged over number of shots).

*   **meas\_map** (`Optional`\[`List`\[`List`\[[`Qubit`](qiskit.circuit.Qubit "qiskit.circuit.quantumregister.Qubit")]]]) – List of lists, containing qubits that must be measured together.

*   **memory\_slot\_size** (`int`) – Size of each memory slot if the output is Level 0.

*   **rep\_time** (`Optional`\[`float`]) – Repetition time of the experiment in s. The delay between experiments will be `rep_time`. Must be from the list provided by the device.

*   **parameter\_binds** (`Optional`\[`List`\[`Dict`\[[`Parameter`](qiskit.circuit.Parameter "qiskit.circuit.parameter.Parameter"), `float`]]]) – List of Parameter bindings over which the set of experiments will be executed. Each list element (bind) should be of the form \{Parameter1: value1, Parameter2: value2, …}. All binds will be executed across all experiments; e.g., if parameter\_binds is a length-n list, and there are m experiments, a total of m x n experiments will be run (one for each experiment/bind pair).

*   **parametric\_pulses** (`Optional`\[`List`\[`str`]]) –

    A list of pulse shapes which are supported internally on the backend. Example:

    ```python
    ['gaussian', 'constant']
    ```

*   **\*\*run\_config** – Extra arguments used to configure the run (e.g., for Aer configurable backends). Refer to the backend documentation for details on these arguments.

**Return type**

[`Qobj`](qiskit.qobj.Qobj "qiskit.qobj.Qobj")

**Returns**

A `Qobj` that can be run on a backend. Depending on the type of input, this will be either a `QasmQobj` or a `PulseQobj`.

**Raises**

**QiskitError** – if the input cannot be interpreted as either circuits or schedules

