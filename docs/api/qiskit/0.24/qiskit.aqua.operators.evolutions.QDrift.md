---
title: QDrift
description: API reference for qiskit.aqua.operators.evolutions.QDrift
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.operators.evolutions.QDrift
---

<span id="qiskit-aqua-operators-evolutions-qdrift" />

# qiskit.aqua.operators.evolutions.QDrift

<span id="qiskit.aqua.operators.evolutions.QDrift" />

`QDrift(reps=1)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.8/qiskit/aqua/operators/evolutions/trotterizations/qdrift.py "view source code")

The QDrift Trotterization method, which selects each each term in the Trotterization randomly, with a probability proportional to its weight. Based on the work of Earl Campbell in [https://arxiv.org/abs/1811.08017](https://arxiv.org/abs/1811.08017).

**Parameters**

**reps** (`int`) – The number of times to repeat the Trotterization circuit.

### \_\_init\_\_

<span id="qiskit.aqua.operators.evolutions.QDrift.__init__" />

`__init__(reps=1)`

**Parameters**

**reps** (`int`) – The number of times to repeat the Trotterization circuit.

## Methods

|                                                                                                                             |                                                                                                                 |
| --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.aqua.operators.evolutions.QDrift.__init__ "qiskit.aqua.operators.evolutions.QDrift.__init__")(\[reps]) | **type reps**`int`                                                                                              |
| [`convert`](#qiskit.aqua.operators.evolutions.QDrift.convert "qiskit.aqua.operators.evolutions.QDrift.convert")(operator)   | Convert a `SummedOp` into a `ComposedOp` or `CircuitOp` representing an approximation of e^-i\*\`\`op\_sum\`\`. |

## Attributes

|                                                                                                        |                                                                                               |
| ------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------- |
| [`reps`](#qiskit.aqua.operators.evolutions.QDrift.reps "qiskit.aqua.operators.evolutions.QDrift.reps") | The number of repetitions to use in the Trotterization, improving the approximation accuracy. |

### convert

<span id="qiskit.aqua.operators.evolutions.QDrift.convert" />

`convert(operator)`

Convert a `SummedOp` into a `ComposedOp` or `CircuitOp` representing an approximation of e^-i\*\`\`op\_sum\`\`.

**Parameters**

**operator** (`OperatorBase`) – The `SummedOp` to evolve.

**Return type**

`OperatorBase`

**Returns**

The Operator approximating op\_sum’s evolution.

**Raises**

**TypeError** – A non-SummedOps Operator is passed into `convert`.

### reps

<span id="qiskit.aqua.operators.evolutions.QDrift.reps" />

`property reps`

The number of repetitions to use in the Trotterization, improving the approximation accuracy.

**Return type**

`int`

