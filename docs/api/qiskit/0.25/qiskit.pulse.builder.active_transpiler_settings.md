---
title: active_transpiler_settings
description: API reference for qiskit.pulse.builder.active_transpiler_settings
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.pulse.builder.active_transpiler_settings
---

# qiskit.pulse.builder.active\_transpiler\_settings

<span id="qiskit.pulse.builder.active_transpiler_settings" />

`active_transpiler_settings()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.17/qiskit/pulse/builder.py "view source code")

Return the current active builder context’s transpiler settings.

Examples:

```python
from qiskit import pulse
from qiskit.test.mock import FakeOpenPulse2Q

backend = FakeOpenPulse2Q()

transpiler_settings = {'optimization_level': 3}

with pulse.build(backend,
                 default_transpiler_settings=transpiler_settings):
    print(pulse.active_transpiler_settings())
```

```python
{'optimization_level': 3}
```

**Return type**

`Dict`\[`str`, `Any`]

