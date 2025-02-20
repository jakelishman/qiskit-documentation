---
title: FakeOslo
description: API reference for qiskit.providers.fake_provider.FakeOslo
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.fake_provider.FakeOslo
---

# FakeOslo

<span id="qiskit.providers.fake_provider.FakeOslo" />

`qiskit.providers.fake_provider.FakeOslo`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/providers/fake_provider/backends/oslo/fake_oslo.py "view source code")

Bases: [`FakeBackendV2`](providers_fake_provider#qiskit.providers.fake_provider.fake_backend.FakeBackendV2 "qiskit.providers.fake_provider.fake_backend.FakeBackendV2")

A fake 7 qubit backend.

FakeBackendV2 initializer.

## Attributes

<span id="qiskit.providers.fake_provider.FakeOslo.backend_name" />

### backend\_name

`= 'fake_oslo'`

<span id="qiskit.providers.fake_provider.FakeOslo.conf_filename" />

### conf\_filename

`= 'conf_oslo.json'`

<span id="qiskit.providers.fake_provider.FakeOslo.coupling_map" />

### coupling\_map

Return the [`CouplingMap`](qiskit.transpiler.CouplingMap "qiskit.transpiler.CouplingMap") object

<span id="qiskit.providers.fake_provider.FakeOslo.defs_filename" />

### defs\_filename

`= 'defs_oslo.json'`

<span id="qiskit.providers.fake_provider.FakeOslo.dirname" />

### dirname

`= '/home/runner/work/qiskit/qiskit/qiskit/providers/fake_provider/backends/oslo'`

<span id="qiskit.providers.fake_provider.FakeOslo.dt" />

### dt

Return the system time resolution of input signals

This is required to be implemented if the backend supports Pulse scheduling.

**Returns**

The input signal timestep in seconds. If the backend doesn’t define `dt`, `None` will be returned.

<span id="qiskit.providers.fake_provider.FakeOslo.dtm" />

### dtm

Return the system time resolution of output signals

**Returns**

The output signal timestep in seconds.

<span id="qiskit.providers.fake_provider.FakeOslo.instruction_durations" />

### instruction\_durations

Return the [`InstructionDurations`](qiskit.transpiler.InstructionDurations "qiskit.transpiler.InstructionDurations") object.

<span id="qiskit.providers.fake_provider.FakeOslo.instruction_schedule_map" />

### instruction\_schedule\_map

Return the [`InstructionScheduleMap`](qiskit.pulse.InstructionScheduleMap "qiskit.pulse.InstructionScheduleMap") for the instructions defined in this backend’s target.

<span id="qiskit.providers.fake_provider.FakeOslo.instructions" />

### instructions

A list of Instruction tuples on the backend of the form `(instruction, (qubits)`

<span id="qiskit.providers.fake_provider.FakeOslo.max_circuits" />

### max\_circuits

<span id="qiskit.providers.fake_provider.FakeOslo.meas_map" />

### meas\_map

Return the grouping of measurements which are multiplexed This is required to be implemented if the backend supports Pulse scheduling.

**Returns**

The grouping of measurements which are multiplexed

<span id="qiskit.providers.fake_provider.FakeOslo.num_qubits" />

### num\_qubits

Return the number of qubits the backend has.

<span id="qiskit.providers.fake_provider.FakeOslo.operation_names" />

### operation\_names

A list of instruction names that the backend supports.

<span id="qiskit.providers.fake_provider.FakeOslo.operations" />

### operations

A list of [`Instruction`](qiskit.circuit.Instruction "qiskit.circuit.Instruction") instances that the backend supports.

<span id="qiskit.providers.fake_provider.FakeOslo.options" />

### options

Return the options for the backend

The options of a backend are the dynamic parameters defining how the backend is used. These are used to control the [`run()`](#qiskit.providers.fake_provider.FakeOslo.run "qiskit.providers.fake_provider.FakeOslo.run") method.

<span id="qiskit.providers.fake_provider.FakeOslo.props_filename" />

### props\_filename

`= 'props_oslo.json'`

<span id="qiskit.providers.fake_provider.FakeOslo.provider" />

### provider

Return the backend Provider.

**Returns**

the Provider responsible for the backend.

**Return type**

[Provider](qiskit.providers.Provider "qiskit.providers.Provider")

<span id="qiskit.providers.fake_provider.FakeOslo.target" />

### target

A [`qiskit.transpiler.Target`](qiskit.transpiler.Target "qiskit.transpiler.Target") object for the backend.

**Return type**

[Target](qiskit.transpiler.Target "qiskit.transpiler.Target")

<span id="qiskit.providers.fake_provider.FakeOslo.version" />

### version

`= 2`

<span id="qiskit.providers.fake_provider.FakeOslo.name" />

### name

Name of the backend.

<span id="qiskit.providers.fake_provider.FakeOslo.description" />

### description

Optional human-readable description.

<span id="qiskit.providers.fake_provider.FakeOslo.online_date" />

### online\_date

Date that the backend came online.

<span id="qiskit.providers.fake_provider.FakeOslo.backend_version" />

### backend\_version

Version of the backend being provided. This is not the same as [`BackendV2.version`](qiskit.providers.BackendV2#version "qiskit.providers.BackendV2.version"), which is the version of the [`Backend`](qiskit.providers.Backend "qiskit.providers.Backend") abstract interface.

## Methods

### acquire\_channel

<span id="qiskit.providers.fake_provider.FakeOslo.acquire_channel" />

`acquire_channel(qubit)`

Return the acquisition channel for the given qubit.

This is required to be implemented if the backend supports Pulse scheduling.

**Returns**

The Qubit measurement acquisition line.

**Return type**

[AcquireChannel](qiskit.pulse.channels.AcquireChannel "qiskit.pulse.channels.AcquireChannel")

### control\_channel

<span id="qiskit.providers.fake_provider.FakeOslo.control_channel" />

`control_channel(qubits)`

Return the secondary drive channel for the given qubit

This is typically utilized for controlling multiqubit interactions. This channel is derived from other channels.

This is required to be implemented if the backend supports Pulse scheduling.

**Parameters**

**qubits** ([*Iterable*](https://docs.python.org/3/library/typing.html#typing.Iterable "(in Python v3.12)")*\[*[*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")*]*) – Tuple or list of qubits of the form `(control_qubit, target_qubit)`.

**Returns**

The multi qubit control line.

**Return type**

List\[[ControlChannel](qiskit.pulse.channels.ControlChannel "qiskit.pulse.channels.ControlChannel")]

### drive\_channel

<span id="qiskit.providers.fake_provider.FakeOslo.drive_channel" />

`drive_channel(qubit)`

Return the drive channel for the given qubit.

This is required to be implemented if the backend supports Pulse scheduling.

**Returns**

The Qubit drive channel

**Return type**

[DriveChannel](qiskit.pulse.channels.DriveChannel "qiskit.pulse.channels.DriveChannel")

### measure\_channel

<span id="qiskit.providers.fake_provider.FakeOslo.measure_channel" />

`measure_channel(qubit)`

Return the measure stimulus channel for the given qubit.

This is required to be implemented if the backend supports Pulse scheduling.

**Returns**

The Qubit measurement stimulus line

**Return type**

[MeasureChannel](qiskit.pulse.channels.MeasureChannel "qiskit.pulse.channels.MeasureChannel")

### qubit\_properties

<span id="qiskit.providers.fake_provider.FakeOslo.qubit_properties" />

`qubit_properties(qubit)`

Return QubitProperties for a given qubit.

If there are no defined or the backend doesn’t support querying these details this method does not need to be implemented.

**Parameters**

**qubit** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")  *|*[*List*](https://docs.python.org/3/library/typing.html#typing.List "(in Python v3.12)")*\[*[*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")*]*) – The qubit to get the [`QubitProperties`](qiskit.providers.QubitProperties "qiskit.providers.QubitProperties") object for. This can be a single integer for 1 qubit or a list of qubits and a list of [`QubitProperties`](qiskit.providers.QubitProperties "qiskit.providers.QubitProperties") objects will be returned in the same order

**Returns**

The [`QubitProperties`](qiskit.providers.QubitProperties "qiskit.providers.QubitProperties") object for the specified qubit. If a list of qubits is provided a list will be returned. If properties are missing for a qubit this can be `None`.

**Raises**

[**NotImplementedError**](https://docs.python.org/3/library/exceptions.html#NotImplementedError "(in Python v3.12)") – if the backend doesn’t support querying the qubit properties

**Return type**

[*QubitProperties*](qiskit.providers.QubitProperties "qiskit.providers.backend.QubitProperties") | [*List*](https://docs.python.org/3/library/typing.html#typing.List "(in Python v3.12)")\[[*QubitProperties*](qiskit.providers.QubitProperties "qiskit.providers.backend.QubitProperties")]

### run

<span id="qiskit.providers.fake_provider.FakeOslo.run" />

`run(run_input, **options)`

Run on the fake backend using a simulator.

This method runs circuit jobs (an individual or a list of QuantumCircuit ) and pulse jobs (an individual or a list of Schedule or ScheduleBlock) using BasicAer or Aer simulator and returns a [`Job`](qiskit.providers.Job "qiskit.providers.Job") object.

If qiskit-aer is installed, jobs will be run using AerSimulator with noise model of the fake backend. Otherwise, jobs will be run using BasicAer simulator without noise.

Currently noisy simulation of a pulse job is not supported yet in FakeBackendV2.

**Parameters**

*   **run\_input** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")  *or*[*Schedule*](qiskit.pulse.Schedule "qiskit.pulse.Schedule")  *or*[*ScheduleBlock*](qiskit.pulse.ScheduleBlock "qiskit.pulse.ScheduleBlock")  *or*[*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")) – An individual or a list of [`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit"), [`ScheduleBlock`](qiskit.pulse.ScheduleBlock "qiskit.pulse.ScheduleBlock"), or [`Schedule`](qiskit.pulse.Schedule "qiskit.pulse.Schedule") objects to run on the backend.
*   **options** – Any kwarg options to pass to the backend for running the config. If a key is also present in the options attribute/object then the expectation is that the value specified will be used instead of what’s set in the options object.

**Returns**

The job object for the run

**Return type**

[Job](qiskit.providers.Job "qiskit.providers.Job")

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – If a pulse job is supplied and qiskit-aer is not installed.

### set\_options

<span id="qiskit.providers.fake_provider.FakeOslo.set_options" />

`set_options(**fields)`

Set the options fields for the backend

This method is used to update the options of a backend. If you need to change any of the options prior to running just pass in the kwarg with the new value for the options.

**Parameters**

**fields** – The fields to update the options

**Raises**

[**AttributeError**](https://docs.python.org/3/library/exceptions.html#AttributeError "(in Python v3.12)") – If the field passed in is not part of the options

