---
title: TensoredExpvalMeasMitigator
description: API reference for qiskit.ignis.mitigation.TensoredExpvalMeasMitigator
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.ignis.mitigation.TensoredExpvalMeasMitigator
---

# qiskit.ignis.mitigation.TensoredExpvalMeasMitigator

<span id="qiskit.ignis.mitigation.TensoredExpvalMeasMitigator" />

`TensoredExpvalMeasMitigator(amats)`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.6/qiskit/ignis/mitigation/expval/tensored_mitigator.py "view source code")

1-qubit tensor product measurement error mitigator.

This class can be used with the [`qiskit.ignis.mitigation.expectation_value()`](qiskit.ignis.mitigation.expectation_value "qiskit.ignis.mitigation.expectation_value") function to apply measurement error mitigation of local single-qubit measurement errors. Expectation values can also be computed directly using the [`expectation_value()`](qiskit.ignis.mitigation.expectation_value "qiskit.ignis.mitigation.expectation_value") method.

For measurement mitigation to be applied the mitigator should be calibrated using the [`qiskit.ignis.mitigation.expval_meas_mitigator_circuits()`](qiskit.ignis.mitigation.expval_meas_mitigator_circuits "qiskit.ignis.mitigation.expval_meas_mitigator_circuits") function and [`qiskit.ignis.mitigation.ExpvalMeasMitigatorFitter`](qiskit.ignis.mitigation.ExpvalMeasMitigatorFitter "qiskit.ignis.mitigation.ExpvalMeasMitigatorFitter") class with the `'tensored'` mitigation method.

Initialize a TensorMeasurementMitigator

**Parameters**

**amats** (`List`\[`ndarray`]) – list of single-qubit readout error assignment matrices.

### \_\_init\_\_

<span id="qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.__init__" />

`__init__(amats)`

Initialize a TensorMeasurementMitigator

**Parameters**

**amats** (`List`\[`ndarray`]) – list of single-qubit readout error assignment matrices.

## Methods

