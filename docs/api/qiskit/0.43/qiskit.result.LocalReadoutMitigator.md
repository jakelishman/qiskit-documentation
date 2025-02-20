---
title: LocalReadoutMitigator
description: API reference for qiskit.result.LocalReadoutMitigator
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.result.LocalReadoutMitigator
---

# LocalReadoutMitigator

<span id="qiskit.result.LocalReadoutMitigator" />

`LocalReadoutMitigator(assignment_matrices=None, qubits=None, backend=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/result/mitigation/local_readout_mitigator.py "view source code")

Bases: [`BaseReadoutMitigator`](qiskit.result.BaseReadoutMitigator "qiskit.result.mitigation.base_readout_mitigator.BaseReadoutMitigator")

1-qubit tensor product readout error mitigator.

Mitigates [`expectation_value()`](qiskit.result.LocalReadoutMitigator#expectation_value "qiskit.result.LocalReadoutMitigator.expectation_value") and [`quasi_probabilities()`](qiskit.result.LocalReadoutMitigator#quasi_probabilities "qiskit.result.LocalReadoutMitigator.quasi_probabilities"). The mitigator should either be calibrated using qiskit experiments, or calculated directly from the backend properties. This mitigation method should be used in case the readout errors of the qubits are assumed to be uncorrelated. For *N* qubits there are *N* mitigation matrices, each of size $2 x 2$ and the mitigation complexity is $O(2^N)$, so it is more efficient than the [`CorrelatedReadoutMitigator`](qiskit.result.CorrelatedReadoutMitigator "qiskit.result.CorrelatedReadoutMitigator") class.

Initialize a LocalReadoutMitigator

**Parameters**

*   **assignment\_matrices** (*List\[*[*ndarray*](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.25)")*] | None*) – Optional, list of single-qubit readout error assignment matrices.
*   **qubits** (*Iterable\[int] | None*) – Optional, the measured physical qubits for mitigation.
*   **backend** – Optional, backend name.

**Raises**

**QiskitError** – matrices sizes do not agree with number of qubits

## Methods

<span id="qiskit-result-localreadoutmitigator-assignment-matrix" />

### assignment\_matrix

<span id="qiskit.result.LocalReadoutMitigator.assignment_matrix" />

`LocalReadoutMitigator.assignment_matrix(qubits=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/result/mitigation/local_readout_mitigator.py "view source code")

Return the measurement assignment matrix for specified qubits.

The assignment matrix is the stochastic matrix $A$ which assigns a noisy measurement probability distribution to an ideal input measurement distribution: $P(i|j) = \langle i | A | j \rangle$.

**Parameters**

**qubits** (*List\[int] | None*) – Optional, qubits being measured for operator expval.

**Returns**

the assignment matrix A.

**Return type**

np.ndarray

<span id="qiskit-result-localreadoutmitigator-expectation-value" />

### expectation\_value

<span id="qiskit.result.LocalReadoutMitigator.expectation_value" />

`LocalReadoutMitigator.expectation_value(data, diagonal=None, qubits=None, clbits=None, shots=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/result/mitigation/local_readout_mitigator.py "view source code")

Compute the mitigated expectation value of a diagonal observable.

This computes the mitigated estimator of $\langle O \rangle = \mbox{Tr}[\rho. O]$ of a diagonal observable $O = \sum_{x\in\{0, 1\}^n} O(x)|x\rangle\!\langle x|$.

**Parameters**

*   **data** ([*Counts*](qiskit.result.Counts "qiskit.result.counts.Counts")) – Counts object
*   **diagonal** (*Callable | dict | str |* [*ndarray*](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.25)") *| None*) – Optional, the vector of diagonal values for summing the expectation value. If `None` the the default value is $[1, -1]^\otimes n$.
*   **qubits** (*Iterable\[int] | None*) – Optional, the measured physical qubits the count bitstrings correspond to. If None qubits are assumed to be $[0, ..., n-1]$.
*   **clbits** (*List\[int] | None*) – Optional, if not None marginalize counts to the specified bits.
*   **shots** (*int | None*) – the number of shots.

**Returns**

the expectation value and an upper bound of the standard deviation.

**Return type**

(float, float)

#### Additional Information:

The diagonal observable $O$ is input using the `diagonal` kwarg as a list or Numpy array $[O(0), ..., O(2^n -1)]$. If no diagonal is specified the diagonal of the Pauli operator :math\`O = mbox\{diag}(Z^\{otimes n}) = \[1, -1]^\{otimes n}\` is used. The `clbits` kwarg is used to marginalize the input counts dictionary over the specified bit-values, and the `qubits` kwarg is used to specify which physical qubits these bit-values correspond to as `circuit.measure(qubits, clbits)`.

<span id="qiskit-result-localreadoutmitigator-mitigation-matrix" />

### mitigation\_matrix

<span id="qiskit.result.LocalReadoutMitigator.mitigation_matrix" />

`LocalReadoutMitigator.mitigation_matrix(qubits=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/result/mitigation/local_readout_mitigator.py "view source code")

Return the measurement mitigation matrix for the specified qubits.

The mitigation matrix $A^{-1}$ is defined as the inverse of the [`assignment_matrix()`](qiskit.result.LocalReadoutMitigator#assignment_matrix "qiskit.result.LocalReadoutMitigator.assignment_matrix") $A$.

**Parameters**

**qubits** (*List\[int] | int | None*) – Optional, qubits being measured for operator expval. if a single int is given, it is assumed to be the index of the qubit in self.\_qubits

**Returns**

the measurement error mitigation matrix $A^{-1}$.

**Return type**

np.ndarray

<span id="qiskit-result-localreadoutmitigator-quasi-probabilities" />

### quasi\_probabilities

<span id="qiskit.result.LocalReadoutMitigator.quasi_probabilities" />

`LocalReadoutMitigator.quasi_probabilities(data, qubits=None, clbits=None, shots=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/result/mitigation/local_readout_mitigator.py "view source code")

Compute mitigated quasi probabilities value.

**Parameters**

*   **data** ([*Counts*](qiskit.result.Counts "qiskit.result.counts.Counts")) – counts object
*   **qubits** (*List\[int] | None*) – qubits the count bitstrings correspond to.
*   **clbits** (*List\[int] | None*) – Optional, marginalize counts to just these bits.
*   **shots** (*int | None*) – Optional, the total number of shots, if None shots will be calculated as the sum of all counts.

**Returns**

**A dictionary containing pairs of \[output, mean] where “output”**

is the key in the dictionaries, which is the length-N bitstring of a measured standard basis state, and “mean” is the mean of non-zero quasi-probability estimates.

**Return type**

QuasiDistibution

**Raises**

**QiskitError** – if qubit and clbit kwargs are not valid.

<span id="qiskit-result-localreadoutmitigator-stddev-upper-bound" />

### stddev\_upper\_bound

<span id="qiskit.result.LocalReadoutMitigator.stddev_upper_bound" />

`LocalReadoutMitigator.stddev_upper_bound(shots, qubits=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/result/mitigation/local_readout_mitigator.py "view source code")

Return an upper bound on standard deviation of expval estimator.

**Parameters**

*   **shots** (*int*) – Number of shots used for expectation value measurement.
*   **qubits** (*List\[int] | None*) – qubits being measured for operator expval.

**Returns**

the standard deviation upper bound.

**Return type**

float

## Attributes

<span id="qiskit.result.LocalReadoutMitigator.qubits" />

### qubits

The device qubits for this mitigator

<span id="qiskit.result.LocalReadoutMitigator.settings" />

### settings

Return settings.

