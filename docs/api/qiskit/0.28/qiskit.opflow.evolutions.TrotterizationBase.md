---
title: TrotterizationBase
description: API reference for qiskit.opflow.evolutions.TrotterizationBase
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.opflow.evolutions.TrotterizationBase
---

# qiskit.opflow\.evolutions.TrotterizationBase

<span id="qiskit.opflow.evolutions.TrotterizationBase" />

`TrotterizationBase(reps=1)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/opflow/evolutions/trotterizations/trotterization_base.py "view source code")

A base for Trotterization methods, algorithms for approximating exponentiations of operator sums by compositions of exponentiations.

### \_\_init\_\_

<span id="qiskit.opflow.evolutions.TrotterizationBase.__init__" />

`__init__(reps=1)`

Initialize self. See help(type(self)) for accurate signature.

## Methods

|                                                                                                                                     |                                                                                                                 |
| ----------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.opflow.evolutions.TrotterizationBase.__init__ "qiskit.opflow.evolutions.TrotterizationBase.__init__")(\[reps]) | Initialize self.                                                                                                |
| [`convert`](#qiskit.opflow.evolutions.TrotterizationBase.convert "qiskit.opflow.evolutions.TrotterizationBase.convert")(operator)   | Convert a `SummedOp` into a `ComposedOp` or `CircuitOp` representing an approximation of e^-i\*\`\`op\_sum\`\`. |

## Attributes

|                                                                                                                |                                                                                               |
| -------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| [`reps`](#qiskit.opflow.evolutions.TrotterizationBase.reps "qiskit.opflow.evolutions.TrotterizationBase.reps") | The number of repetitions to use in the Trotterization, improving the approximation accuracy. |

### convert

<span id="qiskit.opflow.evolutions.TrotterizationBase.convert" />

`abstract convert(operator)`

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

<span id="qiskit.opflow.evolutions.TrotterizationBase.reps" />

`property reps`

The number of repetitions to use in the Trotterization, improving the approximation accuracy.

**Return type**

`int`

