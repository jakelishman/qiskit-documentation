---
title: MinimumPoint
description: API reference for qiskit.transpiler.passes.MinimumPoint
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.MinimumPoint
---

# MinimumPoint

<span id="qiskit.transpiler.passes.MinimumPoint" />

`MinimumPoint(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/transpiler/passes/utils/minimum_point.py "view source code")

Bases: [`TransformationPass`](qiskit.transpiler.TransformationPass "qiskit.transpiler.basepasses.TransformationPass")

Check if the DAG has reached a relative semi-stable point over previous runs

This pass is similar to the [`FixedPoint`](qiskit.transpiler.passes.FixedPoint "qiskit.transpiler.passes.FixedPoint") transpiler pass and is intended primarily to be used to set a loop break condition in the property set. However, unlike the [`FixedPoint`](qiskit.transpiler.passes.FixedPoint "qiskit.transpiler.passes.FixedPoint") class which only sets the condition if 2 consecutive runs have the same value property set value this pass is designed to find a local minimum and use that instead. This pass is designed for an optimization loop where a fixed point may never get reached (for example if synthesis is used and there are multiple equivalent outputs for some cases).

This pass will track the state of fields in the property set over its past executions and set a boolean field when either a fixed point is reached over the backtracking depth or selecting the minimum value found if the backtracking depth is reached. To do this it stores a deep copy of the current minimum DAG in the property set and when `backtrack_depth` number of executions is reached since the last minimum the output dag is set to that copy of the earlier minimum.

Fields used by this pass in the property set are (all relative to the `prefix` argument):

*   `{prefix}_minimum_point_state` - Used to track the state of the minimpoint search

*   **`{prefix}_minimum_point` - This value gets set to `True` when either a fixed point**

    is reached over the `backtrack_depth` executions, or `backtrack_depth` was exceeded and an earlier minimum is restored.

Initialize an instance of this pass

**Parameters**

*   **property\_set\_list** (*list*) – A list of property set keys that will be used to evaluate the local minimum. The values of these property set keys will be used as a tuple for comparison
*   **prefix** (*str*) – The prefix to use for the property set key that is used for tracking previous evaluations
*   **backtrack\_depth** (*int*) – The maximum number of entries to store. If this number is reached and the next iteration doesn’t have a decrease in the number of values the minimum of the previous n will be set as the output dag and `minimum_point` will be set to `True` in the property set

## Methods

<span id="qiskit-transpiler-passes-minimumpoint-name" />

### name

<span id="qiskit.transpiler.passes.MinimumPoint.name" />

`MinimumPoint.name()`

Return the name of the pass.

<span id="qiskit-transpiler-passes-minimumpoint-run" />

### run

<span id="qiskit.transpiler.passes.MinimumPoint.run" />

`MinimumPoint.run(dag)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/transpiler/passes/utils/minimum_point.py "view source code")

Run the MinimumPoint pass on dag.

## Attributes

<span id="qiskit.transpiler.passes.MinimumPoint.is_analysis_pass" />

### is\_analysis\_pass

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

<span id="qiskit.transpiler.passes.MinimumPoint.is_transformation_pass" />

### is\_transformation\_pass

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

