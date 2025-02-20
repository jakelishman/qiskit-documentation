---
title: ResultError
description: API reference for qiskit.result.ResultError
in_page_toc_min_heading_level: 1
python_api_type: exception
python_api_name: qiskit.result.ResultError
---

# ResultError

<span id="qiskit.result.ResultError" />

`ResultError(error)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/result/exceptions.py "view source code")

Exceptions raised due to errors in result output.

It may be better for the Qiskit API to raise this exception.

**Parameters**

**error** (*dict*) –

This is the error record as it comes back from the API. The format is like:

```python
error = {'status': 403,
         'message': 'Your credits are not enough.',
         'code': 'MAX_CREDITS_EXCEEDED'}
```

Set the error message.

### with\_traceback

<span id="qiskit.result.ResultError.with_traceback" />

`with_traceback()`

Exception.with\_traceback(tb) – set self.\_\_traceback\_\_ to tb and return self.

