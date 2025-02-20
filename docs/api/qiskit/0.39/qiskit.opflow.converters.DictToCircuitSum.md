---
title: DictToCircuitSum
description: API reference for qiskit.opflow.converters.DictToCircuitSum
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.opflow.converters.DictToCircuitSum
---

# DictToCircuitSum

<span id="qiskit.opflow.converters.DictToCircuitSum" />

`DictToCircuitSum(traverse=True, convert_dicts=True, convert_vectors=True)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/opflow/converters/dict_to_circuit_sum.py "view source code")

Bases: [`qiskit.opflow.converters.converter_base.ConverterBase`](qiskit.opflow.converters.ConverterBase "qiskit.opflow.converters.converter_base.ConverterBase")

Converts `DictStateFns` or `VectorStateFns` to equivalent `CircuitStateFns` or sums thereof. The behavior of this class can be mostly replicated by calling `to_circuit_op` on an Operator, but with the added control of choosing whether to convert only `DictStateFns` or `VectorStateFns`, rather than both.

**Parameters**

*   **traverse** (`bool`) – Whether to recurse down into Operators with internal sub-operators for conversion.
*   **convert\_dicts** (`bool`) – Whether to convert VectorStateFn.
*   **convert\_vectors** (`bool`) – Whether to convert DictStateFns.

## Methods Defined Here

### convert

<span id="qiskit.opflow.converters.DictToCircuitSum.convert" />

`DictToCircuitSum.convert(operator)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/opflow/converters/dict_to_circuit_sum.py "view source code")

Convert the Operator to `CircuitStateFns`, recursively if `traverse` is True.

**Parameters**

**operator** ([`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")) – The Operator to convert

**Return type**

[`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

**Returns**

The converted Operator.

