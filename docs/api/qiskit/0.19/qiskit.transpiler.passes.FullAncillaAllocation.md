---
title: FullAncillaAllocation
description: API reference for qiskit.transpiler.passes.FullAncillaAllocation
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.FullAncillaAllocation
---

# FullAncillaAllocation

<span id="qiskit.transpiler.passes.FullAncillaAllocation" />

`FullAncillaAllocation(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/transpiler/passes/layout/full_ancilla_allocation.py "view source code")

Allocate all idle nodes from the coupling map as ancilla on the layout.

A pass for allocating all idle physical qubits (those that exist in coupling map but not the dag circuit) as ancilla. It will also choose new virtual qubits to correspond to those physical ancilla.

<Admonition title="Note" type="note">
  This is an analysis pass, and only responsible for choosing physical ancilla locations and their corresponding virtual qubits. A separate transformation pass must add those virtual qubits to the circuit.
</Admonition>

FullAncillaAllocation initializer.

**Parameters**

**coupling\_map** (*Coupling*) – directed graph representing a coupling map.

## Attributes

### is\_analysis\_pass

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

### is\_transformation\_pass

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

## Methods

### name

<span id="qiskit.transpiler.passes.FullAncillaAllocation.name" />

`FullAncillaAllocation.name()`

Return the name of the pass.

### run

<span id="qiskit.transpiler.passes.FullAncillaAllocation.run" />

`FullAncillaAllocation.run(dag)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/transpiler/passes/layout/full_ancilla_allocation.py "view source code")

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

[**TranspilerError**](qiskit.transpiler.TranspilerError "qiskit.transpiler.TranspilerError") – If there is not layout in the property set or not set at init time.

