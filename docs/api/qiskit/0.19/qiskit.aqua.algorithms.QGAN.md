---
title: QGAN
description: API reference for qiskit.aqua.algorithms.QGAN
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.algorithms.QGAN
---

# QGAN

<span id="qiskit.aqua.algorithms.QGAN" />

`QGAN(data, bounds=None, num_qubits=None, batch_size=500, num_epochs=3000, seed=7, discriminator=None, generator=None, tol_rel_ent=None, snapshot_dir=None, quantum_instance=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/distribution_learners/qgan.py "view source code")

The Quantum Generative Adversarial Network algorithm.

The qGAN \[1] is a hybrid quantum-classical algorithm used for generative modeling tasks.

This adaptive algorithm uses the interplay of a generative [`GenerativeNetwork`](qiskit.aqua.components.neural_networks.GenerativeNetwork "qiskit.aqua.components.neural_networks.GenerativeNetwork") and a discriminative [`DiscriminativeNetwork`](qiskit.aqua.components.neural_networks.DiscriminativeNetwork "qiskit.aqua.components.neural_networks.DiscriminativeNetwork") network to learn the probability distribution underlying given training data.

These networks are trained in alternating optimization steps, where the discriminator tries to differentiate between training data samples and data samples from the generator and the generator aims at generating samples which the discriminator classifies as training data samples. Eventually, the quantum generator learns the training data’s underlying probability distribution. The trained quantum generator loads a quantum state which is a model of the target distribution.

**References:**

**\[1] Zoufal et al.,**

[Quantum Generative Adversarial Networks for learning and loading random distributions](https://www.nature.com/articles/s41534-019-0223-2)

**Parameters**

*   **data** (`ndarray`) – Training data of dimension k
*   **bounds** (`Optional`\[`ndarray`]) – k min/max data values \[\[min\_0,max\_0],…,\[min\_k-1,max\_k-1]] if univariate data: \[min\_0,max\_0]
*   **num\_qubits** (`Optional`\[`ndarray`]) – k numbers of qubits to determine representation resolution, i.e. n qubits enable the representation of 2\*\*n values \[num\_qubits\_0,…, num\_qubits\_k-1]
*   **batch\_size** (`int`) – Batch size, has a min. value of 1.
*   **num\_epochs** (`int`) – Number of training epochs
*   **seed** (`int`) – Random number seed
*   **discriminator** (`Optional`\[[`DiscriminativeNetwork`](qiskit.aqua.components.neural_networks.DiscriminativeNetwork "qiskit.aqua.components.neural_networks.discriminative_network.DiscriminativeNetwork")]) – Discriminates between real and fake data samples
*   **generator** (`Optional`\[[`GenerativeNetwork`](qiskit.aqua.components.neural_networks.GenerativeNetwork "qiskit.aqua.components.neural_networks.generative_network.GenerativeNetwork")]) – Generates ‘fake’ data samples
*   **tol\_rel\_ent** (`Optional`\[`float`]) – Set tolerance level for relative entropy. If the training achieves relative entropy equal or lower than tolerance it finishes.
*   **snapshot\_dir** (`Optional`\[`str`]) – Directory in to which to store cvs file with parameters, if None (default) then no cvs file is created.
*   **quantum\_instance** (`Union`\[[`QuantumInstance`](qiskit.aqua.QuantumInstance "qiskit.aqua.quantum_instance.QuantumInstance"), [`BaseBackend`](qiskit.providers.BaseBackend "qiskit.providers.basebackend.BaseBackend"), `None`]) – Quantum Instance or Backend

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – invalid input

## Attributes

### backend

<span id="qiskit.aqua.algorithms.QGAN.backend" />

`qiskit.providers.basebackend.BaseBackend`

Returns backend.

**Return type**

[`BaseBackend`](qiskit.providers.BaseBackend "qiskit.providers.basebackend.BaseBackend")

### d\_loss

Returns discriminator loss

### discriminator

Returns discriminator

### g\_loss

Returns generator loss

### generator

Returns generator

### quantum\_instance

<span id="qiskit.aqua.algorithms.QGAN.quantum_instance" />

`Union[None, qiskit.aqua.quantum_instance.QuantumInstance]`

Returns quantum instance.

**Return type**

`Optional`\[[`QuantumInstance`](qiskit.aqua.QuantumInstance "qiskit.aqua.quantum_instance.QuantumInstance")]

### random

Return a numpy random.

### rel\_entr

Returns relative entropy between target and trained distribution

### seed

Returns random seed

### tol\_rel\_ent

Returns tolerance for relative entropy

## Methods

### get\_rel\_entr

<span id="qiskit.aqua.algorithms.QGAN.get_rel_entr" />

`QGAN.get_rel_entr()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/distribution_learners/qgan.py "view source code")

Get relative entropy between target and trained distribution

### run

<span id="qiskit.aqua.algorithms.QGAN.run" />

`QGAN.run(quantum_instance=None, **kwargs)`

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

### set\_backend

<span id="qiskit.aqua.algorithms.QGAN.set_backend" />

`QGAN.set_backend(backend, **kwargs)`

Sets backend with configuration.

**Return type**

`None`

### set\_discriminator

<span id="qiskit.aqua.algorithms.QGAN.set_discriminator" />

`QGAN.set_discriminator(discriminator=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/distribution_learners/qgan.py "view source code")

Initialize discriminator.

**Parameters**

**discriminator** (*Discriminator*) – discriminator

### set\_generator

<span id="qiskit.aqua.algorithms.QGAN.set_generator" />

`QGAN.set_generator(generator_circuit=None, generator_init_params=None, generator_optimizer=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/distribution_learners/qgan.py "view source code")

Initialize generator.

**Parameters**

*   **generator\_circuit** (`Union`\[[`UnivariateVariationalDistribution`](qiskit.aqua.components.uncertainty_models.UnivariateVariationalDistribution "qiskit.aqua.components.uncertainty_models.univariate_variational_distribution.UnivariateVariationalDistribution"), [`MultivariateVariationalDistribution`](qiskit.aqua.components.uncertainty_models.MultivariateVariationalDistribution "qiskit.aqua.components.uncertainty_models.multivariate_variational_distribution.MultivariateVariationalDistribution"), [`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit"), `None`]) – parameterized quantum circuit which sets the structure of the quantum generator
*   **generator\_init\_params** (`Optional`\[`ndarray`]) – initial parameters for the generator circuit
*   **generator\_optimizer** (`Optional`\[[`Optimizer`](qiskit.aqua.components.optimizers.Optimizer "qiskit.aqua.components.optimizers.optimizer.Optimizer")]) – optimizer to be used for the training of the generator

### train

<span id="qiskit.aqua.algorithms.QGAN.train" />

`QGAN.train()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/distribution_learners/qgan.py "view source code")

Train the qGAN

