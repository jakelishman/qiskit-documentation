---
title: ConverterBase
description: API reference for qiskit.opflow.converters.ConverterBase
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.opflow.converters.ConverterBase
---

# ConverterBase

<span id="qiskit.opflow.converters.ConverterBase" />

`ConverterBase`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/converters/converter_base.py "view source code")

Bases: `abc.ABC`

Converters take an Operator and return a new Operator, generally isomorphic in some way with the first, but with certain desired properties. For example, a converter may accept `CircuitOp` and return a `SummedOp` of `PauliOps` representing the circuit unitary. Converters may not have polynomial space or time scaling in their operations. On the contrary, many converters, such as a `MatrixExpectation` or `MatrixEvolution`, which convert `PauliOps` to `MatrixOps` internally, will require time or space exponential in the number of qubits unless a clever trick is known (such as the use of sparse matrices).

## Methods Defined Here

### convert

<span id="qiskit.opflow.converters.ConverterBase.convert" />

`abstract ConverterBase.convert(operator)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/converters/converter_base.py "view source code")

Accept the Operator and return the converted Operator

**Parameters**

**operator** ([`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")) – The Operator to convert.

**Return type**

[`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

**Returns**

The converted Operator.

