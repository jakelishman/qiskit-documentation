---
title: DensityMatrix
description: API reference for qiskit.quantum_info.DensityMatrix
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.quantum_info.DensityMatrix
---

# DensityMatrix

<span id="qiskit.quantum_info.DensityMatrix" />

`qiskit.quantum_info.DensityMatrix(data, dims=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/quantum_info/states/densitymatrix.py "view source code")

Bases: `QuantumState`, `TolerancesMixin`

DensityMatrix class

Initialize a density matrix object.

**Parameters**

*   **or** (*data (np.ndarray or* [*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")  *or matrix\_like or*[*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – qiskit.circuit.Instruction): A statevector, quantum instruction or an object with a `to_operator` or `to_matrix` method from which the density matrix can be constructed. If a vector the density matrix is constructed as the projector of that vector. If a quantum instruction, the density matrix is constructed by assuming all qubits are initialized in the zero state.
*   **dims** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")  *or*[*tuple*](https://docs.python.org/3/library/stdtypes.html#tuple "(in Python v3.12)")  *or*[*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")) – Optional. The subsystem dimension of the state (See additional information).

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if input data is not valid.

**Additional Information:**

The `dims` kwarg can be None, an integer, or an iterable of integers.

*   `Iterable` – the subsystem dimensions are the values in the list with the total number of subsystems given by the length of the list.
*   `Int` or `None` – the leading dimension of the input matrix specifies the total dimension of the density matrix. If it is a power of two the state will be initialized as an N-qubit state. If it is not a power of two the state will have a single d-dimensional subsystem.

## Attributes

<span id="qiskit.quantum_info.DensityMatrix.atol" />

### atol

`= 1e-08`

<span id="qiskit.quantum_info.DensityMatrix.data" />

### data

Return data.

<span id="qiskit.quantum_info.DensityMatrix.dim" />

### dim

Return total state dimension.

<span id="qiskit.quantum_info.DensityMatrix.num_qubits" />

### num\_qubits

Return the number of qubits if a N-qubit state or None otherwise.

<span id="qiskit.quantum_info.DensityMatrix.rtol" />

### rtol

`= 1e-05`

<span id="qiskit.quantum_info.DensityMatrix.settings" />

### settings

Return settings.

## Methods

### conjugate

<span id="qiskit.quantum_info.DensityMatrix.conjugate" />

`conjugate()`

Return the conjugate of the density matrix.

### copy

<span id="qiskit.quantum_info.DensityMatrix.copy" />

`copy()`

Make a copy of current operator.

### dims

<span id="qiskit.quantum_info.DensityMatrix.dims" />

`dims(qargs=None)`

Return tuple of input dimension for specified subsystems.

### draw

<span id="qiskit.quantum_info.DensityMatrix.draw" />

`draw(output=None, **drawer_args)`

Return a visualization of the Statevector.

**repr**: ASCII TextMatrix of the state’s `__repr__`.

**text**: ASCII TextMatrix that can be printed in the console.

**latex**: An IPython Latex object for displaying in Jupyter Notebooks.

**latex\_source**: Raw, uncompiled ASCII source to generate array using LaTeX.

**qsphere**: Matplotlib figure, rendering of density matrix using plot\_state\_qsphere().

**hinton**: Matplotlib figure, rendering of density matrix using plot\_state\_hinton().

**bloch**: Matplotlib figure, rendering of density matrix using plot\_bloch\_multivector().

**Parameters**

*   **output** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")) – Select the output method to use for drawing the state. Valid choices are repr, text, latex, latex\_source, qsphere, hinton, or bloch. Default is repr. Default can be changed by adding the line `state_drawer = <default>` to `~/.qiskit/settings.conf` under `[default]`.
*   **drawer\_args** – Arguments to be passed directly to the relevant drawing function or constructor (TextMatrix(), array\_to\_latex(), plot\_state\_qsphere(), plot\_state\_hinton() or plot\_bloch\_multivector()). See the relevant function under qiskit.visualization for that function’s documentation.

**Returns**

`matplotlib.Figure` or [`str`](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)") or `TextMatrix` or `IPython.display.Latex`: Drawing of the Statevector.

**Raises**

[**ValueError**](https://docs.python.org/3/library/exceptions.html#ValueError "(in Python v3.12)") – when an invalid output method is selected.

### evolve

<span id="qiskit.quantum_info.DensityMatrix.evolve" />

`evolve(other, qargs=None)`

Evolve a quantum state by an operator.

**Parameters**

*   **QuantumChannel** (*other (Operator or*) – or Instruction or Circuit): The operator to evolve by.
*   **qargs** ([*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")) – a list of QuantumState subsystem positions to apply the operator on.

**Returns**

the output density matrix.

**Return type**

[DensityMatrix](#qiskit.quantum_info.DensityMatrix "qiskit.quantum_info.DensityMatrix")

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if the operator dimension does not match the specified QuantumState subsystem dimensions.

### expand

<span id="qiskit.quantum_info.DensityMatrix.expand" />

`expand(other)`

Return the tensor product state other ⊗ self.

**Parameters**

**other** ([*DensityMatrix*](#qiskit.quantum_info.DensityMatrix "qiskit.quantum_info.DensityMatrix")) – a quantum state object.

**Returns**

the tensor product state other ⊗ self.

**Return type**

[DensityMatrix](#qiskit.quantum_info.DensityMatrix "qiskit.quantum_info.DensityMatrix")

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if other is not a quantum state.

### expectation\_value

<span id="qiskit.quantum_info.DensityMatrix.expectation_value" />

`expectation_value(oper, qargs=None)`

Compute the expectation value of an operator.

**Parameters**

*   **oper** ([*Operator*](qiskit.quantum_info.Operator "qiskit.quantum_info.Operator")) – an operator to evaluate expval.
*   **qargs** (*None or* [*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")) – subsystems to apply the operator on.

**Returns**

the expectation value.

**Return type**

[complex](https://docs.python.org/3/library/functions.html#complex "(in Python v3.12)")

### from\_instruction

<span id="qiskit.quantum_info.DensityMatrix.from_instruction" />

`classmethod from_instruction(instruction)`

Return the output density matrix of an instruction.

The statevector is initialized in the state $|{0,\ldots,0}\rangle$ of the same number of qubits as the input instruction or circuit, evolved by the input instruction, and the output statevector returned.

**Parameters**

**instruction** ([*qiskit.circuit.Instruction*](qiskit.circuit.Instruction "qiskit.circuit.Instruction")  *or*[*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – instruction or circuit

**Returns**

the final density matrix.

**Return type**

[DensityMatrix](#qiskit.quantum_info.DensityMatrix "qiskit.quantum_info.DensityMatrix")

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if the instruction contains invalid instructions for density matrix simulation.

### from\_int

<span id="qiskit.quantum_info.DensityMatrix.from_int" />

`static from_int(i, dims)`

Return a computational basis state density matrix.

**Parameters**

*   **i** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – the basis state element.
*   **dims** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")  *or*[*tuple*](https://docs.python.org/3/library/stdtypes.html#tuple "(in Python v3.12)")  *or*[*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")) – The subsystem dimensions of the statevector (See additional information).

**Returns**

The computational basis state $|i\rangle\!\langle i|$.

**Return type**

[DensityMatrix](#qiskit.quantum_info.DensityMatrix "qiskit.quantum_info.DensityMatrix")

**Additional Information:**

The `dims` kwarg can be an integer or an iterable of integers.

*   `Iterable` – the subsystem dimensions are the values in the list with the total number of subsystems given by the length of the list.
*   `Int` – the integer specifies the total dimension of the state. If it is a power of two the state will be initialized as an N-qubit state. If it is not a power of two the state will have a single d-dimensional subsystem.

### from\_label

<span id="qiskit.quantum_info.DensityMatrix.from_label" />

`classmethod from_label(label)`

Return a tensor product of Pauli X,Y,Z eigenstates.

| Label | Statevector                                                 |
| ----- | ----------------------------------------------------------- |
| `"0"` | $\begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix}$              |
| `"1"` | $\begin{pmatrix} 0 & 0 \\ 0 & 1 \end{pmatrix}$              |
| `"+"` | $\frac{1}{2}\begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix}$   |
| `"-"` | $\frac{1}{2}\begin{pmatrix} 1 & -1 \\ -1 & 1 \end{pmatrix}$ |
| `"r"` | $\frac{1}{2}\begin{pmatrix} 1 & -i \\ i & 1 \end{pmatrix}$  |
| `"l"` | $\frac{1}{2}\begin{pmatrix} 1 & i \\ -i & 1 \end{pmatrix}$  |

**Parameters**

**label** (*string*) – a eigenstate string ket label (see table for allowed values).

**Returns**

The N-qubit basis state density matrix.

**Return type**

[DensityMatrix](#qiskit.quantum_info.DensityMatrix "qiskit.quantum_info.DensityMatrix")

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if the label contains invalid characters, or the length of the label is larger than an explicitly specified num\_qubits.

### is\_valid

<span id="qiskit.quantum_info.DensityMatrix.is_valid" />

`is_valid(atol=None, rtol=None)`

Return True if trace 1 and positive semidefinite.

### measure

<span id="qiskit.quantum_info.DensityMatrix.measure" />

`measure(qargs=None)`

Measure subsystems and return outcome and post-measure state.

Note that this function uses the QuantumStates internal random number generator for sampling the measurement outcome. The RNG seed can be set using the [`seed()`](#qiskit.quantum_info.DensityMatrix.seed "qiskit.quantum_info.DensityMatrix.seed") method.

**Parameters**

**qargs** ([*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)") *or None*) – subsystems to sample measurements for, if None sample measurement of all subsystems (Default: None).

**Returns**

**the pair `(outcome, state)` where `outcome` is the**

measurement outcome string label, and `state` is the collapsed post-measurement state for the corresponding outcome.

**Return type**

[tuple](https://docs.python.org/3/library/stdtypes.html#tuple "(in Python v3.12)")

### partial\_transpose

<span id="qiskit.quantum_info.DensityMatrix.partial_transpose" />

`partial_transpose(qargs)`

Return partially transposed density matrix.

**Parameters**

**qargs** ([*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")) – The subsystems to be transposed.

**Returns**

The partially transposed density matrix.

**Return type**

[DensityMatrix](#qiskit.quantum_info.DensityMatrix "qiskit.quantum_info.DensityMatrix")

### probabilities

<span id="qiskit.quantum_info.DensityMatrix.probabilities" />

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

**Examples**

Consider a 2-qubit product state $\rho=\rho_1\otimes\rho_0$ with $\rho_1=|+\rangle\!\langle+|$, $\rho_0=|0\rangle\!\langle0|$.

```python
from qiskit.quantum_info import DensityMatrix

