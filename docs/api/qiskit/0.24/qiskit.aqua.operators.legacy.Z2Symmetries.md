---
title: Z2Symmetries
description: API reference for qiskit.aqua.operators.legacy.Z2Symmetries
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.operators.legacy.Z2Symmetries
---

<span id="qiskit-aqua-operators-legacy-z2symmetries" />

# qiskit.aqua.operators.legacy.Z2Symmetries

<span id="qiskit.aqua.operators.legacy.Z2Symmetries" />

`Z2Symmetries(symmetries, sq_paulis, sq_list, tapering_values=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.8/qiskit/aqua/operators/legacy/weighted_pauli_operator.py "view source code")

Z2 Symmetries

**Parameters**

*   **symmetries** (*list\[*[*Pauli*](qiskit.quantum_info.Pauli "qiskit.quantum_info.Pauli")*]*) – the list of Pauli objects representing the Z\_2 symmetries
*   **sq\_paulis** (*list\[*[*Pauli*](qiskit.quantum_info.Pauli "qiskit.quantum_info.Pauli")*]*) – the list of single - qubit Pauli objects to construct the Clifford operators
*   **sq\_list** (*list\[int]*) – the list of support of the single-qubit Pauli objects used to build the Clifford operators
*   **tapering\_values** (*list\[int], optional*) – values determines the sector.

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – Invalid paulis

### \_\_init\_\_

<span id="qiskit.aqua.operators.legacy.Z2Symmetries.__init__" />

`__init__(symmetries, sq_paulis, sq_list, tapering_values=None)`

**Parameters**

*   **symmetries** (*list\[*[*Pauli*](qiskit.quantum_info.Pauli "qiskit.quantum_info.Pauli")*]*) – the list of Pauli objects representing the Z\_2 symmetries
*   **sq\_paulis** (*list\[*[*Pauli*](qiskit.quantum_info.Pauli "qiskit.quantum_info.Pauli")*]*) – the list of single - qubit Pauli objects to construct the Clifford operators
*   **sq\_list** (*list\[int]*) – the list of support of the single-qubit Pauli objects used to build the Clifford operators
*   **tapering\_values** (*list\[int], optional*) – values determines the sector.

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – Invalid paulis

## Methods

|                                                                                                                                                                                   |                                                                                                               |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.aqua.operators.legacy.Z2Symmetries.__init__ "qiskit.aqua.operators.legacy.Z2Symmetries.__init__")(symmetries, sq\_paulis, sq\_list\[, …])                    | **param symmetries**the list of Pauli objects representing the Z\_2 symmetries                                |
| [`consistent_tapering`](#qiskit.aqua.operators.legacy.Z2Symmetries.consistent_tapering "qiskit.aqua.operators.legacy.Z2Symmetries.consistent_tapering")(operator)                 | Tapering the operator with the same manner of how this tapered operator is created.                           |
| [`copy`](#qiskit.aqua.operators.legacy.Z2Symmetries.copy "qiskit.aqua.operators.legacy.Z2Symmetries.copy")()                                                                      | Get a copy of self.                                                                                           |
| [`find_Z2_symmetries`](#qiskit.aqua.operators.legacy.Z2Symmetries.find_Z2_symmetries "qiskit.aqua.operators.legacy.Z2Symmetries.find_Z2_symmetries")(operator)                    | Finds Z2 Pauli-type symmetries of an Operator.                                                                |
| [`is_empty`](#qiskit.aqua.operators.legacy.Z2Symmetries.is_empty "qiskit.aqua.operators.legacy.Z2Symmetries.is_empty")()                                                          | Check the z2\_symmetries is empty or not.                                                                     |
| [`taper`](#qiskit.aqua.operators.legacy.Z2Symmetries.taper "qiskit.aqua.operators.legacy.Z2Symmetries.taper")(operator\[, tapering\_values])                                      | Taper an operator based on the z2\_symmetries info and sector defined by tapering\_values.                    |
| [`two_qubit_reduction`](#qiskit.aqua.operators.legacy.Z2Symmetries.two_qubit_reduction "qiskit.aqua.operators.legacy.Z2Symmetries.two_qubit_reduction")(operator, num\_particles) | Eliminates the central and last qubit in a list of Pauli that has diagonal operators (Z,I) at those positions |

## Attributes

|                                                                                                                                             |                                                                       |
| ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| [`cliffords`](#qiskit.aqua.operators.legacy.Z2Symmetries.cliffords "qiskit.aqua.operators.legacy.Z2Symmetries.cliffords")                   | Get clifford operators, build based on symmetries and single-qubit X. |
| [`sq_list`](#qiskit.aqua.operators.legacy.Z2Symmetries.sq_list "qiskit.aqua.operators.legacy.Z2Symmetries.sq_list")                         | returns sq list                                                       |
| [`sq_paulis`](#qiskit.aqua.operators.legacy.Z2Symmetries.sq_paulis "qiskit.aqua.operators.legacy.Z2Symmetries.sq_paulis")                   | returns sq paulis                                                     |
| [`symmetries`](#qiskit.aqua.operators.legacy.Z2Symmetries.symmetries "qiskit.aqua.operators.legacy.Z2Symmetries.symmetries")                | return symmetries                                                     |
| [`tapering_values`](#qiskit.aqua.operators.legacy.Z2Symmetries.tapering_values "qiskit.aqua.operators.legacy.Z2Symmetries.tapering_values") | returns tapering values                                               |

### cliffords

<span id="qiskit.aqua.operators.legacy.Z2Symmetries.cliffords" />

`property cliffords`

Get clifford operators, build based on symmetries and single-qubit X.

**Returns**

a list of unitaries used to diagonalize the Hamiltonian.

**Return type**

list\[[WeightedPauliOperator](qiskit.aqua.operators.legacy.WeightedPauliOperator "qiskit.aqua.operators.legacy.WeightedPauliOperator")]

### consistent\_tapering

<span id="qiskit.aqua.operators.legacy.Z2Symmetries.consistent_tapering" />

`consistent_tapering(operator)`

Tapering the operator with the same manner of how this tapered operator is created. i.e., using the same Cliffords and tapering values.

**Parameters**

**operator** ([*WeightedPauliOperator*](qiskit.aqua.operators.legacy.WeightedPauliOperator "qiskit.aqua.operators.legacy.WeightedPauliOperator")) – the to-be-tapered operator

**Returns**

the tapered operator

**Return type**

TaperedWeightedPauliOperator

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – The given operator does not commute with the symmetry

### copy

<span id="qiskit.aqua.operators.legacy.Z2Symmetries.copy" />

`copy()`

Get a copy of self.

**Return type**

`Z2Symmetries`

**Returns**

copy

### find\_Z2\_symmetries

<span id="qiskit.aqua.operators.legacy.Z2Symmetries.find_Z2_symmetries" />

`classmethod find_Z2_symmetries(operator)`

Finds Z2 Pauli-type symmetries of an Operator.

**Return type**

`Z2Symmetries`

**Returns**

a z2\_symmetries object contains symmetries, single-qubit X, single-qubit list.

### is\_empty

<span id="qiskit.aqua.operators.legacy.Z2Symmetries.is_empty" />

`is_empty()`

Check the z2\_symmetries is empty or not.

**Returns**

empty

**Return type**

bool

### sq\_list

<span id="qiskit.aqua.operators.legacy.Z2Symmetries.sq_list" />

`property sq_list`

returns sq list

### sq\_paulis

<span id="qiskit.aqua.operators.legacy.Z2Symmetries.sq_paulis" />

`property sq_paulis`

returns sq paulis

### symmetries

<span id="qiskit.aqua.operators.legacy.Z2Symmetries.symmetries" />

`property symmetries`

return symmetries

### taper

<span id="qiskit.aqua.operators.legacy.Z2Symmetries.taper" />

`taper(operator, tapering_values=None)`

Taper an operator based on the z2\_symmetries info and sector defined by tapering\_values. The tapering\_values will be stored into the resulted operator for a record.

**Parameters**

*   **operator** ([*WeightedPauliOperator*](qiskit.aqua.operators.legacy.WeightedPauliOperator "qiskit.aqua.operators.legacy.WeightedPauliOperator")) – the to-be-tapered operator.
*   **tapering\_values** (*list\[int], optional*) – if None, returns operators at each sector; otherwise, returns the operator located in that sector.

**Returns**

**If**

tapering\_values is None: \[:class\`WeightedPauliOperator\`]; otherwise, [`WeightedPauliOperator`](qiskit.aqua.operators.legacy.WeightedPauliOperator "qiskit.aqua.operators.legacy.WeightedPauliOperator")

**Return type**

list\[[WeightedPauliOperator](qiskit.aqua.operators.legacy.WeightedPauliOperator "qiskit.aqua.operators.legacy.WeightedPauliOperator")] or [WeightedPauliOperator](qiskit.aqua.operators.legacy.WeightedPauliOperator "qiskit.aqua.operators.legacy.WeightedPauliOperator")

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – Z2 symmetries, single qubit pauli and single qubit list cannot be empty

### tapering\_values

<span id="qiskit.aqua.operators.legacy.Z2Symmetries.tapering_values" />

`property tapering_values`

returns tapering values

### two\_qubit\_reduction

<span id="qiskit.aqua.operators.legacy.Z2Symmetries.two_qubit_reduction" />

`static two_qubit_reduction(operator, num_particles)`

Eliminates the central and last qubit in a list of Pauli that has diagonal operators (Z,I) at those positions

Chemistry specific method: It can be used to taper two qubits in parity and binary-tree mapped fermionic Hamiltonians when the spin orbitals are ordered in two spin sectors, (block spin order) according to the number of particles in the system.

**Parameters**

*   **operator** ([*WeightedPauliOperator*](qiskit.aqua.operators.legacy.WeightedPauliOperator "qiskit.aqua.operators.legacy.WeightedPauliOperator")) – the operator
*   **num\_particles** (*Union(list, int)*) – number of particles, if it is a list, the first number is alpha and the second number if beta.

**Returns**

a new operator whose qubit number is reduced by 2.

**Return type**

[WeightedPauliOperator](qiskit.aqua.operators.legacy.WeightedPauliOperator "qiskit.aqua.operators.legacy.WeightedPauliOperator")

