---
title: LinearSystemObservable
description: API reference for qiskit.algorithms.linear_solvers.LinearSystemObservable
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.linear_solvers.LinearSystemObservable
---

# LinearSystemObservable

<span id="qiskit.algorithms.linear_solvers.LinearSystemObservable" />

`LinearSystemObservable`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/linear_solvers/observables/linear_system_observable.py "view source code")

Bases: `abc.ABC`

The deprecated abstract class for linear system observables in Qiskit.

## Methods

### evaluate\_classically

<span id="qiskit.algorithms.linear_solvers.LinearSystemObservable.evaluate_classically" />

`abstract LinearSystemObservable.evaluate_classically(solution)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/linear_solvers/observables/linear_system_observable.py "view source code")

#### Calculates the analytical value of the given observable from the solution vector to the

linear system.

**Parameters**

**solution** (`Union`\[`array`, [`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit")]) – The solution to the system as a numpy array or the circuit that prepares it.

**Return type**

`float`

**Returns**

The value of the observable.

### observable

<span id="qiskit.algorithms.linear_solvers.LinearSystemObservable.observable" />

`abstract LinearSystemObservable.observable(num_qubits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/linear_solvers/observables/linear_system_observable.py "view source code")

The observable operator.

**Parameters**

**num\_qubits** (`int`) – The number of qubits on which the observable will be applied.

**Return type**

`Union`\[[`TensoredOp`](qiskit.opflow.list_ops.TensoredOp "qiskit.opflow.list_ops.tensored_op.TensoredOp"), `List`\[[`TensoredOp`](qiskit.opflow.list_ops.TensoredOp "qiskit.opflow.list_ops.tensored_op.TensoredOp")]]

**Returns**

The observable as a sum of Pauli strings.

### observable\_circuit

<span id="qiskit.algorithms.linear_solvers.LinearSystemObservable.observable_circuit" />

`abstract LinearSystemObservable.observable_circuit(num_qubits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/linear_solvers/observables/linear_system_observable.py "view source code")

The circuit implementing the observable.

**Parameters**

**num\_qubits** (`int`) – The number of qubits on which the observable will be applied.

**Return type**

`Union`\[[`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit"), `List`\[[`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit")]]

**Returns**

The observable as a QuantumCircuit.

### post\_processing

<span id="qiskit.algorithms.linear_solvers.LinearSystemObservable.post_processing" />

`abstract LinearSystemObservable.post_processing(solution, num_qubits, scaling=1)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/linear_solvers/observables/linear_system_observable.py "view source code")

Evaluates the given observable on the solution to the linear system.

**Parameters**

*   **solution** (`Union`\[`float`, `List`\[`float`]]) – The probability calculated from the circuit and the observable.
*   **num\_qubits** (`int`) – The number of qubits where the observable was applied.
*   **scaling** (`float`) – Scaling of the solution.

**Return type**

`float`

**Returns**

The value of the observable.

