---
title: EvolutionFactory
description: API reference for qiskit.aqua.operators.evolutions.EvolutionFactory
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.operators.evolutions.EvolutionFactory
---

# qiskit.aqua.operators.evolutions.EvolutionFactory

<span id="qiskit.aqua.operators.evolutions.EvolutionFactory" />

`EvolutionFactory`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/evolutions/evolution_factory.py "view source code")

A factory class for convenient automatic selection of an Evolution algorithm based on the Operator to be converted.

### \_\_init\_\_

<span id="qiskit.aqua.operators.evolutions.EvolutionFactory.__init__" />

`__init__()`

Initialize self. See help(type(self)) for accurate signature.

## Methods

|                                                                                                                                            |                                                                                                                      |
| ------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.aqua.operators.evolutions.EvolutionFactory.__init__ "qiskit.aqua.operators.evolutions.EvolutionFactory.__init__")()   | Initialize self.                                                                                                     |
| [`build`](#qiskit.aqua.operators.evolutions.EvolutionFactory.build "qiskit.aqua.operators.evolutions.EvolutionFactory.build")(\[operator]) | A factory method for convenient automatic selection of an Evolution algorithm based on the Operator to be converted. |

### build

<span id="qiskit.aqua.operators.evolutions.EvolutionFactory.build" />

`static build(operator=None)`

A factory method for convenient automatic selection of an Evolution algorithm based on the Operator to be converted.

**Parameters**

**operator** (`Optional`\[`OperatorBase`]) – the Operator being evolved

**Returns**

the `EvolutionBase` best suited to evolve operator.

**Return type**

[EvolutionBase](qiskit.aqua.operators.evolutions.EvolutionBase "qiskit.aqua.operators.evolutions.EvolutionBase")

**Raises**

**ValueError** – If operator is not of a composition for which we know the best Evolution method.

