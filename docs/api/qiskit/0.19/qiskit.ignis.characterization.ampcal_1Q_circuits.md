---
title: ampcal_1Q_circuits
description: API reference for qiskit.ignis.characterization.ampcal_1Q_circuits
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.ignis.characterization.ampcal_1Q_circuits
---

# ampcal\_1Q\_circuits

<span id="qiskit.ignis.characterization.ampcal_1Q_circuits" />

`ampcal_1Q_circuits(max_reps, qubits)`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.3/qiskit/ignis/characterization/gates/circuits.py "view source code")

Generates circuit for measuring the amplitude error of the single qubit gates

The U2 gate is repeatedly applied (in groups of 2) and we look at the population of the qubit in the xy axis (amplitude erorr amplification sequence)

Y90-(Y90-Y90)^n

**Parameters**

*   **max\_reps** (*int*) – the maximum number of repetitions. Circuits will increment by 1 rep up to max\_rep
*   **qubits** (*list*) – a list of integers indices of the qubits to perform the calibration on

**Returns**

**A tuple of the form (`circuits`, `xdata`) where**

`circuits` is a list of QuantumCircuit and `xdata` is a list of gate repetitions (number of u2 gates)

**Return type**

tuple

