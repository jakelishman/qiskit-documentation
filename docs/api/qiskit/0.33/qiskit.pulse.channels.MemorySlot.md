---
title: MemorySlot
description: API reference for qiskit.pulse.channels.MemorySlot
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.pulse.channels.MemorySlot
---

# MemorySlot

<span id="qiskit.pulse.channels.MemorySlot" />

`MemorySlot(index)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/pulse/channels.py "view source code")

Bases: [`qiskit.pulse.channels.Channel`](pulse#qiskit.pulse.channels.Channel "qiskit.pulse.channels.Channel")

Memory slot channels represent classical memory storage.

Channel class.

**Parameters**

**index** (`int`) – Index of channel.

## Methods

### is\_parameterized

<span id="qiskit.pulse.channels.MemorySlot.is_parameterized" />

`MemorySlot.is_parameterized()`

Return True iff the channel is parameterized.

**Return type**

`bool`

## Attributes

<span id="qiskit.pulse.channels.MemorySlot.index" />

### index

Return the index of this channel. The index is a label for a control signal line typically mapped trivially to a qubit index. For instance, `DriveChannel(0)` labels the signal line driving the qubit labeled with index 0.

**Return type**

`Union`\[`int`, `ParameterExpression`]

<span id="qiskit.pulse.channels.MemorySlot.name" />

### name

Return the shorthand alias for this channel, which is based on its type and index.

**Return type**

`str`

<span id="qiskit.pulse.channels.MemorySlot.parameters" />

### parameters

Parameters which determine the channel index.

**Return type**

`Set`

<span id="qiskit.pulse.channels.MemorySlot.prefix" />

### prefix

`= 'm'`

