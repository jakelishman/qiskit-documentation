---
title: CompleteMeasFitter
description: API reference for qiskit.utils.mitigation.CompleteMeasFitter
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.utils.mitigation.CompleteMeasFitter
---

# CompleteMeasFitter

<span id="qiskit.utils.mitigation.CompleteMeasFitter" />

`CompleteMeasFitter(results, state_labels, qubit_list=None, circlabel='')`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/utils/mitigation/fitters.py "view source code")

Bases: `object`

Measurement correction fitter for a full calibration

Initialize a measurement calibration matrix from the results of running the circuits returned by measurement\_calibration\_circuits

A wrapper for the tensored fitter

<Admonition title="Warning" type="caution">
  This class is not a public API. The internals are not stable and will likely change. It is used solely for the `measurement_error_mitigation_cls` kwarg of the [`QuantumInstance`](qiskit.utils.QuantumInstance "qiskit.utils.QuantumInstance") class’s constructor (as a class not an instance). Anything outside of that usage does not have the normal user-facing API stability.
</Admonition>

**Parameters**

*   **results** – the results of running the measurement calibration circuits. If this is None the user will set a calibration matrix later.
*   **state\_labels** (`List`\[`str`]) – list of calibration state labels returned from measurement\_calibration\_circuits. The output matrix will obey this ordering.
*   **qubit\_list** (`Optional`\[`List`\[`int`]]) – List of the qubits (for reference and if the subset is needed). If None, the qubit\_list will be created according to the length of state\_labels\[0].
*   **circlabel** (`str`) – if the qubits were labeled.

## Methods

### add\_data

<span id="qiskit.utils.mitigation.CompleteMeasFitter.add_data" />

`CompleteMeasFitter.add_data(new_results, rebuild_cal_matrix=True)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/utils/mitigation/fitters.py "view source code")

Add measurement calibration data

**Parameters**

*   **new\_results** (*list or* [*qiskit.result.Result*](qiskit.result.Result "qiskit.result.Result")) – a single result or list of result objects.
*   **rebuild\_cal\_matrix** (*bool*) – rebuild the calibration matrix

### readout\_fidelity

<span id="qiskit.utils.mitigation.CompleteMeasFitter.readout_fidelity" />

`CompleteMeasFitter.readout_fidelity(label_list=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/utils/mitigation/fitters.py "view source code")

Based on the results, output the readout fidelity which is the normalized trace of the calibration matrix

**Parameters**

**label\_list** (*bool*) – If None, returns the average assignment fidelity of a single state. Otherwise it returns the assignment fidelity to be in any one of these states averaged over the second index.

**Returns**

readout fidelity (assignment fidelity)

**Return type**

numpy.array

#### Additional Information:

The on-diagonal elements of the calibration matrix are the probabilities of measuring state ‘x’ given preparation of state ‘x’ and so the normalized trace is the average assignment fidelity

### subset\_fitter

<span id="qiskit.utils.mitigation.CompleteMeasFitter.subset_fitter" />

`CompleteMeasFitter.subset_fitter(qubit_sublist=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/utils/mitigation/fitters.py "view source code")

Return a fitter object that is a subset of the qubits in the original list.

**Parameters**

**qubit\_sublist** (*list*) – must be a subset of qubit\_list

**Returns**

**A new fitter that has the calibration for a**

subset of qubits

**Return type**

[CompleteMeasFitter](qiskit.ignis.mitigation.CompleteMeasFitter "qiskit.ignis.mitigation.CompleteMeasFitter")

**Raises**

**QiskitError** – If the calibration matrix is not initialized

## Attributes

<span id="qiskit.utils.mitigation.CompleteMeasFitter.cal_matrix" />

### cal\_matrix

Return cal\_matrix.

<span id="qiskit.utils.mitigation.CompleteMeasFitter.filter" />

### filter

Return a measurement filter using the cal matrix.

<span id="qiskit.utils.mitigation.CompleteMeasFitter.qubit_list" />

### qubit\_list

Return list of qubits.

<span id="qiskit.utils.mitigation.CompleteMeasFitter.state_labels" />

### state\_labels

Return state\_labels.

