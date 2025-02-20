---
title: DictToCircuitSum
description: API reference for qiskit.aqua.operators.converters.DictToCircuitSum
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.operators.converters.DictToCircuitSum
---

<span id="qiskit-aqua-operators-converters-dicttocircuitsum" />

# qiskit.aqua.operators.converters.DictToCircuitSum

<span id="qiskit.aqua.operators.converters.DictToCircuitSum" />

`DictToCircuitSum(traverse=True, convert_dicts=True, convert_vectors=True)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.8/qiskit/aqua/operators/converters/dict_to_circuit_sum.py "view source code")

Converts `DictStateFns` or `VectorStateFns` to equivalent `CircuitStateFns` or sums thereof. The behavior of this class can be mostly replicated by calling `to_circuit_op` on an Operator, but with the added control of choosing whether to convert only `DictStateFns` or `VectorStateFns`, rather than both.

**Parameters**

*   **traverse** (`bool`) – Whether to recurse down into Operators with internal sub-operators for conversion.
*   **convert\_dicts** (`bool`) – Whether to convert VectorStateFn.
*   **convert\_vectors** (`bool`) – Whether to convert DictStateFns.

### \_\_init\_\_

<span id="qiskit.aqua.operators.converters.DictToCircuitSum.__init__" />

`__init__(traverse=True, convert_dicts=True, convert_vectors=True)`

**Parameters**

*   **traverse** (`bool`) – Whether to recurse down into Operators with internal sub-operators for conversion.
*   **convert\_dicts** (`bool`) – Whether to convert VectorStateFn.
*   **convert\_vectors** (`bool`) – Whether to convert DictStateFns.

## Methods

|                                                                                                                                                                        |                                                                               |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| [`__init__`](#qiskit.aqua.operators.converters.DictToCircuitSum.__init__ "qiskit.aqua.operators.converters.DictToCircuitSum.__init__")(\[traverse, convert\_dicts, …]) | **type traverse**`bool`                                                       |
| [`convert`](#qiskit.aqua.operators.converters.DictToCircuitSum.convert "qiskit.aqua.operators.converters.DictToCircuitSum.convert")(operator)                          | Convert the Operator to `CircuitStateFns`, recursively if `traverse` is True. |

### convert

<span id="qiskit.aqua.operators.converters.DictToCircuitSum.convert" />

`convert(operator)`

Convert the Operator to `CircuitStateFns`, recursively if `traverse` is True.

**Parameters**

**operator** (`OperatorBase`) – The Operator to convert

**Return type**

`OperatorBase`

**Returns**

The converted Operator.