rho = DensityMatrix.from_label('+0')

# Probabilities for measuring both qubits
probs = rho.probabilities()
print('probs: {}'.format(probs))

# Probabilities for measuring only qubit-0
probs_qubit_0 = rho.probabilities([0])
print('Qubit-0 probs: {}'.format(probs_qubit_0))

# Probabilities for measuring only qubit-1
probs_qubit_1 = rho.probabilities([1])
print('Qubit-1 probs: {}'.format(probs_qubit_1))
```

```python
probs: [0.5 0.  0.5 0. ]
Qubit-0 probs: [1. 0.]
Qubit-1 probs: [0.5 0.5]
```

We can also permute the order of qubits in the `qargs` list to change the qubit position in the probabilities output

```python
from qiskit.quantum_info import DensityMatrix

rho = DensityMatrix.from_label('+0')

# Probabilities for measuring both qubits
probs = rho.probabilities([0, 1])
print('probs: {}'.format(probs))

# Probabilities for measuring both qubits
# but swapping qubits 0 and 1 in output
probs_swapped = rho.probabilities([1, 0])
print('Swapped probs: {}'.format(probs_swapped))
```

```python
probs: [0.5 0.  0.5 0. ]
Swapped probs: [0.5 0.5 0.  0. ]
```

### probabilities\_dict

<span id="qiskit.quantum_info.DensityMatrix.probabilities_dict" />

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

<span id="qiskit.quantum_info.DensityMatrix.purity" />

`purity()`

Return the purity of the quantum state.

### reset

<span id="qiskit.quantum_info.DensityMatrix.reset" />

`reset(qargs=None)`

Reset state or subsystems to the 0-state.

**Parameters**

**qargs** ([*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)") *or None*) – subsystems to reset, if None all subsystems will be reset to their 0-state (Default: None).

**Returns**

the reset state.

**Return type**

[DensityMatrix](#qiskit.quantum_info.DensityMatrix "qiskit.quantum_info.DensityMatrix")

**Additional Information:**

If all subsystems are reset this will return the ground state on all subsystems. If only a some subsystems are reset this function will perform evolution by the reset [`SuperOp`](qiskit.quantum_info.SuperOp "qiskit.quantum_info.SuperOp") of the reset subsystems.

### reverse\_qargs

<span id="qiskit.quantum_info.DensityMatrix.reverse_qargs" />

`reverse_qargs()`

Return a DensityMatrix with reversed subsystem ordering.

For a tensor product state this is equivalent to reversing the order of tensor product subsystems. For a density matrix $\rho = \rho_{n-1} \otimes ... \otimes \rho_0$ the returned state will be $\rho_0 \otimes ... \otimes \rho_{n-1}$.

**Returns**

the state with reversed subsystem order.

**Return type**

[DensityMatrix](#qiskit.quantum_info.DensityMatrix "qiskit.quantum_info.DensityMatrix")

### sample\_counts

<span id="qiskit.quantum_info.DensityMatrix.sample_counts" />

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

> This function *samples* measurement outcomes using the measure [`probabilities()`](#qiskit.quantum_info.DensityMatrix.probabilities "qiskit.quantum_info.DensityMatrix.probabilities") for the current state and qargs. It does not actually implement the measurement so the current state is not modified.
>
> The seed for random number generator used for sampling can be set to a fixed value by using the stats [`seed()`](#qiskit.quantum_info.DensityMatrix.seed "qiskit.quantum_info.DensityMatrix.seed") method.

### sample\_memory

<span id="qiskit.quantum_info.DensityMatrix.sample_memory" />

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

> This function *samples* measurement outcomes using the measure [`probabilities()`](#qiskit.quantum_info.DensityMatrix.probabilities "qiskit.quantum_info.DensityMatrix.probabilities") for the current state and qargs. It does not actually implement the measurement so the current state is not modified.
>
> The seed for random number generator used for sampling can be set to a fixed value by using the stats [`seed()`](#qiskit.quantum_info.DensityMatrix.seed "qiskit.quantum_info.DensityMatrix.seed") method.

### seed

<span id="qiskit.quantum_info.DensityMatrix.seed" />

`seed(value=None)`

Set the seed for the quantum state RNG.

### tensor

<span id="qiskit.quantum_info.DensityMatrix.tensor" />

`tensor(other)`

Return the tensor product state self ⊗ other.

**Parameters**

**other** ([*DensityMatrix*](#qiskit.quantum_info.DensityMatrix "qiskit.quantum_info.DensityMatrix")) – a quantum state object.

**Returns**

the tensor product operator self ⊗ other.

**Return type**

[DensityMatrix](#qiskit.quantum_info.DensityMatrix "qiskit.quantum_info.DensityMatrix")

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if other is not a quantum state.

### to\_dict

<span id="qiskit.quantum_info.DensityMatrix.to_dict" />

`to_dict(decimals=None)`

Convert the density matrix to dictionary form.

This dictionary representation uses a Ket-like notation where the dictionary keys are qudit strings for the subsystem basis vectors. If any subsystem has a dimension greater than 10 comma delimiters are inserted between integers so that subsystems can be distinguished.

**Parameters**

**decimals** (*None or* [*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – the number of decimal places to round values. If None no rounding is done (Default: None).

**Returns**

the dictionary form of the DensityMatrix.

**Return type**

[dict](https://docs.python.org/3/library/stdtypes.html#dict "(in Python v3.12)")

**Examples**

The ket-form of a 2-qubit density matrix $rho = |-\rangle\!\langle -|\otimes |0\rangle\!\langle 0|$

```python
from qiskit.quantum_info import DensityMatrix

