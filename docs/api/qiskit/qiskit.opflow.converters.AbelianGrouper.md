---
title: AbelianGrouper
description: API reference for qiskit.opflow.converters.AbelianGrouper
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.opflow.converters.AbelianGrouper
---

# AbelianGrouper

<span id="qiskit.opflow.converters.AbelianGrouper" />

`qiskit.opflow.converters.AbelianGrouper(traverse=True)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/opflow/converters/abelian_grouper.py "view source code")

Bases: [`ConverterBase`](qiskit.opflow.converters.ConverterBase "qiskit.opflow.converters.converter_base.ConverterBase")

Deprecated: The AbelianGrouper converts SummedOps into a sum of Abelian sums.

Meaning, it will traverse the Operator, and when it finds a SummedOp, it will evaluate which of the summed sub-Operators commute with one another. It will then convert each of the groups of commuting Operators into their own SummedOps, and return the sum-of-commuting-SummedOps. This is particularly useful for cases where mutually commuting groups can be handled similarly, as in the case of Pauli Expectations, where commuting Paulis have the same diagonalizing circuit rotation, or Pauli Evolutions, where commuting Paulis can be diagonalized together.

<Admonition title="Deprecated since version 0.24.0" type="danger">
  The class `qiskit.opflow.converters.abelian_grouper.AbelianGrouper` is deprecated as of qiskit-terra 0.24.0. It will be removed no earlier than 3 months after the release date. For code migration guidelines, visit [https://qisk.it/opflow\_migration](https://qisk.it/opflow_migration).
</Admonition>

**Parameters**

**traverse** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – Whether to convert only the Operator passed to `convert`, or traverse down that Operator.

## Methods

### convert

<span id="qiskit.opflow.converters.AbelianGrouper.convert" />

`convert(operator)`

Check if operator is a SummedOp, in which case covert it into a sum of mutually commuting sums, or if the Operator contains sub-Operators and `traverse` is True, attempt to convert any sub-Operators.

**Parameters**

**operator** ([*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")) – The Operator to attempt to convert.

**Returns**

The converted Operator.

**Return type**

[*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

### group\_subops

<span id="qiskit.opflow.converters.AbelianGrouper.group_subops" />

`classmethod group_subops(list_op)`

Given a ListOp, attempt to group into Abelian ListOps of the same type.

**Parameters**

**list\_op** ([*ListOp*](qiskit.opflow.list_ops.ListOp "qiskit.opflow.list_ops.list_op.ListOp")  *|*[*PauliSumOp*](qiskit.opflow.primitive_ops.PauliSumOp "qiskit.opflow.primitive_ops.pauli_sum_op.PauliSumOp")) – The Operator to group into Abelian groups

**Returns**

The grouped Operator.

**Raises**

[**OpflowError**](opflow#qiskit.opflow.OpflowError "qiskit.opflow.OpflowError") – If any of list\_op’s sub-ops is not `PauliOp`.

**Return type**

[*ListOp*](qiskit.opflow.list_ops.ListOp "qiskit.opflow.list_ops.list_op.ListOp")

