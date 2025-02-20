---
title: FakeProvider
description: API reference for qiskit.providers.fake_provider.FakeProvider
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.fake_provider.FakeProvider
---

# FakeProvider

<span id="qiskit.providers.fake_provider.FakeProvider" />

`FakeProvider`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/providers/fake_provider/fake_provider.py "view source code")

Bases: [`qiskit.providers.provider.ProviderV1`](qiskit.providers.ProviderV1 "qiskit.providers.provider.ProviderV1")

Fake provider containing fake V1 backends.

Only filtering backends by name is implemented. This class contains all fake V1 backends available in the [`qiskit.providers.fake_provider`](providers_fake_provider#module-qiskit.providers.fake_provider "qiskit.providers.fake_provider").

## Methods

### backends

<span id="qiskit.providers.fake_provider.FakeProvider.backends" />

`FakeProvider.backends(name=None, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/providers/fake_provider/fake_provider.py "view source code")

Return a list of backends matching the specified filtering.

**Parameters**

*   **name** (*str*) – name of the backend.
*   **\*\*kwargs** – dict used for filtering.

**Returns**

**a list of Backends that match the filtering**

criteria.

**Return type**

list\[[Backend](qiskit.providers.Backend "qiskit.providers.Backend")]

### get\_backend

<span id="qiskit.providers.fake_provider.FakeProvider.get_backend" />

`FakeProvider.get_backend(name=None, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/providers/fake_provider/fake_provider.py "view source code")

Return a single backend matching the specified filtering.

**Parameters**

*   **name** (*str*) – name of the backend.
*   **\*\*kwargs** – dict used for filtering.

**Returns**

a backend matching the filtering.

**Return type**

[Backend](qiskit.providers.Backend "qiskit.providers.Backend")

**Raises**

[**QiskitBackendNotFoundError**](qiskit.providers.QiskitBackendNotFoundError "qiskit.providers.QiskitBackendNotFoundError") – if no backend could be found or more than one backend matches the filtering criteria.

## Attributes

<span id="qiskit.providers.fake_provider.FakeProvider.version" />

### version

`= 1`

