---
title: PhaseEstimationCircuit
description: API reference for qiskit.aqua.circuits.PhaseEstimationCircuit
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.circuits.PhaseEstimationCircuit
---

# qiskit.aqua.circuits.PhaseEstimationCircuit

<span id="qiskit.aqua.circuits.PhaseEstimationCircuit" />

`PhaseEstimationCircuit(operator=None, state_in=None, iqft=None, num_time_slices=1, num_ancillae=1, expansion_mode='trotter', expansion_order=1, evo_time=6.283185307179586, state_in_circuit_factory=None, unitary_circuit_factory=None, shallow_circuit_concat=False, pauli_list=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/circuits/phase_estimation_circuit.py "view source code")

Quantum Phase Estimation Circuit.

**Parameters**

*   **operator** (`Optional`\[`WeightedPauliOperator`]) – the hamiltonian Operator object
*   **state\_in** (`Union`\[`QuantumCircuit`, `InitialState`, `None`]) – the InitialState component or a quantum circuit
*   **the initial quantum state** (*representing*) –
*   **iqft** (`Optional`\[`QuantumCircuit`]) – the Inverse Quantum Fourier Transform as circuit or Aqua component
*   **num\_time\_slices** (`int`) – the number of time slices
*   **num\_ancillae** (`int`) – the number of ancillary qubits to use for the measurement
*   **expansion\_mode** (`str`) – the expansion mode (trotter|suzuki)
*   **expansion\_order** (`int`) – the suzuki expansion order
*   **evo\_time** (`float`) – the evolution time
*   **state\_in\_circuit\_factory** (`Optional`\[`CircuitFactory`]) – the initial state represented by a CircuitFactory object
*   **unitary\_circuit\_factory** (`Optional`\[`CircuitFactory`]) – the problem unitary represented by a CircuitFactory object
*   **shallow\_circuit\_concat** (`bool`) – indicate whether to use shallow (cheap) mode for circuit concatenation
*   **pauli\_list** (`Optional`\[`List`\[`Pauli`]]) – the flat list of paulis for the operator

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – Missing input

### \_\_init\_\_

<span id="qiskit.aqua.circuits.PhaseEstimationCircuit.__init__" />

`__init__(operator=None, state_in=None, iqft=None, num_time_slices=1, num_ancillae=1, expansion_mode='trotter', expansion_order=1, evo_time=6.283185307179586, state_in_circuit_factory=None, unitary_circuit_factory=None, shallow_circuit_concat=False, pauli_list=None)`

**Parameters**

*   **operator** (`Optional`\[`WeightedPauliOperator`]) – the hamiltonian Operator object
*   **state\_in** (`Union`\[`QuantumCircuit`, `InitialState`, `None`]) – the InitialState component or a quantum circuit
*   **the initial quantum state** (*representing*) –
*   **iqft** (`Optional`\[`QuantumCircuit`]) – the Inverse Quantum Fourier Transform as circuit or Aqua component
*   **num\_time\_slices** (`int`) – the number of time slices
*   **num\_ancillae** (`int`) – the number of ancillary qubits to use for the measurement
*   **expansion\_mode** (`str`) – the expansion mode (trotter|suzuki)
*   **expansion\_order** (`int`) – the suzuki expansion order
*   **evo\_time** (`float`) – the evolution time
*   **state\_in\_circuit\_factory** (`Optional`\[`CircuitFactory`]) – the initial state represented by a CircuitFactory object
*   **unitary\_circuit\_factory** (`Optional`\[`CircuitFactory`]) – the problem unitary represented by a CircuitFactory object
*   **shallow\_circuit\_concat** (`bool`) – indicate whether to use shallow (cheap) mode for circuit concatenation
*   **pauli\_list** (`Optional`\[`List`\[`Pauli`]]) – the flat list of paulis for the operator

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – Missing input

## Methods

|                                                                                                                                                                              |                                                       |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------- |
| [`__init__`](#qiskit.aqua.circuits.PhaseEstimationCircuit.__init__ "qiskit.aqua.circuits.PhaseEstimationCircuit.__init__")(\[operator, state\_in, iqft, …])                  | **type operator**`Optional`\[`WeightedPauliOperator`] |
| [`construct_circuit`](#qiskit.aqua.circuits.PhaseEstimationCircuit.construct_circuit "qiskit.aqua.circuits.PhaseEstimationCircuit.construct_circuit")(\[state\_register, …]) | Construct the Phase Estimation circuit                |

## Attributes

|                                                                                                                                                          |                            |
| -------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------- |
| [`ancillary_register`](#qiskit.aqua.circuits.PhaseEstimationCircuit.ancillary_register "qiskit.aqua.circuits.PhaseEstimationCircuit.ancillary_register") | returns ancillary register |
| [`auxiliary_register`](#qiskit.aqua.circuits.PhaseEstimationCircuit.auxiliary_register "qiskit.aqua.circuits.PhaseEstimationCircuit.auxiliary_register") | returns auxiliary register |
| [`state_register`](#qiskit.aqua.circuits.PhaseEstimationCircuit.state_register "qiskit.aqua.circuits.PhaseEstimationCircuit.state_register")             | returns state register     |

### ancillary\_register

<span id="qiskit.aqua.circuits.PhaseEstimationCircuit.ancillary_register" />

`property ancillary_register`

returns ancillary register

### auxiliary\_register

<span id="qiskit.aqua.circuits.PhaseEstimationCircuit.auxiliary_register" />

`property auxiliary_register`

returns auxiliary register

### construct\_circuit

<span id="qiskit.aqua.circuits.PhaseEstimationCircuit.construct_circuit" />

`construct_circuit(state_register=None, ancillary_register=None, auxiliary_register=None, measurement=False)`

Construct the Phase Estimation circuit

**Parameters**

*   **state\_register** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")) – the optional register to use for the quantum state
*   **ancillary\_register** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")) – the optional register to use for
*   **ancillary measurement qubits** (*the*) –
*   **auxiliary\_register** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")) – an optional auxiliary quantum register
*   **measurement** (*bool*) – Boolean flag to indicate if measurement should be included
*   **the circuit.** (*in*) –

**Returns**

the QuantumCircuit object for the constructed circuit

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

*   **RuntimeError** – Multiple identity pauli terms are present
*   **ValueError** – invalid mode

### state\_register

<span id="qiskit.aqua.circuits.PhaseEstimationCircuit.state_register" />

`property state_register`

returns state register

