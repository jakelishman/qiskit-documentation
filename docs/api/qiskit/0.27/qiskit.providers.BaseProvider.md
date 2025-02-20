---
title: BaseProvider
description: API reference for qiskit.providers.BaseProvider
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.BaseProvider
---

# qiskit.providers.BaseProvider

<span id="qiskit.providers.BaseProvider" />

`BaseProvider(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.17/qiskit/providers/baseprovider.py "view source code")

Base class for a Backend Provider.

### \_\_init\_\_

<span id="qiskit.providers.BaseProvider.__init__" />

`__init__(*args, **kwargs)`

Initialize self. See help(type(self)) for accurate signature.

## Methods

|                                                                                                                    |                                                             |
| ------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------- |
| [`__init__`](#qiskit.providers.BaseProvider.__init__ "qiskit.providers.BaseProvider.__init__")(\*args, \*\*kwargs) | Initialize self.                                            |
| [`backends`](#qiskit.providers.BaseProvider.backends "qiskit.providers.BaseProvider.backends")(\[name])            | Return a list of backends matching the specified filtering. |
| [`get_backend`](#qiskit.providers.BaseProvider.get_backend "qiskit.providers.BaseProvider.get_backend")(\[name])   | Return a single backend matching the specified filtering.   |

### backends

<span id="qiskit.providers.BaseProvider.backends" />

`abstract backends(name=None, **kwargs)`

Return a list of backends matching the specified filtering.

**Parameters**

*   **name** (*str*) – name of the backend.
*   **\*\*kwargs** – dict used for filtering.

**Returns**

**a list of Backends that match the filtering**

criteria.

**Return type**

list\[[BaseBackend](qiskit.providers.BaseBackend "qiskit.providers.BaseBackend")]

### get\_backend

<span id="qiskit.providers.BaseProvider.get_backend" />

`get_backend(name=None, **kwargs)`

Return a single backend matching the specified filtering.

**Parameters**

*   **name** (*str*) – name of the backend.
*   **\*\*kwargs** – dict used for filtering.

**Returns**

a backend matching the filtering.

**Return type**

[BaseBackend](qiskit.providers.BaseBackend "qiskit.providers.BaseBackend")

**Raises**

[**QiskitBackendNotFoundError**](qiskit.providers.QiskitBackendNotFoundError "qiskit.providers.QiskitBackendNotFoundError") – if no backend could be found or more than one backend matches the filtering criteria.

