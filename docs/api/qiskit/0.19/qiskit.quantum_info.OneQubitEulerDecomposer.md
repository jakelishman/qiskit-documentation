---
title: OneQubitEulerDecomposer
description: API reference for qiskit.quantum_info.OneQubitEulerDecomposer
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.quantum_info.OneQubitEulerDecomposer
---

# OneQubitEulerDecomposer

<span id="qiskit.quantum_info.OneQubitEulerDecomposer" />

`OneQubitEulerDecomposer(basis='U3')`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/synthesis/one_qubit_decompose.py "view source code")

A class for decomposing 1-qubit unitaries into Euler angle rotations.

The resulting decomposition is parameterized by 3 Euler rotation angle parameters $(\theta, \phi, \lambda)$, and a phase parameter $\gamma$. The value of the parameters for an input unitary depends on the decomposition basis. Allowed bases and the resulting circuits are shown in the following table. Note that for the non-Euler bases (U3, U1X, RR), the ZYZ euler parameters are used.

| Basis | Euler Angle Basis              | Decomposition Circuit                                                                                                    |
| ----- | ------------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| ‘ZYZ’ | $Z(\phi) Y(\theta) Z(\lambda)$ | $e^{i\gamma} R_Z(\phi).R_Y(\theta).R_Z(\lambda)$                                                                         |
| ‘ZXZ’ | $Z(\phi) X(\theta) Z(\lambda)$ | $e^{i\gamma} R_Z(\phi).R_X(\theta).R_Z(\lambda)$                                                                         |
| ‘XYX’ | $X(\phi) Y(\theta) X(\lambda)$ | $e^{i\gamma} R_X(\phi).R_Y(\theta).R_X(\lambda)$                                                                         |
| ‘U3’  | $Z(\phi) Y(\theta) Z(\lambda)$ | $e^{i\gamma}{2}\right)\right)} U_3(\theta,\phi,\lambda)$                                                                 |
| ‘U1X’ | $Z(\phi) Y(\theta) Z(\lambda)$ | $e^{i \gamma} U_1(\phi+\pi).R_X\left(\frac{\pi}{2}\right).$ $U_1(\theta+\pi).R_X\left(\frac{\pi}{2}\right).U_1(\lambda)$ |
| ‘RR’  | $Z(\phi) Y(\theta) Z(\lambda)$ | $e^{i\gamma} R\left(-\pi,\frac{\phi-\lambda+\pi}{2}\right).$ $R\left(\theta+\pi,\frac{\pi}{2}-\lambda\right)$            |

Initialize decomposer

Supported bases are: ‘U3’, ‘U1X’, ‘RR’, ‘ZYZ’, ‘ZXZ’, ‘XYX’.

**Parameters**

**basis** (*str*) – the decomposition basis \[Default: ‘U3’]

**Raises**

**QiskitError** – If input basis is not recognized.

## Attributes

### basis

The decomposition basis.

## Methods

### \_\_call\_\_

<span id="qiskit.quantum_info.OneQubitEulerDecomposer.__call__" />

`OneQubitEulerDecomposer.__call__(unitary, simplify=True, atol=1e-12)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/synthesis/one_qubit_decompose.py "view source code")

Decompose single qubit gate into a circuit.

**Parameters**

*   **unitary** ([*Operator*](qiskit.quantum_info.Operator "qiskit.quantum_info.Operator")  *or*[*Gate*](qiskit.circuit.Gate "qiskit.circuit.Gate") *or array*) – 1-qubit unitary matrix
*   **simplify** (*bool*) – reduce gate count in decomposition \[Default: True].
*   **atol** (*bool*) – absolute tolerance for checking angles when simplifing returnd circuit \[Default: 1e-12].

**Returns**

the decomposed single-qubit gate circuit

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if input is invalid or synthesis fails.

### angles

<span id="qiskit.quantum_info.OneQubitEulerDecomposer.angles" />

`OneQubitEulerDecomposer.angles(unitary)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/synthesis/one_qubit_decompose.py "view source code")

Return the Euler angles for input array.

**Parameters**

**unitary** (*np.ndarray*) – 2x2 unitary matrix.

**Returns**

(theta, phi, lambda).

**Return type**

tuple

### angles\_and\_phase

<span id="qiskit.quantum_info.OneQubitEulerDecomposer.angles_and_phase" />

`OneQubitEulerDecomposer.angles_and_phase(unitary)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/quantum_info/synthesis/one_qubit_decompose.py "view source code")

Return the Euler angles and phase for input array.

**Parameters**

**unitary** (*np.ndarray*) – 2x2 unitary matrix.

**Returns**

(theta, phi, lambda, phase).

**Return type**

tuple

