---
title: WeightedPauliOperator
description: API reference for qiskit.aqua.operators.legacy.WeightedPauliOperator
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.operators.legacy.WeightedPauliOperator
---

# WeightedPauliOperator

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator" />

`WeightedPauliOperator(paulis, basis=None, z2_symmetries=None, atol=1e-12, name=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

Bases: `qiskit.aqua.operators.legacy.base_operator.LegacyBaseOperator`

Weighted Pauli Operator

**Parameters**

*   **paulis** (`List`\[`List`\[`Union`\[`complex`, `Pauli`]]]) – the list of weighted Paulis, where a weighted pauli is composed of a length-2 list and the first item is the weight and the second item is the Pauli object.
*   **basis** (`Optional`\[`List`\[`Tuple`\[`object`, `List`\[`int`]]]]) – the grouping basis, each element is a tuple composed of the basis and the indices to paulis which belong to that group. e.g., if tpb basis is used, the object will be a pauli. By default, the group is equal to non-grouping, each pauli is its own basis.
*   **z2\_symmetries** (`Optional`\[`Z2Symmetries`]) – recording the z2 symmetries info
*   **atol** (`float`) – the threshold used in truncating paulis
*   **name** (`Optional`\[`str`]) – the name of operator.

## Methods

### add

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.add" />

`WeightedPauliOperator.add(other, copy=False)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

Perform self + other.

**Parameters**

*   **other** ([*WeightedPauliOperator*](qiskit.aqua.operators.legacy.WeightedPauliOperator "qiskit.aqua.operators.legacy.WeightedPauliOperator")) – to-be-combined operator
*   **copy** (*bool*) – working on a copy or self, if False, the results are written back to self.

**Returns**

operator

**Return type**

[WeightedPauliOperator](qiskit.aqua.operators.legacy.WeightedPauliOperator "qiskit.aqua.operators.legacy.WeightedPauliOperator")

### anticommute\_with

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.anticommute_with" />

`WeightedPauliOperator.anticommute_with(other)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

Anti commutes with

### chop

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.chop" />

`WeightedPauliOperator.chop(threshold=None, copy=False)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

Eliminate the real and imagine part of weight in each pauli by threshold. If pauli’s weight is less then threshold in both real and imaginary parts, the pauli is removed.

<Admonition title="Note" type="note">
  If weight is real-only, the imaginary part is skipped.
</Admonition>

**Parameters**

*   **threshold** (*float*) – the threshold is used to remove the paulis
*   **copy** (*bool*) – chop on a copy or self

**Returns**

**if copy is True, the original operator is unchanged; otherwise,**

the operator is mutated.

**Return type**

[WeightedPauliOperator](qiskit.aqua.operators.legacy.WeightedPauliOperator "qiskit.aqua.operators.legacy.WeightedPauliOperator")

### commute\_with

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.commute_with" />

`WeightedPauliOperator.commute_with(other)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

Commutes with

### construct\_evaluation\_circuit

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.construct_evaluation_circuit" />

`WeightedPauliOperator.construct_evaluation_circuit(wave_function, statevector_mode, qr=None, cr=None, use_simulator_snapshot_mode=False, circuit_name_prefix='')`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

Construct the circuits for evaluation, which calculating the expectation \<psi|H|psi>.

At statevector mode: to simplify the computation, we do not build the whole circuit for \<psi|H|psi>, instead of that we construct an individual circuit \<psi|, and a bundle circuit for H|psi>

**Parameters**

*   **wave\_function** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – the quantum circuit.
*   **statevector\_mode** (*bool*) – indicate which type of simulator are going to use.
*   **qr** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*, optional*) – the quantum register associated with the input\_circuit
*   **cr** ([*ClassicalRegister*](qiskit.circuit.ClassicalRegister "qiskit.circuit.ClassicalRegister")*, optional*) – the classical register associated with the input\_circuit
*   **use\_simulator\_snapshot\_mode** (*bool, optional*) – if aer\_provider is used, we can do faster evaluation for pauli mode on statevector simulation
*   **circuit\_name\_prefix** (*str, optional*) – a prefix of circuit name

**Returns**

**a list of quantum circuits and each circuit with a unique name:**

circuit\_name\_prefix + Pauli string

**Return type**

list\[[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")]

**Raises**

*   [**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – if Operator is empty
*   [**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – if quantum register is not provided explicitly and cannot find quantum register with q as the name
*   [**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – The provided qr is not in the wave\_function

### copy

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.copy" />

`WeightedPauliOperator.copy()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

