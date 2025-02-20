---
title: PauliEvolutionGate
description: API reference for qiskit.circuit.library.PauliEvolutionGate
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.PauliEvolutionGate
---

# PauliEvolutionGate

<span id="qiskit.circuit.library.PauliEvolutionGate" />

`PauliEvolutionGate(operator, time=1.0, label=None, synthesis=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/circuit/library/pauli_evolution.py "view source code")

Bases: [`qiskit.circuit.gate.Gate`](qiskit.circuit.Gate "qiskit.circuit.gate.Gate")

Time-evolution of an operator consisting of Paulis.

For an operator $H$ consisting of Pauli terms and (real) evolution time $t$ this gate implements

$$
U(t) = e^{-itH}.
$$

This gate serves as a high-level definition of the evolution and can be synthesized into a circuit using different algorithms.

The evolution gates are related to the Pauli rotation gates by a factor of 2. For example the time evolution of the Pauli $X$ operator is connected to the Pauli $X$ rotation $R_X$ by

$$
U(t) = e^{-itX} = R_X(2t).
$$

**Examples:**

```python
from qiskit.circuit import QuantumCircuit
from qiskit.circuit.library import PauliEvolutionGate
from qiskit.opflow import I, Z, X

# build the evolution gate
operator = (Z ^ Z) - 0.1 * (X ^ I)
evo = PauliEvolutionGate(operator, time=0.2)

# plug it into a circuit
circuit = QuantumCircuit(2)
circuit.append(evo, range(2))
print(circuit.draw())
```

The above will print (note that the `-0.1` coefficient is not printed!):

```python
     ┌──────────────────────────┐
q_0: ┤0                         ├
     │  exp(-it (ZZ + XI))(0.2) │
q_1: ┤1                         ├
     └──────────────────────────┘
```

**References:**

\[1] G. Li et al. Paulihedral: A Generalized Block-Wise Compiler Optimization Framework For Quantum Simulation Kernels (2021). \[[arXiv:2109.03371](https://arxiv.org/abs/2109.03371)]

**Parameters**

*   **operator** ([*Pauli*](qiskit.quantum_info.Pauli "qiskit.quantum_info.Pauli")  *|*[*PauliOp*](qiskit.opflow.primitive_ops.PauliOp "qiskit.opflow.primitive_ops.PauliOp")  *|*[*SparsePauliOp*](qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp")  *|*[*PauliSumOp*](qiskit.opflow.primitive_ops.PauliSumOp "qiskit.opflow.primitive_ops.PauliSumOp") *| list*) – The operator to evolve. Can also be provided as list of non-commuting operators where the elements are sums of commuting operators. For example: `[XY + YX, ZZ + ZI + IZ, YY]`.
*   **time** (`Union`\[`int`, `float`, [`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")]) – The evolution time.
*   **label** (`Optional`\[`str`]) – A label for the gate to display in visualizations. Per default, the label is set to `exp(-it <operators>)` where `<operators>` is the sum of the Paulis. Note that the label does not include any coefficients of the Paulis. See the class docstring for an example.
*   **synthesis** (`Optional`\[[`EvolutionSynthesis`](qiskit.synthesis.EvolutionSynthesis "qiskit.synthesis.evolution.evolution_synthesis.EvolutionSynthesis")]) – A synthesis strategy. If None, the default synthesis is the Lie-Trotter product formula with a single repetition.

## Methods Defined Here

### validate\_parameter

<span id="qiskit.circuit.library.PauliEvolutionGate.validate_parameter" />

`PauliEvolutionGate.validate_parameter(parameter)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/circuit/library/pauli_evolution.py "view source code")

Gate parameters should be int, float, or ParameterExpression

**Return type**

`Union`\[`float`, [`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")]

## Attributes

<span id="qiskit.circuit.library.PauliEvolutionGate.condition_bits" />

### condition\_bits

Get Clbits in condition.

**Return type**

`List`\[[`Clbit`](qiskit.circuit.Clbit "qiskit.circuit.classicalregister.Clbit")]

<span id="qiskit.circuit.library.PauliEvolutionGate.decompositions" />

### decompositions

Get the decompositions of the instruction from the SessionEquivalenceLibrary.

<span id="qiskit.circuit.library.PauliEvolutionGate.definition" />

### definition

Return definition in terms of other basic gates.

<span id="qiskit.circuit.library.PauliEvolutionGate.duration" />

### duration

Get the duration.

<span id="qiskit.circuit.library.PauliEvolutionGate.label" />

### label

Return instruction label

**Return type**

`str`

<span id="qiskit.circuit.library.PauliEvolutionGate.name" />

### name

Return the name.

<span id="qiskit.circuit.library.PauliEvolutionGate.num_clbits" />

### num\_clbits

Return the number of clbits.

<span id="qiskit.circuit.library.PauliEvolutionGate.num_qubits" />

### num\_qubits

Return the number of qubits.

<span id="qiskit.circuit.library.PauliEvolutionGate.params" />

### params

return instruction params.

<span id="qiskit.circuit.library.PauliEvolutionGate.time" />

### time

Return the evolution time as stored in the gate parameters.

**Return type**

`Union`\[`float`, [`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")]

**Returns**

The evolution time.

<span id="qiskit.circuit.library.PauliEvolutionGate.unit" />

### unit

Get the time unit of duration.

