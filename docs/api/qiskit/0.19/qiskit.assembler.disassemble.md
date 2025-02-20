---
title: disassemble
description: API reference for qiskit.assembler.disassemble
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.assembler.disassemble
---

# disassemble

<span id="qiskit.assembler.disassemble" />

`disassemble(qobj)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/assembler/disassemble.py "view source code")

Disassemble a qobj and return the circuits, run\_config, and user header.

**Parameters**

**qobj** ([*Qobj*](qiskit.qobj.Qobj "qiskit.qobj.Qobj")) – The input qobj object to disassemble

**Returns**

**(circuits, run\_config, user\_qobj\_header):**

*   circuits (list): A list of quantum circuits
*   run\_config (dict): The dict of the run config
*   user\_qobj\_header (dict): The dict of any user headers in the qobj

**Return type**

tuple

