---
title: wrap_method
description: API reference for qiskit.utils.wrap_method
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.utils.wrap_method
---

# qiskit.utils.wrap\_method

<span id="qiskit.utils.wrap_method" />

`wrap_method(cls, name, *, before=None, after=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/utils/classtools.py "view source code")

Wrap the functionality the instance- or class method `cls.name` with additional behaviour `before` and `after`.

This mutates `cls`, replacing the attribute `name` with the new functionality. This is useful when creating class decorators. The method is allowed to be defined on any parent class instead.

If either `before` or `after` are given, they should be callables with a compatible signature to the method referred to. They will be called immediately before or after the method as appropriate, and any return value will be ignored.

**Parameters**

*   **cls** (`Type`) – the class to modify.
*   **name** (`str`) – the name of the method on the class to wrap.
*   **before** (`Optional`\[`Callable`]) – a callable that should be called before the method that is being wrapped.
*   **after** (`Optional`\[`Callable`]) – a callable that should be called after the method that is being wrapped.

**Raises**

**ValueError** – if the named method is not defined on the class or any parent class.

