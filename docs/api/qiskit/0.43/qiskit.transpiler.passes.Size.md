---
title: Size
description: API reference for qiskit.transpiler.passes.Size
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.Size
---

# Size

<span id="qiskit.transpiler.passes.Size" />

`Size(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/transpiler/passes/analysis/size.py "view source code")

Bases: [`AnalysisPass`](qiskit.transpiler.AnalysisPass "qiskit.transpiler.basepasses.AnalysisPass")

Calculate the size of a DAG circuit.

The result is saved in `property_set['size']` as an integer.

**Parameters**

**recurse** – whether to allow recursion into control flow. If this is `False` (default), the pass will throw an error when control flow is present, to avoid returning a number with little meaning.

## Methods

<span id="qiskit-transpiler-passes-size-name" />

### name

<span id="qiskit.transpiler.passes.Size.name" />

`Size.name()`

Return the name of the pass.

<span id="qiskit-transpiler-passes-size-run" />

### run

<span id="qiskit.transpiler.passes.Size.run" />

`Size.run(dag)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/transpiler/passes/analysis/size.py "view source code")

Run the Size pass on dag.

## Attributes

<span id="qiskit.transpiler.passes.Size.is_analysis_pass" />

### is\_analysis\_pass

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

<span id="qiskit.transpiler.passes.Size.is_transformation_pass" />

### is\_transformation\_pass

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

