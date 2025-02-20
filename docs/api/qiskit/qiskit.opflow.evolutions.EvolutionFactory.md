---
title: EvolutionFactory
description: API reference for qiskit.opflow.evolutions.EvolutionFactory
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.opflow.evolutions.EvolutionFactory
---

# EvolutionFactory

<span id="qiskit.opflow.evolutions.EvolutionFactory" />

`qiskit.opflow.evolutions.EvolutionFactory`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/opflow/evolutions/evolution_factory.py "view source code")

Bases: [`object`](https://docs.python.org/3/library/functions.html#object "(in Python v3.12)")

Deprecated: A factory class for convenient automatic selection of an Evolution algorithm based on the Operator to be converted.

## Methods

### build

<span id="qiskit.opflow.evolutions.EvolutionFactory.build" />

`static build(operator=None)`

A factory method for convenient automatic selection of an Evolution algorithm based on the Operator to be converted.

<Admonition title="Deprecated since version 0.24.0" type="danger">
  The method `qiskit.opflow.evolutions.evolution_factory.EvolutionFactory.build()` is deprecated as of qiskit-terra 0.24.0. It will be removed no earlier than 3 months after the release date. For code migration guidelines, visit [https://qisk.it/opflow\_migration](https://qisk.it/opflow_migration).
</Admonition>

**Parameters**

**operator** ([*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")) – the Operator being evolved

**Returns**

the `EvolutionBase` best suited to evolve operator.

**Return type**

[EvolutionBase](qiskit.opflow.evolutions.EvolutionBase "qiskit.opflow.evolutions.EvolutionBase")

**Raises**

[**ValueError**](https://docs.python.org/3/library/exceptions.html#ValueError "(in Python v3.12)") – If operator is not of a composition for which we know the best Evolution method.

