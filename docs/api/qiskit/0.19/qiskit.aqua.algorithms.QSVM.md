---
title: QSVM
description: API reference for qiskit.aqua.algorithms.QSVM
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.algorithms.QSVM
---

# QSVM

<span id="qiskit.aqua.algorithms.QSVM" />

`QSVM(feature_map, training_dataset=None, test_dataset=None, datapoints=None, multiclass_extension=None, quantum_instance=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/classifiers/qsvm/qsvm.py "view source code")

Quantum SVM algorithm.

A key concept in classification methods is that of a kernel. Data cannot typically be separated by a hyperplane in its original space. A common technique used to find such a hyperplane consists on applying a non-linear transformation function to the data. This function is called a *feature map*, as it transforms the raw features, or measurable properties, of the phenomenon or subject under study. Classifying in this new feature space – and, as a matter of fact, also in any other space, including the raw original one – is nothing more than seeing how close data points are to each other. This is the same as computing the inner product for each pair of data in the set. In fact we do not need to compute the non-linear feature map for each datum, but only the inner product of each pair of data points in the new feature space. This collection of inner products is called the **kernel** and it is perfectly possible to have feature maps that are hard to compute but whose kernels are not.

The QSVM algorithm applies to classification problems that require a feature map for which computing the kernel is not efficient classically. This means that the required computational resources are expected to scale exponentially with the size of the problem. QSVM uses a Quantum processor to solve this problem by a direct estimation of the kernel in the feature space. The method used falls in the category of what is called **supervised learning**, consisting of a **training phase** (where the kernel is calculated and the support vectors obtained) and a **test or classification phase** (where new data without labels is classified according to the solution found in the training phase).

Internally, QSVM will run the binary classification or multiclass classification based on how many classes the data has. If the data has more than 2 classes then a *multiclass\_extension* is required to be supplied. Aqua provides several [`multiclass_extensions`](qiskit.aqua.components.multiclass_extensions#module-qiskit.aqua.components.multiclass_extensions "qiskit.aqua.components.multiclass_extensions").

See also [https://arxiv.org/abs/1804.11326](https://arxiv.org/abs/1804.11326)

**Parameters**

*   **feature\_map** (`Union`\[[`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit"), [`FeatureMap`](qiskit.aqua.components.feature_maps.FeatureMap "qiskit.aqua.components.feature_maps.feature_map.FeatureMap")]) – Feature map module, used to transform data
*   **training\_dataset** (`Optional`\[`Dict`\[`str`, `ndarray`]]) – Training dataset.
*   **test\_dataset** (`Optional`\[`Dict`\[`str`, `ndarray`]]) – Testing dataset.
*   **datapoints** (`Optional`\[`ndarray`]) – Prediction dataset.
*   **multiclass\_extension** (`Optional`\[[`MulticlassExtension`](qiskit.aqua.components.multiclass_extensions.MulticlassExtension "qiskit.aqua.components.multiclass_extensions.multiclass_extension.MulticlassExtension")]) – If number of classes is greater than 2 then a multiclass scheme must be supplied, in the form of a multiclass extension.
*   **quantum\_instance** (`Union`\[[`QuantumInstance`](qiskit.aqua.QuantumInstance "qiskit.aqua.quantum_instance.QuantumInstance"), [`BaseBackend`](qiskit.providers.BaseBackend "qiskit.providers.basebackend.BaseBackend"), `None`]) – Quantum Instance or Backend

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – Multiclass extension not supplied when number of classes > 2

## Attributes

### BATCH\_SIZE

<span id="qiskit.aqua.algorithms.QSVM.BATCH_SIZE" />

`= 1000`

### backend

<span id="qiskit.aqua.algorithms.QSVM.backend" />

`qiskit.providers.basebackend.BaseBackend`

Returns backend.

**Return type**

[`BaseBackend`](qiskit.providers.BaseBackend "qiskit.providers.basebackend.BaseBackend")

### quantum\_instance

<span id="qiskit.aqua.algorithms.QSVM.quantum_instance" />

