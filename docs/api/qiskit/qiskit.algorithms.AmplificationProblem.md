---
title: AmplificationProblem
description: API reference for qiskit.algorithms.AmplificationProblem
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.AmplificationProblem
---

# AmplificationProblem

<span id="qiskit.algorithms.AmplificationProblem" />

`qiskit.algorithms.AmplificationProblem(oracle, state_preparation=None, grover_operator=None, post_processing=None, objective_qubits=None, is_good_state=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/algorithms/amplitude_amplifiers/amplification_problem.py "view source code")

Bases: [`object`](https://docs.python.org/3/library/functions.html#object "(in Python v3.12)")

The amplification problem is the input to amplitude amplification algorithms, like Grover.

This class contains all problem-specific information required to run an amplitude amplification algorithm. It minimally contains the Grover operator. It can further hold some post processing on the optimal bitstring.

**Parameters**

*   **oracle** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")  *|*[*Statevector*](qiskit.quantum_info.Statevector "qiskit.quantum_info.Statevector")) – The oracle reflecting about the bad states.
*   **state\_preparation** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit") *| None*) – A circuit preparing the input state, referred to as $\mathcal{A}$. If None, a layer of Hadamard gates is used.
*   **grover\_operator** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit") *| None*) – The Grover operator $\mathcal{Q}$ used as unitary in the phase estimation circuit. If None, this operator is constructed from the `oracle` and `state_preparation`.
*   **post\_processing** (*Callable\[\[*[*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")*], Any] | None*) – A mapping applied to the most likely bitstring.
*   **objective\_qubits** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")  *|*[*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")*\[*[*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")*] | None*) – If set, specifies the indices of the qubits that should be measured. If None, all qubits will be measured. The `is_good_state` function will be applied on the measurement outcome of these qubits.
*   **is\_good\_state** (*Callable\[\[*[*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")*],* [*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")*] |* [*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")*\[*[*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")*] |* [*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")*\[*[*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")*] |* [*Statevector*](qiskit.quantum_info.Statevector "qiskit.quantum_info.Statevector") *| None*) – A function to check whether a string represents a good state. By default if the `oracle` argument has an `evaluate_bitstring` method (currently only provided by the [`PhaseOracle`](qiskit.circuit.library.PhaseOracle "qiskit.circuit.library.PhaseOracle") class) this will be used, otherwise this kwarg is required and **must** be specified.

## Attributes

<span id="qiskit.algorithms.AmplificationProblem.grover_operator" />

### grover\_operator

Get the $\mathcal{Q}$ operator, or Grover operator.

If the Grover operator is not set, we try to build it from the $\mathcal{A}$ operator and objective\_qubits. This only works if objective\_qubits is a list of integers.

**Returns**

The Grover operator, or None if neither the Grover operator nor the $\mathcal{A}$ operator is set.

<span id="qiskit.algorithms.AmplificationProblem.is_good_state" />

### is\_good\_state

Check whether a provided bitstring is a good state or not.

**Returns**

A callable that takes in a bitstring and returns True if the measurement is a good state, False otherwise.

<span id="qiskit.algorithms.AmplificationProblem.objective_qubits" />

### objective\_qubits

The indices of the objective qubits.

**Returns**

The indices of the objective qubits as list of integers.

<span id="qiskit.algorithms.AmplificationProblem.oracle" />

### oracle

Return the oracle.

**Returns**

The oracle.

<span id="qiskit.algorithms.AmplificationProblem.post_processing" />

### post\_processing

Apply post processing to the input value.

**Returns**

A handle to the post processing function. Acts as identity by default.

<span id="qiskit.algorithms.AmplificationProblem.state_preparation" />

### state\_preparation

Get the state preparation operator $\mathcal{A}$.

**Returns**

The $\mathcal{A}$ operator as QuantumCircuit.

