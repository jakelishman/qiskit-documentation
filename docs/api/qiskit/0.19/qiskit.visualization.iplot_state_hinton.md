---
title: iplot_state_hinton
description: API reference for qiskit.visualization.iplot_state_hinton
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.visualization.iplot_state_hinton
---

# iplot\_state\_hinton

<span id="qiskit.visualization.iplot_state_hinton" />

`iplot_state_hinton(rho, figsize=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/visualization/interactive/iplot_hinton.py "view source code")

Create a hinton representation.

Graphical representation of the input array using a 2D city style graph (hinton).

**Parameters**

*   **rho** (*array*) – Density matrix
*   **figsize** (*tuple*) – Figure size in pixels.

## Example

```python
from qiskit import QuantumCircuit, BasicAer, execute
from qiskit.visualization import iplot_state_hinton
%matplotlib inline

qc = QuantumCircuit(2, 2)
qc.h(0)
qc.cx(0, 1)
qc.measure([0, 1], [0, 1])

backend = BasicAer.get_backend('statevector_simulator')
job = execute(qc, backend).result()
iplot_state_hinton(job.get_statevector(qc))
```

