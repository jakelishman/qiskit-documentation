---
title: Constant
description: API reference for qiskit.pulse.library.Constant
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.pulse.library.Constant
---

# Constant

<span id="qiskit.pulse.library.Constant" />

`Constant(duration: Union[int, qiskit.circuit.parameterexpression.ParameterExpression], amp: Union[complex, qiskit.circuit.parameterexpression.ParameterExpression], name: Optional[str] = None, limit_amplitude: Optional[bool] = None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/pulse/library/symbolic_pulses.py "view source code")

Bases: `object`

A simple constant pulse, with an amplitude value and a duration:

$$
f(x) = amp    ,  0 <= x < duration
f(x) = 0      ,  elsewhere
$$

Create new pulse instance.

**Parameters**

*   **duration** – Pulse length in terms of the sampling period dt.
*   **amp** – The amplitude of the constant square pulse.
*   **name** – Display name for this pulse envelope.
*   **limit\_amplitude** – If `True`, then limit the amplitude of the waveform to 1. The default is `True` and the amplitude is constrained to 1.

**Returns**

SymbolicPulse instance.

## Attributes

<span id="qiskit.pulse.library.Constant.alias" />

### alias

`= 'Constant'`

