---
title: Statevector
description: API reference for qiskit.quantum_info.Statevector
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.quantum_info.Statevector
---

# Statevector

<span id="qiskit.quantum_info.Statevector" />

`Statevector(data, dims=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/states/statevector.py "view source code")

Statevector class

Initialize a statevector object.

**Parameters**

*   **data** (*vector\_like*) – a complex statevector.
*   **dims** (*int or tuple or list*) – Optional. The subsystem dimension of the state (See additional information).

**Raises**

**QiskitError** – if input data is not valid.

**Additional Information:**

The `dims` kwarg can be None, an integer, or an iterable of integers.

*   `Iterable` – the subsystem dimensions are the values in the list with the total number of subsystems given by the length of the list.
*   `Int` or `None` – the length of the input vector specifies the total dimension of the density matrix. If it is a power of two the state will be initialized as an N-qubit state. If it is not a power of two the state will have a single d-dimensional subsystem.

## Attributes

### atol

The absolute tolerance parameter for float comparisons.

### data

Return data.

### dim

Return total state dimension.

### num\_qubits

Return the number of qubits if a N-qubit state or None otherwise.

### rtol

The relative tolerance parameter for float comparisons.

## Methods

### \_\_mul\_\_

<span id="qiskit.quantum_info.Statevector.__mul__" />

`Statevector.__mul__(other)`

### add

<span id="qiskit.quantum_info.Statevector.add" />

`Statevector.add(other)`

Return the linear combination self + other.

DEPRECATED: use `state + other` instead.

**Parameters**

**other** (*QuantumState*) – a quantum state object.

**Returns**

the linear combination self + other.

**Return type**

LinearOperator

**Raises**

**QiskitError** – if other is not a quantum state, or has incompatible dimensions.

### conjugate

<span id="qiskit.quantum_info.Statevector.conjugate" />

`Statevector.conjugate()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/states/statevector.py "view source code")

Return the conjugate of the operator.

### copy

<span id="qiskit.quantum_info.Statevector.copy" />

`Statevector.copy()`

Make a copy of current operator.

### dims

<span id="qiskit.quantum_info.Statevector.dims" />

`Statevector.dims(qargs=None)`

Return tuple of input dimension for specified subsystems.

### equiv

<span id="qiskit.quantum_info.Statevector.equiv" />

`Statevector.equiv(other, rtol=None, atol=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/states/statevector.py "view source code")

Return True if statevectors are equivalent up to global phase.

**Parameters**

*   **other** ([*Statevector*](qiskit.quantum_info.Statevector "qiskit.quantum_info.Statevector")) – a statevector object.
*   **rtol** (*float*) – relative tolerance value for comparison.
*   **atol** (*float*) – absolute tolerance value for comparison.

**Returns**

True if statevectors are equivalent up to global phase.

**Return type**

bool

### evolve

<span id="qiskit.quantum_info.Statevector.evolve" />

`Statevector.evolve(other, qargs=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/states/statevector.py "view source code")

Evolve a quantum state by the operator.

**Parameters**

*   **other** ([*Operator*](qiskit.quantum_info.Operator "qiskit.quantum_info.Operator")) – The operator to evolve by.
*   **qargs** (*list*) – a list of Statevector subsystem positions to apply the operator on.

**Returns**

the output quantum state.

**Return type**

[Statevector](qiskit.quantum_info.Statevector "qiskit.quantum_info.Statevector")

**Raises**

**QiskitError** – if the operator dimension does not match the specified Statevector subsystem dimensions.

### expand

<span id="qiskit.quantum_info.Statevector.expand" />

`Statevector.expand(other)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/states/statevector.py "view source code")

Return the tensor product state other ⊗ self.

**Parameters**

**other** ([*Statevector*](qiskit.quantum_info.Statevector "qiskit.quantum_info.Statevector")) – a quantum state object.

**Returns**

the tensor product state other ⊗ self.

**Return type**

[Statevector](qiskit.quantum_info.Statevector "qiskit.quantum_info.Statevector")

**Raises**

**QiskitError** – if other is not a quantum state.

### from\_instruction

<span id="qiskit.quantum_info.Statevector.from_instruction" />

`classmethod Statevector.from_instruction(instruction)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/states/statevector.py "view source code")

Return the output statevector of an instruction.

The statevector is initialized in the state $|{0,\ldots,0}\rangle$ of the same number of qubits as the input instruction or circuit, evolved by the input instruction, and the output statevector returned.

**Parameters**

