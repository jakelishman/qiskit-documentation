---
title: channels
description: API reference for qiskit.pulse.channels
in_page_toc_min_heading_level: 1
python_api_type: module
python_api_name: qiskit.pulse.channels
---

<span id="module-qiskit.pulse.channels" />

<span id="qiskit-pulse-channels" />

# qiskit.pulse.channels

This module defines Pulse Channels. Channels include:

> *   transmit channels, which should subclass `PulseChannel`
> *   receive channels, such as `AcquireChannel`
> *   non-signal “channels” such as `SnapshotChannel`, `MemorySlot` and `RegisterChannel`.

Novel channel types can often utilize the `ControlChannel`, but if this is not sufficient, new channel types can be created. Then, they must be supported in the PulseQobj schema and the assembler.

## Classes

|                                                                                                         |                                                                                                |
| ------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| [`AcquireChannel`](#qiskit.pulse.channels.AcquireChannel "qiskit.pulse.channels.AcquireChannel")(index) | Acquire channels are used to collect data.                                                     |
| [`Channel`](#qiskit.pulse.channels.Channel "qiskit.pulse.channels.Channel")(index)                      | Base class of channels.                                                                        |
| [`ControlChannel`](#qiskit.pulse.channels.ControlChannel "qiskit.pulse.channels.ControlChannel")(index) | Control channels provide supplementary control over the qubit to the drive channel.            |
| [`DriveChannel`](#qiskit.pulse.channels.DriveChannel "qiskit.pulse.channels.DriveChannel")(index)       | Drive channels transmit signals to qubits which enact gate operations.                         |
| [`MeasureChannel`](#qiskit.pulse.channels.MeasureChannel "qiskit.pulse.channels.MeasureChannel")(index) | Measure channels transmit measurement stimulus pulses for readout.                             |
| [`MemorySlot`](#qiskit.pulse.channels.MemorySlot "qiskit.pulse.channels.MemorySlot")(index)             | Memory slot channels represent classical memory storage.                                       |
| [`PulseChannel`](#qiskit.pulse.channels.PulseChannel "qiskit.pulse.channels.PulseChannel")(index)       | Base class of transmit Channels.                                                               |
| [`RegisterSlot`](#qiskit.pulse.channels.RegisterSlot "qiskit.pulse.channels.RegisterSlot")(index)       | Classical resister slot channels represent classical registers (low-latency classical memory). |
| [`SnapshotChannel`](#qiskit.pulse.channels.SnapshotChannel "qiskit.pulse.channels.SnapshotChannel")()   | Snapshot channels are used to specify instructions for simulators.                             |

<span id="qiskit.pulse.channels.AcquireChannel" />

`AcquireChannel(index)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.16/qiskit/pulse/channels.py "view source code")

Acquire channels are used to collect data.

Channel class.

**Parameters**

**index** (`int`) – Index of channel.

**Raises**

[**PulseError**](qiskit.pulse.PulseError "qiskit.pulse.PulseError") – If `index` is not a nonnegative integer.

### index

<span id="qiskit.pulse.channels.AcquireChannel.index" />

`property index`

Return the index of this channel. The index is a label for a control signal line typically mapped trivially to a qubit index. For instance, `DriveChannel(0)` labels the signal line driving the qubit labeled with index 0.

**Return type**

`int`

### name

<span id="qiskit.pulse.channels.AcquireChannel.name" />

`property name`

Return the shorthand alias for this channel, which is based on its type and index.

**Return type**

`str`

<span id="qiskit.pulse.channels.Channel" />

`Channel(index)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.16/qiskit/pulse/channels.py "view source code")

Base class of channels. Channels provide a Qiskit-side label for typical quantum control hardware signal channels. The final label -> physical channel mapping is the responsibility of the hardware backend. For instance, `DriveChannel(0)` holds instructions which the backend should map to the signal line driving gate operations on the qubit labeled (indexed) 0.

Channel class.

**Parameters**

**index** (`int`) – Index of channel.

**Raises**

[**PulseError**](qiskit.pulse.PulseError "qiskit.pulse.PulseError") – If `index` is not a nonnegative integer.

### index

<span id="qiskit.pulse.channels.Channel.index" />

`property index`

Return the index of this channel. The index is a label for a control signal line typically mapped trivially to a qubit index. For instance, `DriveChannel(0)` labels the signal line driving the qubit labeled with index 0.

**Return type**

`int`

### name

<span id="qiskit.pulse.channels.Channel.name" />

`property name`

Return the shorthand alias for this channel, which is based on its type and index.

**Return type**

`str`

<span id="qiskit.pulse.channels.Channel.prefix" />

### prefix

`= None`

A shorthand string prefix for characterizing the channel type.

<span id="qiskit.pulse.channels.ControlChannel" />

`ControlChannel(index)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.16/qiskit/pulse/channels.py "view source code")

Control channels provide supplementary control over the qubit to the drive channel. These are often associated with multi-qubit gate operations. They may not map trivially to a particular qubit index.

Channel class.

**Parameters**

**index** (`int`) – Index of channel.

**Raises**

[**PulseError**](qiskit.pulse.PulseError "qiskit.pulse.PulseError") – If `index` is not a nonnegative integer.

### index

<span id="qiskit.pulse.channels.ControlChannel.index" />

`property index`

Return the index of this channel. The index is a label for a control signal line typically mapped trivially to a qubit index. For instance, `DriveChannel(0)` labels the signal line driving the qubit labeled with index 0.

**Return type**

`int`

### name

<span id="qiskit.pulse.channels.ControlChannel.name" />

`property name`

Return the shorthand alias for this channel, which is based on its type and index.

**Return type**

`str`

<span id="qiskit.pulse.channels.DriveChannel" />

`DriveChannel(index)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.16/qiskit/pulse/channels.py "view source code")

Drive channels transmit signals to qubits which enact gate operations.

Channel class.

**Parameters**

**index** (`int`) – Index of channel.

**Raises**

[**PulseError**](qiskit.pulse.PulseError "qiskit.pulse.PulseError") – If `index` is not a nonnegative integer.

### index

<span id="qiskit.pulse.channels.DriveChannel.index" />

`property index`

Return the index of this channel. The index is a label for a control signal line typically mapped trivially to a qubit index. For instance, `DriveChannel(0)` labels the signal line driving the qubit labeled with index 0.

**Return type**

`int`

### name

<span id="qiskit.pulse.channels.DriveChannel.name" />

`property name`

Return the shorthand alias for this channel, which is based on its type and index.

**Return type**

`str`

<span id="qiskit.pulse.channels.MeasureChannel" />

`MeasureChannel(index)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.16/qiskit/pulse/channels.py "view source code")

Measure channels transmit measurement stimulus pulses for readout.

Channel class.

**Parameters**

**index** (`int`) – Index of channel.

**Raises**

[**PulseError**](qiskit.pulse.PulseError "qiskit.pulse.PulseError") – If `index` is not a nonnegative integer.

### index

<span id="qiskit.pulse.channels.MeasureChannel.index" />

`property index`

Return the index of this channel. The index is a label for a control signal line typically mapped trivially to a qubit index. For instance, `DriveChannel(0)` labels the signal line driving the qubit labeled with index 0.

**Return type**

`int`

### name

<span id="qiskit.pulse.channels.MeasureChannel.name" />

`property name`

Return the shorthand alias for this channel, which is based on its type and index.

**Return type**

`str`

<span id="qiskit.pulse.channels.MemorySlot" />

`MemorySlot(index)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.16/qiskit/pulse/channels.py "view source code")

Memory slot channels represent classical memory storage.

Channel class.

**Parameters**

**index** (`int`) – Index of channel.

**Raises**

[**PulseError**](qiskit.pulse.PulseError "qiskit.pulse.PulseError") – If `index` is not a nonnegative integer.

### index

<span id="qiskit.pulse.channels.MemorySlot.index" />

`property index`

Return the index of this channel. The index is a label for a control signal line typically mapped trivially to a qubit index. For instance, `DriveChannel(0)` labels the signal line driving the qubit labeled with index 0.

**Return type**

`int`

### name

<span id="qiskit.pulse.channels.MemorySlot.name" />

`property name`

Return the shorthand alias for this channel, which is based on its type and index.

**Return type**

`str`

<span id="qiskit.pulse.channels.PulseChannel" />

`PulseChannel(index)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.16/qiskit/pulse/channels.py "view source code")

Base class of transmit Channels. Pulses can be played on these channels.

Channel class.

**Parameters**

**index** (`int`) – Index of channel.

**Raises**

[**PulseError**](qiskit.pulse.PulseError "qiskit.pulse.PulseError") – If `index` is not a nonnegative integer.

### index

<span id="qiskit.pulse.channels.PulseChannel.index" />

`property index`

Return the index of this channel. The index is a label for a control signal line typically mapped trivially to a qubit index. For instance, `DriveChannel(0)` labels the signal line driving the qubit labeled with index 0.

**Return type**

`int`

### name

<span id="qiskit.pulse.channels.PulseChannel.name" />

`property name`

Return the shorthand alias for this channel, which is based on its type and index.

**Return type**

`str`

<span id="qiskit.pulse.channels.RegisterSlot" />

`RegisterSlot(index)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.16/qiskit/pulse/channels.py "view source code")

Classical resister slot channels represent classical registers (low-latency classical memory).

Channel class.

**Parameters**

**index** (`int`) – Index of channel.

**Raises**

[**PulseError**](qiskit.pulse.PulseError "qiskit.pulse.PulseError") – If `index` is not a nonnegative integer.

### index

<span id="qiskit.pulse.channels.RegisterSlot.index" />

`property index`

Return the index of this channel. The index is a label for a control signal line typically mapped trivially to a qubit index. For instance, `DriveChannel(0)` labels the signal line driving the qubit labeled with index 0.

**Return type**

`int`

### name

<span id="qiskit.pulse.channels.RegisterSlot.name" />

`property name`

Return the shorthand alias for this channel, which is based on its type and index.

**Return type**

`str`

<span id="qiskit.pulse.channels.SnapshotChannel" />

`SnapshotChannel`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.16/qiskit/pulse/channels.py "view source code")

Snapshot channels are used to specify instructions for simulators.

Create new snapshot channel.

### index

<span id="qiskit.pulse.channels.SnapshotChannel.index" />

`property index`

Return the index of this channel. The index is a label for a control signal line typically mapped trivially to a qubit index. For instance, `DriveChannel(0)` labels the signal line driving the qubit labeled with index 0.

**Return type**

`int`

### name

<span id="qiskit.pulse.channels.SnapshotChannel.name" />

`property name`

Return the shorthand alias for this channel, which is based on its type and index.

**Return type**

`str`

