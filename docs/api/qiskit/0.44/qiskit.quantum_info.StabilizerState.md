---
title: StabilizerState
description: API reference for qiskit.quantum_info.StabilizerState
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.quantum_info.StabilizerState
---

# StabilizerState

<span id="qiskit.quantum_info.StabilizerState" />

`qiskit.quantum_info.StabilizerState(data, validate=True)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.25/qiskit/quantum_info/states/stabilizerstate.py "view source code")

Bases: `QuantumState`

StabilizerState class. Stabilizer simulator using the convention from reference \[1]. Based on the internal class [`Clifford`](qiskit.quantum_info.Clifford "qiskit.quantum_info.Clifford").

```python
from qiskit import QuantumCircuit
from qiskit.quantum_info import StabilizerState, Pauli

# Bell state generation circuit
qc = QuantumCircuit(2)
qc.h(0)
qc.cx(0, 1)
stab = StabilizerState(qc)

# Print the StabilizerState
print(stab)

# Calculate the StabilizerState measurement probabilities dictionary
print (stab.probabilities_dict())

# Calculate expectation value of the StabilizerState
print (stab.expectation_value(Pauli('ZZ')))
```

```python
StabilizerState(StabilizerTable: ['+XX', '+ZZ'])
{'00': 0.5, '11': 0.5}
1
```

## References

1.  S. Aaronson, D. Gottesman, *Improved Simulation of Stabilizer Circuits*, Phys. Rev. A 70, 052328 (2004). [arXiv:quant-ph/0406196](https://arxiv.org/abs/quant-ph/0406196)

Initialize a StabilizerState object.

**Parameters**

*   **or** (*data (*[*StabilizerState*](#qiskit.quantum_info.StabilizerState "qiskit.quantum_info.StabilizerState")  *or*[*Clifford*](qiskit.quantum_info.Clifford "qiskit.quantum_info.Clifford")  *or*[*Pauli*](qiskit.quantum_info.Pauli "qiskit.quantum_info.Pauli")  *or*[*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – qiskit.circuit.Instruction): Data from which the stabilizer state can be constructed.
*   **validate** (*boolean*) – validate that the stabilizer state data is a valid Clifford.

## Attributes

<span id="qiskit.quantum_info.StabilizerState.clifford" />

### clifford

Return StabilizerState Clifford data

<span id="qiskit.quantum_info.StabilizerState.dim" />

### dim

Return total state dimension.

<span id="qiskit.quantum_info.StabilizerState.num_qubits" />

### num\_qubits

Return the number of qubits if a N-qubit state or None otherwise.

## Methods

### conjugate

<span id="qiskit.quantum_info.StabilizerState.conjugate" />

`conjugate()`

Return the conjugate of the operator.

### copy

<span id="qiskit.quantum_info.StabilizerState.copy" />

`copy()`

Make a copy of current operator.

### dims

<span id="qiskit.quantum_info.StabilizerState.dims" />

`dims(qargs=None)`

Return tuple of input dimension for specified subsystems.

### equiv

<span id="qiskit.quantum_info.StabilizerState.equiv" />

`equiv(other)`

Return True if the two generating sets generate the same stabilizer group.

**Parameters**

**other** ([*StabilizerState*](#qiskit.quantum_info.StabilizerState "qiskit.quantum_info.StabilizerState")) – another StabilizerState.

**Returns**

True if other has a generating set that generates the same StabilizerState.

**Return type**

[bool](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")

### evolve

<span id="qiskit.quantum_info.StabilizerState.evolve" />

`evolve(other, qargs=None)`

Evolve a stabilizer state by a Clifford operator.

**Parameters**

*   **other** ([*Clifford*](qiskit.quantum_info.Clifford "qiskit.quantum_info.Clifford")  *or*[*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")  *or*[*qiskit.circuit.Instruction*](qiskit.circuit.Instruction "qiskit.circuit.Instruction")) – The Clifford operator to evolve by.
*   **qargs** ([*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")) – a list of stabilizer subsystem positions to apply the operator on.

**Returns**

the output stabilizer state.

**Return type**

[StabilizerState](#qiskit.quantum_info.StabilizerState "qiskit.quantum_info.StabilizerState")

**Raises**

*   [**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if other is not a StabilizerState.
*   [**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if the operator dimension does not match the specified StabilizerState subsystem dimensions.

### expand

<span id="qiskit.quantum_info.StabilizerState.expand" />

`expand(other)`

Return the tensor product stabilizer state other ⊗ self.

**Parameters**

**other** ([*StabilizerState*](#qiskit.quantum_info.StabilizerState "qiskit.quantum_info.StabilizerState")) – a stabilizer state object.

**Returns**

the tensor product operator other ⊗ self.

**Return type**

[StabilizerState](#qiskit.quantum_info.StabilizerState "qiskit.quantum_info.StabilizerState")

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if other is not a StabilizerState.

### expectation\_value

<span id="qiskit.quantum_info.StabilizerState.expectation_value" />

`expectation_value(oper, qargs=None)`

Compute the expectation value of a Pauli operator.

**Parameters**

*   **oper** ([*Pauli*](qiskit.quantum_info.Pauli "qiskit.quantum_info.Pauli")) – a Pauli operator to evaluate expval.
*   **qargs** (*None or* [*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")) – subsystems to apply the operator on.

**Returns**

the expectation value (only 0 or 1 or -1 or i or -i).

**Return type**

[complex](https://docs.python.org/3/library/functions.html#complex "(in Python v3.12)")

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if oper is not a Pauli operator.

### is\_valid

<span id="qiskit.quantum_info.StabilizerState.is_valid" />

`is_valid(atol=None, rtol=None)`

Return True if a valid StabilizerState.

### measure

<span id="qiskit.quantum_info.StabilizerState.measure" />

`measure(qargs=None)`

Measure subsystems and return outcome and post-measure state.

Note that this function uses the QuantumStates internal random number generator for sampling the measurement outcome. The RNG seed can be set using the [`seed()`](#qiskit.quantum_info.StabilizerState.seed "qiskit.quantum_info.StabilizerState.seed") method.

**Parameters**

**qargs** ([*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)") *or None*) – subsystems to sample measurements for, if None sample measurement of all subsystems (Default: None).

**Returns**

**the pair `(outcome, state)` where `outcome` is the**

measurement outcome string label, and `state` is the collapsed post-measurement stabilizer state for the corresponding outcome.

**Return type**

[tuple](https://docs.python.org/3/library/stdtypes.html#tuple "(in Python v3.12)")

### probabilities

<span id="qiskit.quantum_info.StabilizerState.probabilities" />

`probabilities(qargs=None, decimals=None)`

Return the subsystem measurement probability vector.

Measurement probabilities are with respect to measurement in the computation (diagonal) basis.

**Parameters**

*   **qargs** (*None or* [*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")) – subsystems to return probabilities for, if None return for all subsystems (Default: None).
*   **decimals** (*None or* [*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – the number of decimal places to round values. If None no rounding is done (Default: None).

**Returns**

The Numpy vector array of probabilities.

**Return type**

np.array

### probabilities\_dict

<span id="qiskit.quantum_info.StabilizerState.probabilities_dict" />

`probabilities_dict(qargs=None, decimals=None)`

Return the subsystem measurement probability dictionary.

Measurement probabilities are with respect to measurement in the computation (diagonal) basis.

This dictionary representation uses a Ket-like notation where the dictionary keys are qudit strings for the subsystem basis vectors. If any subsystem has a dimension greater than 10 comma delimiters are inserted between integers so that subsystems can be distinguished.

**Parameters**

*   **qargs** (*None or* [*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")) – subsystems to return probabilities for, if None return for all subsystems (Default: None).
*   **decimals** (*None or* [*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – the number of decimal places to round values. If None no rounding is done (Default: None).

**Returns**

The measurement probabilities in dict (ket) form.

**Return type**

[dict](https://docs.python.org/3/library/stdtypes.html#dict "(in Python v3.12)")

### purity

<span id="qiskit.quantum_info.StabilizerState.purity" />

`purity()`

Return the purity of the quantum state, which equals to 1, since it is always a pure state.

**Returns**

the purity (should equal 1).

**Return type**

[float](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if input is not a StabilizerState.

### reset

<span id="qiskit.quantum_info.StabilizerState.reset" />

`reset(qargs=None)`

Reset state or subsystems to the 0-state.

**Parameters**

**qargs** ([*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)") *or None*) – subsystems to reset, if None all subsystems will be reset to their 0-state (Default: None).

**Returns**

the reset state.

**Return type**

[StabilizerState](#qiskit.quantum_info.StabilizerState "qiskit.quantum_info.StabilizerState")

**Additional Information:**

If all subsystems are reset this will return the ground state on all subsystems. If only some subsystems are reset this function will perform a measurement on those subsystems and evolve the subsystems so that the collapsed post-measurement states are rotated to the 0-state. The RNG seed for this sampling can be set using the [`seed()`](#qiskit.quantum_info.StabilizerState.seed "qiskit.quantum_info.StabilizerState.seed") method.

### sample\_counts

<span id="qiskit.quantum_info.StabilizerState.sample_counts" />

`sample_counts(shots, qargs=None)`

Sample a dict of qubit measurement outcomes in the computational basis.

**Parameters**

*   **shots** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – number of samples to generate.
*   **qargs** (*None or* [*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")) – subsystems to sample measurements for, if None sample measurement of all subsystems (Default: None).

**Returns**

sampled counts dictionary.

**Return type**

[Counts](qiskit.result.Counts "qiskit.result.Counts")

Additional Information:

> This function *samples* measurement outcomes using the measure [`probabilities()`](#qiskit.quantum_info.StabilizerState.probabilities "qiskit.quantum_info.StabilizerState.probabilities") for the current state and qargs. It does not actually implement the measurement so the current state is not modified.
>
> The seed for random number generator used for sampling can be set to a fixed value by using the stats [`seed()`](#qiskit.quantum_info.StabilizerState.seed "qiskit.quantum_info.StabilizerState.seed") method.

### sample\_memory

<span id="qiskit.quantum_info.StabilizerState.sample_memory" />

`sample_memory(shots, qargs=None)`

Sample a list of qubit measurement outcomes in the computational basis.

**Parameters**

*   **shots** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – number of samples to generate.
*   **qargs** (*None or* [*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")) – subsystems to sample measurements for, if None sample measurement of all subsystems (Default: None).

**Returns**

list of sampled counts if the order sampled.

**Return type**

np.array

Additional Information:

> This function implements the measurement [`measure()`](#qiskit.quantum_info.StabilizerState.measure "qiskit.quantum_info.StabilizerState.measure") method.
>
> The seed for random number generator used for sampling can be set to a fixed value by using the stats [`seed()`](#qiskit.quantum_info.StabilizerState.seed "qiskit.quantum_info.StabilizerState.seed") method.

### seed

<span id="qiskit.quantum_info.StabilizerState.seed" />

`seed(value=None)`

Set the seed for the quantum state RNG.

### tensor

<span id="qiskit.quantum_info.StabilizerState.tensor" />

`tensor(other)`

Return the tensor product stabilizer state self ⊗ other.

**Parameters**

**other** ([*StabilizerState*](#qiskit.quantum_info.StabilizerState "qiskit.quantum_info.StabilizerState")) – a stabilizer state object.

**Returns**

the tensor product operator self ⊗ other.

**Return type**

[StabilizerState](#qiskit.quantum_info.StabilizerState "qiskit.quantum_info.StabilizerState")

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if other is not a StabilizerState.

### to\_operator

<span id="qiskit.quantum_info.StabilizerState.to_operator" />

`to_operator()`

Convert state to matrix operator class

**Return type**

[*Operator*](qiskit.quantum_info.Operator "qiskit.quantum_info.operators.operator.Operator")

### trace

<span id="qiskit.quantum_info.StabilizerState.trace" />

`trace()`

Return the trace of the stabilizer state as a density matrix, which equals to 1, since it is always a pure state.

**Returns**

the trace (should equal 1).

**Return type**

[float](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if input is not a StabilizerState.

