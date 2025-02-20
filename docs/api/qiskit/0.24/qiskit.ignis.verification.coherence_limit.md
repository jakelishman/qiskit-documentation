---
title: coherence_limit
description: API reference for qiskit.ignis.verification.coherence_limit
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.ignis.verification.coherence_limit
---

<span id="qiskit-ignis-verification-coherence-limit" />

# qiskit.ignis.verification.coherence\_limit

<span id="qiskit.ignis.verification.coherence_limit" />

`coherence_limit(nQ=2, T1_list=None, T2_list=None, gatelen=0.1)`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.5/qiskit/ignis/verification/randomized_benchmarking/rb_utils.py "view source code")

The error per gate (1-average\_gate\_fidelity) given by the T1,T2 limit.

**Parameters**

*   **nQ** (*int*) – number of qubits (1 and 2 supported).
*   **T1\_list** (*list*) – list of T1’s (Q1,…,Qn).
*   **T2\_list** (*list*) – list of T2’s (as measured, not Tphi). If not given assume T2=2\*T1 .
*   **gatelen** (*float*) – length of the gate.

**Returns**

coherence limited error per gate.

**Return type**

float

**Raises**

**ValueError** – if there are invalid inputs

