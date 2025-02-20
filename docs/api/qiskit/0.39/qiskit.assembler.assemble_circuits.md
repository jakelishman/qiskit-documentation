---
title: assemble_circuits
description: API reference for qiskit.assembler.assemble_circuits
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.assembler.assemble_circuits
---

# qiskit.assembler.assemble\_circuits

<span id="qiskit.assembler.assemble_circuits" />

`assemble_circuits(circuits, run_config, qobj_id, qobj_header)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/assembler/assemble_circuits.py "view source code")

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

