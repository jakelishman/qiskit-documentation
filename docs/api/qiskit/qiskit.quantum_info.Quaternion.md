---
title: Quaternion
description: API reference for qiskit.quantum_info.Quaternion
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.quantum_info.Quaternion
---

# Quaternion

<span id="qiskit.quantum_info.Quaternion" />

`qiskit.quantum_info.Quaternion(data)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/quantum_info/synthesis/quaternion.py "view source code")

Bases: [`object`](https://docs.python.org/3/library/functions.html#object "(in Python v3.12)")

A class representing a Quaternion.

## Methods

### from\_axis\_rotation

<span id="qiskit.quantum_info.Quaternion.from_axis_rotation" />

`classmethod from_axis_rotation(angle, axis)`

Return quaternion for rotation about given axis.

**Parameters**

*   **angle** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")) – Angle in radians.
*   **axis** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")) – Axis for rotation

**Returns**

Quaternion for axis rotation.

**Return type**

[Quaternion](#qiskit.quantum_info.Quaternion "qiskit.quantum_info.Quaternion")

**Raises**

[**ValueError**](https://docs.python.org/3/library/exceptions.html#ValueError "(in Python v3.12)") – Invalid input axis.

### from\_euler

<span id="qiskit.quantum_info.Quaternion.from_euler" />

`classmethod from_euler(angles, order='yzy')`

Generate a quaternion from a set of Euler angles.

**Parameters**

*   **angles** (*array\_like*) – Array of Euler angles.
*   **order** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")) – Order of Euler rotations. ‘yzy’ is default.

**Returns**

Quaternion representation of Euler rotation.

**Return type**

[Quaternion](#qiskit.quantum_info.Quaternion "qiskit.quantum_info.Quaternion")

### norm

<span id="qiskit.quantum_info.Quaternion.norm" />

`norm()`

Norm of quaternion.

### normalize

<span id="qiskit.quantum_info.Quaternion.normalize" />

`normalize(inplace=False)`

Normalizes a Quaternion to unit length so that it represents a valid rotation.

**Parameters**

**inplace** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – Do an inplace normalization.

**Returns**

Normalized quaternion.

**Return type**

[Quaternion](#qiskit.quantum_info.Quaternion "qiskit.quantum_info.Quaternion")

### to\_matrix

<span id="qiskit.quantum_info.Quaternion.to_matrix" />

`to_matrix()`

Converts a unit-length quaternion to a rotation matrix.

**Returns**

Rotation matrix.

**Return type**

ndarray

### to\_zyz

<span id="qiskit.quantum_info.Quaternion.to_zyz" />

`to_zyz()`

Converts a unit-length quaternion to a sequence of ZYZ Euler angles.

**Returns**

Array of Euler angles.

**Return type**

ndarray

