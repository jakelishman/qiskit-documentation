---
title: AlignMeasures
description: API reference for qiskit.transpiler.passes.AlignMeasures
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.passes.AlignMeasures
---

# AlignMeasures

<span id="qiskit.transpiler.passes.AlignMeasures" />

`AlignMeasures(alignment=1)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/transpiler/passes/scheduling/instruction_alignment.py "view source code")

Bases: `qiskit.transpiler.basepasses.TransformationPass`

Measurement alignment.

This is a control electronics aware optimization pass.

In many quantum computing architectures gates (instructions) are implemented with shaped analog stimulus signals. These signals are digitally stored in the waveform memory of the control electronics and converted into analog voltage signals by electronic components called digital to analog converters (DAC).

In a typical hardware implementation of superconducting quantum processors, a single qubit instruction is implemented by a microwave signal with the duration of around several tens of ns with a per-sample time resolution of \~0.1-10ns, as reported by `backend.configuration().dt`. In such systems requiring higher DAC bandwidth, control electronics often defines a pulse granularity, in other words a data chunk, to allow the DAC to perform the signal conversion in parallel to gain the bandwidth.

Measurement alignment is required if a backend only allows triggering `measure` instructions at a certain multiple value of this pulse granularity. This value is usually provided by `backend.configuration().timing_constraints`.

In Qiskit SDK, the duration of delay can take arbitrary value in units of `dt`, thus circuits involving delays may violate the above alignment constraint (i.e. misalignment). This pass shifts measurement instructions to a new time position to fix the misalignment, by inserting extra delay right before the measure instructions. The input of this pass should be scheduled [`DAGCircuit`](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit"), thus one should select one of the scheduling passes ([`ALAPSchedule`](qiskit.transpiler.passes.ALAPSchedule "qiskit.transpiler.passes.ALAPSchedule") or `ASAPSchedule`) before calling this.

## Examples

We assume executing the following circuit on a backend with `alignment=16`.

```python
     ┌───┐┌────────────────┐┌─┐
q_0: ┤ X ├┤ Delay(100[dt]) ├┤M├
     └───┘└────────────────┘└╥┘
c: 1/════════════════════════╩═
                             0
```

Note that delay of 100 dt induces a misalignment of 4 dt at the measurement. This pass appends an extra 12 dt time shift to the input circuit.

```python
     ┌───┐┌────────────────┐┌─┐
q_0: ┤ X ├┤ Delay(112[dt]) ├┤M├
     └───┘└────────────────┘└╥┘
c: 1/════════════════════════╩═
                             0
```

This pass always inserts a positive delay before measurements rather than reducing other delays.

## Notes

The Backend may allow users to execute circuits violating the alignment constraint. However, it may return meaningless measurement data mainly due to the phase error.

Create new pass.

**Parameters**

**alignment** (`int`) – Integer number representing the minimum time resolution to trigger measure instruction in units of `dt`. This value depends on the control electronics of your quantum processor.

## Methods

### name

<span id="qiskit.transpiler.passes.AlignMeasures.name" />

`AlignMeasures.name()`

Return the name of the pass.

### run

<span id="qiskit.transpiler.passes.AlignMeasures.run" />

`AlignMeasures.run(dag)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/transpiler/passes/scheduling/instruction_alignment.py "view source code")

Run the measurement alignment pass on dag.

**Parameters**

**dag** ([*DAGCircuit*](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")) – DAG to be checked.

**Returns**

DAG with consistent timing and op nodes annotated with duration.

**Return type**

[DAGCircuit](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")

**Raises**

[**TranspilerError**](qiskit.transpiler.TranspilerError "qiskit.transpiler.TranspilerError") – If circuit is not scheduled.

## Attributes

<span id="qiskit.transpiler.passes.AlignMeasures.is_analysis_pass" />

### is\_analysis\_pass

Check if the pass is an analysis pass.

If the pass is an AnalysisPass, that means that the pass can analyze the DAG and write the results of that analysis in the property set. Modifications on the DAG are not allowed by this kind of pass.

<span id="qiskit.transpiler.passes.AlignMeasures.is_transformation_pass" />

### is\_transformation\_pass

Check if the pass is a transformation pass.

If the pass is a TransformationPass, that means that the pass can manipulate the DAG, but cannot modify the property set (but it can be read).

