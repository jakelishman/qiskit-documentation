---
title: inline_subroutines
description: API reference for qiskit.pulse.transforms.inline_subroutines
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.pulse.transforms.inline_subroutines
---

# qiskit.pulse.transforms.inline\_subroutines

<span id="qiskit.pulse.transforms.inline_subroutines" />

`inline_subroutines(program)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/pulse/transforms/canonicalization.py "view source code")

Recursively remove call instructions and inline the respective subroutine instructions.

Assigned parameter values, which are stored in the parameter table, are also applied. The subroutine is copied before the parameter assignment to avoid mutation problem.

**Parameters**

**program** (`Union`\[`Schedule`, `ScheduleBlock`]) – A program which may contain the subroutine, i.e. `Call` instruction.

**Return type**

`Union`\[`Schedule`, `ScheduleBlock`]

**Returns**

A schedule without subroutine.

**Raises**

[**PulseError**](pulse#qiskit.pulse.PulseError "qiskit.pulse.PulseError") – When input program is not valid data format.

