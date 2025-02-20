---
title: mutual_information
description: API reference for qiskit.tools.mutual_information
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.tools.mutual_information
---

# mutual\_information

<span id="qiskit.tools.mutual_information" />

`mutual_information(state, d0, d1=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/tools/qi/qi.py "view source code")

Compute the mutual information of a bipartite state.

**Parameters**

*   **state** (*array\_like*) – a bipartite state-vector or density-matrix.
*   **d0** (*int*) – dimension of the first subsystem.
*   **d1** (*int or None*) – dimension of the second subsystem.

**Returns**

The mutual information S(rho\_A) + S(rho\_B) - S(rho\_AB).

**Return type**

float

