---
title: generate_scheduling
description: API reference for qiskit.transpiler.preset_passmanagers.common.generate_scheduling
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.transpiler.preset_passmanagers.common.generate_scheduling
---

# qiskit.transpiler.preset\_passmanagers.common.generate\_scheduling

<span id="qiskit.transpiler.preset_passmanagers.common.generate_scheduling" />

`generate_scheduling(instruction_durations, scheduling_method, timing_constraints, inst_map)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/transpiler/preset_passmanagers/common.py "view source code")

Generate a post optimization scheduling [`PassManager`](qiskit.transpiler.PassManager "qiskit.transpiler.PassManager")

**Parameters**

*   **instruction\_durations** (*dict*) – The dictionary of instruction durations
*   **scheduling\_method** (*str*) – The scheduling method to use, can either be `'asap'`/`'as_soon_as_possible'` or `'alap'`/`'as_late_as_possible'`
*   **timing\_constraints** (*TimingConstraints*) – Hardware time alignment restrictions.
*   **inst\_map** ([*InstructionScheduleMap*](qiskit.pulse.InstructionScheduleMap "qiskit.pulse.InstructionScheduleMap")) – Mapping object that maps gate to schedule.

**Returns**

The scheduling pass manager

**Return type**

[PassManager](qiskit.transpiler.PassManager "qiskit.transpiler.PassManager")

**Raises**

[**TranspilerError**](qiskit.transpiler.TranspilerError "qiskit.transpiler.TranspilerError") – If the `scheduling_method` kwarg is not a valid value

