---
title: pad
description: API reference for qiskit.pulse.transforms.pad
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.pulse.transforms.pad
---

<span id="qiskit-pulse-transforms-pad" />

# qiskit.pulse.transforms.pad

<span id="qiskit.pulse.transforms.pad" />

`pad(schedule, channels=None, until=None, inplace=False, pad_with=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/pulse/transforms/canonicalization.py "view source code")

Pad the input Schedule with `Delay``s on all unoccupied timeslots until ``schedule.duration` or `until` if not `None`.

**Parameters**

*   **schedule** ([*Schedule*](qiskit.pulse.Schedule "qiskit.pulse.schedule.Schedule")) – Schedule to pad.
*   **channels** (*Iterable\[*[*Channel*](pulse#qiskit.pulse.channels.Channel "qiskit.pulse.channels.Channel")*] | None*) – Channels to pad. Defaults to all channels in `schedule` if not provided. If the supplied channel is not a member of `schedule` it will be added.
*   **until** (*int | None*) – Time to pad until. Defaults to `schedule.duration` if not provided.
*   **inplace** (*bool*) – Pad this schedule by mutating rather than returning a new schedule.
*   **pad\_with** (*Type\[*[*Instruction*](pulse#qiskit.pulse.instructions.Instruction "qiskit.pulse.instructions.instruction.Instruction")*] | None*) – Pulse `Instruction` subclass to be used for padding. Default to [`Delay`](qiskit.pulse.instructions.Delay "qiskit.pulse.instructions.Delay") instruction.

**Returns**

The padded schedule.

**Raises**

[**PulseError**](pulse#qiskit.pulse.PulseError "qiskit.pulse.PulseError") – When non pulse instruction is set to pad\_with.

**Return type**

[*Schedule*](qiskit.pulse.Schedule "qiskit.pulse.schedule.Schedule")

