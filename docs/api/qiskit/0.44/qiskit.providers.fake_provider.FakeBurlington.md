---
title: FakeBurlington
description: API reference for qiskit.providers.fake_provider.FakeBurlington
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.fake_provider.FakeBurlington
---

# FakeBurlington

<span id="qiskit.providers.fake_provider.FakeBurlington" />

`qiskit.providers.fake_provider.FakeBurlington`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.25/qiskit/providers/fake_provider/backends/burlington/fake_burlington.py "view source code")

Bases: `FakeQasmBackend`

A fake 5 qubit backend.

```python
0 ↔ 1 ↔ 3 ↔ 4
    ↕
    2
```

FakeBackend initializer.

**Parameters**

*   **configuration** ([*BackendConfiguration*](qiskit.providers.models.BackendConfiguration "qiskit.providers.models.BackendConfiguration")) – backend configuration
*   **time\_alive** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – time to wait before returning result

## Attributes

<span id="qiskit.providers.fake_provider.FakeBurlington.backend_name" />

### backend\_name

`= 'fake_burlington'`

<span id="qiskit.providers.fake_provider.FakeBurlington.conf_filename" />

### conf\_filename

`= 'conf_burlington.json'`

<span id="qiskit.providers.fake_provider.FakeBurlington.dirname" />

### dirname

`= '/home/runner/work/qiskit/qiskit/.tox/docs/lib/python3.9/site-packages/qiskit/providers/fake_provider/backends/burlington'`

<span id="qiskit.providers.fake_provider.FakeBurlington.options" />

### options

Return the options for the backend

The options of a backend are the dynamic parameters defining how the backend is used. These are used to control the [`run()`](#qiskit.providers.fake_provider.FakeBurlington.run "qiskit.providers.fake_provider.FakeBurlington.run") method.

<span id="qiskit.providers.fake_provider.FakeBurlington.props_filename" />

### props\_filename

`= 'props_burlington.json'`

<span id="qiskit.providers.fake_provider.FakeBurlington.version" />

### version

`= 1`

## Methods

### configuration

<span id="qiskit.providers.fake_provider.FakeBurlington.configuration" />

`configuration()`

Return the backend configuration.

**Returns**

the configuration for the backend.

**Return type**

[BackendConfiguration](qiskit.providers.models.BackendConfiguration "qiskit.providers.models.BackendConfiguration")

### name

<span id="qiskit.providers.fake_provider.FakeBurlington.name" />

`name()`

Return the backend name.

**Returns**

the name of the backend.

**Return type**

[str](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")

### properties

<span id="qiskit.providers.fake_provider.FakeBurlington.properties" />

`properties()`

Returns a snapshot of device properties

### provider

<span id="qiskit.providers.fake_provider.FakeBurlington.provider" />

`provider()`

Return the backend Provider.

**Returns**

the Provider responsible for the backend.

**Return type**

[Provider](qiskit.providers.Provider "qiskit.providers.Provider")

### run

<span id="qiskit.providers.fake_provider.FakeBurlington.run" />

`run(run_input, **kwargs)`

Main job in simulator

### set\_options

<span id="qiskit.providers.fake_provider.FakeBurlington.set_options" />

`set_options(**fields)`

Set the options fields for the backend

This method is used to update the options of a backend. If you need to change any of the options prior to running just pass in the kwarg with the new value for the options.

**Parameters**

**fields** – The fields to update the options

**Raises**

[**AttributeError**](https://docs.python.org/3/library/exceptions.html#AttributeError "(in Python v3.12)") – If the field passed in is not part of the options

### status

<span id="qiskit.providers.fake_provider.FakeBurlington.status" />

`status()`

Return the backend status.

**Returns**

the status of the backend.

**Return type**

[BackendStatus](qiskit.providers.models.BackendStatus "qiskit.providers.models.BackendStatus")

