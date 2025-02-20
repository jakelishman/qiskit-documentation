---
title: passmanager_stage_plugins
description: API reference for qiskit.transpiler.preset_passmanagers.plugin.passmanager_stage_plugins
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.transpiler.preset_passmanagers.plugin.passmanager_stage_plugins
---

<span id="qiskit-transpiler-preset-passmanagers-plugin-passmanager-stage-plugins" />

# qiskit.transpiler.preset\_passmanagers.plugin.passmanager\_stage\_plugins

<span id="qiskit.transpiler.preset_passmanagers.plugin.passmanager_stage_plugins" />

`passmanager_stage_plugins(stage)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/transpiler/preset_passmanagers/plugin.py "view source code")

Return a dict with, for each stage name, the class type of the plugin.

This function is useful for getting more information about a plugin:

```python
from qiskit.transpiler.preset_passmanagers.plugin import passmanager_stage_plugins
routing_plugins = passmanager_stage_plugins('routing')
basic_plugin = routing_plugins['basic']
help(basic_plugin)
```

```python
Help on BasicSwapPassManager in module ...preset_passmanagers.builtin_plugins object:

class BasicSwapPassManager(...preset_passmanagers.plugin.PassManagerStagePlugin)
 |  Plugin class for routing stage with :class:`~.BasicSwap`
 |
 |  Method resolution order:
 |      BasicSwapPassManager
 |      ...preset_passmanagers.plugin.PassManagerStagePlugin
 |      abc.ABC
 |      builtins.object
 ...
```

**Parameters**

**stage** (*str*) – The stage name to get

**Returns**

the key is the name of the plugin and the value is the class type for each.

**Return type**

dict

**Raises**

[**TranspilerError**](qiskit.transpiler.TranspilerError "qiskit.transpiler.TranspilerError") – If an invalid stage name is specified.

