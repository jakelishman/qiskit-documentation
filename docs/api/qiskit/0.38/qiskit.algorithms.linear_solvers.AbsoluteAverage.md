---
title: AbsoluteAverage
description: API reference for qiskit.algorithms.linear_solvers.AbsoluteAverage
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.linear_solvers.AbsoluteAverage
---

# AbsoluteAverage

<span id="qiskit.algorithms.linear_solvers.AbsoluteAverage" />

`AbsoluteAverage`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/algorithms/linear_solvers/observables/absolute_average.py "view source code")

Bases: [`qiskit.algorithms.linear_solvers.observables.linear_system_observable.LinearSystemObservable`](qiskit.algorithms.linear_solvers.LinearSystemObservable "qiskit.algorithms.linear_solvers.observables.linear_system_observable.LinearSystemObservable")

An observable for the absolute average of a linear system of equations solution.

For a vector $x=(x_1,...,x_N)$, the absolute average is defined as $\abs{\frac{1}{N}\sum_{i=1}^{N}x_i}$.

## Examples

```python
import numpy as np
from qiskit import QuantumCircuit
from qiskit.algorithms.linear_solvers.observables.absolute_average import \
AbsoluteAverage
from qiskit.opflow import StateFn

observable = AbsoluteAverage()
vector = [1.0, -2.1, 3.2, -4.3]

init_state = vector / np.linalg.norm(vector)
num_qubits = int(np.log2(len(vector)))

qc = QuantumCircuit(num_qubits)
qc.isometry(init_state, list(range(num_qubits)), None)
qc.append(observable.observable_circuit(num_qubits), list(range(num_qubits)))

# Observable operator
observable_op = observable.observable(num_qubits)
state_vec = (~StateFn(observable_op) @ StateFn(qc)).eval()

# Obtain result
result = observable.post_processing(state_vec, num_qubits)

# Obtain analytical evaluation
exact = observable.evaluate_classically(init_state)
```

## Methods

### evaluate\_classically

<span id="qiskit.algorithms.linear_solvers.AbsoluteAverage.evaluate_classically" />

`AbsoluteAverage.evaluate_classically(solution)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/algorithms/linear_solvers/observables/absolute_average.py "view source code")

Evaluates the given observable on the solution to the linear system.

**Parameters**

**solution** (`Union`\[`array`, [`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit")]) – The solution to the system as a numpy array or the circuit that prepares it.

**Return type**

`float`

**Returns**

The value of the observable.

### observable

<span id="qiskit.algorithms.linear_solvers.AbsoluteAverage.observable" />

`AbsoluteAverage.observable(num_qubits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/algorithms/linear_solvers/observables/absolute_average.py "view source code")

The observable operator.

**Parameters**

**num\_qubits** (`int`) – The number of qubits on which the observable will be applied.

**Return type**

`Union`\[[`TensoredOp`](qiskit.opflow.list_ops.TensoredOp "qiskit.opflow.list_ops.tensored_op.TensoredOp"), `List`\[[`TensoredOp`](qiskit.opflow.list_ops.TensoredOp "qiskit.opflow.list_ops.tensored_op.TensoredOp")]]

**Returns**

The observable as a sum of Pauli strings.

### observable\_circuit

<span id="qiskit.algorithms.linear_solvers.AbsoluteAverage.observable_circuit" />

`AbsoluteAverage.observable_circuit(num_qubits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/algorithms/linear_solvers/observables/absolute_average.py "view source code")

The circuit implementing the absolute average observable.

**Parameters**

**num\_qubits** (`int`) – The number of qubits on which the observable will be applied.

**Return type**

`Union`\[[`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit"), `List`\[[`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit")]]

**Returns**

The observable as a QuantumCircuit.

### post\_processing

<span id="qiskit.algorithms.linear_solvers.AbsoluteAverage.post_processing" />

`AbsoluteAverage.post_processing(solution, num_qubits, scaling=1)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.21/qiskit/algorithms/linear_solvers/observables/absolute_average.py "view source code")

Evaluates the absolute average on the solution to the linear system.

**Parameters**

*   **solution** (`Union`\[`float`, `List`\[`float`]]) – The probability calculated from the circuit and the observable.
*   **num\_qubits** (`int`) – The number of qubits where the observable was applied.
*   **scaling** (`float`) – Scaling of the solution.

**Return type**

`float`

**Returns**

The value of the absolute average.

**Raises**

**ValueError** – If the input is not in the correct format.

