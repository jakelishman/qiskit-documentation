---
title: PulseQobjConfig
description: API reference for qiskit.qobj.PulseQobjConfig
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.qobj.PulseQobjConfig
---

# PulseQobjConfig

<span id="qiskit.qobj.PulseQobjConfig" />

`PulseQobjConfig(meas_level, meas_return, pulse_library, qubit_lo_freq, meas_lo_freq, memory_slot_size=None, rep_time=None, rep_delay=None, shots=None, max_credits=None, seed_simulator=None, memory_slots=None, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/qobj/pulse_qobj.py "view source code")

Bases: `qiskit.qobj.common.QobjDictField`

A configuration for a Pulse Qobj.

Instantiate a PulseQobjConfig object.

**Parameters**

*   **meas\_level** (*int*) – The measurement level to use.
*   **meas\_return** (*int*) – The level of measurement information to return.
*   **pulse\_library** (*list*) – A list of [`PulseLibraryItem`](qiskit.qobj.PulseLibraryItem "qiskit.qobj.PulseLibraryItem") objects which define the set of primitive pulses
*   **qubit\_lo\_freq** (*list*) – List of frequencies (as floats) for the qubit driver LO’s in GHz.
*   **meas\_lo\_freq** (*list*) – List of frequencies (as floats) for the’ measurement driver LO’s in GHz.
*   **memory\_slot\_size** (*int*) – Size of each memory slot if the output is Level 0.
*   **rep\_time** (*int*) – Time per program execution in sec. Must be from the list provided by the backend (`backend.configuration().rep_times`). Defaults to the first entry in `backend.configuration().rep_times`.
*   **rep\_delay** (*float*) – Delay between programs in sec. Only supported on certain backends (`backend.configuration().dynamic_reprate_enabled` ). If supported, `rep_delay` will be used instead of `rep_time` and must be from the range supplied by the backend (`backend.configuration().rep_delay_range`). Default is `backend.configuration().default_rep_delay`.
*   **shots** (*int*) – The number of shots
*   **max\_credits** (*int*) – DEPRECATED This parameter is deprecated as of Qiskit Terra 0.20.0, and will be removed in a future release. This parameter has no effect on modern IBM Quantum systems, and no alternative is necessary.
*   **seed\_simulator** (*int*) – the seed to use in the simulator
*   **memory\_slots** (*list*) – The number of memory slots on the device
*   **kwargs** – Additional free form key value fields to add to the configuration

## Methods

### from\_dict

<span id="qiskit.qobj.PulseQobjConfig.from_dict" />

`classmethod PulseQobjConfig.from_dict(data)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/qobj/pulse_qobj.py "view source code")

Create a new PulseQobjConfig object from a dictionary.

**Parameters**

**data** (*dict*) – A dictionary for the config

**Returns**

The object from the input dictionary.

**Return type**

[PulseQobjConfig](qiskit.qobj.PulseQobjConfig "qiskit.qobj.PulseQobjConfig")

### to\_dict

<span id="qiskit.qobj.PulseQobjConfig.to_dict" />

`PulseQobjConfig.to_dict()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/qobj/pulse_qobj.py "view source code")

Return a dictionary format representation of the Pulse Qobj config.

**Returns**

The dictionary form of the PulseQobjConfig.

**Return type**

dict

