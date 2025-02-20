---
title: CNOTUnitObjective
description: API reference for qiskit.transpiler.synthesis.aqc.CNOTUnitObjective
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.synthesis.aqc.CNOTUnitObjective
---

# CNOTUnitObjective

<span id="qiskit.transpiler.synthesis.aqc.CNOTUnitObjective" />

`qiskit.transpiler.synthesis.aqc.CNOTUnitObjective(num_qubits, cnots)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.25/qiskit/transpiler/synthesis/aqc/cnot_unit_objective.py "view source code")

Bases: [`ApproximatingObjective`](qiskit.transpiler.synthesis.aqc.ApproximatingObjective "qiskit.transpiler.synthesis.aqc.approximate.ApproximatingObjective"), [`ABC`](https://docs.python.org/3/library/abc.html#abc.ABC "(in Python v3.12)")

A base class for a problem definition based on CNOT unit. This class may have different subclasses for objective and gradient computations.

**Parameters**

*   **num\_qubits** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – number of qubits.
*   **cnots** (*np.ndarray*) – a CNOT structure to be used in the optimization procedure.

## Attributes

<span id="qiskit.transpiler.synthesis.aqc.CNOTUnitObjective.num_cnots" />

### num\_cnots

Returns: A number of CNOT units to be used by the approximate circuit.

<span id="qiskit.transpiler.synthesis.aqc.CNOTUnitObjective.num_thetas" />

### num\_thetas

Returns: Number of parameters (angles) of rotation gates in this circuit.

<span id="qiskit.transpiler.synthesis.aqc.CNOTUnitObjective.target_matrix" />

### target\_matrix

Returns: a matrix being approximated

