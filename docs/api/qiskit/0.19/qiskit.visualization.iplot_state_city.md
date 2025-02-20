---
title: iplot_state_city
description: API reference for qiskit.visualization.iplot_state_city
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.visualization.iplot_state_city
---

# iplot\_state\_city

<span id="qiskit.visualization.iplot_state_city" />

`iplot_state_city(rho, figsize=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/visualization/interactive/iplot_cities.py "view source code")

Create a cities representation.

Graphical representation of the input array using a city style graph.

**Parameters**

*   **rho** (*array*) – State vector or density matrix.
*   **figsize** (*tuple*) – The figure size in pixels.

## Example

```python
from qiskit import QuantumCircuit, BasicAer, execute
from qiskit.visualization import iplot_state_city
%matplotlib inline

qc = QuantumCircuit(2, 2)
qc.h(0)
qc.cx(0, 1)
qc.measure([0, 1], [0, 1])

backend = BasicAer.get_backend('statevector_simulator')
job = execute(qc, backend).result()
iplot_state_city(job.get_statevector(qc))
```

