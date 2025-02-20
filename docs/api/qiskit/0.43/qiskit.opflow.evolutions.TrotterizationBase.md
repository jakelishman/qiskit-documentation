---
title: TrotterizationBase
description: API reference for qiskit.opflow.evolutions.TrotterizationBase
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.opflow.evolutions.TrotterizationBase
---

# TrotterizationBase

<span id="qiskit.opflow.evolutions.TrotterizationBase" />

`TrotterizationBase(reps=1)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/evolutions/trotterizations/trotterization_base.py "view source code")

Bases: [`EvolutionBase`](qiskit.opflow.evolutions.EvolutionBase "qiskit.opflow.evolutions.evolution_base.EvolutionBase")

Deprecated: A base for Trotterization methods, algorithms for approximating exponentiations of operator sums by compositions of exponentiations.

<Admonition title="Deprecated since version 0.24.0" type="danger">
  The class `qiskit.opflow.evolutions.trotterizations.trotterization_base.TrotterizationBase` is deprecated as of qiskit-terra 0.24.0. It will be removed no earlier than 3 months after the release date. For code migration guidelines, visit [https://qisk.it/opflow\_migration](https://qisk.it/opflow_migration).
</Admonition>

## Methods Defined Here

<span id="qiskit-opflow-evolutions-trotterizationbase-convert" />

### convert

<span id="qiskit.opflow.evolutions.TrotterizationBase.convert" />

`abstract TrotterizationBase.convert(operator)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/evolutions/trotterizations/trotterization_base.py "view source code")

Convert a `SummedOp` into a `ComposedOp` or `CircuitOp` representing an approximation of e^-i\*\`\`op\_sum\`\`.

**Parameters**

**operator** ([*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")) – The `SummedOp` to evolve.

**Returns**

The Operator approximating op\_sum’s evolution.

**Raises**

**TypeError** – A non-SummedOps Operator is passed into `convert`.

**Return type**

[*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

## Attributes

<span id="qiskit.opflow.evolutions.TrotterizationBase.reps" />

### reps

The number of repetitions to use in the Trotterization, improving the approximation accuracy.

