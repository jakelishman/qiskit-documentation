---
title: ParametricPulse
description: API reference for qiskit.pulse.library.ParametricPulse
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.pulse.library.ParametricPulse
---

# ParametricPulse

<span id="qiskit.pulse.library.ParametricPulse" />

`ParametricPulse(duration, name=None, limit_amplitude=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/pulse/library/parametric_pulses.py "view source code")

Bases: `qiskit.pulse.library.pulse.Pulse`

The abstract superclass for parametric pulses.

<Admonition title="Warning" type="caution">
  This class is superseded by [`SymbolicPulse`](qiskit.pulse.library.SymbolicPulse "qiskit.pulse.library.SymbolicPulse") and will be deprecated and eventually removed in the future because of the poor flexibility for defining a new waveform type and serializing it through the [`qiskit.qpy`](qpy#module-qiskit.qpy "qiskit.qpy") framework.
</Admonition>

Create a parametric pulse and validate the input parameters.

**Parameters**

*   **duration** (`Union`\[`int`, [`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")]) – Pulse length in terms of the the sampling period dt.
*   **name** (`Optional`\[`str`]) – Display name for this pulse envelope.
*   **limit\_amplitude** (`Optional`\[`bool`]) – If `True`, then limit the amplitude of the waveform to 1. The default is `True` and the amplitude is constrained to 1.

## Methods

### draw

<span id="qiskit.pulse.library.ParametricPulse.draw" />

`ParametricPulse.draw(style=None, backend=None, time_range=None, time_unit='dt', show_waveform_info=True, plotter='mpl2d', axis=None)`

Plot the interpolated envelope of pulse.

**Parameters**

*   **style** (`Optional`\[`Dict`\[`str`, `Any`]]) – Stylesheet options. This can be dictionary or preset stylesheet classes. See `IQXStandard`, `IQXSimple`, and `IQXDebugging` for details of preset stylesheets.

*   **backend** (*Optional\[BaseBackend]*) – Backend object to play the input pulse program. If provided, the plotter may use to make the visualization hardware aware.

*   **time\_range** (`Optional`\[`Tuple`\[`int`, `int`]]) – Set horizontal axis limit. Tuple `(tmin, tmax)`.

*   **time\_unit** (`str`) – The unit of specified time range either `dt` or `ns`. The unit of `ns` is available only when `backend` object is provided.

*   **show\_waveform\_info** (`bool`) – Show waveform annotations, i.e. name, of waveforms. Set `True` to show additional information about waveforms.

*   **plotter** (`str`) –

    Name of plotter API to generate an output image. One of following APIs should be specified:

    ```python
    mpl2d: Matplotlib API for 2D image generation.
        Matplotlib API to generate 2D image. Charts are placed along y axis with
        vertical offset. This API takes matplotlib.axes.Axes as `axis` input.
    ```

    axis and style kwargs may depend on the plotter.

*   **axis** (`Optional`\[`Any`]) – Arbitrary object passed to the plotter. If this object is provided, the plotters use a given `axis` instead of internally initializing a figure object. This object format depends on the plotter. See plotter argument for details.

**Returns**

Visualization output data. The returned data type depends on the `plotter`. If matplotlib family is specified, this will be a `matplotlib.pyplot.Figure` data.

### get\_waveform

<span id="qiskit.pulse.library.ParametricPulse.get_waveform" />

`abstract ParametricPulse.get_waveform()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/pulse/library/parametric_pulses.py "view source code")

Return a Waveform with samples filled according to the formula that the pulse represents and the parameter values it contains.

**Return type**

[`Waveform`](qiskit.pulse.library.Waveform "qiskit.pulse.library.waveform.Waveform")

### is\_parameterized

<span id="qiskit.pulse.library.ParametricPulse.is_parameterized" />

`ParametricPulse.is_parameterized()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/pulse/library/parametric_pulses.py "view source code")

Return True iff the instruction is parameterized.

**Return type**

`bool`

### validate\_parameters

<span id="qiskit.pulse.library.ParametricPulse.validate_parameters" />

`abstract ParametricPulse.validate_parameters()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/pulse/library/parametric_pulses.py "view source code")

Validate parameters.

**Raises**

[**PulseError**](pulse#qiskit.pulse.PulseError "qiskit.pulse.PulseError") – If the parameters passed are not valid.

**Return type**

`None`

## Attributes

<span id="qiskit.pulse.library.ParametricPulse.duration" />

### duration

<span id="qiskit.pulse.library.ParametricPulse.name" />

### name

<span id="qiskit.pulse.library.ParametricPulse.id" />

### id

Unique identifier for this pulse.

**Return type**

`int`

<span id="qiskit.pulse.library.ParametricPulse.limit_amplitude" />

### limit\_amplitude

`= True`

<span id="qiskit.pulse.library.ParametricPulse.parameters" />

### parameters

Return a dictionary containing the pulse’s parameters.

**Return type**

`Dict`\[`str`, `Any`]

