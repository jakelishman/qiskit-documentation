---
title: SetPhase
description: API reference for qiskit.pulse.SetPhase
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.pulse.SetPhase
---

# qiskit.pulse.SetPhase

<span id="qiskit.pulse.SetPhase" />

`SetPhase(phase, channel, name=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.17/qiskit/pulse/instructions/phase.py "view source code")

The set phase instruction sets the phase of the proceeding pulses on that channel to `phase` radians.

In particular, a PulseChannel creates pulses of the form

$$
Re[\exp(i 2\pi f jdt + \phi) d_j]
$$

The `SetPhase` instruction sets $\phi$ to the instruction’s `phase` operand.

Instantiate a set phase instruction, setting the output signal phase on `channel` to `phase` \[radians].

**Parameters**

*   **phase** (`Union`\[`complex`, `ParameterExpression`]) – The rotation angle in radians.
*   **channel** ([`PulseChannel`](qiskit.pulse.channels#qiskit.pulse.channels.PulseChannel "qiskit.pulse.channels.PulseChannel")) – The channel this instruction operates on.
*   **name** (`Optional`\[`str`]) – Display name for this instruction.

### \_\_init\_\_

<span id="qiskit.pulse.SetPhase.__init__" />

`__init__(phase, channel, name=None)`

Instantiate a set phase instruction, setting the output signal phase on `channel` to `phase` \[radians].

**Parameters**

*   **phase** (`Union`\[`complex`, `ParameterExpression`]) – The rotation angle in radians.
*   **channel** ([`PulseChannel`](qiskit.pulse.channels#qiskit.pulse.channels.PulseChannel "qiskit.pulse.channels.PulseChannel")) – The channel this instruction operates on.
*   **name** (`Optional`\[`str`]) – Display name for this instruction.

## Methods

|                                                                                                                        |                                                                                                                                                                               |
| ---------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.pulse.SetPhase.__init__ "qiskit.pulse.SetPhase.__init__")(phase, channel\[, name])                | Instantiate a set phase instruction, setting the output signal phase on `channel` to `phase` \[radians].                                                                      |
| [`append`](#qiskit.pulse.SetPhase.append "qiskit.pulse.SetPhase.append")(schedule\[, name])                            | Return a new [`Schedule`](qiskit.pulse.Schedule "qiskit.pulse.Schedule") with `schedule` inserted at the maximum time over all channels shared between `self` and `schedule`. |
| [`assign_parameters`](#qiskit.pulse.SetPhase.assign_parameters "qiskit.pulse.SetPhase.assign_parameters")(value\_dict) | Modify and return self with parameters assigned according to the input.                                                                                                       |
| [`ch_duration`](#qiskit.pulse.SetPhase.ch_duration "qiskit.pulse.SetPhase.ch_duration")(\*channels)                    | Return duration of the supplied channels in this Instruction.                                                                                                                 |
| [`ch_start_time`](#qiskit.pulse.SetPhase.ch_start_time "qiskit.pulse.SetPhase.ch_start_time")(\*channels)              | Return minimum start time for supplied channels.                                                                                                                              |
| [`ch_stop_time`](#qiskit.pulse.SetPhase.ch_stop_time "qiskit.pulse.SetPhase.ch_stop_time")(\*channels)                 | Return maximum start time for supplied channels.                                                                                                                              |
| [`draw`](#qiskit.pulse.SetPhase.draw "qiskit.pulse.SetPhase.draw")(\[dt, style, filename, interp\_method, …])          | Plot the instruction.                                                                                                                                                         |
| [`flatten`](#qiskit.pulse.SetPhase.flatten "qiskit.pulse.SetPhase.flatten")()                                          | Return itself as already single instruction.                                                                                                                                  |
| [`insert`](#qiskit.pulse.SetPhase.insert "qiskit.pulse.SetPhase.insert")(start\_time, schedule\[, name])               | Return a new [`Schedule`](qiskit.pulse.Schedule "qiskit.pulse.Schedule") with `schedule` inserted within `self` at `start_time`.                                              |
| [`is_parameterized`](#qiskit.pulse.SetPhase.is_parameterized "qiskit.pulse.SetPhase.is_parameterized")()               | Return True iff the instruction is parameterized.                                                                                                                             |
| [`shift`](#qiskit.pulse.SetPhase.shift "qiskit.pulse.SetPhase.shift")(time\[, name])                                   | Return a new schedule shifted forward by time.                                                                                                                                |

## Attributes

|                                                                                            |                                                                                                                                                    |
| ------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`channel`](#qiskit.pulse.SetPhase.channel "qiskit.pulse.SetPhase.channel")                | Return the [`Channel`](qiskit.pulse.channels#qiskit.pulse.channels.Channel "qiskit.pulse.channels.Channel") that this instruction is scheduled on. |
| [`channels`](#qiskit.pulse.SetPhase.channels "qiskit.pulse.SetPhase.channels")             | Returns the channels that this schedule uses.                                                                                                      |
| [`duration`](#qiskit.pulse.SetPhase.duration "qiskit.pulse.SetPhase.duration")             | Duration of this instruction.                                                                                                                      |
| [`id`](#qiskit.pulse.SetPhase.id "qiskit.pulse.SetPhase.id")                               | Unique identifier for this instruction.                                                                                                            |
| [`instructions`](#qiskit.pulse.SetPhase.instructions "qiskit.pulse.SetPhase.instructions") | Iterable for getting instructions from Schedule tree.                                                                                              |
| [`name`](#qiskit.pulse.SetPhase.name "qiskit.pulse.SetPhase.name")                         | Name of this instruction.                                                                                                                          |
| [`operands`](#qiskit.pulse.SetPhase.operands "qiskit.pulse.SetPhase.operands")             | Return instruction operands.                                                                                                                       |
| [`parameters`](#qiskit.pulse.SetPhase.parameters "qiskit.pulse.SetPhase.parameters")       | Parameters which determine the instruction behavior.                                                                                               |
| [`phase`](#qiskit.pulse.SetPhase.phase "qiskit.pulse.SetPhase.phase")                      | Return the rotation angle enacted by this instruction in radians.                                                                                  |
| [`start_time`](#qiskit.pulse.SetPhase.start_time "qiskit.pulse.SetPhase.start_time")       | Relative begin time of this instruction.                                                                                                           |
| [`stop_time`](#qiskit.pulse.SetPhase.stop_time "qiskit.pulse.SetPhase.stop_time")          | Relative end time of this instruction.                                                                                                             |

### append

<span id="qiskit.pulse.SetPhase.append" />

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

<span id="qiskit.pulse.SetPhase.assign_parameters" />

`assign_parameters(value_dict)`

Modify and return self with parameters assigned according to the input.

**Parameters**

**value\_dict** (`Dict`\[`ParameterExpression`, `Union`\[`ParameterExpression`, `float`, `int`]]) – A mapping from Parameters to either numeric values or another Parameter expression.

**Return type**

`Instruction`

**Returns**

Self with updated parameters.

### ch\_duration

<span id="qiskit.pulse.SetPhase.ch_duration" />

`ch_duration(*channels)`

Return duration of the supplied channels in this Instruction.

**Parameters**

**\*channels** – Supplied channels

**Return type**

`int`

### ch\_start\_time

<span id="qiskit.pulse.SetPhase.ch_start_time" />

`ch_start_time(*channels)`

Return minimum start time for supplied channels.

**Parameters**

**\*channels** – Supplied channels

**Return type**

`int`

### ch\_stop\_time

<span id="qiskit.pulse.SetPhase.ch_stop_time" />

`ch_stop_time(*channels)`

Return maximum start time for supplied channels.

**Parameters**

**\*channels** – Supplied channels

**Return type**

`int`

### channel

<span id="qiskit.pulse.SetPhase.channel" />

`property channel`

Return the [`Channel`](qiskit.pulse.channels#qiskit.pulse.channels.Channel "qiskit.pulse.channels.Channel") that this instruction is scheduled on.

**Return type**

[`PulseChannel`](qiskit.pulse.channels#qiskit.pulse.channels.PulseChannel "qiskit.pulse.channels.PulseChannel")

### channels

<span id="qiskit.pulse.SetPhase.channels" />

`property channels`

Returns the channels that this schedule uses.

**Return type**

`Tuple`\[[`PulseChannel`](qiskit.pulse.channels#qiskit.pulse.channels.PulseChannel "qiskit.pulse.channels.PulseChannel")]

### draw

<span id="qiskit.pulse.SetPhase.draw" />

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

<span id="qiskit.pulse.SetPhase.duration" />

`property duration`

Duration of this instruction.

**Return type**

`int`

### flatten

<span id="qiskit.pulse.SetPhase.flatten" />

`flatten()`

Return itself as already single instruction.

**Return type**

`Instruction`

### id

<span id="qiskit.pulse.SetPhase.id" />

`property id`

Unique identifier for this instruction.

**Return type**

`int`

### insert

<span id="qiskit.pulse.SetPhase.insert" />

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

<span id="qiskit.pulse.SetPhase.instructions" />

`property instructions`

Iterable for getting instructions from Schedule tree.

**Return type**

`Tuple`\[`Tuple`\[`int`, `Instruction`]]

### is\_parameterized

<span id="qiskit.pulse.SetPhase.is_parameterized" />

`is_parameterized()`

Return True iff the instruction is parameterized.

**Return type**

`bool`

### name

<span id="qiskit.pulse.SetPhase.name" />

`property name`

Name of this instruction.

**Return type**

`str`

### operands

<span id="qiskit.pulse.SetPhase.operands" />

`property operands`

Return instruction operands.

**Return type**

`Tuple`

### parameters

<span id="qiskit.pulse.SetPhase.parameters" />

`property parameters`

Parameters which determine the instruction behavior.

**Return type**

`Set`

### phase

<span id="qiskit.pulse.SetPhase.phase" />

`property phase`

Return the rotation angle enacted by this instruction in radians.

**Return type**

`Union`\[`complex`, `ParameterExpression`]

### shift

<span id="qiskit.pulse.SetPhase.shift" />

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

<span id="qiskit.pulse.SetPhase.start_time" />

`property start_time`

Relative begin time of this instruction.

**Return type**

`int`

### stop\_time

<span id="qiskit.pulse.SetPhase.stop_time" />

`property stop_time`

Relative end time of this instruction.

**Return type**

`int`

