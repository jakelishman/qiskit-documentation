---
title: PauliTrotterEvolution
description: API reference for qiskit.opflow.evolutions.PauliTrotterEvolution
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.opflow.evolutions.PauliTrotterEvolution
---

# PauliTrotterEvolution

<span id="qiskit.opflow.evolutions.PauliTrotterEvolution" />

`qiskit.opflow.evolutions.PauliTrotterEvolution(trotter_mode='trotter', reps=1)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/opflow/evolutions/pauli_trotter_evolution.py "view source code")

Bases: [`EvolutionBase`](qiskit.opflow.evolutions.EvolutionBase "qiskit.opflow.evolutions.evolution_base.EvolutionBase")

Deprecated: An Evolution algorithm replacing exponentiated sums of Paulis by changing them each to the Z basis, rotating with an rZ, changing back, and Trotterizing.

More specifically, we compute basis change circuits for each Pauli into a single-qubit Z, evolve the Z by the desired evolution time with an rZ gate, and change the basis back using the adjoint of the original basis change circuit. For sums of Paulis, the individual Pauli evolution circuits are composed together by Trotterization scheme.

<Admonition title="Deprecated since version 0.24.0" type="danger">
  The class `qiskit.opflow.evolutions.pauli_trotter_evolution.PauliTrotterEvolution` is deprecated as of qiskit-terra 0.24.0. It will be removed no earlier than 3 months after the release date. For code migration guidelines, visit [https://qisk.it/opflow\_migration](https://qisk.it/opflow_migration).
</Admonition>

**Parameters**

*   **trotter\_mode** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")  *|*[*TrotterizationBase*](qiskit.opflow.evolutions.TrotterizationBase "qiskit.opflow.evolutions.trotterizations.trotterization_base.TrotterizationBase") *| None*) – A string (‘trotter’, ‘suzuki’, or ‘qdrift’) to pass to the TrotterizationFactory, or a TrotterizationBase, indicating how to combine individual Pauli evolution circuits to equal the exponentiation of the Pauli sum.
*   **reps** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)") *| None*) – How many Trotterization repetitions to make, to improve the approximation accuracy.
*   **evolution.** (*# TODO uncomment when we implement Abelian grouped*) –
*   **group\_paulis** (*#*) – Whether to group Pauli sums into Abelian
*   **sub-groups** (*#*) –
*   **group** (*so a single diagonalization circuit can be used for each*) –
*   **Pauli.** (*# rather than each*) –

## Attributes

<span id="qiskit.opflow.evolutions.PauliTrotterEvolution.trotter" />

### trotter

TrotterizationBase used to evolve SummedOps.

## Methods

### convert

<span id="qiskit.opflow.evolutions.PauliTrotterEvolution.convert" />

`convert(operator)`

Traverse the operator, replacing `EvolvedOps` with `CircuitOps` containing Trotterized evolutions equalling the exponentiation of -i \* operator.

**Parameters**

**operator** ([*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")) – The Operator to convert.

**Returns**

The converted operator.

**Return type**

[*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

### evolution\_for\_abelian\_paulisum

<span id="qiskit.opflow.evolutions.PauliTrotterEvolution.evolution_for_abelian_paulisum" />

`evolution_for_abelian_paulisum(op_sum)`

Evolution for abelian pauli sum

**Return type**

[*PrimitiveOp*](qiskit.opflow.primitive_ops.PrimitiveOp "qiskit.opflow.primitive_ops.primitive_op.PrimitiveOp")

### evolution\_for\_pauli

<span id="qiskit.opflow.evolutions.PauliTrotterEvolution.evolution_for_pauli" />

`evolution_for_pauli(pauli_op)`

Compute evolution Operator for a single Pauli using a `PauliBasisChange`.

**Parameters**

**pauli\_op** ([*PauliOp*](qiskit.opflow.primitive_ops.PauliOp "qiskit.opflow.primitive_ops.pauli_op.PauliOp")) – The `PauliOp` to evolve.

**Returns**

A `PrimitiveOp`, either the evolution `CircuitOp` or a `PauliOp` equal to the identity if pauli\_op is the identity.

**Return type**

[*PrimitiveOp*](qiskit.opflow.primitive_ops.PrimitiveOp "qiskit.opflow.primitive_ops.primitive_op.PrimitiveOp")

