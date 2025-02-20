---
title: block_to_schedule
description: API reference for qiskit.pulse.transforms.block_to_schedule
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.pulse.transforms.block_to_schedule
---

<span id="qiskit-pulse-transforms-block-to-schedule" />

# qiskit.pulse.transforms.block\_to\_schedule

<span id="qiskit.pulse.transforms.block_to_schedule" />

`block_to_schedule(block)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/pulse/transforms/canonicalization.py "view source code")

Convert `ScheduleBlock` to `Schedule`.

**Parameters**

**block** ([*ScheduleBlock*](qiskit.pulse.ScheduleBlock "qiskit.pulse.schedule.ScheduleBlock")) – A `ScheduleBlock` to convert.

**Returns**

Scheduled pulse program.

**Raises**

*   **UnassignedDurationError** – When any instruction duration is not assigned.
*   [**PulseError**](pulse#qiskit.pulse.PulseError "qiskit.pulse.PulseError") – When the alignment context duration is shorter than the schedule duration.

**Return type**

[*Schedule*](qiskit.pulse.Schedule "qiskit.pulse.schedule.Schedule")

<Admonition title="Note" type="note">
  This transform may insert barriers in between contexts.
</Admonition>

