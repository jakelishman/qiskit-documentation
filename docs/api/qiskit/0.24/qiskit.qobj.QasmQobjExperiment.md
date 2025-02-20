---
title: QasmQobjExperiment
description: API reference for qiskit.qobj.QasmQobjExperiment
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.qobj.QasmQobjExperiment
---

<span id="qiskit-qobj-qasmqobjexperiment" />

# qiskit.qobj.QasmQobjExperiment

<span id="qiskit.qobj.QasmQobjExperiment" />

`QasmQobjExperiment(config=None, header=None, instructions=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.16/qiskit/qobj/qasm_qobj.py "view source code")

A QASM Qobj Experiment.

Each instance of this class is used to represent a QASM experiment as part of a larger QASM qobj.

Instatiate a QasmQobjExperiment.

**Parameters**

*   **config** ([*QasmQobjExperimentConfig*](qiskit.qobj.QasmQobjExperimentConfig "qiskit.qobj.QasmQobjExperimentConfig")) – A config object for the experiment
*   **header** (*QasmQobjExperimentHeader*) – A header object for the experiment
*   **instructions** (*list*) – A list of [`QasmQobjInstruction`](qiskit.qobj.QasmQobjInstruction "qiskit.qobj.QasmQobjInstruction") objects

### \_\_init\_\_

<span id="qiskit.qobj.QasmQobjExperiment.__init__" />

`__init__(config=None, header=None, instructions=None)`

Instatiate a QasmQobjExperiment.

**Parameters**

*   **config** ([*QasmQobjExperimentConfig*](qiskit.qobj.QasmQobjExperimentConfig "qiskit.qobj.QasmQobjExperimentConfig")) – A config object for the experiment
*   **header** (*QasmQobjExperimentHeader*) – A header object for the experiment
*   **instructions** (*list*) – A list of [`QasmQobjInstruction`](qiskit.qobj.QasmQobjInstruction "qiskit.qobj.QasmQobjInstruction") objects

## Methods

|                                                                                                                                   |                                                              |
| --------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| [`__init__`](#qiskit.qobj.QasmQobjExperiment.__init__ "qiskit.qobj.QasmQobjExperiment.__init__")(\[config, header, instructions]) | Instatiate a QasmQobjExperiment.                             |
| [`from_dict`](#qiskit.qobj.QasmQobjExperiment.from_dict "qiskit.qobj.QasmQobjExperiment.from_dict")(data)                         | Create a new QasmQobjExperiment object from a dictionary.    |
| [`to_dict`](#qiskit.qobj.QasmQobjExperiment.to_dict "qiskit.qobj.QasmQobjExperiment.to_dict")()                                   | Return a dictionary format representation of the Experiment. |

### from\_dict

<span id="qiskit.qobj.QasmQobjExperiment.from_dict" />

`classmethod from_dict(data)`

Create a new QasmQobjExperiment object from a dictionary.

**Parameters**

**data** (*dict*) – A dictionary for the experiment config

**Returns**

The object from the input dictionary.

**Return type**

[QasmQobjExperiment](#qiskit.qobj.QasmQobjExperiment "qiskit.qobj.QasmQobjExperiment")

### to\_dict

<span id="qiskit.qobj.QasmQobjExperiment.to_dict" />

`to_dict()`

Return a dictionary format representation of the Experiment.

**Returns**

The dictionary form of the QasmQObjExperiment.

**Return type**

dict

