---
title: AbelianGrouper
description: API reference for qiskit.opflow.converters.AbelianGrouper
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.opflow.converters.AbelianGrouper
---

# qiskit.opflow\.converters.AbelianGrouper

<span id="qiskit.opflow.converters.AbelianGrouper" />

`AbelianGrouper(traverse=True)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/opflow/converters/abelian_grouper.py "view source code")

The AbelianGrouper converts SummedOps into a sum of Abelian sums.

Meaning, it will traverse the Operator, and when it finds a SummedOp, it will evaluate which of the summed sub-Operators commute with one another. It will then convert each of the groups of commuting Operators into their own SummedOps, and return the sum-of-commuting-SummedOps. This is particularly useful for cases where mutually commuting groups can be handled similarly, as in the case of Pauli Expectations, where commuting Paulis have the same diagonalizing circuit rotation, or Pauli Evolutions, where commuting Paulis can be diagonalized together.

**Parameters**

**traverse** (`bool`) – Whether to convert only the Operator passed to `convert`, or traverse down that Operator.

### \_\_init\_\_

<span id="qiskit.opflow.converters.AbelianGrouper.__init__" />

`__init__(traverse=True)`

**Parameters**

**traverse** (`bool`) – Whether to convert only the Operator passed to `convert`, or traverse down that Operator.

## Methods

|                                                                                                                                          |                                                                                                                                                                                                         |
| ---------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.opflow.converters.AbelianGrouper.__init__ "qiskit.opflow.converters.AbelianGrouper.__init__")(\[traverse])          | **type traverse**`bool`                                                                                                                                                                                 |
| [`convert`](#qiskit.opflow.converters.AbelianGrouper.convert "qiskit.opflow.converters.AbelianGrouper.convert")(operator)                | Check if operator is a SummedOp, in which case covert it into a sum of mutually commuting sums, or if the Operator contains sub-Operators and `traverse` is True, attempt to convert any sub-Operators. |
| [`group_subops`](#qiskit.opflow.converters.AbelianGrouper.group_subops "qiskit.opflow.converters.AbelianGrouper.group_subops")(list\_op) | Given a ListOp, attempt to group into Abelian ListOps of the same type.                                                                                                                                 |

### convert

<span id="qiskit.opflow.converters.AbelianGrouper.convert" />

`convert(operator)`

Check if operator is a SummedOp, in which case covert it into a sum of mutually commuting sums, or if the Operator contains sub-Operators and `traverse` is True, attempt to convert any sub-Operators.

**Parameters**

**operator** (`OperatorBase`) – The Operator to attempt to convert.

**Return type**

`OperatorBase`

**Returns**

The converted Operator.

### group\_subops

<span id="qiskit.opflow.converters.AbelianGrouper.group_subops" />

`classmethod group_subops(list_op)`

Given a ListOp, attempt to group into Abelian ListOps of the same type.

**Parameters**

**list\_op** (`Union`\[`ListOp`, `PauliSumOp`]) – The Operator to group into Abelian groups

**Return type**

`ListOp`

**Returns**

The grouped Operator.

**Raises**

[**OpflowError**](qiskit.opflow.OpflowError "qiskit.opflow.OpflowError") – If any of list\_op’s sub-ops is not `PauliOp`.

