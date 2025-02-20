---
title: TimeBlockade
description: API reference for qiskit.pulse.instructions.TimeBlockade
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.pulse.instructions.TimeBlockade
---

# TimeBlockade

<span id="qiskit.pulse.instructions.TimeBlockade" />

`TimeBlockade(duration, channel, name=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/pulse/instructions/directives.py "view source code")

Bases: `Directive`

Pulse `TimeBlockade` directive.

This instruction is intended to be used internally within the pulse builder, to convert [`Schedule`](qiskit.pulse.Schedule "qiskit.pulse.Schedule") into [`ScheduleBlock`](qiskit.pulse.ScheduleBlock "qiskit.pulse.ScheduleBlock"). Because [`ScheduleBlock`](qiskit.pulse.ScheduleBlock "qiskit.pulse.ScheduleBlock") cannot take an absolute instruction time interval, this directive helps the block representation to find the starting time of an instruction.

## Example

This schedule plays constant pulse at t0 = 120.

```python
schedule = Schedule()
schedule.insert(120, Play(Constant(10, 0.1), DriveChannel(0)))
```

This schedule block is expected to be identical to above at a time of execution.

```python
block = ScheduleBlock()
block.append(TimeBlockade(120, DriveChannel(0)))
block.append(Play(Constant(10, 0.1), DriveChannel(0)))
```

Such conversion may be done by

```python
from qiskit.pulse.transforms import block_to_schedule, remove_directives

