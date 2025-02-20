---
title: AlignFunc
description: API reference for qiskit.pulse.transforms.AlignFunc
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.pulse.transforms.AlignFunc
---

# AlignFunc

<span id="qiskit.pulse.transforms.AlignFunc" />

`AlignFunc(duration, func)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/pulse/transforms/alignments.py "view source code")

Bases: [`qiskit.pulse.transforms.alignments.AlignmentKind`](pulse#qiskit.pulse.transforms.AlignmentKind "qiskit.pulse.transforms.alignments.AlignmentKind")

Allocate instructions at position specified by callback function.

The position is specified for each instruction of index `j` as a fractional coordinate in \[0, 1] within the specified duration.

Instructions played on different channels are also arranged in a sequence. This alignment is convenient to create dynamical decoupling sequences such as UDD.

For example, UDD sequence with 10 pulses can be specified with following function.

```python
def udd10_pos(j):
return np.sin(np.pi*j/(2*10 + 2))**2
```

<Admonition title="Note" type="note">
  This context cannot be QPY serialized because of the callable. If you use this context, your program cannot be saved in QPY format.
</Admonition>

Create new equispaced context.

**Parameters**

*   **duration** (`Union`\[`int`, [`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")]) – Duration of this context. This should be larger than the schedule duration. If the specified duration is shorter than the schedule duration, no alignment is performed and the input schedule is just returned. This duration can be parametrized.
*   **func** (`Callable`) – A function that takes an index of sub-schedule and returns the fractional coordinate of of that sub-schedule. The returned value should be defined within \[0, 1]. The pulse index starts from 1.

## Methods

### align

<span id="qiskit.pulse.transforms.AlignFunc.align" />

`AlignFunc.align(schedule)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/pulse/transforms/alignments.py "view source code")

Reallocate instructions according to the policy.

Only top-level sub-schedules are aligned. If sub-schedules are nested, nested schedules are not recursively aligned.

**Parameters**

**schedule** ([`Schedule`](qiskit.pulse.Schedule "qiskit.pulse.schedule.Schedule")) – Schedule to align.

**Return type**

[`Schedule`](qiskit.pulse.Schedule "qiskit.pulse.schedule.Schedule")

**Returns**

Schedule with reallocated instructions.

### to\_dict

<span id="qiskit.pulse.transforms.AlignFunc.to_dict" />

`AlignFunc.to_dict()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/pulse/transforms/alignments.py "view source code")

Returns dictionary to represent this alignment.

<Admonition title="Note" type="note">
  `func` is not presented in this dictionary. Just name.
</Admonition>

**Return type**

`Dict`\[`str`, `Any`]

## Attributes

<span id="qiskit.pulse.transforms.AlignFunc.duration" />

### duration

Return context duration.

<span id="qiskit.pulse.transforms.AlignFunc.func" />

### func

Return context alignment function.

<span id="qiskit.pulse.transforms.AlignFunc.is_sequential" />

### is\_sequential

**Return type**

`bool`