**instruction** ([*qiskit.circuit.Instruction*](qiskit.circuit.Instruction "qiskit.circuit.Instruction")  *or*[*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – instruction or circuit

**Returns**

The final statevector.

**Return type**

[Statevector](qiskit.quantum_info.Statevector "qiskit.quantum_info.Statevector")

**Raises**

**QiskitError** – if the instruction contains invalid instructions for the statevector simulation.

### from\_int

<span id="qiskit.quantum_info.Statevector.from_int" />

`static Statevector.from_int(i, dims)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/states/statevector.py "view source code")

Return a computational basis statevector.

**Parameters**

*   **i** (*int*) – the basis state element.
*   **dims** (*int or tuple or list*) – The subsystem dimensions of the statevector (See additional information).

**Returns**

The computational basis state $|i\rangle$.

**Return type**

[Statevector](qiskit.quantum_info.Statevector "qiskit.quantum_info.Statevector")

#### Additional Information:

The `dims` kwarg can be an integer or an iterable of integers.

*   `Iterable` – the subsystem dimensions are the values in the list with the total number of subsystems given by the length of the list.
*   `Int` – the integer specifies the total dimension of the state. If it is a power of two the state will be initialized as an N-qubit state. If it is not a power of two the state will have a single d-dimensional subsystem.

### from\_label

<span id="qiskit.quantum_info.Statevector.from_label" />

`classmethod Statevector.from_label(label)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/states/statevector.py "view source code")

Return a tensor product of Pauli X,Y,Z eigenstates.

| Label | Statevector                     |
| ----- | ------------------------------- |
| `"0"` | $[1, 0]$                        |
| `"1"` | $[0, 1]$                        |
| `"+"` | $[1 / \sqrt{2}, 1 / \sqrt{2}]$  |
| `"-"` | $[1 / \sqrt{2}, -1 / \sqrt{2}]$ |
| `"r"` | $[1 / \sqrt{2}, i / \sqrt{2}]$  |
| `"l"` | $[1 / \sqrt{2}, -i / \sqrt{2}]$ |

**Parameters**

**label** (*string*) – a eigenstate string ket label (see table for allowed values).

**Returns**

The N-qubit basis state density matrix.

**Return type**

[Statevector](qiskit.quantum_info.Statevector "qiskit.quantum_info.Statevector")

**Raises**

**QiskitError** – if the label contains invalid characters, or the length of the label is larger than an explicitly specified num\_qubits.

### is\_valid

<span id="qiskit.quantum_info.Statevector.is_valid" />

`Statevector.is_valid(atol=None, rtol=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/states/statevector.py "view source code")

Return True if a Statevector has norm 1.

### measure

<span id="qiskit.quantum_info.Statevector.measure" />

`Statevector.measure(qargs=None)`

Measure subsystems and return outcome and post-measure state.

Note that this function uses the QuantumStates internal random number generator for sampling the measurement outcome. The RNG seed can be set using the [`seed()`](qiskit.quantum_info.Statevector#seed "qiskit.quantum_info.Statevector.seed") method.

**Parameters**

**qargs** (*list or None*) – subsystems to sample measurements for, if None sample measurement of all subsystems (Default: None).

**Returns**

**the pair `(outcome, state)` where `outcome` is the**

measurement outcome string label, and `state` is the collapsed post-measurement state for the corresponding outcome.

**Return type**

tuple

### multiply

<span id="qiskit.quantum_info.Statevector.multiply" />

`Statevector.multiply(other)`

Return the scalar multipled state other \* self.

**Parameters**

**other** (*complex*) – a complex number.

**Returns**

the scalar multipled state other \* self.

**Return type**

QuantumState

**Raises**

**QiskitError** – if other is not a valid complex number.

### probabilities

<span id="qiskit.quantum_info.Statevector.probabilities" />

`Statevector.probabilities(qargs=None, decimals=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/states/statevector.py "view source code")

Return the subsystem measurement probability vector.

Measurement probabilities are with respect to measurement in the computation (diagonal) basis.

**Parameters**

*   **qargs** (*None or list*) – subsystems to return probabilities for, if None return for all subsystems (Default: None).
*   **decimals** (*None or int*) – the number of decimal places to round values. If None no rounding is done (Default: None).

**Returns**

The Numpy vector array of probabilities.

**Return type**

np.array

#### Examples

Consider a 2-qubit product state $|\psi\rangle=|+\rangle\otimes|0\rangle$.

```python
from qiskit.quantum_info import Statevector

psi = Statevector.from_label('+0')

# Probabilities for measuring both qubits
probs = psi.probabilities()
print('probs: {}'.format(probs))

# Probabilities for measuring only qubit-0
probs_qubit_0 = psi.probabilities([0])
print('Qubit-0 probs: {}'.format(probs_qubit_0))

# Probabilities for measuring only qubit-1
probs_qubit_1 = psi.probabilities([1])
print('Qubit-1 probs: {}'.format(probs_qubit_1))
```

```python
probs: [0.5 0.  0.5 0. ]
Qubit-0 probs: [1. 0.]
Qubit-1 probs: [0.5 0.5]
```

We can also permute the order of qubits in the `qargs` list to change the qubit position in the probabilities output

```python
from qiskit.quantum_info import Statevector

psi = Statevector.from_label('+0')

# Probabilities for measuring both qubits
probs = psi.probabilities([0, 1])
print('probs: {}'.format(probs))

# Probabilities for measuring both qubits
# but swapping qubits 0 and 1 in output
probs_swapped = psi.probabilities([1, 0])
print('Swapped probs: {}'.format(probs_swapped))
```

```python
probs: [0.5 0.  0.5 0. ]
Swapped probs: [0.5 0.5 0.  0. ]
```

### probabilities\_dict

<span id="qiskit.quantum_info.Statevector.probabilities_dict" />

`Statevector.probabilities_dict(qargs=None, decimals=None)`

Return the subsystem measurement probability dictionary.

Measurement probabilities are with respect to measurement in the computation (diagonal) basis.

This dictionary representation uses a Ket-like notation where the dictionary keys are qudit strings for the subsystem basis vectors. If any subsystem has a dimension greater than 10 comma delimiters are inserted between integers so that subsystems can be distinguished.

**Parameters**

*   **qargs** (*None or list*) – subsystems to return probabilities for, if None return for all subsystems (Default: None).
*   **decimals** (*None or int*) – the number of decimal places to round values. If None no rounding is done (Default: None).

**Returns**

The measurement probabilities in dict (ket) form.

**Return type**

dict

### purity

<span id="qiskit.quantum_info.Statevector.purity" />

`Statevector.purity()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/states/statevector.py "view source code")

Return the purity of the quantum state.

### reset

<span id="qiskit.quantum_info.Statevector.reset" />

`Statevector.reset(qargs=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/states/statevector.py "view source code")

Reset state or subsystems to the 0-state.

**Parameters**

**qargs** (*list or None*) – subsystems to reset, if None all subsystems will be reset to their 0-state (Default: None).

**Returns**

the reset state.

**Return type**

[Statevector](qiskit.quantum_info.Statevector "qiskit.quantum_info.Statevector")

#### Additional Information:

If all subsystems are reset this will return the ground state on all subsystems. If only a some subsystems are reset this function will perform a measurement on those subsystems and evolve the subsystems so that the collapsed post-measurement states are rotated to the 0-state. The RNG seed for this sampling can be set using the [`seed()`](qiskit.quantum_info.Statevector#seed "qiskit.quantum_info.Statevector.seed") method.

### sample\_counts

<span id="qiskit.quantum_info.Statevector.sample_counts" />

`Statevector.sample_counts(shots, qargs=None)`

Sample a dict of qubit measurement outcomes in the computational basis.

**Parameters**

*   **shots** (*int*) – number of samples to generate.
*   **qargs** (*None or list*) – subsystems to sample measurements for, if None sample measurement of all subsystems (Default: None).

**Returns**

sampled counts dictionary.

**Return type**

dict

Additional Information:

> This function *samples* measurement outcomes using the measure [`probabilities()`](qiskit.quantum_info.Statevector#probabilities "qiskit.quantum_info.Statevector.probabilities") for the current state and qargs. It does not actually implement the measurement so the current state is not modified.
>
> The seed for random number generator used for sampling can be set to a fixed value by using the stats [`seed()`](qiskit.quantum_info.Statevector#seed "qiskit.quantum_info.Statevector.seed") method.

### sample\_memory

<span id="qiskit.quantum_info.Statevector.sample_memory" />

`Statevector.sample_memory(shots, qargs=None)`

Sample a list of qubit measurement outcomes in the computational basis.

**Parameters**

*   **shots** (*int*) – number of samples to generate.
*   **qargs** (*None or list*) – subsystems to sample measurements for, if None sample measurement of all subsystems (Default: None).

**Returns**

list of sampled counts if the order sampled.

**Return type**

np.array

Additional Information:

> This function *samples* measurement outcomes using the measure [`probabilities()`](qiskit.quantum_info.Statevector#probabilities "qiskit.quantum_info.Statevector.probabilities") for the current state and qargs. It does not actually implement the measurement so the current state is not modified.
>
> The seed for random number generator used for sampling can be set to a fixed value by using the stats [`seed()`](qiskit.quantum_info.Statevector#seed "qiskit.quantum_info.Statevector.seed") method.

### seed

<span id="qiskit.quantum_info.Statevector.seed" />

`Statevector.seed(value=None)`

Set the seed for the quantum state RNG.

### set\_atol

<span id="qiskit.quantum_info.Statevector.set_atol" />

`classmethod Statevector.set_atol(value)`

Set the class default absolute tolerance parameter for float comparisons.

### set\_rtol

<span id="qiskit.quantum_info.Statevector.set_rtol" />

`classmethod Statevector.set_rtol(value)`

Set the class default relative tolerance parameter for float comparisons.

### subtract

<span id="qiskit.quantum_info.Statevector.subtract" />

`Statevector.subtract(other)`

Return the linear operator self - other.

DEPRECATED: use `state - other` instead.

**Parameters**

**other** (*QuantumState*) – a quantum state object.

**Returns**

the linear combination self - other.

**Return type**

LinearOperator

**Raises**

**QiskitError** – if other is not a quantum state, or has incompatible dimensions.

### tensor

<span id="qiskit.quantum_info.Statevector.tensor" />

`Statevector.tensor(other)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/states/statevector.py "view source code")

Return the tensor product state self ⊗ other.

**Parameters**

**other** ([*Statevector*](qiskit.quantum_info.Statevector "qiskit.quantum_info.Statevector")) – a quantum state object.

**Returns**

the tensor product operator self ⊗ other.

**Return type**

[Statevector](qiskit.quantum_info.Statevector "qiskit.quantum_info.Statevector")

**Raises**

**QiskitError** – if other is not a quantum state.

### to\_counts

<span id="qiskit.quantum_info.Statevector.to_counts" />

`Statevector.to_counts()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/states/statevector.py "view source code")

Returns the statevector as a counts dict of probabilities.

DEPRECATED: use [`probabilities_dict()`](qiskit.quantum_info.Statevector#probabilities_dict "qiskit.quantum_info.Statevector.probabilities_dict") instead.

**Returns**

Counts of probabilities.

**Return type**

dict

### to\_dict

<span id="qiskit.quantum_info.Statevector.to_dict" />

`Statevector.to_dict(decimals=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/states/statevector.py "view source code")

Convert the statevector to dictionary form.

This dictionary representation uses a Ket-like notation where the dictionary keys are qudit strings for the subsystem basis vectors. If any subsystem has a dimension greater than 10 comma delimiters are inserted between integers so that subsystems can be distinguished.

**Parameters**

**decimals** (*None or int*) – the number of decimal places to round values. If None no rounding is done (Default: None).

**Returns**

the dictionary form of the Statevector.

**Return type**

dict

#### Example

The ket-form of a 2-qubit statevector $|\psi\rangle = |-\rangle\otimes |0\rangle$

```python
from qiskit.quantum_info import Statevector

psi = Statevector.from_label('-0')
print(psi.to_dict())
```

```python
{'00': (0.7071067811865475+0j), '10': (-0.7071067811865475+0j)}
```

For non-qubit subsystems the integer range can go from 0 to 9. For example in a qutrit system

```python
import numpy as np
from qiskit.quantum_info import Statevector

vec = np.zeros(9)
vec[0] = 1 / np.sqrt(2)
vec[-1] = 1 / np.sqrt(2)
psi = Statevector(vec, dims=(3, 3))
print(psi.to_dict())
```

```python
{'00': (0.7071067811865475+0j), '22': (0.7071067811865475+0j)}
```

For large subsystem dimensions delimeters are required. The following example is for a 20-dimensional system consisting of a qubit and 10-dimensional qudit.

```python
import numpy as np
from qiskit.quantum_info import Statevector

vec = np.zeros(2 * 10)
vec[0] = 1 / np.sqrt(2)
vec[-1] = 1 / np.sqrt(2)
psi = Statevector(vec, dims=(2, 10))
print(psi.to_dict())
```

```python
{'00': (0.7071067811865475+0j), '91': (0.7071067811865475+0j)}
```

### to\_operator

<span id="qiskit.quantum_info.Statevector.to_operator" />

`Statevector.to_operator()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/states/statevector.py "view source code")

Convert state to a rank-1 projector operator

### trace

<span id="qiskit.quantum_info.Statevector.trace" />

`Statevector.trace()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/states/statevector.py "view source code")

Return the trace of the quantum state as a density matrix.