schedule = remove_directives(block_to_schedule(block))
```

<Admonition title="Note" type="note">
  The TimeBlockade instruction behaves almost identically to [`Delay`](qiskit.pulse.instructions.Delay "qiskit.pulse.instructions.Delay") instruction. However, the TimeBlockade is just a compiler directive and must be removed before execution. This may be done by [`remove_directives()`](qiskit.pulse.transforms.remove_directives "qiskit.pulse.transforms.remove_directives") transform. Once these directives are removed, occupied timeslots are released and user can insert another instruction without timing overlap.
</Admonition>

Create a time blockade directive.

**Parameters**

*   **duration** (*int*) – Length of time of the occupation in terms of dt.
*   **channel** ([*Channel*](pulse#qiskit.pulse.channels.Channel "qiskit.pulse.channels.Channel")) – The channel that will be the occupied.
*   **name** (*str | None*) – Name of the time blockade for display purposes.

## Methods

<span id="qiskit-pulse-instructions-timeblockade-append" />

### append

<span id="qiskit.pulse.instructions.TimeBlockade.append" />

`TimeBlockade.append(schedule, name=None)`

Return a new [`Schedule`](qiskit.pulse.Schedule "qiskit.pulse.Schedule") with `schedule` inserted at the maximum time over all channels shared between `self` and `schedule`.

**Parameters**

*   **schedule** (*Union\['Schedule', 'Instruction']*) – Schedule or instruction to be appended
*   **name** (*str | None*) – Name of the new schedule. Defaults to name of self

**Returns**

A new schedule with `schedule` a this instruction at t=0.

**Return type**

[Schedule](qiskit.pulse.Schedule "qiskit.pulse.Schedule")

<span id="qiskit-pulse-instructions-timeblockade-ch-duration" />

### ch\_duration

<span id="qiskit.pulse.instructions.TimeBlockade.ch_duration" />

`TimeBlockade.ch_duration(*channels)`

Return duration of the supplied channels in this Instruction.

**Parameters**

**\*channels** (*List\[*[*Channel*](pulse#qiskit.pulse.channels.Channel "qiskit.pulse.channels.Channel")*]*) – Supplied channels

**Return type**

int

<span id="qiskit-pulse-instructions-timeblockade-ch-start-time" />

### ch\_start\_time

<span id="qiskit.pulse.instructions.TimeBlockade.ch_start_time" />

`TimeBlockade.ch_start_time(*channels)`

Return minimum start time for supplied channels.

**Parameters**

**\*channels** (*List\[*[*Channel*](pulse#qiskit.pulse.channels.Channel "qiskit.pulse.channels.Channel")*]*) – Supplied channels

**Return type**

int

<span id="qiskit-pulse-instructions-timeblockade-ch-stop-time" />

### ch\_stop\_time

<span id="qiskit.pulse.instructions.TimeBlockade.ch_stop_time" />

`TimeBlockade.ch_stop_time(*channels)`

Return maximum start time for supplied channels.

**Parameters**

**\*channels** (*List\[*[*Channel*](pulse#qiskit.pulse.channels.Channel "qiskit.pulse.channels.Channel")*]*) – Supplied channels

**Return type**

int

<span id="qiskit-pulse-instructions-timeblockade-draw" />

### draw

<span id="qiskit.pulse.instructions.TimeBlockade.draw" />

`TimeBlockade.draw(dt=1, style=None, filename=None, interp_method=None, scale=1, plot_all=False, plot_range=None, interactive=False, table=True, label=False, framechange=True, channels=None)`

Plot the instruction.

<Admonition title="Deprecated since version 0.23.0" type="danger">
  The method `qiskit.pulse.instructions.instruction.Instruction.draw()` is deprecated as of qiskit-terra 0.23.0. It will be removed no earlier than 3 months after the release date. No direct alternative is being provided to drawing individual pulses. But, instructions can be visualized as part of a complete schedule using `qiskit.visualization.pulse_drawer`.
</Admonition>

**Parameters**

*   **dt** (*float*) – Time interval of samples
*   **style** (*Optional\[SchedStyle]*) – A style sheet to configure plot appearance
*   **filename** (*str | None*) – Name required to save pulse image
*   **interp\_method** (*Callable | None*) – A function for interpolation
*   **scale** (*float*) – Relative visual scaling of waveform amplitudes
*   **plot\_all** (*bool*) – Plot empty channels
*   **plot\_range** (*Tuple\[float] | None*) – A tuple of time range to plot
*   **interactive** (*bool*) – When set true show the circuit in a new window (this depends on the matplotlib backend being used supporting this)
*   **table** (*bool*) – Draw event table for supported instructions
*   **label** (*bool*) – Label individual instructions
*   **framechange** (*bool*) – Add framechange indicators
*   **channels** (*List\[*[*Channel*](pulse#qiskit.pulse.channels.Channel "qiskit.pulse.channels.Channel")*] | None*) – A list of channel names to plot

**Returns**

A matplotlib figure object of the pulse schedule

**Return type**

matplotlib.figure

<span id="qiskit-pulse-instructions-timeblockade-insert" />

### insert

<span id="qiskit.pulse.instructions.TimeBlockade.insert" />

`TimeBlockade.insert(start_time, schedule, name=None)`

Return a new [`Schedule`](qiskit.pulse.Schedule "qiskit.pulse.Schedule") with `schedule` inserted within `self` at `start_time`.

**Parameters**

*   **start\_time** (*int*) – Time to insert the schedule schedule
*   **schedule** (*Union\['Schedule', 'Instruction']*) – Schedule or instruction to insert
*   **name** (*str | None*) – Name of the new schedule. Defaults to name of self

**Returns**

A new schedule with `schedule` inserted with this instruction at t=0.

**Return type**

[Schedule](qiskit.pulse.Schedule "qiskit.pulse.Schedule")

<span id="qiskit-pulse-instructions-timeblockade-is-parameterized" />

### is\_parameterized

<span id="qiskit.pulse.instructions.TimeBlockade.is_parameterized" />

`TimeBlockade.is_parameterized()`

Return True iff the instruction is parameterized.

**Return type**

bool

<span id="qiskit-pulse-instructions-timeblockade-shift" />

### shift

<span id="qiskit.pulse.instructions.TimeBlockade.shift" />

`TimeBlockade.shift(time, name=None)`

Return a new schedule shifted forward by time.

**Parameters**

*   **time** (*int*) – Time to shift by
*   **name** (*str | None*) – Name of the new schedule. Defaults to name of self

**Returns**

The shifted schedule.

**Return type**

[Schedule](qiskit.pulse.Schedule "qiskit.pulse.Schedule")

## Attributes

<span id="qiskit.pulse.instructions.TimeBlockade.channel" />

### channel

Return the [`Channel`](pulse#qiskit.pulse.channels.Channel "qiskit.pulse.channels.Channel") that this instruction is scheduled on.

<span id="qiskit.pulse.instructions.TimeBlockade.channels" />

### channels

Returns the channels that this schedule uses.

<span id="qiskit.pulse.instructions.TimeBlockade.duration" />

### duration

Duration of this instruction.

<span id="qiskit.pulse.instructions.TimeBlockade.id" />

### id

Unique identifier for this instruction.

<span id="qiskit.pulse.instructions.TimeBlockade.instructions" />

### instructions

Iterable for getting instructions from Schedule tree.

<span id="qiskit.pulse.instructions.TimeBlockade.name" />

### name

Name of this instruction.

<span id="qiskit.pulse.instructions.TimeBlockade.operands" />

### operands

Return instruction operands.

<span id="qiskit.pulse.instructions.TimeBlockade.parameters" />

### parameters

Parameters which determine the instruction behavior.

<span id="qiskit.pulse.instructions.TimeBlockade.start_time" />

### start\_time

Relative begin time of this instruction.

<span id="qiskit.pulse.instructions.TimeBlockade.stop_time" />

### stop\_time

Relative end time of this instruction.

