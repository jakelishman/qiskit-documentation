---
title: Qobj
description: API reference for qiskit.qobj.Qobj
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.qobj.Qobj
---

<span id="qiskit-qobj-qobj" />

# qiskit.qobj.Qobj

<span id="qiskit.qobj.Qobj" />

`Qobj(qobj_id=None, config=None, experiments=None, header=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.16/qiskit/qobj/__init__.py "view source code")

A backwards compat alias for QasmQobj.

Initialize a Qobj object.

### \_\_init\_\_

<span id="qiskit.qobj.Qobj.__init__" />

`__init__(qobj_id=None, config=None, experiments=None, header=None)`

Initialize a Qobj object.

## Methods

|                                                                                                                |                                                             |
| -------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| [`__init__`](#qiskit.qobj.Qobj.__init__ "qiskit.qobj.Qobj.__init__")(\[qobj\_id, config, experiments, header]) | Initialize a Qobj object.                                   |
| [`from_dict`](#qiskit.qobj.Qobj.from_dict "qiskit.qobj.Qobj.from_dict")(data)                                  | Create a new QASMQobj object from a dictionary.             |
| [`to_dict`](#qiskit.qobj.Qobj.to_dict "qiskit.qobj.Qobj.to_dict")(\[validate])                                 | Return a dictionary format representation of the QASM Qobj. |

### from\_dict

<span id="qiskit.qobj.Qobj.from_dict" />

`classmethod from_dict(data)`

Create a new QASMQobj object from a dictionary.

**Parameters**

**data** (*dict*) – A dictionary representing the QasmQobj to create. It will be in the same format as output by [`to_dict()`](#qiskit.qobj.Qobj.to_dict "qiskit.qobj.Qobj.to_dict").

**Returns**

The QasmQobj from the input dictionary.

**Return type**

[QasmQobj](qiskit.qobj.QasmQobj "qiskit.qobj.QasmQobj")

### to\_dict

<span id="qiskit.qobj.Qobj.to_dict" />

`to_dict(validate=False)`

Return a dictionary format representation of the QASM Qobj.

Note this dict is not in the json wire format expected by IBMQ and qobj specification because complex numbers are still of type complex. Also this may contain native numpy arrays. When serializing this output for use with IBMQ you can leverage a json encoder that converts these as expected. For example:

```python
import json
import numpy

class QobjEncoder(json.JSONEncoder):
    def default(self, obj):
        if isinstance(obj, numpy.ndarray):
            return obj.tolist()
        if isinstance(obj, complex):
            return (obj.real, obj.imag)
        return json.JSONEncoder.default(self, obj)

json.dumps(qobj.to_dict(), cls=QobjEncoder)
```

**Parameters**

**validate** (*bool*) – When set to true validate the output dictionary against the jsonschema for qobj spec.

**Returns**

A dictionary representation of the QasmQobj object

**Return type**

dict

