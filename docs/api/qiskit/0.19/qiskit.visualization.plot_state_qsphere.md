---
title: plot_state_qsphere
description: API reference for qiskit.visualization.plot_state_qsphere
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.visualization.plot_state_qsphere
---

# plot\_state\_qsphere

<span id="qiskit.visualization.plot_state_qsphere" />

`plot_state_qsphere(rho, figsize=None, ax=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/visualization/state_visualization.py "view source code")

Plot the qsphere representation of a quantum state. Here, the size of the points is proportional to the probability of the corresponding term in the state and the color represents the phase.

**Parameters**

*   **rho** (*ndarray*) – State vector or density matrix representation. of quantum state.
*   **figsize** (*tuple*) – Figure size in inches.
*   **ax** (*matplotlib.axes.Axes*) – An optional Axes object to be used for the visualization output. If none is specified a new matplotlib Figure will be created and used. Additionally, if specified there will be no returned Figure since it is redundant.

**Returns**

A matplotlib figure instance if the `ax` kwag is not set

**Return type**

Figure

**Raises**

**ImportError** – Requires matplotlib.

## Example

```python
from qiskit import QuantumCircuit, BasicAer, execute
from qiskit.visualization import plot_state_qsphere
%matplotlib inline

qc = QuantumCircuit(2, 2)
qc.h(0)
qc.cx(0, 1)
qc.measure([0, 1], [0, 1])

backend = BasicAer.get_backend('statevector_simulator')
job = execute(qc, backend).result()
plot_state_qsphere(job.get_statevector(qc))
```

![../\_images/qiskit.visualization.plot\_state\_qsphere\_0\_2.png](/images/api/qiskit/0.19/qiskit.visualization.plot_state_qsphere_0_2.png) ![../\_images/qiskit.visualization.plot\_state\_qsphere\_0\_3.png](/images/api/qiskit/0.19/qiskit.visualization.plot_state_qsphere_0_3.png)

