---
title: HighLevelSynthesisPlugin
description: API reference for qiskit.transpiler.passes.synthesis.plugin.HighLevelSynthesisPlugin
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.synthesis.plugin.HighLevelSynthesisPlugin
---

# HighLevelSynthesisPlugin

<span id="qiskit.transpiler.passes.synthesis.plugin.HighLevelSynthesisPlugin" />

`qiskit.transpiler.passes.synthesis.plugin.HighLevelSynthesisPlugin`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/transpiler/passes/synthesis/plugin.py "view source code")

Bases: [`ABC`](https://docs.python.org/3/library/abc.html#abc.ABC "(in Python v3.12)")

Abstract high-level synthesis plugin class.

This abstract class defines the interface for high-level synthesis plugins.

## Methods

### run

<span id="qiskit.transpiler.passes.synthesis.plugin.HighLevelSynthesisPlugin.run" />

`abstract run(high_level_object, coupling_map=None, target=None, qubits=None, **options)`

Run synthesis for the given Operation.

**Parameters**

*   **high\_level\_object** ([*Operation*](qiskit.circuit.Operation "qiskit.circuit.Operation")) – The Operation to synthesize to a [`DAGCircuit`](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit") object.
*   **coupling\_map** ([*CouplingMap*](qiskit.transpiler.CouplingMap "qiskit.transpiler.CouplingMap")) – The coupling map of the backend in case synthesis is done on a physical circuit.
*   **target** ([*Target*](qiskit.transpiler.Target "qiskit.transpiler.Target")) – A target representing the target backend.
*   **qubits** ([*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")) – List of qubits over which the operation is defined in case synthesis is done on a physical circuit.
*   **options** – Additional method-specific optional kwargs.

**Returns**

**The quantum circuit representation of the Operation**

when successful, and `None` otherwise.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

