---
title: HighLevelSynthesisPlugin
description: API reference for qiskit.transpiler.passes.synthesis.plugin.HighLevelSynthesisPlugin
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.synthesis.plugin.HighLevelSynthesisPlugin
---

# HighLevelSynthesisPlugin

<span id="qiskit.transpiler.passes.synthesis.plugin.HighLevelSynthesisPlugin" />

`HighLevelSynthesisPlugin`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/transpiler/passes/synthesis/plugin.py "view source code")

Bases: `abc.ABC`

Abstract high-level synthesis plugin class.

This abstract class defines the interface for high-level synthesis plugins.

## Methods

### run

<span id="qiskit.transpiler.passes.synthesis.plugin.HighLevelSynthesisPlugin.run" />

`abstract HighLevelSynthesisPlugin.run(high_level_object, **options)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/transpiler/passes/synthesis/plugin.py "view source code")

Run synthesis for the given Operation.

**Parameters**

*   **high\_level\_object** ([*Operation*](qiskit.circuit.Operation "qiskit.circuit.Operation")) – The Operation to synthesize to a [`DAGCircuit`](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit") object
*   **options** – The optional kwargs.

**Returns**

**The quantum circuit representation of the Operation**

when successful, and `None` otherwise.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

