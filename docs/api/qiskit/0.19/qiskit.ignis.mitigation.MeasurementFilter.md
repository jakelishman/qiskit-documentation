---
title: MeasurementFilter
description: API reference for qiskit.ignis.mitigation.MeasurementFilter
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.ignis.mitigation.MeasurementFilter
---

# MeasurementFilter

<span id="qiskit.ignis.mitigation.MeasurementFilter" />

`MeasurementFilter(cal_matrix, state_labels)`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.3/qiskit/ignis/mitigation/measurement/filters.py "view source code")

Measurement error mitigation filter.

Produced from a measurement calibration fitter and can be applied to data.

Initialize a measurement error mitigation filter using the cal\_matrix from a measurement calibration fitter.

**Parameters**

*   **cal\_matrix** (`matrix`) – the calibration matrix for applying the correction
*   **state\_labels** (`list`) – the states for the ordering of the cal matrix

## Attributes

### cal\_matrix

Return cal\_matrix.

### state\_labels

return the state label ordering of the cal matrix

## Methods

### apply

<span id="qiskit.ignis.mitigation.MeasurementFilter.apply" />

`MeasurementFilter.apply(raw_data, method='least_squares')`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.3/qiskit/ignis/mitigation/measurement/filters.py "view source code")

Apply the calibration matrix to results.

**Parameters**

*   **raw\_data** (*dict or list*) –

    The data to be corrected. Can be in a number of forms:

    Form 1: a counts dictionary from results.get\_counts

    Form 2: a list of counts of length==len(state\_labels)

    Form 3: a list of counts of length==M\*len(state\_labels) where M is an integer (e.g. for use with the tomography data)

    Form 4: a qiskit Result

*   **method** (*str*) –

    fitting method. If None, then least\_squares is used.

    `pseudo_inverse`: direct inversion of the A matrix

    `least_squares`: constrained to have physical probabilities

**Returns**

The corrected data in the same form as raw\_data

**Return type**

dict or list

**Raises**

**QiskitError** – if raw\_data is not an integer multiple of the number of calibrated states.

