---
title: add_implicit_acquires
description: API reference for qiskit.pulse.transforms.add_implicit_acquires
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.pulse.transforms.add_implicit_acquires
---

# qiskit.pulse.transforms.add\_implicit\_acquires

<span id="qiskit.pulse.transforms.add_implicit_acquires" />

`add_implicit_acquires(schedule, meas_map)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/pulse/transforms/canonicalization.py "view source code")

Return a new schedule with implicit acquires from the measurement mapping replaced by explicit ones.

<Admonition title="Warning" type="caution">
  Since new acquires are being added, Memory Slots will be set to match the qubit index. This may overwrite your specification.
</Admonition>

**Parameters**

*   **schedule** (`Union`\[[`Schedule`](qiskit.pulse.Schedule "qiskit.pulse.schedule.Schedule"), [`Instruction`](pulse#qiskit.pulse.instructions.Instruction "qiskit.pulse.instructions.instruction.Instruction")]) – Schedule to be aligned.
*   **meas\_map** (`List`\[`List`\[`int`]]) – List of lists of qubits that are measured together.

**Return type**

[`Schedule`](qiskit.pulse.Schedule "qiskit.pulse.schedule.Schedule")

**Returns**

A `Schedule` with the additional acquisition instructions.

