---
title: UncertaintyProblem
description: API reference for qiskit.aqua.components.uncertainty_problems.UncertaintyProblem
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.components.uncertainty_problems.UncertaintyProblem
---

# qiskit.aqua.components.uncertainty\_problems.UncertaintyProblem

<span id="qiskit.aqua.components.uncertainty_problems.UncertaintyProblem" />

`UncertaintyProblem(num_qubits)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/components/uncertainty_problems/uncertainty_problem.py "view source code")

The abstract Uncertainty Problem component.

### \_\_init\_\_

<span id="qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.__init__" />

`__init__(num_qubits)`

Initialize self. See help(type(self)) for accurate signature.

## Methods

|                                                                                                                                                                                                                                                    |                                                                       |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| [`__init__`](#qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.__init__ "qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.__init__")(num\_qubits)                                                                      | Initialize self.                                                      |
| [`build`](#qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.build "qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.build")(qc, q\[, q\_ancillas, params])                                                             | Adds corresponding sub-circuit to given circuit                       |
| [`build_controlled`](#qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.build_controlled "qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.build_controlled")(qc, q, q\_control\[, …])                                  | Adds corresponding controlled sub-circuit to given circuit            |
| [`build_controlled_inverse`](#qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.build_controlled_inverse "qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.build_controlled_inverse")(qc, q, q\_control\[, …])          | Adds controlled inverse of corresponding sub-circuit to given circuit |
| [`build_controlled_inverse_power`](#qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.build_controlled_inverse_power "qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.build_controlled_inverse_power")(qc, q, …\[, …]) | Adds controlled, inverse, power of corresponding circuit.             |
| [`build_controlled_power`](#qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.build_controlled_power "qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.build_controlled_power")(qc, q, q\_control, power)               | Adds controlled power of corresponding circuit.                       |
| [`build_inverse`](#qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.build_inverse "qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.build_inverse")(qc, q\[, q\_ancillas])                                             | Adds inverse of corresponding sub-circuit to given circuit            |
| [`build_inverse_power`](#qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.build_inverse_power "qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.build_inverse_power")(qc, q, power\[, q\_ancillas])                    | Adds inverse power of corresponding circuit.                          |
| [`build_power`](#qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.build_power "qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.build_power")(qc, q, power\[, q\_ancillas])                                            | Adds power of corresponding circuit.                                  |
| [`get_num_qubits`](#qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.get_num_qubits "qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.get_num_qubits")()                                                               | returns number of qubits                                              |
| [`get_num_qubits_controlled`](#qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.get_num_qubits_controlled "qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.get_num_qubits_controlled")()                              | returns number of qubits controlled                                   |
| [`required_ancillas`](#qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.required_ancillas "qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.required_ancillas")()                                                      | returns required ancillas                                             |
| [`required_ancillas_controlled`](#qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.required_ancillas_controlled "qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.required_ancillas_controlled")()                     | returns required ancillas controlled                                  |
| [`value_to_estimation`](#qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.value_to_estimation "qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.value_to_estimation")(value)                                           | value to estimate                                                     |

## Attributes

|                                                                                                                                                                                             |                                     |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------- |
| [`num_target_qubits`](#qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.num_target_qubits "qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.num_target_qubits") | Returns the number of target qubits |

### build

<span id="qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.build" />

`abstract build(qc, q, q_ancillas=None, params=None)`

Adds corresponding sub-circuit to given circuit

**Parameters**

*   **qc** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – quantum circuit
*   **q** (*list*) – list of qubits (has to be same length as self.\_num\_qubits)
*   **q\_ancillas** (*list*) – list of ancilla qubits (or None if none needed)
*   **params** (*list*) – parameters for circuit

### build\_controlled

<span id="qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.build_controlled" />

`build_controlled(qc, q, q_control, q_ancillas=None, use_basis_gates=True)`

Adds corresponding controlled sub-circuit to given circuit

**Parameters**

*   **qc** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – quantum circuit
*   **q** (*list*) – list of qubits (has to be same length as self.\_num\_qubits)
*   **q\_control** ([*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")) – control qubit
*   **q\_ancillas** (*list*) – list of ancilla qubits (or None if none needed)
*   **use\_basis\_gates** (*bool*) – use basis gates for expansion of controlled circuit

### build\_controlled\_inverse

<span id="qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.build_controlled_inverse" />

`build_controlled_inverse(qc, q, q_control, q_ancillas=None, use_basis_gates=True)`

Adds controlled inverse of corresponding sub-circuit to given circuit

**Parameters**

*   **qc** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – quantum circuit
*   **q** (*list*) – list of qubits (has to be same length as self.\_num\_qubits)
*   **q\_control** ([*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")) – control qubit
*   **q\_ancillas** (*list*) – list of ancilla qubits (or None if none needed)
*   **use\_basis\_gates** (*bool*) – use basis gates for expansion of controlled circuit

### build\_controlled\_inverse\_power

<span id="qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.build_controlled_inverse_power" />

`build_controlled_inverse_power(qc, q, q_control, power, q_ancillas=None, use_basis_gates=True)`

Adds controlled, inverse, power of corresponding circuit. May be overridden if a more efficient implementation is possible

### build\_controlled\_power

<span id="qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.build_controlled_power" />

`build_controlled_power(qc, q, q_control, power, q_ancillas=None, use_basis_gates=True)`

Adds controlled power of corresponding circuit. May be overridden if a more efficient implementation is possible

### build\_inverse

<span id="qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.build_inverse" />

`build_inverse(qc, q, q_ancillas=None)`

Adds inverse of corresponding sub-circuit to given circuit

**Parameters**

*   **qc** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – quantum circuit
*   **q** (*list*) – list of qubits (has to be same length as self.\_num\_qubits)
*   **q\_ancillas** (*list*) – list of ancilla qubits (or None if none needed)

### build\_inverse\_power

<span id="qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.build_inverse_power" />

`build_inverse_power(qc, q, power, q_ancillas=None)`

Adds inverse power of corresponding circuit. May be overridden if a more efficient implementation is possible

### build\_power

<span id="qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.build_power" />

`build_power(qc, q, power, q_ancillas=None)`

Adds power of corresponding circuit. May be overridden if a more efficient implementation is possible

### get\_num\_qubits

<span id="qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.get_num_qubits" />

`get_num_qubits()`

returns number of qubits

### get\_num\_qubits\_controlled

<span id="qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.get_num_qubits_controlled" />

`get_num_qubits_controlled()`

returns number of qubits controlled

### num\_target\_qubits

<span id="qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.num_target_qubits" />

`property num_target_qubits`

Returns the number of target qubits

### required\_ancillas

<span id="qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.required_ancillas" />

`required_ancillas()`

returns required ancillas

### required\_ancillas\_controlled

<span id="qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.required_ancillas_controlled" />

`required_ancillas_controlled()`

returns required ancillas controlled

### value\_to\_estimation

<span id="qiskit.aqua.components.uncertainty_problems.UncertaintyProblem.value_to_estimation" />

`value_to_estimation(value)`

value to estimate

