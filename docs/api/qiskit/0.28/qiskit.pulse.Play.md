---
title: Play
description: API reference for qiskit.pulse.Play
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.pulse.Play
---

# qiskit.pulse.Play

<span id="qiskit.pulse.Play" />

`Play(pulse, channel, name=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/pulse/instructions/play.py "view source code")

This instruction is responsible for applying a pulse on a channel.

The pulse specifies the exact time dynamics of the output signal envelope for a limited time. The output is modulated by a phase and frequency which are controlled by separate instructions. The pulse duration must be fixed, and is implicitly given in terms of the cycle time, dt, of the backend.

Create a new pulse instruction.

**Parameters**

*   **pulse** (`Pulse`) – A pulse waveform description, such as [`Waveform`](qiskit.pulse.library.Waveform "qiskit.pulse.library.Waveform").
*   **channel** ([`PulseChannel`](qiskit.pulse.channels#qiskit.pulse.channels.PulseChannel "qiskit.pulse.channels.PulseChannel")) – The channel to which the pulse is applied.
*   **name** (`Optional`\[`str`]) – Name of the instruction for display purposes. Defaults to `pulse.name`.

**Raises**

[**PulseError**](qiskit.pulse.PulseError "qiskit.pulse.PulseError") – If pulse is not a Pulse type.

### \_\_init\_\_

<span id="qiskit.pulse.Play.__init__" />

`__init__(pulse, channel, name=None)`

Create a new pulse instruction.

**Parameters**

*   **pulse** (`Pulse`) – A pulse waveform description, such as [`Waveform`](qiskit.pulse.library.Waveform "qiskit.pulse.library.Waveform").
*   **channel** ([`PulseChannel`](qiskit.pulse.channels#qiskit.pulse.channels.PulseChannel "qiskit.pulse.channels.PulseChannel")) – The channel to which the pulse is applied.
*   **name** (`Optional`\[`str`]) – Name of the instruction for display purposes. Defaults to `pulse.name`.

**Raises**

[**PulseError**](qiskit.pulse.PulseError "qiskit.pulse.PulseError") – If pulse is not a Pulse type.

## Methods

|                                                                                                                |                                                                                                                                                                               |
| -------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.pulse.Play.__init__ "qiskit.pulse.Play.__init__")(pulse, channel\[, name])                | Create a new pulse instruction.                                                                                                                                               |
| [`append`](#qiskit.pulse.Play.append "qiskit.pulse.Play.append")(schedule\[, name])                            | Return a new [`Schedule`](qiskit.pulse.Schedule "qiskit.pulse.Schedule") with `schedule` inserted at the maximum time over all channels shared between `self` and `schedule`. |
| [`assign_parameters`](#qiskit.pulse.Play.assign_parameters "qiskit.pulse.Play.assign_parameters")(value\_dict) | Modify and return self with parameters assigned according to the input.                                                                                                       |
| [`ch_duration`](#qiskit.pulse.Play.ch_duration "qiskit.pulse.Play.ch_duration")(\*channels)                    | Return duration of the supplied channels in this Instruction.                                                                                                                 |
| [`ch_start_time`](#qiskit.pulse.Play.ch_start_time "qiskit.pulse.Play.ch_start_time")(\*channels)              | Return minimum start time for supplied channels.                                                                                                                              |
| [`ch_stop_time`](#qiskit.pulse.Play.ch_stop_time "qiskit.pulse.Play.ch_stop_time")(\*channels)                 | Return maximum start time for supplied channels.                                                                                                                              |
| [`draw`](#qiskit.pulse.Play.draw "qiskit.pulse.Play.draw")(\[dt, style, filename, interp\_method, …])          | Plot the instruction.                                                                                                                                                         |
| [`flatten`](#qiskit.pulse.Play.flatten "qiskit.pulse.Play.flatten")()                                          | Return itself as already single instruction.                                                                                                                                  |
| [`insert`](#qiskit.pulse.Play.insert "qiskit.pulse.Play.insert")(start\_time, schedule\[, name])               | Return a new [`Schedule`](qiskit.pulse.Schedule "qiskit.pulse.Schedule") with `schedule` inserted within `self` at `start_time`.                                              |
| [`is_parameterized`](#qiskit.pulse.Play.is_parameterized "qiskit.pulse.Play.is_parameterized")()               | Return True iff the instruction is parameterized.                                                                                                                             |
| [`shift`](#qiskit.pulse.Play.shift "qiskit.pulse.Play.shift")(time\[, name])                                   | Return a new schedule shifted forward by time.                                                                                                                                |

## Attributes

|                                                                                    |                                                                                                                                                    |
| ---------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`channel`](#qiskit.pulse.Play.channel "qiskit.pulse.Play.channel")                | Return the [`Channel`](qiskit.pulse.channels#qiskit.pulse.channels.Channel "qiskit.pulse.channels.Channel") that this instruction is scheduled on. |
| [`channels`](#qiskit.pulse.Play.channels "qiskit.pulse.Play.channels")             | Returns the channels that this schedule uses.                                                                                                      |
| [`duration`](#qiskit.pulse.Play.duration "qiskit.pulse.Play.duration")             | Duration of this instruction.                                                                                                                      |
| [`id`](#qiskit.pulse.Play.id "qiskit.pulse.Play.id")                               | Unique identifier for this instruction.                                                                                                            |
| [`instructions`](#qiskit.pulse.Play.instructions "qiskit.pulse.Play.instructions") | Iterable for getting instructions from Schedule tree.                                                                                              |
| [`name`](#qiskit.pulse.Play.name "qiskit.pulse.Play.name")                         | Name of this instruction.                                                                                                                          |
| [`operands`](#qiskit.pulse.Play.operands "qiskit.pulse.Play.operands")             | Return instruction operands.                                                                                                                       |
| [`parameters`](#qiskit.pulse.Play.parameters "qiskit.pulse.Play.parameters")       | Parameters which determine the instruction behavior.                                                                                               |
| [`pulse`](#qiskit.pulse.Play.pulse "qiskit.pulse.Play.pulse")                      | A description of the samples that will be played.                                                                                                  |
| [`start_time`](#qiskit.pulse.Play.start_time "qiskit.pulse.Play.start_time")       | Relative begin time of this instruction.                                                                                                           |
| [`stop_time`](#qiskit.pulse.Play.stop_time "qiskit.pulse.Play.stop_time")          | Relative end time of this instruction.                                                                                                             |

### append

<span id="qiskit.pulse.Play.append" />

`append(schedule, name=None)`

Return a new [`Schedule`](qiskit.pulse.Schedule "qiskit.pulse.Schedule") with `schedule` inserted at the maximum time over all channels shared between `self` and `schedule`.

**Parameters**

*   **schedule** (*Union\['Schedule', 'Instruction']*) – Schedule or instruction to be appended
*   **name** (`Optional`\[`str`]) – Name of the new schedule. Defaults to name of self

**Returns**

A new schedule with `schedule` a this instruction at t=0.

**Return type**

[Schedule](qiskit.pulse.Schedule "qiskit.pulse.Schedule")

### assign\_parameters

<span id="qiskit.pulse.Play.assign_parameters" />

`assign_parameters(value_dict)`

Modify and return self with parameters assigned according to the input.

**Parameters**

**value\_dict** (`Dict`\[`ParameterExpression`, `Union`\[`ParameterExpression`, `float`]]) – A mapping from Parameters to either numeric values or another Parameter expression.

**Return type**

`Play`

**Returns**

Self with updated parameters.

### ch\_duration

<span id="qiskit.pulse.Play.ch_duration" />

`ch_duration(*channels)`

Return duration of the supplied channels in this Instruction.

**Parameters**

**\*channels** – Supplied channels

**Return type**

`int`

### ch\_start\_time

<span id="qiskit.pulse.Play.ch_start_time" />

`ch_start_time(*channels)`

Return minimum start time for supplied channels.

**Parameters**

**\*channels** – Supplied channels

**Return type**

`int`

### ch\_stop\_time

<span id="qiskit.pulse.Play.ch_stop_time" />

`ch_stop_time(*channels)`

Return maximum start time for supplied channels.

**Parameters**

**\*channels** – Supplied channels

**Return type**

`int`

### channel

<span id="qiskit.pulse.Play.channel" />

`property channel`

Return the [`Channel`](qiskit.pulse.channels#qiskit.pulse.channels.Channel "qiskit.pulse.channels.Channel") that this instruction is scheduled on.

**Return type**

[`PulseChannel`](qiskit.pulse.channels#qiskit.pulse.channels.PulseChannel "qiskit.pulse.channels.PulseChannel")

### channels

<span id="qiskit.pulse.Play.channels" />

`property channels`

Returns the channels that this schedule uses.

**Return type**

`Tuple`\[[`PulseChannel`](qiskit.pulse.channels#qiskit.pulse.channels.PulseChannel "qiskit.pulse.channels.PulseChannel")]

### draw

<span id="qiskit.pulse.Play.draw" />

`draw(dt=1, style=None, filename=None, interp_method=None, scale=1, plot_all=False, plot_range=None, interactive=False, table=True, label=False, framechange=True, channels=None)`

Plot the instruction.

**Parameters**

*   **dt** (`float`) – Time interval of samples
*   **style** (*Optional\[SchedStyle]*) – A style sheet to configure plot appearance
*   **filename** (`Optional`\[`str`]) – Name required to save pulse image
*   **interp\_method** (`Optional`\[`Callable`]) – A function for interpolation
*   **scale** (`float`) – Relative visual scaling of waveform amplitudes
*   **plot\_all** (`bool`) – Plot empty channels
*   **plot\_range** (`Optional`\[`Tuple`\[`float`]]) – A tuple of time range to plot
*   **interactive** (`bool`) – When set true show the circuit in a new window (this depends on the matplotlib backend being used supporting this)
*   **table** (`bool`) – Draw event table for supported instructions
*   **label** (`bool`) – Label individual instructions
*   **framechange** (`bool`) – Add framechange indicators
*   **channels** (`Optional`\[`List`\[[`Channel`](qiskit.pulse.channels#qiskit.pulse.channels.Channel "qiskit.pulse.channels.Channel")]]) – A list of channel names to plot

**Returns**

A matplotlib figure object of the pulse schedule

**Return type**

matplotlib.figure

### duration

<span id="qiskit.pulse.Play.duration" />

`property duration`

Duration of this instruction.

**Return type**

`Union`\[`int`, `ParameterExpression`]

### flatten

<span id="qiskit.pulse.Play.flatten" />

`flatten()`

Return itself as already single instruction.

**Return type**

`Instruction`

### id

<span id="qiskit.pulse.Play.id" />

`property id`

Unique identifier for this instruction.

**Return type**

`int`

### insert

<span id="qiskit.pulse.Play.insert" />

`insert(start_time, schedule, name=None)`

Return a new [`Schedule`](qiskit.pulse.Schedule "qiskit.pulse.Schedule") with `schedule` inserted within `self` at `start_time`.

**Parameters**

*   **start\_time** (`int`) – Time to insert the schedule schedule
*   **schedule** (*Union\['Schedule', 'Instruction']*) – Schedule or instruction to insert
*   **name** (`Optional`\[`str`]) – Name of the new schedule. Defaults to name of self

**Returns**

A new schedule with `schedule` inserted with this instruction at t=0.

**Return type**

[Schedule](qiskit.pulse.Schedule "qiskit.pulse.Schedule")

### instructions

<span id="qiskit.pulse.Play.instructions" />

`property instructions`

Iterable for getting instructions from Schedule tree.

**Return type**

`Tuple`\[`Tuple`\[`int`, `Instruction`]]

### is\_parameterized

<span id="qiskit.pulse.Play.is_parameterized" />

`is_parameterized()`

Return True iff the instruction is parameterized.

**Return type**

`bool`

### name

<span id="qiskit.pulse.Play.name" />

`property name`

Name of this instruction.

**Return type**

`str`

### operands

<span id="qiskit.pulse.Play.operands" />

`property operands`

Return instruction operands.

**Return type**

`Tuple`

### parameters

<span id="qiskit.pulse.Play.parameters" />

`property parameters`

Parameters which determine the instruction behavior.

**Return type**

`Set`

### pulse

<span id="qiskit.pulse.Play.pulse" />

`property pulse`

A description of the samples that will be played.

**Return type**

`Pulse`

### shift

<span id="qiskit.pulse.Play.shift" />

`shift(time, name=None)`

Return a new schedule shifted forward by time.

**Parameters**

*   **time** (`int`) – Time to shift by
*   **name** (`Optional`\[`str`]) – Name of the new schedule. Defaults to name of self

**Returns**

The shifted schedule.

**Return type**

[Schedule](qiskit.pulse.Schedule "qiskit.pulse.Schedule")

### start\_time

<span id="qiskit.pulse.Play.start_time" />

`property start_time`

Relative begin time of this instruction.

**Return type**

`int`

### stop\_time

<span id="qiskit.pulse.Play.stop_time" />

`property stop_time`

Relative end time of this instruction.

**Return type**

`int`

