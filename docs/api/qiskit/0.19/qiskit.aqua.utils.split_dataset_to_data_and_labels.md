---
title: split_dataset_to_data_and_labels
description: API reference for qiskit.aqua.utils.split_dataset_to_data_and_labels
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.aqua.utils.split_dataset_to_data_and_labels
---

# split\_dataset\_to\_data\_and\_labels

<span id="qiskit.aqua.utils.split_dataset_to_data_and_labels" />

`split_dataset_to_data_and_labels(dataset, class_names=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/utils/dataset_helper.py "view source code")

Split dataset to data and labels numpy array

If class\_names is given, use the desired label to class name mapping, or create the mapping based on the keys in the dataset.

**Parameters**

*   **dataset** (*dict*) – \{‘A’: numpy.ndarray, ‘B’: numpy.ndarray, …}
*   **class\_names** (*dict*) – class name of dataset, \{class\_name: label}

**Returns**

List contains two arrays of numpy.ndarray type where the array at index 0 is data, an NxD array, and at index 1 it is labels, an Nx1 array, containing values in range 0 to K-1, where K is the number of classes. The dict is a map \{str: int}, mapping class name to label. The tuple of list, dict is returned when class\_names is not None, otherwise just the list is returned.

**Return type**

Union(tuple(list, dict), list)

**Raises**

**KeyError** – data set invalid

