---
title: TensoredFilter
description: API reference for qiskit.ignis.mitigation.TensoredFilter
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.ignis.mitigation.TensoredFilter
---

# TensoredFilter

<span id="qiskit.ignis.mitigation.TensoredFilter" />

`TensoredFilter(cal_matrices, substate_labels_list, mit_pattern)`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.7/qiskit/ignis/mitigation/measurement/filters.py "view source code")

Bases: `object`

Tensored measurement error mitigation filter.

Produced from a tensored measurement calibration fitter and can be applied to data.

Initialize a tensored measurement error mitigation filter using the cal\_matrices from a tensored measurement calibration fitter. A simple usage this class is explained \[here] ([https://qiskit.org/documentation/tutorials/noise/3\_measurement\_error\_mitigation.html](https://qiskit.org/documentation/tutorials/noise/3_measurement_error_mitigation.html)).

**Parameters**

*   **cal\_matrices** (`matrix`) – the calibration matrices for applying the correction.
*   **substate\_labels\_list** (`list`) – for each calibration matrix a list of the states (as strings, states in the subspace)
*   **mit\_pattern** (`list`) – for each calibration matrix a list of the logical qubit indices (as int, states in the subspace)

## Methods

### apply

<span id="qiskit.ignis.mitigation.TensoredFilter.apply" />

`TensoredFilter.apply(raw_data, method='least_squares', meas_layout=None)`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.7/qiskit/ignis/mitigation/measurement/filters.py "view source code")

Apply the calibration matrices to results.

**Parameters**

*   **raw\_data** (*dict or* [*Result*](qiskit.result.Result "qiskit.result.Result")) –

    The data to be corrected. Can be in one of two forms:

    *   A counts dictionary from results.get\_counts
    *   A Qiskit Result

*   **method** (*str*) –

    fitting method. The following methods are supported:

    *   **’pseudo\_inverse’: direct inversion of the cal matrices.**

        Mitigated counts can contain negative values and the sum of counts would not equal to the shots. Mitigation is conducted qubit wise: For each qubit, mitigate the whole counts using the calibration matrices which affect the corresponding qubit. For example, assume we are mitigating the 3rd bit of the 4-bit counts using ‘2 imes 2’ calibration matrix A\_3. When mitigating the count of ‘0110’ in this step, the following formula is applied: count\[‘0110’] = A\_3^\{-1}\[1, 0]\*count\[‘0100’] + A\_3^\{-1}\[1, 1]\*count\[‘0110’].

        The total time complexity of this method is O(m2^\{n + t}), where n is the size of calibrated qubits, m is the number of sets in mit\_pattern, and t is the size of largest set of mit\_pattern. If the mit\_pattern is shaped like \[\[0], \[1], \[2], …, \[n-1]], which corresponds to the tensor product noise model without cross-talk, then the time complexity would be O(n2^n). If the mit\_pattern is shaped like \[\[0, 1, 2, …, n-1]], which exactly corresponds to the complete error mitigation, then the time complexity would be O(2^(n+n)) = O(4^n).

    *   **’least\_squares’: constrained to have physical probabilities.**

        Instead of directly applying inverse calibration matrices, this method solve a constrained optimization problem to find the closest probability vector to the result from ‘pseudo\_inverse’ method. Sequential least square quadratic programming (SLSQP) is used in the internal process. Every updating step in SLSQP takes O(m2^\{n+t}) time. Since this method is using the SLSQP optimization over the vector with lenght 2^n, the mitigation for 8 bit counts with the mit\_pattern = \[\[0], \[1], \[2], …, \[n-1]] would take 10 seconds or more.

    *   If None, ‘least\_squares’ is used.

*   **meas\_layout** (*list of int*) –

    the mapping from classical registers to qubits

    *   **If you measure qubit 2 to clbit 0, 0 to 1, and 1 to 2,**

        the list becomes \[2, 0, 1]

    *   If None, flatten(mit\_pattern) is used.

**Returns**

The corrected data in the same form as raw\_data

**Return type**

dict or [Result](qiskit.result.Result "qiskit.result.Result")

**Raises**

**QiskitError** – if raw\_data is not in a one of the defined forms.

### compute\_index\_of\_cal\_mat

<span id="qiskit.ignis.mitigation.TensoredFilter.compute_index_of_cal_mat" />

`TensoredFilter.compute_index_of_cal_mat(state, pos_qubits, indices)`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.7/qiskit/ignis/mitigation/measurement/filters.py "view source code")

Return the index of (pseudo inverse) calibration matrix for the input quantum state

**Return type**

`int`

### flip\_state

<span id="qiskit.ignis.mitigation.TensoredFilter.flip_state" />

`TensoredFilter.flip_state(state, mat_index, flip_poses)`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.7/qiskit/ignis/mitigation/measurement/filters.py "view source code")

Flip the state according to the chosen qubit positions

**Return type**

`str`

## Attributes

<span id="qiskit.ignis.mitigation.TensoredFilter.cal_matrices" />

### cal\_matrices

Return cal\_matrices.

<span id="qiskit.ignis.mitigation.TensoredFilter.nqubits" />

### nqubits

Return the number of qubits. See also MeasurementFilter.apply()

<span id="qiskit.ignis.mitigation.TensoredFilter.qubit_list_sizes" />

### qubit\_list\_sizes

Return \_qubit\_list\_sizes.

<span id="qiskit.ignis.mitigation.TensoredFilter.substate_labels_list" />

### substate\_labels\_list

Return \_substate\_labels\_list

