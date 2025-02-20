---
title: target_qobj_transform
description: API reference for qiskit.pulse.transforms.target_qobj_transform
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.pulse.transforms.target_qobj_transform
---

# qiskit.pulse.transforms.target\_qobj\_transform

<span id="qiskit.pulse.transforms.target_qobj_transform" />

`target_qobj_transform(sched, remove_directives=True)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/pulse/transforms/base_transforms.py "view source code")

A basic pulse program transformation for OpenPulse API execution.

**Parameters**

*   **sched** (`Union`\[`ScheduleBlock`, `Schedule`, `Tuple`\[`int`, `Instruction`], `Instruction`, `Iterable`\[`Union`\[`Tuple`\[`int`, `Instruction`], `Instruction`]]]) – Input program to transform.
*   **remove\_directives** (`bool`) – Set True to remove compiler directives.

**Return type**

`Schedule`

**Returns**

Transformed program for execution.

