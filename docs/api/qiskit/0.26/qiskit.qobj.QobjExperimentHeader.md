---
title: QobjExperimentHeader
description: API reference for qiskit.qobj.QobjExperimentHeader
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.qobj.QobjExperimentHeader
---

# qiskit.qobj.QobjExperimentHeader

<span id="qiskit.qobj.QobjExperimentHeader" />

`QobjExperimentHeader(**kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.17/qiskit/qobj/common.py "view source code")

A class representing a header dictionary for a Qobj Experiment.

Instantiate a new Qobj dict field object.

**Parameters**

**kwargs** – arbitrary keyword arguments that can be accessed as attributes of the object.

### \_\_init\_\_

<span id="qiskit.qobj.QobjExperimentHeader.__init__" />

`__init__(**kwargs)`

Instantiate a new Qobj dict field object.

**Parameters**

**kwargs** – arbitrary keyword arguments that can be accessed as attributes of the object.

## Methods

|                                                                                                                  |                                                             |
| ---------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| [`__init__`](#qiskit.qobj.QobjExperimentHeader.__init__ "qiskit.qobj.QobjExperimentHeader.__init__")(\*\*kwargs) | Instantiate a new Qobj dict field object.                   |
| [`from_dict`](#qiskit.qobj.QobjExperimentHeader.from_dict "qiskit.qobj.QobjExperimentHeader.from_dict")(data)    | Create a new QobjHeader object from a dictionary.           |
| [`to_dict`](#qiskit.qobj.QobjExperimentHeader.to_dict "qiskit.qobj.QobjExperimentHeader.to_dict")()              | Return a dictionary format representation of the QASM Qobj. |

### from\_dict

<span id="qiskit.qobj.QobjExperimentHeader.from_dict" />

`classmethod from_dict(data)`

Create a new QobjHeader object from a dictionary.

**Parameters**

**data** (*dict*) – A dictionary representing the QobjHeader to create. It will be in the same format as output by [`to_dict()`](#qiskit.qobj.QobjExperimentHeader.to_dict "qiskit.qobj.QobjExperimentHeader.to_dict").

**Returns**

The QobjDictField from the input dictionary.

**Return type**

QobjDictFieldr

### to\_dict

<span id="qiskit.qobj.QobjExperimentHeader.to_dict" />

`to_dict()`

Return a dictionary format representation of the QASM Qobj.

**Returns**

The dictionary form of the QobjHeader.

**Return type**

dict

