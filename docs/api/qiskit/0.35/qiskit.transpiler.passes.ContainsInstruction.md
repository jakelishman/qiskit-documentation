---
title: ContainsInstruction
description: API reference for qiskit.transpiler.passes.ContainsInstruction
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.ContainsInstruction
---

# ContainsInstruction

<span id="qiskit.transpiler.passes.ContainsInstruction" />

`ContainsInstruction(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/transpiler/passes/utils/contains_instruction.py "view source code")

Bases: `qiskit.transpiler.basepasses.AnalysisPass`

An analysis pass to detect if the DAG contains a specific instruction.

This pass takes in a single instruction name for example `'delay'` and will set the property set `contains_delay` to `True` if the DAG contains that instruction and `False` if it does not.

ContainsInstruction initializer.

**Parameters**

**instruction\_name** (*str*) – The instruction to check if it’s in the DAG. The output in the property set is set to `contains_` prefixed on the value for this parameter.

## Methods

### name

<span id="qiskit.transpiler.passes.ContainsInstruction.name" />

`ContainsInstruction.name()`

Return the name of the pass.

### run

<span id="qiskit.transpiler.passes.ContainsInstruction.run" />

`ContainsInstruction.run(dag)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/transpiler/passes/utils/contains_instruction.py "view source code")

Run the ContainsInstruction pass on dag.

## Attributes

<span id="qiskit.transpiler.passes.ContainsInstruction.is_analysis_pass" />

### is\_analysis\_pass

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

<span id="qiskit.transpiler.passes.ContainsInstruction.is_transformation_pass" />

### is\_transformation\_pass

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

