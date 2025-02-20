---
title: QobjExperimentHeader
description: API reference for qiskit.qobj.QobjExperimentHeader
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.qobj.QobjExperimentHeader
---

# QobjExperimentHeader

<span id="qiskit.qobj.QobjExperimentHeader" />

`qiskit.qobj.QobjExperimentHeader(**kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.25/qiskit/qobj/common.py "view source code")

Bases: [`QobjHeader`](qiskit.qobj.QobjHeader "qiskit.qobj.common.QobjHeader")

A class representing a header dictionary for a Qobj Experiment.

Instantiate a new Qobj dict field object.

**Parameters**

**kwargs** – arbitrary keyword arguments that can be accessed as attributes of the object.

## Methods

### from\_dict

<span id="qiskit.qobj.QobjExperimentHeader.from_dict" />

`classmethod from_dict(data)`

Create a new QobjHeader object from a dictionary.

**Parameters**

**data** ([*dict*](https://docs.python.org/3/library/stdtypes.html#dict "(in Python v3.12)")) – A dictionary representing the QobjHeader to create. It will be in the same format as output by [`to_dict()`](#qiskit.qobj.QobjExperimentHeader.to_dict "qiskit.qobj.QobjExperimentHeader.to_dict").

**Returns**

The QobjDictField from the input dictionary.

**Return type**

QobjDictFieldr

### to\_dict

<span id="qiskit.qobj.QobjExperimentHeader.to_dict" />

`to_dict()`

Return a dictionary format representation of the OpenQASM 2 Qobj.

**Returns**

The dictionary form of the QobjHeader.

**Return type**

[dict](https://docs.python.org/3/library/stdtypes.html#dict "(in Python v3.12)")

