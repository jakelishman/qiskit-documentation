---
title: schedule_circuit
description: API reference for qiskit.scheduler.schedule_circuit
in_page_toc_min_heading_level: 1
python_api_type: module
python_api_name: qiskit.scheduler.schedule_circuit
---

<span id="module-qiskit.scheduler.schedule_circuit" />

<span id="qiskit-scheduler-schedule-circuit" />

# qiskit.scheduler.schedule\_circuit

QuantumCircuit to Pulse scheduler.

## Functions

|                                                                                                                                                                 |                                                                              |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| [`schedule_circuit`](#qiskit.scheduler.schedule_circuit.schedule_circuit "qiskit.scheduler.schedule_circuit.schedule_circuit")(circuit, schedule\_config\[, …]) | Basic scheduling pass from a circuit to a pulse Schedule, using the backend. |

<span id="qiskit.scheduler.schedule_circuit.schedule_circuit" />

`schedule_circuit(circuit, schedule_config, method=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.16/qiskit/scheduler/schedule_circuit.py "view source code")

Basic scheduling pass from a circuit to a pulse Schedule, using the backend. If no method is specified, then a basic, as late as possible scheduling pass is performed, i.e. pulses are scheduled to occur as late as possible.

Supported methods:

> *   `'as_soon_as_possible'`: Schedule pulses greedily, as early as possible on a qubit resource. alias: `'asap'`)
> *   `'as_late_as_possible'`: Schedule pulses late– keep qubits in the ground state when possible. (alias: `'alap'`)

**Parameters**

*   **circuit** (`QuantumCircuit`) – The quantum circuit to translate.
*   **schedule\_config** (`ScheduleConfig`) – Backend specific parameters used for building the Schedule.
*   **method** (`Optional`\[`str`]) – The scheduling pass method to use.

**Return type**

`Schedule`

**Returns**

Schedule corresponding to the input circuit.

**Raises**

**QiskitError** – If method isn’t recognized.

