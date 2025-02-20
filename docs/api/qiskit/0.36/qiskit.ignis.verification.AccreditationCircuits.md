---
title: AccreditationCircuits
description: API reference for qiskit.ignis.verification.AccreditationCircuits
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.ignis.verification.AccreditationCircuits
---

# AccreditationCircuits

<span id="qiskit.ignis.verification.AccreditationCircuits" />

`AccreditationCircuits(target_circ, two_qubit_gate='cx', coupling_map=None, seed=None)`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.7/qiskit/ignis/verification/accreditation/circuits.py "view source code")

Bases: `object`

This class generates accreditation circuits from a target.

Implementation follows the methods from \[1]

## References

1.  S. Ferracin, T. Kapourniotis, A. Datta. *Accrediting outputs of noisy intermediate-scale quantum computing devices*, New Journal of Physics, Volume 21, 113038. (2019). [NJP 113038](https://iopscience.iop.org/article/10.1088/1367-2630/ab4fd6)

Initialize the circuit generation class parse into layers

**Parameters**

*   **target\_circ** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – a qiskit circuit to accredit
*   **two\_qubit\_gate** (*string*) – a flag as to which 2 qubit gate to compile with, can be cx or cz
*   **coupling\_map** (*list*) – some particular device topology as list of list (e.g. \[\[0,1],\[1,2],\[2,0]])
*   **seed** (*int*) – seed to the random number generator

## Methods

### generate\_circuits

<span id="qiskit.ignis.verification.AccreditationCircuits.generate_circuits" />

`AccreditationCircuits.generate_circuits(num_trap)`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.7/qiskit/ignis/verification/accreditation/circuits.py "view source code")

Generate quantum circuits for accreditation

**Parameters**

**num\_trap** (*int*) – number of trap circuits

**Returns**

**A tuple of the form**

(`circuit_list`, postp\_list\`, `v_zero`) where: circuit\_list (list): accreditation circuits postp\_list (list): strings used for classical post-processing v\_zero (int): position of target circuit

**Return type**

tuple

### target\_circuit

<span id="qiskit.ignis.verification.AccreditationCircuits.target_circuit" />

`AccreditationCircuits.target_circuit(target_circ, two_qubit_gate='cx', coupling_map=None)`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.7/qiskit/ignis/verification/accreditation/circuits.py "view source code")

Load target circuit in to class, and parse into layers

**Parameters**

*   **target\_circ** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – a qiskit circuit to accredit
*   **two\_qubit\_gate** (*string*) – a flag as to which 2 qubit gate to compile with, can be cx or cz
*   **coupling\_map** (*list*) – some particular device topology as list of list (e.g. \[\[0,1],\[1,2],\[2,0]])

