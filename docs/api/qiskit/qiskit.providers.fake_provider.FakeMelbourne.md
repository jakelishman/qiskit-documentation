---
title: FakeMelbourne
description: API reference for qiskit.providers.fake_provider.FakeMelbourne
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.fake_provider.FakeMelbourne
---

# FakeMelbourne

<span id="qiskit.providers.fake_provider.FakeMelbourne" />

`qiskit.providers.fake_provider.FakeMelbourne`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/providers/fake_provider/backends/melbourne/fake_melbourne.py "view source code")

Bases: [`FakeBackend`](providers_fake_provider#qiskit.providers.fake_provider.FakeBackend "qiskit.providers.fake_provider.fake_backend.FakeBackend")

A fake 14 qubit backend.

```python
0 ← 1 →  2 →  3 ←  4 ← 5 → 6
    ↑    ↑    ↑    ↓   ↓   ↓
   13 → 12 ← 11 → 10 ← 9 → 8 ← 7
```

## Attributes

<span id="qiskit.providers.fake_provider.FakeMelbourne.options" />

### options

Return the options for the backend

The options of a backend are the dynamic parameters defining how the backend is used. These are used to control the [`run()`](#qiskit.providers.fake_provider.FakeMelbourne.run "qiskit.providers.fake_provider.FakeMelbourne.run") method.

<span id="qiskit.providers.fake_provider.FakeMelbourne.version" />

### version

`= 1`

## Methods

### configuration

<span id="qiskit.providers.fake_provider.FakeMelbourne.configuration" />

`configuration()`

Return the backend configuration.

**Returns**

the configuration for the backend.

**Return type**

[BackendConfiguration](qiskit.providers.models.BackendConfiguration "qiskit.providers.models.BackendConfiguration")

### name

<span id="qiskit.providers.fake_provider.FakeMelbourne.name" />

`name()`

Return the backend name.

**Returns**

the name of the backend.

**Return type**

[str](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")

### properties

<span id="qiskit.providers.fake_provider.FakeMelbourne.properties" />

`properties()`

Returns a snapshot of device properties

### provider

<span id="qiskit.providers.fake_provider.FakeMelbourne.provider" />

`provider()`

Return the backend Provider.

**Returns**

the Provider responsible for the backend.

**Return type**

[Provider](qiskit.providers.Provider "qiskit.providers.Provider")

### run

<span id="qiskit.providers.fake_provider.FakeMelbourne.run" />

`run(run_input, **kwargs)`

Main job in simulator

### set\_options

<span id="qiskit.providers.fake_provider.FakeMelbourne.set_options" />

`set_options(**fields)`

Set the options fields for the backend

This method is used to update the options of a backend. If you need to change any of the options prior to running just pass in the kwarg with the new value for the options.

**Parameters**

**fields** – The fields to update the options

**Raises**

[**AttributeError**](https://docs.python.org/3/library/exceptions.html#AttributeError "(in Python v3.12)") – If the field passed in is not part of the options

### status

<span id="qiskit.providers.fake_provider.FakeMelbourne.status" />

`status()`

Return the backend status.

**Returns**

the status of the backend.

**Return type**

[BackendStatus](qiskit.providers.models.BackendStatus "qiskit.providers.models.BackendStatus")

