---
title: visualize_transition
description: API reference for qiskit.visualization.visualize_transition
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.visualization.visualize_transition
---

# qiskit.visualization.visualize\_transition

<span id="qiskit.visualization.visualize_transition" />

`visualize_transition(circuit, trace=False, saveas=None, fpg=100, spg=2)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/visualization/transition_visualization.py "view source code")

Creates animation showing transitions between states of a single qubit by applying quantum gates.

**Parameters**

*   **circuit** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – Qiskit single-qubit QuantumCircuit. Gates supported are h,x, y, z, rx, ry, rz, s, sdg, t, tdg and u1.
*   **trace** (*bool*) – Controls whether to display tracing vectors - history of 10 past vectors at each step of the animation.
*   **saveas** (*str*) – User can choose to save the animation as a video to their filesystem. This argument is a string of path with filename and extension (e.g. “movie.mp4” to save the video in current working directory).
*   **fpg** (*int*) – Frames per gate. Finer control over animation smoothness and computational needs to render the animation. Works well for tkinter GUI as it is, for jupyter GUI it might be preferable to choose fpg between 5-30.
*   **spg** (*int*) – Seconds per gate. How many seconds should animation of individual gate transitions take.

**Returns**

If arg jupyter is set to True. Otherwise opens tkinter GUI and returns after the GUI is closed.

**Return type**

IPython.core.display.HTML

**Raises**

*   **MissingOptionalLibraryError** – Must have Matplotlib (and/or IPython) installed.
*   [**VisualizationError**](qiskit.visualization.VisualizationError "qiskit.visualization.VisualizationError") – Given gate(s) are not supported.

