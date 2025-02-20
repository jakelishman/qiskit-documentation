---
title: FakeCasablanca
description: API reference for qiskit.providers.fake_provider.FakeCasablanca
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.fake_provider.FakeCasablanca
---

# FakeCasablanca

<span id="qiskit.providers.fake_provider.FakeCasablanca" />

`FakeCasablanca`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/providers/fake_provider/backends/casablanca/fake_casablanca.py "view source code")

Bases: `FakePulseBackend`

A fake 7 qubit backend.

FakeBackend initializer.

**Parameters**

*   **configuration** ([*BackendConfiguration*](qiskit.providers.models.BackendConfiguration "qiskit.providers.models.BackendConfiguration")) – backend configuration
*   **time\_alive** (*int*) – time to wait before returning result

## Methods

<span id="qiskit-providers-fake-provider-fakecasablanca-configuration" />

### configuration

<span id="qiskit.providers.fake_provider.FakeCasablanca.configuration" />

`FakeCasablanca.configuration()`

Return the backend configuration.

**Returns**

the configuration for the backend.

**Return type**

[BackendConfiguration](qiskit.providers.models.BackendConfiguration "qiskit.providers.models.BackendConfiguration")

<span id="qiskit-providers-fake-provider-fakecasablanca-defaults" />

### defaults

<span id="qiskit.providers.fake_provider.FakeCasablanca.defaults" />

`FakeCasablanca.defaults()`

Returns a snapshot of device defaults

<span id="qiskit-providers-fake-provider-fakecasablanca-name" />

### name

<span id="qiskit.providers.fake_provider.FakeCasablanca.name" />

`FakeCasablanca.name()`

Return the backend name.

**Returns**

the name of the backend.

**Return type**

str

<span id="qiskit-providers-fake-provider-fakecasablanca-properties" />

### properties

<span id="qiskit.providers.fake_provider.FakeCasablanca.properties" />

`FakeCasablanca.properties()`

Returns a snapshot of device properties

<span id="qiskit-providers-fake-provider-fakecasablanca-provider" />

### provider

<span id="qiskit.providers.fake_provider.FakeCasablanca.provider" />

`FakeCasablanca.provider()`

Return the backend Provider.

**Returns**

the Provider responsible for the backend.

**Return type**

[Provider](qiskit.providers.Provider "qiskit.providers.Provider")

<span id="qiskit-providers-fake-provider-fakecasablanca-run" />

### run

<span id="qiskit.providers.fake_provider.FakeCasablanca.run" />

`FakeCasablanca.run(run_input, **kwargs)`

Main job in simulator

<span id="qiskit-providers-fake-provider-fakecasablanca-set-options" />

### set\_options

<span id="qiskit.providers.fake_provider.FakeCasablanca.set_options" />

`FakeCasablanca.set_options(**fields)`

Set the options fields for the backend

This method is used to update the options of a backend. If you need to change any of the options prior to running just pass in the kwarg with the new value for the options.

**Parameters**

**fields** – The fields to update the options

**Raises**

**AttributeError** – If the field passed in is not part of the options

<span id="qiskit-providers-fake-provider-fakecasablanca-status" />

### status

<span id="qiskit.providers.fake_provider.FakeCasablanca.status" />

`FakeCasablanca.status()`

Return the backend status.

**Returns**

the status of the backend.

**Return type**

[BackendStatus](qiskit.providers.models.BackendStatus "qiskit.providers.models.BackendStatus")

## Attributes

<span id="qiskit.providers.fake_provider.FakeCasablanca.backend_name" />

### backend\_name

`= 'fake_casablanca'`

<span id="qiskit.providers.fake_provider.FakeCasablanca.conf_filename" />

### conf\_filename

`= 'conf_casablanca.json'`

<span id="qiskit.providers.fake_provider.FakeCasablanca.defs_filename" />

### defs\_filename

`= 'defs_casablanca.json'`

<span id="qiskit.providers.fake_provider.FakeCasablanca.dirname" />

### dirname

`= '/home/computertreker/git/qiskit/qiskit/.tox/docs/lib/python3.8/site-packages/qiskit/providers/fake_provider/backends/casablanca'`

<span id="qiskit.providers.fake_provider.FakeCasablanca.options" />

### options

Return the options for the backend

The options of a backend are the dynamic parameters defining how the backend is used. These are used to control the [`run()`](qiskit.providers.fake_provider.FakeCasablanca#run "qiskit.providers.fake_provider.FakeCasablanca.run") method.

<span id="qiskit.providers.fake_provider.FakeCasablanca.props_filename" />

### props\_filename

`= 'props_casablanca.json'`

<span id="qiskit.providers.fake_provider.FakeCasablanca.version" />

### version

`= 1`

