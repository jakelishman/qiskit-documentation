---
title: hellinger_fidelity
description: API reference for qiskit.quantum_info.hellinger_fidelity
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.quantum_info.hellinger_fidelity
---

# hellinger\_fidelity

<span id="qiskit.quantum_info.hellinger_fidelity" />

`hellinger_fidelity(dist_p, dist_q)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/analysis/distance.py "view source code")

Computes the Hellinger fidelity between two counts distributions.

The fidelity is defined as 1-H where H is the Hellinger distance. This value is bounded in the range \[0, 1].

**Parameters**

*   **dist\_p** (*dict*) – First dict of counts.
*   **dist\_q** (*dict*) – Second dict of counts.

**Returns**

Fidelity

**Return type**

float

## Example

```python
from qiskit import QuantumCircuit, execute, BasicAer
from qiskit.quantum_info.analysis import hellinger_fidelity

qc = QuantumCircuit(5, 5)
qc.h(2)
qc.cx(2, 1)
qc.cx(2, 3)
qc.cx(3, 4)
qc.cx(1, 0)
qc.measure(range(5), range(5))

sim = BasicAer.get_backend('qasm_simulator')
res1 = execute(qc, sim).result()
res2 = execute(qc, sim).result()

hellinger_fidelity(res1.get_counts(), res2.get_counts())
```

```python
1.0
```

