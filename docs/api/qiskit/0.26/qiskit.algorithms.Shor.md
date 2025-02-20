---
title: Shor
description: API reference for qiskit.algorithms.Shor
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.Shor
---

# qiskit.algorithms.Shor

<span id="qiskit.algorithms.Shor" />

`Shor(quantum_instance=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.17/qiskit/algorithms/factorizers/shor.py "view source code")

Shor’s factoring algorithm.

Shor’s Factoring algorithm is one of the most well-known quantum algorithms and finds the prime factors for input integer $N$ in polynomial time.

Adapted from [https://github.com/ttlion/ShorAlgQiskit](https://github.com/ttlion/ShorAlgQiskit)

See also [https://arxiv.org/abs/quant-ph/0205095](https://arxiv.org/abs/quant-ph/0205095)

**Parameters**

**quantum\_instance** (`Union`\[`Backend`, `BaseBackend`, `QuantumInstance`, `None`]) – Quantum Instance or Backend

### \_\_init\_\_

<span id="qiskit.algorithms.Shor.__init__" />

`__init__(quantum_instance=None)`

**Parameters**

**quantum\_instance** (`Union`\[`Backend`, `BaseBackend`, `QuantumInstance`, `None`]) – Quantum Instance or Backend

## Methods

|                                                                                                                                   |                                                                                         |
| --------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.algorithms.Shor.__init__ "qiskit.algorithms.Shor.__init__")(\[quantum\_instance])                            | **type quantum\_instance**`Union`\[`Backend`, `BaseBackend`, `QuantumInstance`, `None`] |
| [`construct_circuit`](#qiskit.algorithms.Shor.construct_circuit "qiskit.algorithms.Shor.construct_circuit")(N\[, a, measurement]) | Construct circuit.                                                                      |
| [`factor`](#qiskit.algorithms.Shor.factor "qiskit.algorithms.Shor.factor")(N\[, a])                                               | Execute the algorithm.                                                                  |
| [`modinv`](#qiskit.algorithms.Shor.modinv "qiskit.algorithms.Shor.modinv")(a, m)                                                  | Returns the modular multiplicative inverse of a with respect to the modulus m.          |

## Attributes

|                                                                                                          |                           |
| -------------------------------------------------------------------------------------------------------- | ------------------------- |
| [`quantum_instance`](#qiskit.algorithms.Shor.quantum_instance "qiskit.algorithms.Shor.quantum_instance") | Returns quantum instance. |

### construct\_circuit

<span id="qiskit.algorithms.Shor.construct_circuit" />

`construct_circuit(N, a=2, measurement=False)`

Construct circuit.

**Parameters**

*   **N** (`int`) – The integer to be factored, has a min. value of 3.
*   **a** (`int`) – Any integer that satisfies 1 \< a \< N and gcd(a, N) = 1.
*   **measurement** (`bool`) – Boolean flag to indicate if measurement should be included in the circuit.

**Return type**

`QuantumCircuit`

**Returns**

Quantum circuit.

**Raises**

**ValueError** – Invalid N

### factor

<span id="qiskit.algorithms.Shor.factor" />

`factor(N, a=2)`

Execute the algorithm.

The input integer $N$ to be factored is expected to be odd and greater than 2. Even though this implementation is general, its capability will be limited by the capacity of the simulator/hardware. Another input integer $a$ can also be supplied, which needs to be a co-prime smaller than $N$ .

**Parameters**

*   **N** (`int`) – The integer to be factored, has a min. value of 3.
*   **a** (`int`) – Any integer that satisfies 1 \< a \< N and gcd(a, N) = 1.

**Returns**

results of the algorithm.

**Return type**

[ShorResult](qiskit.algorithms.ShorResult "qiskit.algorithms.ShorResult")

**Raises**

*   **ValueError** – Invalid input
*   [**AlgorithmError**](qiskit.algorithms.AlgorithmError "qiskit.algorithms.AlgorithmError") – If a quantum instance or backend has not been provided

### modinv

<span id="qiskit.algorithms.Shor.modinv" />

`static modinv(a, m)`

Returns the modular multiplicative inverse of a with respect to the modulus m.

**Return type**

`int`

### quantum\_instance

<span id="qiskit.algorithms.Shor.quantum_instance" />

`property quantum_instance`

Returns quantum instance.

**Return type**

`Optional`\[`QuantumInstance`]

