---
title: EvolutionBase
description: API reference for qiskit.opflow.evolutions.EvolutionBase
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.opflow.evolutions.EvolutionBase
---

# qiskit.opflow\.evolutions.EvolutionBase

<span id="qiskit.opflow.evolutions.EvolutionBase" />

`EvolutionBase`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/opflow/evolutions/evolution_base.py "view source code")

A base for Evolution converters. Evolutions are converters which traverse an Operator tree, replacing any `EvolvedOp` e with a Schrodinger equation-style evolution `CircuitOp` equalling or approximating the matrix exponential of -i \* the Operator contained inside (e.primitive). The Evolutions are essentially implementations of Hamiltonian Simulation algorithms, including various methods for Trotterization.

### \_\_init\_\_

<span id="qiskit.opflow.evolutions.EvolutionBase.__init__" />

`__init__()`

Initialize self. See help(type(self)) for accurate signature.

## Methods

|                                                                                                                         |                                                                                                   |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.opflow.evolutions.EvolutionBase.__init__ "qiskit.opflow.evolutions.EvolutionBase.__init__")()      | Initialize self.                                                                                  |
| [`convert`](#qiskit.opflow.evolutions.EvolutionBase.convert "qiskit.opflow.evolutions.EvolutionBase.convert")(operator) | Traverse the operator, replacing any `EvolutionOps` with their equivalent evolution `CircuitOps`. |

### convert

<span id="qiskit.opflow.evolutions.EvolutionBase.convert" />

`abstract convert(operator)`

Traverse the operator, replacing any `EvolutionOps` with their equivalent evolution `CircuitOps`.

> **Args:**
>
> operator: The Operator to convert.

**Return type**

`OperatorBase`

**Returns**

The converted Operator, with `EvolutionOps` replaced by `CircuitOps`.

