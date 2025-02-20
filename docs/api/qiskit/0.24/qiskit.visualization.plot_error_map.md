---
title: plot_error_map
description: API reference for qiskit.visualization.plot_error_map
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.visualization.plot_error_map
---

<span id="qiskit-visualization-plot-error-map" />

# qiskit.visualization.plot\_error\_map

<span id="qiskit.visualization.plot_error_map" />

`plot_error_map(backend, figsize=(12, 9), show_title=True)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.16/qiskit/visualization/gate_map.py "view source code")

Plots the error map of a given backend.

**Parameters**

*   **backend** ([*IBMQBackend*](qiskit.providers.ibmq.IBMQBackend "qiskit.providers.ibmq.IBMQBackend")) – Given backend.
*   **figsize** (*tuple*) – Figure size in inches.
*   **show\_title** (*bool*) – Show the title or not.

**Returns**

A matplotlib figure showing error map.

**Return type**

Figure

**Raises**

*   [**VisualizationError**](qiskit.visualization.VisualizationError "qiskit.visualization.VisualizationError") – Input is not IBMQ backend.
*   **ImportError** – If seaborn is not installed

## Example

```python
from qiskit import QuantumCircuit, execute, IBMQ
from qiskit.visualization import plot_error_map
%matplotlib inline

IBMQ.load_account()
provider = IBMQ.get_provider(hub='ibm-q')
backend = provider.get_backend('ibmq_vigo')
plot_error_map(backend)
```

![../\_images/qiskit.visualization.plot\_error\_map\_1\_0.png](/images/api/qiskit/0.24/qiskit.visualization.plot_error_map_1_0.png) ![../\_images/qiskit.visualization.plot\_error\_map\_1\_1.png](/images/api/qiskit/0.24/qiskit.visualization.plot_error_map_1_1.png)

