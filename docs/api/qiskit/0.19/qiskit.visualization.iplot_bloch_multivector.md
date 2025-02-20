---
title: iplot_bloch_multivector
description: API reference for qiskit.visualization.iplot_bloch_multivector
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.visualization.iplot_bloch_multivector
---

# iplot\_bloch\_multivector

<span id="qiskit.visualization.iplot_bloch_multivector" />

`iplot_bloch_multivector(rho, figsize=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/visualization/interactive/iplot_blochsphere.py "view source code")

Create a bloch sphere representation.

Graphical representation of the input array, using as much bloch spheres as qubit are required.

**Parameters**

*   **rho** (*array*) – State vector or density matrix
*   **figsize** (*tuple*) – Figure size in pixels.

## Example

```python
from qiskit import QuantumCircuit, BasicAer, execute
from qiskit.visualization import iplot_bloch_multivector
%matplotlib inline

qc = QuantumCircuit(2, 2)
qc.h(0)
qc.cx(0, 1)
qc.measure([0, 1], [0, 1])

backend = BasicAer.get_backend('statevector_simulator')
job = execute(qc, backend).result()
iplot_bloch_multivector(job.get_statevector(qc))
```

