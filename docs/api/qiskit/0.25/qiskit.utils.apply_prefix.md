---
title: apply_prefix
description: API reference for qiskit.utils.apply_prefix
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.utils.apply_prefix
---

# qiskit.utils.apply\_prefix

<span id="qiskit.utils.apply_prefix" />

`apply_prefix(value, unit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.17/qiskit/utils/units.py "view source code")

Given a SI unit prefix and value, apply the prefix to convert to standard SI unit.

**Parameters**

*   **value** (`float`) – The number to apply prefix to.
*   **unit** (`str`) – String prefix.

**Return type**

`float`

**Returns**

Converted value.

**Raises**

**Exception** – If the units aren’t recognized.

