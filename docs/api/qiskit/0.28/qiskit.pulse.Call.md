---
title: Call
description: API reference for qiskit.pulse.Call
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.pulse.Call
---

# qiskit.pulse.Call

<span id="qiskit.pulse.Call" />

`Call(subroutine, value_dict=None, name=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/pulse/instructions/call.py "view source code")

Pulse `Call` instruction.

The `Call` instruction represents the calling of a referenced subroutine (schedule). It enables code reuse both within the pulse representation and hardware (if supported).

Define new subroutine.

<Admonition title="Note" type="note">
  Inline subroutine is mutable. This requires special care for modification.
</Admonition>

**Parameters**

*   **subroutine** (*Union\[*[*Schedule*](qiskit.pulse.Schedule "qiskit.pulse.Schedule")*,* [*ScheduleBlock*](qiskit.pulse.ScheduleBlock "qiskit.pulse.ScheduleBlock")*]*) – A program subroutine to be referred to.
*   **value\_dict** (`Optional`\[`Dict`\[`ParameterExpression`, `Union`\[`ParameterExpression`, `float`]]]) – Mapping of parameter object to assigned value.
*   **name** (`Optional`\[`str`]) – Unique ID of this subroutine. If not provided, this is generated based on the subroutine name.

**Raises**

[**PulseError**](qiskit.pulse.PulseError "qiskit.pulse.PulseError") – If subroutine is not valid data format.

### \_\_init\_\_

<span id="qiskit.pulse.Call.__init__" />

`__init__(subroutine, value_dict=None, name=None)`

Define new subroutine.

<Admonition title="Note" type="note">
  Inline subroutine is mutable. This requires special care for modification.
</Admonition>

**Parameters**

*   **subroutine** (*Union\[*[*Schedule*](qiskit.pulse.Schedule "qiskit.pulse.Schedule")*,* [*ScheduleBlock*](qiskit.pulse.ScheduleBlock "qiskit.pulse.ScheduleBlock")*]*) – A program subroutine to be referred to.
*   **value\_dict** (`Optional`\[`Dict`\[`ParameterExpression`, `Union`\[`ParameterExpression`, `float`]]]) – Mapping of parameter object to assigned value.
*   **name** (`Optional`\[`str`]) – Unique ID of this subroutine. If not provided, this is generated based on the subroutine name.

**Raises**

[**PulseError**](qiskit.pulse.PulseError "qiskit.pulse.PulseError") – If subroutine is not valid data format.

## Methods

|                                                                                                                |                                                                                                                                                                               |
| -------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.pulse.Call.__init__ "qiskit.pulse.Call.__init__")(subroutine\[, value\_dict, name])       | Define new subroutine.                                                                                                                                                        |
| [`append`](#qiskit.pulse.Call.append "qiskit.pulse.Call.append")(schedule\[, name])                            | Return a new [`Schedule`](qiskit.pulse.Schedule "qiskit.pulse.Schedule") with `schedule` inserted at the maximum time over all channels shared between `self` and `schedule`. |
| [`assign_parameters`](#qiskit.pulse.Call.assign_parameters "qiskit.pulse.Call.assign_parameters")(value\_dict) | Store parameters which will be later assigned to the subroutine.                                                                                                              |
| [`assigned_subroutine`](#qiskit.pulse.Call.assigned_subroutine "qiskit.pulse.Call.assigned_subroutine")()      | Returns this subroutine with the parameters assigned.                                                                                                                         |
| [`ch_duration`](#qiskit.pulse.Call.ch_duration "qiskit.pulse.Call.ch_duration")(\*channels)                    | Return duration of the supplied channels in this Instruction.                                                                                                                 |
| [`ch_start_time`](#qiskit.pulse.Call.ch_start_time "qiskit.pulse.Call.ch_start_time")(\*channels)              | Return minimum start time for supplied channels.                                                                                                                              |
| [`ch_stop_time`](#qiskit.pulse.Call.ch_stop_time "qiskit.pulse.Call.ch_stop_time")(\*channels)                 | Return maximum start time for supplied channels.                                                                                                                              |
| [`draw`](#qiskit.pulse.Call.draw "qiskit.pulse.Call.draw")(\[dt, style, filename, interp\_method, …])          | Plot the instruction.                                                                                                                                                         |
| [`flatten`](#qiskit.pulse.Call.flatten "qiskit.pulse.Call.flatten")()                                          | Return itself as already single instruction.                                                                                                                                  |
| [`insert`](#qiskit.pulse.Call.insert "qiskit.pulse.Call.insert")(start\_time, schedule\[, name])               | Return a new [`Schedule`](qiskit.pulse.Schedule "qiskit.pulse.Schedule") with `schedule` inserted within `self` at `start_time`.                                              |
| [`is_parameterized`](#qiskit.pulse.Call.is_parameterized "qiskit.pulse.Call.is_parameterized")()               | Return True iff the instruction is parameterized.                                                                                                                             |
| [`shift`](#qiskit.pulse.Call.shift "qiskit.pulse.Call.shift")(time\[, name])                                   | Return a new schedule shifted forward by time.                                                                                                                                |

## Attributes

|                                                                                    |                                                                 |
| ---------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| [`arguments`](#qiskit.pulse.Call.arguments "qiskit.pulse.Call.arguments")          | Parameters dictionary to be assigned to subroutine.             |
| [`channels`](#qiskit.pulse.Call.channels "qiskit.pulse.Call.channels")             | Returns the channels that this schedule uses.                   |
| [`duration`](#qiskit.pulse.Call.duration "qiskit.pulse.Call.duration")             | Duration of this instruction.                                   |
| [`id`](#qiskit.pulse.Call.id "qiskit.pulse.Call.id")                               | Unique identifier for this instruction.                         |
| [`instructions`](#qiskit.pulse.Call.instructions "qiskit.pulse.Call.instructions") | Iterable for getting instructions from Schedule tree.           |
| [`name`](#qiskit.pulse.Call.name "qiskit.pulse.Call.name")                         | Name of this instruction.                                       |
| [`operands`](#qiskit.pulse.Call.operands "qiskit.pulse.Call.operands")             | Return instruction operands.                                    |
| [`parameters`](#qiskit.pulse.Call.parameters "qiskit.pulse.Call.parameters")       | Unassigned parameters which determine the instruction behavior. |
| `prefix`                                                                           |                                                                 |
| [`start_time`](#qiskit.pulse.Call.start_time "qiskit.pulse.Call.start_time")       | Relative begin time of this instruction.                        |
| [`stop_time`](#qiskit.pulse.Call.stop_time "qiskit.pulse.Call.stop_time")          | Relative end time of this instruction.                          |
| [`subroutine`](#qiskit.pulse.Call.subroutine "qiskit.pulse.Call.subroutine")       | Return attached subroutine.                                     |

### append

<span id="qiskit.pulse.Call.append" />

`append(schedule, name=None)`

Return a new [`Schedule`](qiskit.pulse.Schedule "qiskit.pulse.Schedule") with `schedule` inserted at the maximum time over all channels shared between `self` and `schedule`.

**Parameters**

*   **schedule** (*Union\['Schedule', 'Instruction']*) – Schedule or instruction to be appended
*   **name** (`Optional`\[`str`]) – Name of the new schedule. Defaults to name of self

**Returns**

A new schedule with `schedule` a this instruction at t=0.

**Return type**

[Schedule](qiskit.pulse.Schedule "qiskit.pulse.Schedule")

### arguments

<span id="qiskit.pulse.Call.arguments" />

`property arguments`

Parameters dictionary to be assigned to subroutine.

**Return type**

`Dict`\[`ParameterExpression`, `Union`\[`ParameterExpression`, `float`]]

### assign\_parameters

<span id="qiskit.pulse.Call.assign_parameters" />

`assign_parameters(value_dict)`

Store parameters which will be later assigned to the subroutine.

Parameter values are not immediately assigned. The subroutine with parameters assigned according to the populated parameter table will be generated only when `inline_subroutines()` function is applied to this instruction. Note that parameter assignment logic creates a copy of subroutine to avoid the mutation problem. This function is usually applied by the Qiskit compiler when the program is submitted to the backend.

**Parameters**

**value\_dict** (`Dict`\[`ParameterExpression`, `Union`\[`ParameterExpression`, `float`]]) – A mapping from Parameters to either numeric values or another Parameter expression.

**Return type**

`Call`

**Returns**

Self with updated parameters.

### assigned\_subroutine

<span id="qiskit.pulse.Call.assigned_subroutine" />

`assigned_subroutine()`

Returns this subroutine with the parameters assigned.

<Admonition title="Note" type="note">
  This function may be often called internally for class equality check despite its overhead of parameter assignment. The subroutine with parameter assigned is cached based on `.argument` hash. Once this argument is updated, new assigned instance will be returned. Note that this update is not mutable operation.
</Admonition>

**Returns**

Attached program.

**Return type**

program (Union\[[Schedule](qiskit.pulse.Schedule "qiskit.pulse.Schedule"), [ScheduleBlock](qiskit.pulse.ScheduleBlock "qiskit.pulse.ScheduleBlock")])

### ch\_duration

<span id="qiskit.pulse.Call.ch_duration" />

`ch_duration(*channels)`

Return duration of the supplied channels in this Instruction.

**Parameters**

**\*channels** – Supplied channels

**Return type**

`int`

### ch\_start\_time

<span id="qiskit.pulse.Call.ch_start_time" />

`ch_start_time(*channels)`

Return minimum start time for supplied channels.

**Parameters**

**\*channels** – Supplied channels

**Return type**

`int`

### ch\_stop\_time

<span id="qiskit.pulse.Call.ch_stop_time" />

`ch_stop_time(*channels)`

Return maximum start time for supplied channels.

**Parameters**

**\*channels** – Supplied channels

**Return type**

`int`

### channels

<span id="qiskit.pulse.Call.channels" />

`property channels`

Returns the channels that this schedule uses.

**Return type**

`Tuple`\[[`Channel`](qiskit.pulse.channels#qiskit.pulse.channels.Channel "qiskit.pulse.channels.Channel")]

### draw

<span id="qiskit.pulse.Call.draw" />

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

<span id="qiskit.pulse.Call.duration" />

`property duration`

Duration of this instruction.

**Return type**

`Union`\[`int`, `ParameterExpression`]

### flatten

<span id="qiskit.pulse.Call.flatten" />

`flatten()`

Return itself as already single instruction.

**Return type**

`Instruction`

### id

<span id="qiskit.pulse.Call.id" />

`property id`

Unique identifier for this instruction.

**Return type**

`int`

### insert

<span id="qiskit.pulse.Call.insert" />

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

<span id="qiskit.pulse.Call.instructions" />

`property instructions`

Iterable for getting instructions from Schedule tree.

**Return type**

`Tuple`\[`Tuple`\[`int`, `Instruction`]]

### is\_parameterized

<span id="qiskit.pulse.Call.is_parameterized" />

`is_parameterized()`

Return True iff the instruction is parameterized.

**Return type**

`bool`

### name

<span id="qiskit.pulse.Call.name" />

`property name`

Name of this instruction.

**Return type**

`str`

### operands

<span id="qiskit.pulse.Call.operands" />

`property operands`

Return instruction operands.

**Return type**

`Tuple`

### parameters

<span id="qiskit.pulse.Call.parameters" />

`property parameters`

Unassigned parameters which determine the instruction behavior.

**Return type**

`Set`

### shift

<span id="qiskit.pulse.Call.shift" />

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

<span id="qiskit.pulse.Call.start_time" />

`property start_time`

Relative begin time of this instruction.

**Return type**

`int`

### stop\_time

<span id="qiskit.pulse.Call.stop_time" />

`property stop_time`

Relative end time of this instruction.

**Return type**

`int`

### subroutine

<span id="qiskit.pulse.Call.subroutine" />

`property subroutine`

Return attached subroutine.

**Returns**

The program referenced by the call.

**Return type**

program (Union\[[Schedule](qiskit.pulse.Schedule "qiskit.pulse.Schedule"), [ScheduleBlock](qiskit.pulse.ScheduleBlock "qiskit.pulse.ScheduleBlock")])

