---
title: FakeMumbai
description: API reference for qiskit.providers.fake_provider.FakeMumbai
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.fake_provider.FakeMumbai
---

# FakeMumbai

<span id="qiskit.providers.fake_provider.FakeMumbai" />

`qiskit.providers.fake_provider.FakeMumbai`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.25/qiskit/providers/fake_provider/backends/mumbai/fake_mumbai.py "view source code")

Bases: `FakePulseBackend`

A fake 27 qubit backend.

FakeBackend initializer.

**Parameters**

*   **configuration** ([*BackendConfiguration*](qiskit.providers.models.BackendConfiguration "qiskit.providers.models.BackendConfiguration")) – backend configuration
*   **time\_alive** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – time to wait before returning result

## Attributes

<span id="qiskit.providers.fake_provider.FakeMumbai.backend_name" />

### backend\_name

`= 'fake_mumbai'`

<span id="qiskit.providers.fake_provider.FakeMumbai.conf_filename" />

### conf\_filename

`= 'conf_mumbai.json'`

<span id="qiskit.providers.fake_provider.FakeMumbai.defs_filename" />

### defs\_filename

`= 'defs_mumbai.json'`

<span id="qiskit.providers.fake_provider.FakeMumbai.dirname" />

### dirname

`= '/home/runner/work/qiskit/qiskit/.tox/docs/lib/python3.9/site-packages/qiskit/providers/fake_provider/backends/mumbai'`

<span id="qiskit.providers.fake_provider.FakeMumbai.options" />

### options

Return the options for the backend

The options of a backend are the dynamic parameters defining how the backend is used. These are used to control the [`run()`](#qiskit.providers.fake_provider.FakeMumbai.run "qiskit.providers.fake_provider.FakeMumbai.run") method.

<span id="qiskit.providers.fake_provider.FakeMumbai.props_filename" />

### props\_filename

`= 'props_mumbai.json'`

<span id="qiskit.providers.fake_provider.FakeMumbai.version" />

### version

`= 1`

## Methods

### configuration

<span id="qiskit.providers.fake_provider.FakeMumbai.configuration" />

`configuration()`

Return the backend configuration.

**Returns**

the configuration for the backend.

**Return type**

[BackendConfiguration](qiskit.providers.models.BackendConfiguration "qiskit.providers.models.BackendConfiguration")

### defaults

<span id="qiskit.providers.fake_provider.FakeMumbai.defaults" />

`defaults()`

Returns a snapshot of device defaults

### name

<span id="qiskit.providers.fake_provider.FakeMumbai.name" />

`name()`

Return the backend name.

**Returns**

the name of the backend.

**Return type**

[str](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")

### properties

<span id="qiskit.providers.fake_provider.FakeMumbai.properties" />

`properties()`

Returns a snapshot of device properties

### provider

<span id="qiskit.providers.fake_provider.FakeMumbai.provider" />

`provider()`

Return the backend Provider.

**Returns**

the Provider responsible for the backend.

**Return type**

[Provider](qiskit.providers.Provider "qiskit.providers.Provider")

### run

<span id="qiskit.providers.fake_provider.FakeMumbai.run" />

`run(run_input, **kwargs)`

Main job in simulator

### set\_options

<span id="qiskit.providers.fake_provider.FakeMumbai.set_options" />

`set_options(**fields)`

Set the options fields for the backend

This method is used to update the options of a backend. If you need to change any of the options prior to running just pass in the kwarg with the new value for the options.

**Parameters**

**fields** – The fields to update the options

**Raises**

[**AttributeError**](https://docs.python.org/3/library/exceptions.html#AttributeError "(in Python v3.12)") – If the field passed in is not part of the options

### status

<span id="qiskit.providers.fake_provider.FakeMumbai.status" />

`status()`

Return the backend status.

**Returns**

the status of the backend.

**Return type**

[BackendStatus](qiskit.providers.models.BackendStatus "qiskit.providers.models.BackendStatus")

