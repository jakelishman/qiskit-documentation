---
title: sech_deriv
description: API reference for qiskit.pulse.library.sech_deriv
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.pulse.library.sech_deriv
---

<span id="qiskit-pulse-library-sech-deriv" />

# qiskit.pulse.library.sech\_deriv

<span id="qiskit.pulse.library.sech_deriv" />

`sech_deriv(duration, amp, sigma, name=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/pulse/library/discrete.py "view source code")

Generates unnormalized sech derivative [`Waveform`](qiskit.pulse.library.Waveform "qiskit.pulse.library.Waveform").

For $A=$ `amp`, $\sigma=$ `sigma`, and center $\mu=$ `duration/2`, applies the midpoint sampling strategy to generate a discrete pulse sampled from the continuous function:

$$
f(x) = \frac{d}{dx}\left[A\text{sech}\left(\frac{x-\mu}{\sigma} \right)\right],
$$

i.e. the derivative of $\text{sech}$.

**Parameters**

*   **duration** (*int*) – Duration of pulse. Must be greater than zero.
*   **amp** (*complex*) – Pulse amplitude at center.
*   **sigma** (*float*) – Width (standard deviation) of pulse.
*   **name** (*str | None*) – Name of pulse.

**Return type**

[*Waveform*](qiskit.pulse.library.Waveform "qiskit.pulse.library.waveform.Waveform")

