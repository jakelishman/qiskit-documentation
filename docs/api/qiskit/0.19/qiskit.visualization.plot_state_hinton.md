---
title: plot_state_hinton
description: API reference for qiskit.visualization.plot_state_hinton
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.visualization.plot_state_hinton
---

# plot\_state\_hinton

<span id="qiskit.visualization.plot_state_hinton" />

`plot_state_hinton(rho, title='', figsize=None, ax_real=None, ax_imag=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/visualization/state_visualization.py "view source code")

Plot a hinton diagram for the quantum state.

**Parameters**

*   **rho** (*ndarray*) – Numpy array for state vector or density matrix.
*   **title** (*str*) – a string that represents the plot title
*   **figsize** (*tuple*) – Figure size in inches.
*   **ax\_real** (*matplotlib.axes.Axes*) – An optional Axes object to be used for the visualization output. If none is specified a new matplotlib Figure will be created and used. If this is specified without an ax\_imag only the real component plot will be generated. Additionally, if specified there will be no returned Figure since it is redundant.
*   **ax\_imag** (*matplotlib.axes.Axes*) – An optional Axes object to be used for the visualization output. If none is specified a new matplotlib Figure will be created and used. If this is specified without an ax\_imag only the real component plot will be generated. Additionally, if specified there will be no returned Figure since it is redundant.

**Returns**

The matplotlib.Figure of the visualization if neither ax\_real or ax\_imag is set.

**Return type**

matplotlib.Figure

**Raises**

**ImportError** – Requires matplotlib.

## Example

```python
from qiskit import QuantumCircuit, BasicAer, execute
from qiskit.visualization import plot_state_hinton
%matplotlib inline

qc = QuantumCircuit(2, 2)
qc.h(0)
qc.cx(0, 1)
qc.measure([0, 1], [0, 1])

backend = BasicAer.get_backend('statevector_simulator')
job = execute(qc, backend).result()
plot_state_hinton(job.get_statevector(qc), title="New Hinton Plot")
```

![../\_images/qiskit.visualization.plot\_state\_hinton\_0\_2.png](/images/api/qiskit/0.19/qiskit.visualization.plot_state_hinton_0_2.png) ![../\_images/qiskit.visualization.plot\_state\_hinton\_0\_3.png](/images/api/qiskit/0.19/qiskit.visualization.plot_state_hinton_0_3.png)

