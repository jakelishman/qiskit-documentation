---
title: BackendProperties
description: API reference for qiskit.providers.models.BackendProperties
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.models.BackendProperties
---

# BackendProperties

<span id="qiskit.providers.models.BackendProperties" />

`BackendProperties(backend_name, backend_version, last_update_date, qubits, gates, general, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/providers/models/backendproperties.py "view source code")

Class representing backend properties

This holds backend properties measured by the provider. All properties which are provided optionally. These properties may describe qubits, gates, or other general propeties of the backend.

Initialize a BackendProperties instance.

**Parameters**

*   **backend\_name** (*str*) – Backend name.
*   **backend\_version** (*str*) – Backend version in the form X.Y.Z.
*   **last\_update\_date** (*datetime or str*) – Last date/time that a property was updated. If specified as a `str`, it must be in ISO format.
*   **qubits** (*list*) – System qubit parameters as a list of lists of `Nduv` objects
*   **gates** (*list*) – System gate parameters as a list of `Gate` objects
*   **general** (*list*) – General parameters as a list of `Nduv` objects
*   **kwargs** – optional additional fields

## Methods

### frequency

<span id="qiskit.providers.models.BackendProperties.frequency" />

`BackendProperties.frequency(qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/providers/models/backendproperties.py "view source code")

Return the frequency of the given qubit.

**Parameters**

**qubit** (`int`) – Qubit for which to return frequency of.

**Return type**

`float`

**Returns**

Frequency of the given qubit.

### from\_dict

<span id="qiskit.providers.models.BackendProperties.from_dict" />

`classmethod BackendProperties.from_dict(data)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/providers/models/backendproperties.py "view source code")

Create a new Gate object from a dictionary.

**Parameters**

**data** (*dict*) – A dictionary representing the Gate to create. It will be in the same format as output by [`to_dict()`](qiskit.providers.models.BackendProperties#to_dict "qiskit.providers.models.BackendProperties.to_dict").

**Returns**

**The BackendProperties from the input**

dictionary.

**Return type**

[BackendProperties](qiskit.providers.models.BackendProperties "qiskit.providers.models.BackendProperties")

### gate\_error

<span id="qiskit.providers.models.BackendProperties.gate_error" />

`BackendProperties.gate_error(gate, qubits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/providers/models/backendproperties.py "view source code")

Return gate error estimates from backend properties.

**Parameters**

*   **gate** (`str`) – The gate for which to get the error.
*   **qubits** (`Union`\[`int`, `Iterable`\[`int`]]) – The specific qubits for the gate.

**Return type**

`float`

**Returns**

Gate error of the given gate and qubit(s).

### gate\_length

<span id="qiskit.providers.models.BackendProperties.gate_length" />

`BackendProperties.gate_length(gate, qubits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/providers/models/backendproperties.py "view source code")

Return the duration of the gate in units of seconds.

**Parameters**

*   **gate** (`str`) – The gate for which to get the duration.
*   **qubits** (`Union`\[`int`, `Iterable`\[`int`]]) – The specific qubits for the gate.

**Return type**

`float`

**Returns**

Gate length of the given gate and qubit(s).

### gate\_property

<span id="qiskit.providers.models.BackendProperties.gate_property" />

`BackendProperties.gate_property(gate, qubits=None, name=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/providers/models/backendproperties.py "view source code")

Return the property of the given gate.

**Parameters**

*   **gate** (`str`) – Name of the gate.
*   **qubits** (`Union`\[`int`, `Iterable`\[`int`], `None`]) – The qubit to find the property for.
*   **name** (`Optional`\[`str`]) – Optionally used to specify which gate property to return.

**Return type**

`Tuple`\[`Any`, `datetime`]

**Returns**

Gate property as a tuple of the value and the time it was measured.

**Raises**

[**BackendPropertyError**](qiskit.providers.BackendPropertyError "qiskit.providers.BackendPropertyError") – If the property is not found or name is specified but qubit is not.

### qubit\_property

<span id="qiskit.providers.models.BackendProperties.qubit_property" />

`BackendProperties.qubit_property(qubit, name=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/providers/models/backendproperties.py "view source code")

Return the property of the given qubit.

**Parameters**

*   **qubit** (`int`) – The property to look for.
*   **name** (`Optional`\[`str`]) – Optionally used to specify within the hierarchy which property to return.

**Return type**

`Tuple`\[`Any`, `datetime`]

**Returns**

Qubit property as a tuple of the value and the time it was measured.

**Raises**

[**BackendPropertyError**](qiskit.providers.BackendPropertyError "qiskit.providers.BackendPropertyError") – If the property is not found.

### readout\_error

<span id="qiskit.providers.models.BackendProperties.readout_error" />

`BackendProperties.readout_error(qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/providers/models/backendproperties.py "view source code")

Return the readout error of the given qubit.

**Parameters**

**qubit** (`int`) – Qubit for which to return the readout error of.

**Return type**

`float`

**Returns**

Readout error of the given qubit,

### t1

<span id="qiskit.providers.models.BackendProperties.t1" />

`BackendProperties.t1(qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/providers/models/backendproperties.py "view source code")

Return the T1 time of the given qubit.

**Parameters**

**qubit** (`int`) – Qubit for which to return the T1 time of.

**Return type**

`float`

**Returns**

T1 time of the given qubit.

### t2

<span id="qiskit.providers.models.BackendProperties.t2" />

`BackendProperties.t2(qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/providers/models/backendproperties.py "view source code")

Return the T2 time of the given qubit.

**Parameters**

**qubit** (`int`) – Qubit for which to return the T2 time of.

**Return type**

`float`

**Returns**

T2 time of the given qubit.

### to\_dict

<span id="qiskit.providers.models.BackendProperties.to_dict" />

`BackendProperties.to_dict()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/providers/models/backendproperties.py "view source code")

Return a dictionary format representation of the BackendProperties.

**Returns**

The dictionary form of the BackendProperties.

**Return type**

dict