Get a copy of self

### evaluate\_with\_result

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.evaluate_with_result" />

`WeightedPauliOperator.evaluate_with_result(result, statevector_mode, use_simulator_snapshot_mode=False, circuit_name_prefix='')`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

This method can be only used with the circuits generated by the [`construct_evaluation_circuit()`](qiskit.aqua.operators.legacy.WeightedPauliOperator#construct_evaluation_circuit "qiskit.aqua.operators.legacy.WeightedPauliOperator.construct_evaluation_circuit") method with the same circuit\_name\_prefix name since the circuit names are tied to some meanings.

Calculate the evaluated value with the measurement results.

**Parameters**

*   **result** (*qiskit.Result*) – the result from the backend.
*   **statevector\_mode** (*bool*) – indicate which type of simulator are used.
*   **use\_simulator\_snapshot\_mode** (*bool*) – if aer\_provider is used, we can do faster evaluation for pauli mode on statevector simulation
*   **circuit\_name\_prefix** (*str*) – a prefix of circuit name

**Returns**

the mean value float: the standard deviation

**Return type**

float

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – if Operator is empty

### evaluate\_with\_statevector

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.evaluate_with_statevector" />

`WeightedPauliOperator.evaluate_with_statevector(quantum_state)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

**Parameters**

**quantum\_state** (*numpy.ndarray*) – a quantum state.

**Returns**

the mean value float: the standard deviation

**Return type**

float

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – if Operator is empty

### evaluation\_instruction

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.evaluation_instruction" />

`WeightedPauliOperator.evaluation_instruction(statevector_mode, use_simulator_snapshot_mode=False)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

**Parameters**

*   **statevector\_mode** (*bool*) – will it be run on statevector simulator or not
*   **use\_simulator\_snapshot\_mode** (*bool*) – will it use qiskit aer simulator operator mode

**Returns**

Pauli-instruction pair.

**Return type**

dict

**Raises**

*   [**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – if Operator is empty
*   [**MissingOptionalLibraryError**](qiskit.aqua.MissingOptionalLibraryError "qiskit.aqua.MissingOptionalLibraryError") – qiskit-aer not installed

### evolve

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.evolve" />

`WeightedPauliOperator.evolve(state_in=None, evo_time=0, num_time_slices=1, quantum_registers=None, expansion_mode='trotter', expansion_order=1)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

Carry out the eoh evolution for the operator under supplied specifications.

**Parameters**

*   **state\_in** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – a circuit describes the input state
*   **evo\_time** (*Union(complex, float,* [*Parameter*](qiskit.circuit.Parameter "qiskit.circuit.Parameter")*,* [*ParameterExpression*](qiskit.circuit.ParameterExpression "qiskit.circuit.ParameterExpression")*)*) – The evolution time
*   **num\_time\_slices** (*int*) – The number of time slices for the expansion
*   **quantum\_registers** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")) – The QuantumRegister to build the QuantumCircuit off of
*   **expansion\_mode** (*str*) – The mode under which the expansion is to be done. Currently support ‘trotter’, which follows the expansion as discussed in [http://science.sciencemag.org/content/273/5278/1073](http://science.sciencemag.org/content/273/5278/1073), and ‘suzuki’, which corresponds to the discussion in [https://arxiv.org/pdf/quant-ph/0508139.pdf](https://arxiv.org/pdf/quant-ph/0508139.pdf)
*   **expansion\_order** (*int*) – The order for suzuki expansion

**Returns**

The constructed circuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

*   [**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – quantum\_registers must be in the provided state\_in circuit
*   [**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – if operator is empty

### evolve\_instruction

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.evolve_instruction" />

`WeightedPauliOperator.evolve_instruction(evo_time=0, num_time_slices=1, expansion_mode='trotter', expansion_order=1)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

Carry out the eoh evolution for the operator under supplied specifications.

**Parameters**

*   **evo\_time** (*Union(complex, float,* [*Parameter*](qiskit.circuit.Parameter "qiskit.circuit.Parameter")*,* [*ParameterExpression*](qiskit.circuit.ParameterExpression "qiskit.circuit.ParameterExpression")*)*) – The evolution time
*   **num\_time\_slices** (*int*) – The number of time slices for the expansion
*   **expansion\_mode** (*str*) – The mode under which the expansion is to be done. Currently support ‘trotter’, which follows the expansion as discussed in [http://science.sciencemag.org/content/273/5278/1073](http://science.sciencemag.org/content/273/5278/1073), and ‘suzuki’, which corresponds to the discussion in [https://arxiv.org/pdf/quant-ph/0508139.pdf](https://arxiv.org/pdf/quant-ph/0508139.pdf)
*   **expansion\_order** (*int*) – The order for suzuki expansion

**Returns**

The constructed QuantumCircuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

*   **ValueError** – Number of time slices should be a non-negative integer
*   **NotImplementedError** – expansion mode not supported
*   [**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – if operator is empty

### from\_dict

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.from_dict" />

`classmethod WeightedPauliOperator.from_dict(dictionary, before_04=False)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

Load paulis from a dictionary to construct an Operator. The dictionary must comprise the key ‘paulis’ having a value which is an array of pauli dicts. Each dict in this array must be represented by label and coeff (real and imag) such as in the following example:

```python
{'paulis':
    [
        {'label': 'IIII',
         'coeff': {'real': -0.33562957575267038, 'imag': 0.0}},
        {'label': 'ZIII',
         'coeff': {'real': 0.28220597164664896, 'imag': 0.0}},
         ...
    ]
 }
```

**Parameters**

*   **dictionary** (*dict*) – dictionary, which contains a list of Paulis and coefficients.
*   **before\_04** (*bool*) – support the format before Aqua 0.4.

**Returns**

the operator created from the input dictionary.

**Return type**

[WeightedPauliOperator](qiskit.aqua.operators.legacy.WeightedPauliOperator "qiskit.aqua.operators.legacy.WeightedPauliOperator")

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – Invalid dictionary

### from\_file

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.from_file" />

`classmethod WeightedPauliOperator.from_file(file_name, before_04=False)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

Load paulis in a file to construct an Operator.

**Parameters**

*   **file\_name** (*str*) – path to the file, which contains a list of Paulis and coefficients.
*   **before\_04** (*bool*) – support the format before Aqua 0.4.

**Returns**

the loaded operator.

**Return type**

[WeightedPauliOperator](qiskit.aqua.operators.legacy.WeightedPauliOperator "qiskit.aqua.operators.legacy.WeightedPauliOperator")

### from\_list

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.from_list" />

`classmethod WeightedPauliOperator.from_list(paulis, weights=None, name=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

Create a WeightedPauliOperator via a pair of list.

**Parameters**

*   **paulis** (*list\[*[*Pauli*](qiskit.quantum_info.Pauli "qiskit.quantum_info.Pauli")*]*) – the list of Paulis
*   **weights** (*list\[complex], optional*) – the list of weights, if it is None, all weights are 1.
*   **name** (*str, optional*) – name of the operator.

**Returns**

operator

**Return type**

[WeightedPauliOperator](qiskit.aqua.operators.legacy.WeightedPauliOperator "qiskit.aqua.operators.legacy.WeightedPauliOperator")

**Raises**

**ValueError** – The length of weights and paulis must be the same

### is\_empty

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.is_empty" />

`WeightedPauliOperator.is_empty()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

Check Operator is empty or not.

**Returns**

True if empty, False otherwise

**Return type**

bool

### multiply

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.multiply" />

`WeightedPauliOperator.multiply(other)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

Perform self \* other, and the phases are tracked.

**Parameters**

**other** ([*WeightedPauliOperator*](qiskit.aqua.operators.legacy.WeightedPauliOperator "qiskit.aqua.operators.legacy.WeightedPauliOperator")) – an operator

**Returns**

the multiplied operator

**Return type**

[WeightedPauliOperator](qiskit.aqua.operators.legacy.WeightedPauliOperator "qiskit.aqua.operators.legacy.WeightedPauliOperator")

### print\_details

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.print_details" />

`WeightedPauliOperator.print_details()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

Print out the operator in details.

**Returns**

a formatted string describes the operator.

**Return type**

str

### reorder\_paulis

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.reorder_paulis" />

`WeightedPauliOperator.reorder_paulis()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

Reorder the paulis based on the basis and return the reordered paulis.

**Return type**

`List`\[`List`\[`Union`\[`complex`, `Pauli`]]]

**Returns**

the ordered paulis based on the basis.

### rounding

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.rounding" />

`WeightedPauliOperator.rounding(decimals, copy=False)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

Rounding the weight.

**Parameters**

*   **decimals** (*int*) – rounding the weight to the decimals.
*   **copy** (*bool*) – chop on a copy or self

**Returns**

operator

**Return type**

[WeightedPauliOperator](qiskit.aqua.operators.legacy.WeightedPauliOperator "qiskit.aqua.operators.legacy.WeightedPauliOperator")

### simplify

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.simplify" />

`WeightedPauliOperator.simplify(copy=False)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

Merge the paulis whose bases are identical and the pauli with zero coefficient would be removed.

<Admonition title="Note" type="note">
  This behavior of this method is slightly changed, it will remove the paulis whose weights are zero.
</Admonition>

**Parameters**

**copy** (*bool*) – simplify on a copy or self

**Returns**

the simplified operator

**Return type**

[WeightedPauliOperator](qiskit.aqua.operators.legacy.WeightedPauliOperator "qiskit.aqua.operators.legacy.WeightedPauliOperator")

### sub

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.sub" />

`WeightedPauliOperator.sub(other, copy=False)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

Perform self - other.

**Parameters**

*   **other** ([*WeightedPauliOperator*](qiskit.aqua.operators.legacy.WeightedPauliOperator "qiskit.aqua.operators.legacy.WeightedPauliOperator")) – to-be-combined operator
*   **copy** (*bool*) – working on a copy or self, if False, the results are written back to self.

**Returns**

operator

**Return type**

[WeightedPauliOperator](qiskit.aqua.operators.legacy.WeightedPauliOperator "qiskit.aqua.operators.legacy.WeightedPauliOperator")

### to\_dict

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.to_dict" />

`WeightedPauliOperator.to_dict()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

Save operator to a dict in pauli representation.

**Returns**

a dictionary contains an operator with pauli representation.

**Return type**

dict

### to\_file

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.to_file" />

`WeightedPauliOperator.to_file(file_name)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

Save operator to a file in pauli representation.

**Parameters**

**file\_name** (*str*) – path to the file

### to\_opflow

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.to_opflow" />

`WeightedPauliOperator.to_opflow(reverse_endianness=False)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

to op flow

## Attributes

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.atol" />

### atol

get atol

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.basis" />

### basis

returns basis

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.name" />

### name

returns name

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.num_qubits" />

### num\_qubits

Number of qubits required for the operator.

**Returns**

number of qubits

**Return type**

int

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.paulis" />

### paulis

get paulis

<span id="qiskit.aqua.operators.legacy.WeightedPauliOperator.z2_symmetries" />

### z2\_symmetries

returns z2 symmetries

