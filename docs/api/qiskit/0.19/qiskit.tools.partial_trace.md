---
title: partial_trace
description: API reference for qiskit.tools.partial_trace
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.tools.partial_trace
---

# partial\_trace

<span id="qiskit.tools.partial_trace" />

`partial_trace(state, trace_systems, dimensions=None, reverse=True)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/tools/qi/qi.py "view source code")

Partial trace over subsystems of multi-partite matrix.

Note that subsystems are ordered as rho012 = rho0(x)rho1(x)rho2.

**Parameters**

*   **state** (*matrix\_like*) – a matrix NxN
*   **trace\_systems** (*list(int)*) – a list of subsystems (starting from 0) to trace over.
*   **dimensions** (*list(int)*) – a list of the dimensions of the subsystems. If this is not set it will assume all subsystems are qubits.
*   **reverse** (*bool*) – ordering of systems in operator. If True system-0 is the right most system in tensor product. If False system-0 is the left most system in tensor product.

**Returns**

**A density matrix with the appropriate subsystems traced**

over.

**Return type**

matrix\_like

**Raises**

**Exception** – if input is not a multi-qubit state.