rho = DensityMatrix.from_label('-0')
print(rho.to_dict())
```

```python
{
    '00|00': (0.4999999999999999+0j),
    '10|00': (-0.4999999999999999-0j),
    '00|10': (-0.4999999999999999+0j),
    '10|10': (0.4999999999999999+0j)
}
```

For non-qubit subsystems the integer range can go from 0 to 9. For example in a qutrit system

```python
import numpy as np
from qiskit.quantum_info import DensityMatrix

mat = np.zeros((9, 9))
mat[0, 0] = 0.25
mat[3, 3] = 0.25
mat[6, 6] = 0.25
mat[-1, -1] = 0.25
rho = DensityMatrix(mat, dims=(3, 3))
print(rho.to_dict())
```

```python
{'00|00': (0.25+0j), '10|10': (0.25+0j), '20|20': (0.25+0j), '22|22': (0.25+0j)}
```

For large subsystem dimensions delimiters are required. The following example is for a 20-dimensional system consisting of a qubit and 10-dimensional qudit.

```python
import numpy as np
from qiskit.quantum_info import DensityMatrix

mat = np.zeros((2 * 10, 2 * 10))
mat[0, 0] = 0.5
mat[-1, -1] = 0.5
rho = DensityMatrix(mat, dims=(2, 10))
print(rho.to_dict())
```

```python
{'00|00': (0.5+0j), '91|91': (0.5+0j)}
```

### to\_operator

<span id="qiskit.quantum_info.DensityMatrix.to_operator" />

`to_operator()`

Convert to Operator

**Return type**

[*Operator*](qiskit.quantum_info.Operator "qiskit.quantum_info.operators.operator.Operator")

### to\_statevector

<span id="qiskit.quantum_info.DensityMatrix.to_statevector" />

`to_statevector(atol=None, rtol=None)`

Return a statevector from a pure density matrix.

**Parameters**

*   **atol** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")) – Absolute tolerance for checking operation validity.
*   **rtol** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")) – Relative tolerance for checking operation validity.

**Returns**

**The pure density matrix’s corresponding statevector.**

Corresponds to the eigenvector of the only non-zero eigenvalue.

**Return type**

[Statevector](qiskit.quantum_info.Statevector "qiskit.quantum_info.Statevector")

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if the state is not pure.

### trace

<span id="qiskit.quantum_info.DensityMatrix.trace" />

`trace()`

Return the trace of the density matrix.

