---
title: VF2Layout
description: API reference for qiskit.transpiler.passes.VF2Layout
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.VF2Layout
---

# VF2Layout

<span id="qiskit.transpiler.passes.VF2Layout" />

`VF2Layout(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/transpiler/passes/layout/vf2_layout.py "view source code")

Bases: [`qiskit.transpiler.basepasses.AnalysisPass`](qiskit.transpiler.AnalysisPass "qiskit.transpiler.basepasses.AnalysisPass")

A pass for choosing a Layout of a circuit onto a Coupling graph, as a a subgraph isomorphism problem, solved by VF2++.

If a solution is found that means there is a “perfect layout” and that no further swap mapping or routing is needed. If a solution is found the layout will be set in the property set as `property_set['layout']`. However, if no solution is found, no `property_set['layout']` is set. The stopping reason is set in `property_set['VF2Layout_stop_reason']` in all the cases and will be one of the values enumerated in `VF2LayoutStopReason` which has the following values:

> *   `"solution found"`: If a perfect layout was found.
> *   `"nonexistent solution"`: If no perfect layout was found.
> *   `">2q gates in basis"`: If VF2Layout can’t work with basis

Initialize a `VF2Layout` pass instance

**Parameters**

*   **coupling\_map** ([*CouplingMap*](qiskit.transpiler.CouplingMap "qiskit.transpiler.CouplingMap")) – Directed graph representing a coupling map.
*   **strict\_direction** (*bool*) – If True, considers the direction of the coupling map. Default is False.
*   **seed** (*int*) – Sets the seed of the PRNG. -1 Means no node shuffling.
*   **call\_limit** (*int*) – The number of state visits to attempt in each execution of VF2.
*   **time\_limit** (*float*) – The total time limit in seconds to run `VF2Layout`
*   **properties** ([*BackendProperties*](qiskit.providers.models.BackendProperties "qiskit.providers.models.BackendProperties")) – The backend properties for the backend. If [`readout_error()`](qiskit.providers.models.BackendProperties#readout_error "qiskit.providers.models.BackendProperties.readout_error") is available it is used to score the layout.
*   **max\_trials** (*int*) – The maximum number of trials to run VF2 to find a layout. If this is not specified the number of trials will be limited based on the number of edges in the interaction graph or the coupling graph (whichever is larger) if no other limits are set. If set to a value \<= 0 no limit on the number of trials will be set.
*   **target** ([*Target*](qiskit.transpiler.Target "qiskit.transpiler.Target")) – A target representing the backend device to run `VF2Layout` on. If specified it will supersede a set value for `properties` and `coupling_map`.

**Raises**

**TypeError** – At runtime, if neither `coupling_map` or `target` are provided.

## Methods

### name

<span id="qiskit.transpiler.passes.VF2Layout.name" />

`VF2Layout.name()`

Return the name of the pass.

### run

<span id="qiskit.transpiler.passes.VF2Layout.run" />

`VF2Layout.run(dag)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/transpiler/passes/layout/vf2_layout.py "view source code")

run the layout method

## Attributes

<span id="qiskit.transpiler.passes.VF2Layout.is_analysis_pass" />

### is\_analysis\_pass

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

<span id="qiskit.transpiler.passes.VF2Layout.is_transformation_pass" />

### is\_transformation\_pass

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

