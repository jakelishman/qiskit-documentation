---
title: ProviderV1
description: API reference for qiskit.providers.ProviderV1
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.ProviderV1
---

# qiskit.providers.ProviderV1

<span id="qiskit.providers.ProviderV1" />

`ProviderV1`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.17/qiskit/providers/provider.py "view source code")

Base class for a Backend Provider.

### \_\_init\_\_

<span id="qiskit.providers.ProviderV1.__init__" />

`__init__()`

Initialize self. See help(type(self)) for accurate signature.

## Methods

|                                                                                                              |                                                             |
| ------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------- |
| [`__init__`](#qiskit.providers.ProviderV1.__init__ "qiskit.providers.ProviderV1.__init__")()                 | Initialize self.                                            |
| [`backends`](#qiskit.providers.ProviderV1.backends "qiskit.providers.ProviderV1.backends")(\[name])          | Return a list of backends matching the specified filtering. |
| [`get_backend`](#qiskit.providers.ProviderV1.get_backend "qiskit.providers.ProviderV1.get_backend")(\[name]) | Return a single backend matching the specified filtering.   |

## Attributes

|           |   |
| --------- | - |
| `version` |   |

### backends

<span id="qiskit.providers.ProviderV1.backends" />

`abstract backends(name=None, **kwargs)`

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

<span id="qiskit.providers.ProviderV1.get_backend" />

`get_backend(name=None, **kwargs)`

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