`Union[None, qiskit.aqua.quantum_instance.QuantumInstance]`

Returns quantum instance.

**Return type**

`Optional`\[[`QuantumInstance`](qiskit.aqua.QuantumInstance "qiskit.aqua.quantum_instance.QuantumInstance")]

### random

Return a numpy random.

### ret

returns result

## Methods

### construct\_circuit

<span id="qiskit.aqua.algorithms.QSVM.construct_circuit" />

`QSVM.construct_circuit(x1, x2, measurement=False)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/classifiers/qsvm/qsvm.py "view source code")

Generate inner product of x1 and x2 with the given feature map.

The dimension of x1 and x2 must be the same.

**Parameters**

*   **x1** (*numpy.ndarray*) – data points, 1-D array, dimension is D
*   **x2** (*numpy.ndarray*) – data points, 1-D array, dimension is D
*   **measurement** (*bool*) – add measurement gates at the end

**Returns**

constructed circuit

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### construct\_kernel\_matrix

<span id="qiskit.aqua.algorithms.QSVM.construct_kernel_matrix" />

`QSVM.construct_kernel_matrix(x1_vec, x2_vec=None, quantum_instance=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/classifiers/qsvm/qsvm.py "view source code")

Construct kernel matrix, if x2\_vec is None, self-innerproduct is conducted.

#### Notes

When using statevector\_simulator, we only build the circuits for Psi(x1)|0> rather than Psi(x2)^dagger Psi(x1)|0>, and then we perform the inner product classically. That is, for statevector\_simulator, the total number of circuits will be O(N) rather than O(N^2) for qasm\_simulator.

**Parameters**

*   **x1\_vec** (*numpy.ndarray*) – data points, 2-D array, N1xD, where N1 is the number of data, D is the feature dimension
*   **x2\_vec** (*numpy.ndarray*) – data points, 2-D array, N2xD, where N2 is the number of data, D is the feature dimension
*   **quantum\_instance** ([*QuantumInstance*](qiskit.aqua.QuantumInstance "qiskit.aqua.QuantumInstance")) – quantum backend with all settings

**Returns**

2-D matrix, N1xN2

**Return type**

numpy.ndarray

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – Quantum instance is not present.

### get\_kernel\_matrix

<span id="qiskit.aqua.algorithms.QSVM.get_kernel_matrix" />

`static QSVM.get_kernel_matrix(quantum_instance, feature_map, x1_vec, x2_vec=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/classifiers/qsvm/qsvm.py "view source code")

Construct kernel matrix, if x2\_vec is None, self-innerproduct is conducted.

#### Notes

When using statevector\_simulator, we only build the circuits for Psi(x1)|0> rather than Psi(x2)^dagger Psi(x1)|0>, and then we perform the inner product classically. That is, for statevector\_simulator, the total number of circuits will be O(N) rather than O(N^2) for qasm\_simulator.

**Parameters**

*   **quantum\_instance** ([*QuantumInstance*](qiskit.aqua.QuantumInstance "qiskit.aqua.QuantumInstance")) – quantum backend with all settings
*   **feature\_map** ([*FeatureMap*](qiskit.aqua.components.feature_maps.FeatureMap "qiskit.aqua.components.feature_maps.FeatureMap")) – a feature map that maps data to feature space
*   **x1\_vec** (*numpy.ndarray*) – data points, 2-D array, N1xD, where N1 is the number of data, D is the feature dimension
*   **x2\_vec** (*numpy.ndarray*) – data points, 2-D array, N2xD, where N2 is the number of data, D is the feature dimension

**Returns**

2-D matrix, N1xN2

**Return type**

numpy.ndarray

### load\_model

<span id="qiskit.aqua.algorithms.QSVM.load_model" />

`QSVM.load_model(file_path)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/classifiers/qsvm/qsvm.py "view source code")

Load a model from a file path.

**Parameters**

**file\_path** (*str*) – the path of the saved model.

### predict

<span id="qiskit.aqua.algorithms.QSVM.predict" />

