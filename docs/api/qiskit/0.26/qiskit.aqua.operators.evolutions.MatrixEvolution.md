---
title: MatrixEvolution
description: API reference for qiskit.aqua.operators.evolutions.MatrixEvolution
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.operators.evolutions.MatrixEvolution
---

# qiskit.aqua.operators.evolutions.MatrixEvolution

<span id="qiskit.aqua.operators.evolutions.MatrixEvolution" />

`MatrixEvolution`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/evolutions/matrix_evolution.py "view source code")

Performs Evolution by classical matrix exponentiation, constructing a circuit with `UnitaryGates` or `HamiltonianGates` containing the exponentiation of the Operator.

### \_\_init\_\_

<span id="qiskit.aqua.operators.evolutions.MatrixEvolution.__init__" />

`__init__()`

Initialize self. See help(type(self)) for accurate signature.

## Methods

|                                                                                                                                             |                                                                                                                                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.aqua.operators.evolutions.MatrixEvolution.__init__ "qiskit.aqua.operators.evolutions.MatrixEvolution.__init__")()      | Initialize self.                                                                                                                                                                                           |
| [`convert`](#qiskit.aqua.operators.evolutions.MatrixEvolution.convert "qiskit.aqua.operators.evolutions.MatrixEvolution.convert")(operator) | Traverse the operator, replacing `EvolvedOps` with `CircuitOps` containing `UnitaryGates` or `HamiltonianGates` (if self.coeff is a `ParameterExpression`) equalling the exponentiation of -i \* operator. |

### convert

<span id="qiskit.aqua.operators.evolutions.MatrixEvolution.convert" />

`convert(operator)`

Traverse the operator, replacing `EvolvedOps` with `CircuitOps` containing `UnitaryGates` or `HamiltonianGates` (if self.coeff is a `ParameterExpression`) equalling the exponentiation of -i \* operator. This is done by converting the `EvolvedOp.primitive` to a `MatrixOp` and simply calling `.exp_i()` on that.

**Parameters**

**operator** (`OperatorBase`) – The Operator to convert.

**Return type**

`OperatorBase`

**Returns**

The converted operator.

