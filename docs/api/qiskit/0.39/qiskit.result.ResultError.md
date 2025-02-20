---
title: ResultError
description: API reference for qiskit.result.ResultError
in_page_toc_min_heading_level: 1
python_api_type: exception
python_api_name: qiskit.result.ResultError
---

# qiskit.result.ResultError

<span id="qiskit.result.ResultError" />

`ResultError(error)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/result/exceptions.py "view source code")

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

