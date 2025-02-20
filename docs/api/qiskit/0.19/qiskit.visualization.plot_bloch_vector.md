---
title: plot_bloch_vector
description: API reference for qiskit.visualization.plot_bloch_vector
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.visualization.plot_bloch_vector
---

# plot\_bloch\_vector

<span id="qiskit.visualization.plot_bloch_vector" />

`plot_bloch_vector(bloch, title='', ax=None, figsize=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/visualization/state_visualization.py "view source code")

Plot the Bloch sphere.

Plot a sphere, axes, the Bloch vector, and its projections onto each axis.

**Parameters**

*   **bloch** (*list\[double]*) – array of three elements where \[\<x>, \<y>, \<z>]
*   **title** (*str*) – a string that represents the plot title
*   **ax** (*matplotlib.axes.Axes*) – An Axes to use for rendering the bloch sphere
*   **figsize** (*tuple*) – Figure size in inches. Has no effect is passing `ax`.

**Returns**

A matplotlib figure instance if `ax = None`.

**Return type**

Figure

**Raises**

**ImportError** – Requires matplotlib.

## Example

```python
from qiskit.visualization import plot_bloch_vector
%matplotlib inline

plot_bloch_vector([0,1,0], title="New Bloch Sphere")
```

![../\_images/qiskit.visualization.plot\_bloch\_vector\_0\_2.png](/images/api/qiskit/0.19/qiskit.visualization.plot_bloch_vector_0_2.png) ![../\_images/qiskit.visualization.plot\_bloch\_vector\_0\_3.png](/images/api/qiskit/0.19/qiskit.visualization.plot_bloch_vector_0_3.png)