|                                                                                                                                                                                                     |                                                                       |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| [`__init__`](#qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.__init__ "qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.__init__")(amats)                                                   | Initialize a TensorMeasurementMitigator                               |
| [`assignment_fidelity`](#qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.assignment_fidelity "qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.assignment_fidelity")(\[qubits])              | Return the measurement assignment fidelity on the specified qubits.   |
| [`assignment_matrix`](#qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.assignment_matrix "qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.assignment_matrix")(\[qubits])                    | Return the measurement assignment matrix for specified qubits.        |
| [`expectation_value`](#qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.expectation_value "qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.expectation_value")(counts\[, diagonal, …])       | Compute the mitigated expectation value of a diagonal observable.     |
| [`mitigation_matrix`](#qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.mitigation_matrix "qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.mitigation_matrix")(\[qubits])                    | Return the measurement mitigation matrix for the specified qubits.    |
| [`mitigation_overhead`](#qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.mitigation_overhead "qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.mitigation_overhead")(\[qubits])              | Return the mitigation overhead for expectation value estimation.      |
| [`plot_assignment_matrix`](#qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.plot_assignment_matrix "qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.plot_assignment_matrix")(\[qubits, ax]) | Matrix plot of the readout error assignment matrix.                   |
| [`plot_mitigation_matrix`](#qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.plot_mitigation_matrix "qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.plot_mitigation_matrix")(\[qubits, ax]) | Matrix plot of the readout error mitigation matrix.                   |
| [`required_shots`](#qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.required_shots "qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.required_shots")(delta\[, qubits])                      | Return the number of shots required for expectation value estimation. |
| [`stddev_upper_bound`](#qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.stddev_upper_bound "qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.stddev_upper_bound")(\[shots, qubits])          | Return an upper bound on standard deviation of expval estimator.      |

### assignment\_fidelity

<span id="qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.assignment_fidelity" />

`assignment_fidelity(qubits=None)`

Return the measurement assignment fidelity on the specified qubits.

The assignment fidelity on N-qubits is defined as $\sum_{x\in\{0, 1\}^n} P(x|x) / 2^n$, where $P(x|x) = \rangle x|A|x\langle$, and $A$ is the [`assignment_matrix()`](#qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.assignment_matrix "qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.assignment_matrix").

**Parameters**

**qubits** (`Optional`\[`List`\[`int`]]) – Optional, qubits being measured for operator expval.

**Returns**

the assignment fidelity.

**Return type**

float

### assignment\_matrix

<span id="qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.assignment_matrix" />

`assignment_matrix(qubits=None)`

Return the measurement assignment matrix for specified qubits.

The assignment matrix is the stochastic matrix $A$ which assigns a noisy measurement probability distribution to an ideal input measurement distribution: $P(i|j) = \langle i | A | j \rangle$.

**Parameters**

**qubits** (`Optional`\[`List`\[`int`]]) – Optional, qubits being measured for operator expval.

**Returns**

the assignment matrix A.

**Return type**

np.ndarray

### expectation\_value

<span id="qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.expectation_value" />

`expectation_value(counts, diagonal=None, qubits=None, clbits=None)`

Compute the mitigated expectation value of a diagonal observable.

This computes the mitigated estimator of $\langle O \rangle = \mbox{Tr}[\rho. O]$ of a diagonal observable $O = \sum_{x\in\{0, 1\}^n} O(x)|x\rangle\!\langle x|$.

**Parameters**

*   **counts** (`Dict`) – counts object
*   **diagonal** (`Optional`\[`ndarray`]) – Optional, the vector of diagonal values for summing the expectation value. If `None` the the default value is $[1, -1]^\otimes n$.
*   **qubits** (`Optional`\[`List`\[`int`]]) – Optional, the measured physical qubits the count bitstrings correspond to. If None qubits are assumed to be $[0, ..., n-1]$.
*   **clbits** (`Optional`\[`List`\[`int`]]) – Optional, if not None marginalize counts to the specified bits.

**Returns**

the expectation value and standard deviation.

**Return type**

(float, float)

**Additional Information:**

The diagonal observable $O$ is input using the `diagonal` kwarg as a list or Numpy array $[O(0), ..., O(2^n -1)]$. If no diagonal is specified the diagonal of the Pauli operator :math\`O = mbox\{diag}(Z^\{otimes n}) = \[1, -1]^\{otimes n}\` is used.

The `clbits` kwarg is used to marginalize the input counts dictionary over the specified bit-values, and the `qubits` kwarg is used to specify which physical qubits these bit-values correspond to as `circuit.measure(qubits, clbits)`.

### mitigation\_matrix

<span id="qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.mitigation_matrix" />

`mitigation_matrix(qubits=None)`

Return the measurement mitigation matrix for the specified qubits.

The mitigation matrix $A^{-1}$ is defined as the inverse of the [`assignment_matrix()`](#qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.assignment_matrix "qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.assignment_matrix") $A$.

**Parameters**

**qubits** (`Optional`\[`List`\[`int`]]) – Optional, qubits being measured for operator expval.

**Returns**

the measurement error mitigation matrix $A^{-1}$.

**Return type**

np.ndarray

### mitigation\_overhead

<span id="qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.mitigation_overhead" />

`mitigation_overhead(qubits=None)`

Return the mitigation overhead for expectation value estimation.

This is the multiplicative factor of extra shots required for estimating a mitigated expectation value with the same accuracy as an unmitigated expectation value.

**Parameters**

**qubits** (`Optional`\[`List`\[`int`]]) – Optional, qubits being measured for operator expval.

**Returns**

the mitigation overhead factor.

**Return type**

int

### plot\_assignment\_matrix

<span id="qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.plot_assignment_matrix" />

`plot_assignment_matrix(qubits=None, ax=None)`

Matrix plot of the readout error assignment matrix.

**Parameters**

*   **qubits** (*list(int)*) – Optional, qubits being measured for operator expval.
*   **ax** (*axes*) – Optional. Axes object to add plot to.

**Returns**

the figure axes object.

**Return type**

plt.axes

**Raises**

**ImportError** – if matplotlib is not installed.

### plot\_mitigation\_matrix

<span id="qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.plot_mitigation_matrix" />

`plot_mitigation_matrix(qubits=None, ax=None)`

Matrix plot of the readout error mitigation matrix.

**Parameters**

*   **qubits** (*list(int)*) – Optional, qubits being measured for operator expval.
*   **ax** (*plt.axes*) – Optional. Axes object to add plot to.

**Returns**

the figure axes object.

**Return type**

plt.axes

**Raises**

**ImportError** – if matplotlib is not installed.

### required\_shots

<span id="qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.required_shots" />

`required_shots(delta, qubits=None)`

Return the number of shots required for expectation value estimation.

This is the number of shots required so that $|\langle O \rangle_{est} - \langle O \rangle_{true}| < \delta$ with high probability (at least 2/3) and is given by $4\delta^2 \Gamma^2$ where $\Gamma^2$ is the [`mitigation_overhead()`](#qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.mitigation_overhead "qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.mitigation_overhead").

**Parameters**

*   **delta** (`float`) – Error tolerance for expectation value estimator.
*   **qubits** (`Optional`\[`List`\[`int`]]) – Optional, qubits being measured for operator expval.

**Returns**

the required shots.

**Return type**

int

### stddev\_upper\_bound

<span id="qiskit.ignis.mitigation.TensoredExpvalMeasMitigator.stddev_upper_bound" />

`stddev_upper_bound(shots=1, qubits=None)`

Return an upper bound on standard deviation of expval estimator.

**Parameters**

*   **shots** (`int`) – Number of shots used for expectation value measurement.
*   **qubits** (`Optional`\[`List`\[`int`]]) – qubits being measured for operator expval.

**Returns**

the standard deviation upper bound.

**Return type**

float