`QSVM.predict(data, quantum_instance=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/classifiers/qsvm/qsvm.py "view source code")

Predict using the svm.

**Parameters**

*   **data** (*numpy.ndarray*) – NxD array, where N is the number of data, D is the feature dimension.
*   **quantum\_instance** ([*QuantumInstance*](qiskit.aqua.QuantumInstance "qiskit.aqua.QuantumInstance")) – quantum backend with all setting

**Returns**

predicted labels, Nx1 array

**Return type**

numpy.ndarray

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – Quantum instance is not present.

### run

<span id="qiskit.aqua.algorithms.QSVM.run" />

`QSVM.run(quantum_instance=None, **kwargs)`

Execute the algorithm with selected backend.

**Parameters**

*   **quantum\_instance** (`Union`\[[`QuantumInstance`](qiskit.aqua.QuantumInstance "qiskit.aqua.quantum_instance.QuantumInstance"), [`BaseBackend`](qiskit.providers.BaseBackend "qiskit.providers.basebackend.BaseBackend"), `None`]) – the experimental setting.
*   **kwargs** (*dict*) – kwargs

**Returns**

results of an algorithm.

**Return type**

dict

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – If a quantum instance or backend has not been provided

### save\_model

<span id="qiskit.aqua.algorithms.QSVM.save_model" />

`QSVM.save_model(file_path)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/classifiers/qsvm/qsvm.py "view source code")

Save the model to a file path.

**Parameters**

**file\_path** (*str*) – a path to save the model.

### set\_backend

<span id="qiskit.aqua.algorithms.QSVM.set_backend" />

`QSVM.set_backend(backend, **kwargs)`

Sets backend with configuration.

**Return type**

`None`

### setup\_datapoint

<span id="qiskit.aqua.algorithms.QSVM.setup_datapoint" />

`QSVM.setup_datapoint(datapoints)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/classifiers/qsvm/qsvm.py "view source code")

Setup data points, if the data were there, they would be overwritten.

**Parameters**

**datapoints** (*numpy.ndarray*) – prediction dataset.

### setup\_test\_data

<span id="qiskit.aqua.algorithms.QSVM.setup_test_data" />

`QSVM.setup_test_data(test_dataset)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/classifiers/qsvm/qsvm.py "view source code")

Setup test data, if the data were there, they would be overwritten.

**Parameters**

**test\_dataset** (*dict*) – test dataset.

### setup\_training\_data

<span id="qiskit.aqua.algorithms.QSVM.setup_training_data" />

`QSVM.setup_training_data(training_dataset)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/classifiers/qsvm/qsvm.py "view source code")

Setup training data, if the data were there, they would be overwritten.

**Parameters**

**training\_dataset** (*dict*) – training dataset.

### test

<span id="qiskit.aqua.algorithms.QSVM.test" />

`QSVM.test(data, labels, quantum_instance=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/classifiers/qsvm/qsvm.py "view source code")

Test the svm.

**Parameters**

*   **data** (*numpy.ndarray*) – NxD array, where N is the number of data, D is the feature dimension.
*   **labels** (*numpy.ndarray*) – Nx1 array, where N is the number of data
*   **quantum\_instance** ([*QuantumInstance*](qiskit.aqua.QuantumInstance "qiskit.aqua.QuantumInstance")) – quantum backend with all setting

**Returns**

accuracy

**Return type**

float

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – Quantum instance is not present.

### train

<span id="qiskit.aqua.algorithms.QSVM.train" />

`QSVM.train(data, labels, quantum_instance=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/classifiers/qsvm/qsvm.py "view source code")

Train the svm.

**Parameters**

*   **data** (*numpy.ndarray*) – NxD array, where N is the number of data, D is the feature dimension.
*   **labels** (*numpy.ndarray*) – Nx1 array, where N is the number of data
*   **quantum\_instance** ([*QuantumInstance*](qiskit.aqua.QuantumInstance "qiskit.aqua.QuantumInstance")) – quantum backend with all setting

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – Quantum instance is not present.

