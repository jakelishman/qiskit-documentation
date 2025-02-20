---
title: iplot_gate_map
description: API reference for qiskit_ibm_provider.visualization.iplot_gate_map
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit_ibm_provider.visualization.iplot_gate_map
---

<span id="iplot-gate-map" />

# iplot\_gate\_map

<span id="qiskit_ibm_provider.visualization.iplot_gate_map" />

`iplot_gate_map(backend, figsize=(None, None), label_qubits=True, qubit_size=None, line_width=None, font_size=None, qubit_color='#2f4b7c', qubit_labels=None, line_color='#2f4b7c', font_color='white', background_color='white', as_widget=False)`[GitHub](https://github.com/qiskit/qiskit-ibm-provider/tree/stable/0.7/qiskit_ibm_provider/visualization/interactive/gate_map.py "view source code")

Plots an interactive gate map of a device.

**Parameters**

*   **backend** ([`IBMBackend`](qiskit_ibm_provider.IBMBackend "qiskit_ibm_provider.ibm_backend.IBMBackend")) – Plot the gate map for this backend.
*   **figsize** (`Tuple`\[`Optional`\[`int`], `Optional`\[`int`]]) – Output figure size (wxh) in inches.
*   **label\_qubits** (`bool`) – Labels for the qubits.
*   **qubit\_size** (`Optional`\[`float`]) – Size of qubit marker.
*   **line\_width** (`Optional`\[`float`]) – Width of lines.
*   **font\_size** (`Optional`\[`int`]) – Font size of qubit labels.
*   **qubit\_color** (`Union`\[`List`\[`str`], `str`]) – A list of colors for the qubits. If a single color is given, it’s used for all qubits.
*   **qubit\_labels** (`Optional`\[`List`\[`str`]]) – A list of qubit labels
*   **line\_color** (`Union`\[`List`\[`str`], `str`]) – A list of colors for each line from the coupling map. If a single color is given, it’s used for all lines.
*   **font\_color** (`str`) – The font color for the qubit labels.
*   **background\_color** (`str`) – The background color, either ‘white’ or ‘black’.
*   **as\_widget** (`bool`) – `True` if the figure is to be returned as a `PlotlyWidget`. Otherwise the figure is to be returned as a `PlotlyFigure`.

**Return type**

`Union`\[`PlotlyFigure`, `PlotlyWidget`]

**Returns**

The gate map figure.

**Example**

```python
from qiskit_ibm_provider import IBMProvider
from qiskit_ibm_provider.visualization import iplot_gate_map

provider = IBMProvider(group='open', project='main')
backend = provider.get_backend('ibmq_vigo')

iplot_gate_map(backend, as_widget=True)
```

