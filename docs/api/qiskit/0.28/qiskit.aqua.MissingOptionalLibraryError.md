---
title: MissingOptionalLibraryError
description: API reference for qiskit.aqua.MissingOptionalLibraryError
in_page_toc_min_heading_level: 1
python_api_type: exception
python_api_name: qiskit.aqua.MissingOptionalLibraryError
---

# qiskit.aqua.MissingOptionalLibraryError

<span id="qiskit.aqua.MissingOptionalLibraryError" />

`MissingOptionalLibraryError(libname, name, pip_install=None, msg=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/missing_optional_library_error.py "view source code")

Raised when an optional library is missing.

Set the error message.

**Parameters**

*   **libname** (`str`) – Name of missing library
*   **name** (`str`) – Name of class, function, module that uses this library
*   **pip\_install** (`Optional`\[`str`]) – pip install command, if any
*   **msg** (`Optional`\[`str`]) – Descriptive message, if any

### with\_traceback

<span id="qiskit.aqua.MissingOptionalLibraryError.with_traceback" />

`with_traceback()`

Exception.with\_traceback(tb) – set self.\_\_traceback\_\_ to tb and return self.

