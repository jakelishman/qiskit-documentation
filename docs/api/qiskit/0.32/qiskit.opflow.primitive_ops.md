<span id="qiskit-opflow-primitive-ops" />

# qiskit.opflow\.primitive\_ops

## Primitive Operators ([`qiskit.opflow.primitive_ops`](#module-qiskit.opflow.primitive_ops "qiskit.opflow.primitive_ops"))

Operators are defined to be functions which take State functions to State functions.

PrimitiveOps are the classes for representing basic Operators, backed by computational Operator primitives from Terra. These classes (and inheritors) primarily serve to allow the underlying primitives to “flow” - i.e. interoperability and adherence to the Operator formalism - while the core computational logic mostly remains in the underlying primitives. For example, we would not produce an interface in Terra in which `QuantumCircuit1 + QuantumCircuit2` equaled the Operator sum of the circuit unitaries, rather than simply appending the circuits. However, within the Operator flow summing the unitaries is the expected behavior.

<Admonition title="Note" type="note">
  All mathematical methods are not in-place, meaning that they return a new object, but the underlying primitives are not copied.
</Admonition>

### Primitive Operators

|                                                                                                                                                 |                                                                                     |
| ----------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| [`PrimitiveOp`](qiskit.opflow.primitive_ops.PrimitiveOp "qiskit.opflow.primitive_ops.PrimitiveOp")(primitive\[, coeff])                         | A class for representing basic Operators, backed by Operator primitives from Terra. |
| [`CircuitOp`](qiskit.opflow.primitive_ops.CircuitOp "qiskit.opflow.primitive_ops.CircuitOp")(primitive\[, coeff])                               | Class for Operators backed by Terra’s `QuantumCircuit` module.                      |
| [`MatrixOp`](qiskit.opflow.primitive_ops.MatrixOp "qiskit.opflow.primitive_ops.MatrixOp")(primitive\[, coeff])                                  | Class for Operators represented by matrices, backed by Terra’s `Operator` module.   |
| [`PauliOp`](qiskit.opflow.primitive_ops.PauliOp "qiskit.opflow.primitive_ops.PauliOp")(primitive\[, coeff])                                     | Class for Operators backed by Terra’s `Pauli` module.                               |
| [`PauliSumOp`](qiskit.opflow.primitive_ops.PauliSumOp "qiskit.opflow.primitive_ops.PauliSumOp")(primitive\[, coeff, grouping\_type])            | Class for Operators backend by Terra’s `SparsePauliOp` class.                       |
| [`TaperedPauliSumOp`](qiskit.opflow.primitive_ops.TaperedPauliSumOp "qiskit.opflow.primitive_ops.TaperedPauliSumOp")(primitive, z2\_symmetries) | Class for PauliSumOp after tapering                                                 |

### Symmetries

|                                                                                                                                         |               |
| --------------------------------------------------------------------------------------------------------------------------------------- | ------------- |
| [`Z2Symmetries`](qiskit.opflow.primitive_ops.Z2Symmetries "qiskit.opflow.primitive_ops.Z2Symmetries")(symmetries, sq\_paulis, sq\_list) | Z2 Symmetries |
