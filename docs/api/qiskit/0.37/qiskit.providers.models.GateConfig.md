---
title: GateConfig
description: API reference for qiskit.providers.models.GateConfig
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.models.GateConfig
---

# GateConfig

<span id="qiskit.providers.models.GateConfig" />

`GateConfig(name, parameters, qasm_def, coupling_map=None, latency_map=None, conditional=None, description=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/providers/models/backendconfiguration.py "view source code")

Bases: `object`

Class representing a Gate Configuration

<span id="qiskit.providers.models.GateConfig.name" />

### name

the gate name as it will be referred to in Qasm.

<span id="qiskit.providers.models.GateConfig.parameters" />

### parameters

variable names for the gate parameters (if any).

<span id="qiskit.providers.models.GateConfig.qasm_def" />

### qasm\_def

definition of this gate in terms of Qasm primitives U and CX.

Initialize a GateConfig object

**Parameters**

*   **name** (*str*) – the gate name as it will be referred to in Qasm.
*   **parameters** (*list*) – variable names for the gate parameters (if any) as a list of strings.
*   **qasm\_def** (*str*) – definition of this gate in terms of Qasm primitives U and CX.
*   **coupling\_map** (*list*) – An optional coupling map for the gate. In the form of a list of lists of integers representing the qubit groupings which are coupled by this gate.
*   **latency\_map** (*list*) – An optional map of latency for the gate. In the the form of a list of lists of integers of either 0 or 1 representing an array of dimension len(coupling\_map) X n\_registers that specifies the register latency (1: fast, 0: slow) conditional operations on the gate
*   **conditional** (*bool*) – Optionally specify whether this gate supports conditional operations (true/false). If this is not specified, then the gate inherits the conditional property of the backend.
*   **description** (*str*) – Description of the gate operation

## Methods

### from\_dict

<span id="qiskit.providers.models.GateConfig.from_dict" />

`classmethod GateConfig.from_dict(data)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/providers/models/backendconfiguration.py "view source code")

Create a new GateConfig object from a dictionary.

**Parameters**

**data** (*dict*) – A dictionary representing the GateConfig to create. It will be in the same format as output by [`to_dict()`](qiskit.providers.models.GateConfig#to_dict "qiskit.providers.models.GateConfig.to_dict").

**Returns**

The GateConfig from the input dictionary.

**Return type**

[GateConfig](qiskit.providers.models.GateConfig "qiskit.providers.models.GateConfig")

### to\_dict

<span id="qiskit.providers.models.GateConfig.to_dict" />

`GateConfig.to_dict()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/providers/models/backendconfiguration.py "view source code")

Return a dictionary format representation of the GateConfig.

**Returns**

The dictionary form of the GateConfig.

**Return type**

dict

