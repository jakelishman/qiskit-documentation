---
title: assemble_circuits
description: API reference for qiskit.assembler.assemble_circuits
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.assembler.assemble_circuits
---

# qiskit.assembler.assemble\_circuits

<span id="qiskit.assembler.assemble_circuits" />

`assemble_circuits(circuits, run_config, qobj_id, qobj_header)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/assembler/assemble_circuits.py "view source code")

Assembles a list of circuits into a qobj that can be run on the backend.

**Parameters**

*   **circuits** (`List`\[[`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit")]) – circuit(s) to assemble
*   **run\_config** ([`RunConfig`](qiskit.assembler.RunConfig "qiskit.assembler.run_config.RunConfig")) – configuration of the runtime environment
*   **qobj\_id** (`int`) – identifier for the generated qobj
*   **qobj\_header** ([`QobjHeader`](qiskit.qobj.QobjHeader "qiskit.qobj.common.QobjHeader")) – header to pass to the results

**Return type**

[`QasmQobj`](qiskit.qobj.QasmQobj "qiskit.qobj.qasm_qobj.QasmQobj")

**Returns**

The qobj to be run on the backends

## Examples

```python
from qiskit.circuit import QuantumRegister, ClassicalRegister, QuantumCircuit
from qiskit.assembler import assemble_circuits
from qiskit.assembler.run_config import RunConfig
# Build a circuit to convert into a Qobj
q = QuantumRegister(2)
c = ClassicalRegister(2)
qc = QuantumCircuit(q, c)
qc.h(q[0])
qc.cx(q[0], q[1])
qc.measure(q, c)
# Assemble a Qobj from the input circuit
qobj = assemble_circuits(circuits=[qc],
                         qobj_id="custom-id",
                         qobj_header=[],
                         run_config=RunConfig(shots=2000, memory=True, init_qubits=True))
```

