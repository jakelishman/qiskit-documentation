---
title: LogNormalDistribution
description: API reference for qiskit.aqua.components.uncertainty_models.LogNormalDistribution
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.components.uncertainty_models.LogNormalDistribution
---

# LogNormalDistribution

<span id="qiskit.aqua.components.uncertainty_models.LogNormalDistribution" />

`LogNormalDistribution(num_target_qubits, mu=0, sigma=1, low=0, high=1)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/components/uncertainty_models/log_normal_distribution.py "view source code")

The Univariate Log-Normal Distribution.

Log-normal distribution, truncated to lower and upper bound and discretized on a grid defined by the number of qubits.

**Parameters**

*   **num\_target\_qubits** (`int`) – Number of qubits it acts on, has a minimum value of 1.
*   **mu** (`float`) – Expected value of considered normal distribution
*   **sigma** (`float`) – Standard deviation of considered normal distribution
*   **low** (`float`) – Lower bound, i.e., the value corresponding to |0…0> (assuming an equidistant grid)
*   **high** (`float`) – Upper bound, i.e., the value corresponding to |1…1> (assuming an equidistant grid)

## Attributes

### high

returns high

### low

returns low

### num\_target\_qubits

Returns the number of target qubits

### num\_values

returns number of values

### probabilities

returns probabilities

### values

returns values

## Methods

### build

<span id="qiskit.aqua.components.uncertainty_models.LogNormalDistribution.build" />

`LogNormalDistribution.build(qc, q, q_ancillas=None, params=None)`

### build\_controlled

<span id="qiskit.aqua.components.uncertainty_models.LogNormalDistribution.build_controlled" />

`LogNormalDistribution.build_controlled(qc, q, q_control, q_ancillas=None, use_basis_gates=True)`

Adds corresponding controlled sub-circuit to given circuit

**Parameters**

*   **qc** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – quantum circuit
*   **q** (*list*) – list of qubits (has to be same length as self.\_num\_qubits)
*   **q\_control** ([*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")) – control qubit
*   **q\_ancillas** (*list*) – list of ancilla qubits (or None if none needed)
*   **use\_basis\_gates** (*bool*) – use basis gates for expansion of controlled circuit

### build\_controlled\_inverse

<span id="qiskit.aqua.components.uncertainty_models.LogNormalDistribution.build_controlled_inverse" />

`LogNormalDistribution.build_controlled_inverse(qc, q, q_control, q_ancillas=None, use_basis_gates=True)`

Adds controlled inverse of corresponding sub-circuit to given circuit

**Parameters**

*   **qc** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – quantum circuit
*   **q** (*list*) – list of qubits (has to be same length as self.\_num\_qubits)
*   **q\_control** ([*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")) – control qubit
*   **q\_ancillas** (*list*) – list of ancilla qubits (or None if none needed)
*   **use\_basis\_gates** (*bool*) – use basis gates for expansion of controlled circuit

### build\_controlled\_inverse\_power

<span id="qiskit.aqua.components.uncertainty_models.LogNormalDistribution.build_controlled_inverse_power" />

`LogNormalDistribution.build_controlled_inverse_power(qc, q, q_control, power, q_ancillas=None, use_basis_gates=True)`

Adds controlled, inverse, power of corresponding circuit. May be overridden if a more efficient implementation is possible

### build\_controlled\_power

<span id="qiskit.aqua.components.uncertainty_models.LogNormalDistribution.build_controlled_power" />

`LogNormalDistribution.build_controlled_power(qc, q, q_control, power, q_ancillas=None, use_basis_gates=True)`

Adds controlled power of corresponding circuit. May be overridden if a more efficient implementation is possible

### build\_inverse

<span id="qiskit.aqua.components.uncertainty_models.LogNormalDistribution.build_inverse" />

`LogNormalDistribution.build_inverse(qc, q, q_ancillas=None)`

Adds inverse of corresponding sub-circuit to given circuit

**Parameters**

*   **qc** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – quantum circuit
*   **q** (*list*) – list of qubits (has to be same length as self.\_num\_qubits)
*   **q\_ancillas** (*list*) – list of ancilla qubits (or None if none needed)

### build\_inverse\_power

<span id="qiskit.aqua.components.uncertainty_models.LogNormalDistribution.build_inverse_power" />

`LogNormalDistribution.build_inverse_power(qc, q, power, q_ancillas=None)`

Adds inverse power of corresponding circuit. May be overridden if a more efficient implementation is possible

### build\_power

<span id="qiskit.aqua.components.uncertainty_models.LogNormalDistribution.build_power" />

`LogNormalDistribution.build_power(qc, q, power, q_ancillas=None)`

Adds power of corresponding circuit. May be overridden if a more efficient implementation is possible

### get\_num\_qubits

<span id="qiskit.aqua.components.uncertainty_models.LogNormalDistribution.get_num_qubits" />

`LogNormalDistribution.get_num_qubits()`

returns number of qubits

### get\_num\_qubits\_controlled

<span id="qiskit.aqua.components.uncertainty_models.LogNormalDistribution.get_num_qubits_controlled" />

`LogNormalDistribution.get_num_qubits_controlled()`

returns number of qubits controlled

### pdf\_to\_probabilities

<span id="qiskit.aqua.components.uncertainty_models.LogNormalDistribution.pdf_to_probabilities" />

`static LogNormalDistribution.pdf_to_probabilities(pdf, low, high, num_values)`

Takes a probability density function (pdf), and returns a truncated and discretized array of probabilities corresponding to it

**Parameters**

*   **pdf** (*function*) – probability density function
*   **low** (*float*) – lower bound of equidistant grid
*   **high** (*float*) – upper bound of equidistant grid
*   **num\_values** (*int*) – number of grid points

**Returns**

array of probabilities

**Return type**

list

### required\_ancillas

<span id="qiskit.aqua.components.uncertainty_models.LogNormalDistribution.required_ancillas" />

`LogNormalDistribution.required_ancillas()`

returns required ancillas

### required\_ancillas\_controlled

<span id="qiskit.aqua.components.uncertainty_models.LogNormalDistribution.required_ancillas_controlled" />

`LogNormalDistribution.required_ancillas_controlled()`

returns required ancillas controlled

