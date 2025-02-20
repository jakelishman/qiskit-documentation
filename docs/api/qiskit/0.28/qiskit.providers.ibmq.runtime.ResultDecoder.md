---
title: ResultDecoder
description: API reference for qiskit.providers.ibmq.runtime.ResultDecoder
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.ibmq.runtime.ResultDecoder
---

# qiskit.providers.ibmq.runtime.ResultDecoder

<span id="qiskit.providers.ibmq.runtime.ResultDecoder" />

`ResultDecoder`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.15/qiskit/providers/ibmq/runtime/program/result_decoder.py "view source code")

Runtime job result decoder.

You can subclass this class and overwrite the [`decode()`](#qiskit.providers.ibmq.runtime.ResultDecoder.decode "qiskit.providers.ibmq.runtime.ResultDecoder.decode") method to create a custom result decoder for the results of your runtime program. For example:

```python
class MyResultDecoder(ResultDecoder):

    @classmethod
    def decode(cls, data):
        decoded = super().decode(data)
        custom_processing(decoded)  # perform custom processing
```

Users of your program will need to pass in the subclass when invoking [`qiskit.providers.ibmq.runtime.RuntimeJob.result()`](qiskit.providers.ibmq.runtime.RuntimeJob#result "qiskit.providers.ibmq.runtime.RuntimeJob.result") or [`qiskit.providers.ibmq.runtime.IBMRuntimeService.run()`](qiskit.providers.ibmq.runtime.IBMRuntimeService#run "qiskit.providers.ibmq.runtime.IBMRuntimeService.run").

### \_\_init\_\_

<span id="qiskit.providers.ibmq.runtime.ResultDecoder.__init__" />

`__init__()`

Initialize self. See help(type(self)) for accurate signature.

## Methods

|                                                                                                                              |                         |
| ---------------------------------------------------------------------------------------------------------------------------- | ----------------------- |
| [`__init__`](#qiskit.providers.ibmq.runtime.ResultDecoder.__init__ "qiskit.providers.ibmq.runtime.ResultDecoder.__init__")() | Initialize self.        |
| [`decode`](#qiskit.providers.ibmq.runtime.ResultDecoder.decode "qiskit.providers.ibmq.runtime.ResultDecoder.decode")(data)   | Decode the result data. |

### decode

<span id="qiskit.providers.ibmq.runtime.ResultDecoder.decode" />

`classmethod decode(data)`

Decode the result data.

**Parameters**

**data** (`str`) – Result data to be decoded.

**Return type**

`Any`

**Returns**

Decoded result data.

