---
title: MemorySlot
description: API reference for qiskit.pulse.MemorySlot
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.pulse.MemorySlot
---

# MemorySlot

<span id="qiskit.pulse.MemorySlot" />

`MemorySlot(index)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/pulse/channels.py "view source code")

Bases: `qiskit.pulse.channels.Channel`

Memory slot channels represent classical memory storage.

Channel class.

**Parameters**

**index** (`int`) – Index of channel.

## Methods

### assign

<span id="qiskit.pulse.MemorySlot.assign" />

`MemorySlot.assign(parameter, value)`

Return a new channel with the input Parameter assigned to value.

**Parameters**

*   **parameter** (`Parameter`) – A parameter in this expression whose value will be updated.
*   **value** (`Union`\[`ParameterExpression`, `float`]) – The new value to bind to.

**Return type**

`Channel`

**Returns**

A new channel with updated parameters.

**Raises**

[**PulseError**](qiskit.pulse.PulseError "qiskit.pulse.PulseError") – If the parameter is not present in the channel.

### is\_parameterized

<span id="qiskit.pulse.MemorySlot.is_parameterized" />

`MemorySlot.is_parameterized()`

Return True iff the channel is parameterized.

**Return type**

`bool`

## Attributes

<span id="qiskit.pulse.MemorySlot.index" />

### index

Return the index of this channel. The index is a label for a control signal line typically mapped trivially to a qubit index. For instance, `DriveChannel(0)` labels the signal line driving the qubit labeled with index 0.

**Return type**

`Union`\[`int`, `ParameterExpression`]

<span id="qiskit.pulse.MemorySlot.name" />

### name

Return the shorthand alias for this channel, which is based on its type and index.

**Return type**

`str`

<span id="qiskit.pulse.MemorySlot.parameters" />

### parameters

Parameters which determine the channel index.

**Return type**

`Set`

<span id="qiskit.pulse.MemorySlot.prefix" />

### prefix

`= 'm'`

