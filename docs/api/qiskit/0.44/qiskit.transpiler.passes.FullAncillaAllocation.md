---
title: FullAncillaAllocation
description: API reference for qiskit.transpiler.passes.FullAncillaAllocation
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.FullAncillaAllocation
---

# FullAncillaAllocation

<span id="qiskit.transpiler.passes.FullAncillaAllocation" />

`qiskit.transpiler.passes.FullAncillaAllocation(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.25/qiskit/transpiler/passes/layout/full_ancilla_allocation.py "view source code")

Bases: [`AnalysisPass`](qiskit.transpiler.AnalysisPass "qiskit.transpiler.basepasses.AnalysisPass")

Allocate all idle nodes from the coupling map or target as ancilla on the layout.

A pass for allocating all idle physical qubits (those that exist in coupling map or target but not the dag circuit) as ancilla. It will also choose new virtual qubits to correspond to those physical ancilla.

<Admonition title="Note" type="note">
  This is an analysis pass, and only responsible for choosing physical ancilla locations and their corresponding virtual qubits. A separate transformation pass must add those virtual qubits to the circuit.
</Admonition>

FullAncillaAllocation initializer.

**Parameters**

**coupling\_map** (*Union\[*[*CouplingMap*](qiskit.transpiler.CouplingMap "qiskit.transpiler.CouplingMap")*,* [*Target*](qiskit.transpiler.Target "qiskit.transpiler.Target")*]*) – directed graph representing a coupling map.

## Attributes

<span id="qiskit.transpiler.passes.FullAncillaAllocation.is_analysis_pass" />

### is\_analysis\_pass

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

<span id="qiskit.transpiler.passes.FullAncillaAllocation.is_transformation_pass" />

### is\_transformation\_pass

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

## Methods

### name

<span id="qiskit.transpiler.passes.FullAncillaAllocation.name" />

`name()`

Return the name of the pass.

### run

<span id="qiskit.transpiler.passes.FullAncillaAllocation.run" />

`run(dag)`

Run the FullAncillaAllocation pass on dag.

Extend the layout with new (physical qubit, virtual qubit) pairs. The dag signals which virtual qubits are already in the circuit. This pass will allocate new virtual qubits such that no collision occurs (i.e. Layout bijectivity is preserved)

The coupling\_map and layout together determine which physical qubits are free.

**Parameters**

**dag** ([*DAGCircuit*](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")) – circuit to analyze

**Returns**

returns the same dag circuit, unmodified

**Return type**

[DAGCircuit](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")

**Raises**

[**TranspilerError**](transpiler#qiskit.transpiler.TranspilerError "qiskit.transpiler.TranspilerError") – If there is not layout in the property set or not set at init time.

### validate\_layout

<span id="qiskit.transpiler.passes.FullAncillaAllocation.validate_layout" />

`static validate_layout(layout_qubits, dag_qubits)`

Checks if all the qregs in layout\_qregs already exist in dag\_qregs. Otherwise, raise.

