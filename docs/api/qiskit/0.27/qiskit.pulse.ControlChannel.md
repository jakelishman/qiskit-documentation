---
title: ControlChannel
description: API reference for qiskit.pulse.ControlChannel
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.pulse.ControlChannel
---

# qiskit.pulse.ControlChannel

<span id="qiskit.pulse.ControlChannel" />

`ControlChannel(index)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.17/qiskit/pulse/channels.py "view source code")

Control channels provide supplementary control over the qubit to the drive channel. These are often associated with multi-qubit gate operations. They may not map trivially to a particular qubit index.

Channel class.

**Parameters**

**index** (`int`) – Index of channel.

### \_\_init\_\_

<span id="qiskit.pulse.ControlChannel.__init__" />

`__init__(index)`

Channel class.

**Parameters**

**index** (`int`) – Index of channel.

## Methods

|                                                                                                                      |                                                                  |
| -------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| [`__init__`](#qiskit.pulse.ControlChannel.__init__ "qiskit.pulse.ControlChannel.__init__")(index)                    | Channel class.                                                   |
| [`assign`](#qiskit.pulse.ControlChannel.assign "qiskit.pulse.ControlChannel.assign")(parameter, value)               | Return a new channel with the input Parameter assigned to value. |
| [`is_parameterized`](#qiskit.pulse.ControlChannel.is_parameterized "qiskit.pulse.ControlChannel.is_parameterized")() | Return True iff the channel is parameterized.                    |

## Attributes

|                                                                                                  |                                                                                    |
| ------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------- |
| [`index`](#qiskit.pulse.ControlChannel.index "qiskit.pulse.ControlChannel.index")                | Return the index of this channel.                                                  |
| [`name`](#qiskit.pulse.ControlChannel.name "qiskit.pulse.ControlChannel.name")                   | Return the shorthand alias for this channel, which is based on its type and index. |
| [`parameters`](#qiskit.pulse.ControlChannel.parameters "qiskit.pulse.ControlChannel.parameters") | Parameters which determine the channel index.                                      |
| `prefix`                                                                                         |                                                                                    |

### assign

<span id="qiskit.pulse.ControlChannel.assign" />

`assign(parameter, value)`

Return a new channel with the input Parameter assigned to value.

**Parameters**

*   **parameter** (`Parameter`) – A parameter in this expression whose value will be updated.
*   **value** (`Union`\[`ParameterExpression`, `float`, `int`]) – The new value to bind to.

**Return type**

[`Channel`](qiskit.pulse.channels#qiskit.pulse.channels.Channel "qiskit.pulse.channels.Channel")

**Returns**

A new channel with updated parameters.

**Raises**

[**PulseError**](qiskit.pulse.PulseError "qiskit.pulse.PulseError") – If the parameter is not present in the channel.

### index

<span id="qiskit.pulse.ControlChannel.index" />

`property index`

Return the index of this channel. The index is a label for a control signal line typically mapped trivially to a qubit index. For instance, `DriveChannel(0)` labels the signal line driving the qubit labeled with index 0.

**Return type**

`Union`\[`int`, `ParameterExpression`]

### is\_parameterized

<span id="qiskit.pulse.ControlChannel.is_parameterized" />

`is_parameterized()`

Return True iff the channel is parameterized.

**Return type**

`bool`

### name

<span id="qiskit.pulse.ControlChannel.name" />

`property name`

Return the shorthand alias for this channel, which is based on its type and index.

**Return type**

`str`

### parameters

<span id="qiskit.pulse.ControlChannel.parameters" />

`property parameters`

Parameters which determine the channel index.

**Return type**

`Set`

