---
title: GenerativeNetwork
description: API reference for qiskit.aqua.components.neural_networks.GenerativeNetwork
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.components.neural_networks.GenerativeNetwork
---

# qiskit.aqua.components.neural\_networks.GenerativeNetwork

<span id="qiskit.aqua.components.neural_networks.GenerativeNetwork" />

`GenerativeNetwork`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/components/neural_networks/generative_network.py "view source code")

Base class for generative Quantum and Classical Neural Networks.

This method should initialize the module, but raise an exception if a required component of the module is not available.

### \_\_init\_\_

<span id="qiskit.aqua.components.neural_networks.GenerativeNetwork.__init__" />

`abstract __init__()`

Initialize self. See help(type(self)) for accurate signature.

## Methods

|                                                                                                                                                                                                |                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.aqua.components.neural_networks.GenerativeNetwork.__init__ "qiskit.aqua.components.neural_networks.GenerativeNetwork.__init__")()                                         | Initialize self.                                                                    |
| [`get_output`](#qiskit.aqua.components.neural_networks.GenerativeNetwork.get_output "qiskit.aqua.components.neural_networks.GenerativeNetwork.get_output")(quantum\_instance, params, shots)   | Apply quantum/classical neural network to given input and get the respective output |
| [`loss`](#qiskit.aqua.components.neural_networks.GenerativeNetwork.loss "qiskit.aqua.components.neural_networks.GenerativeNetwork.loss")()                                                     | Loss function used for optimization                                                 |
| [`set_discriminator`](#qiskit.aqua.components.neural_networks.GenerativeNetwork.set_discriminator "qiskit.aqua.components.neural_networks.GenerativeNetwork.set_discriminator")(discriminator) | Set discriminator network.                                                          |
| [`set_seed`](#qiskit.aqua.components.neural_networks.GenerativeNetwork.set_seed "qiskit.aqua.components.neural_networks.GenerativeNetwork.set_seed")(seed)                                     | Set seed.                                                                           |
| [`train`](#qiskit.aqua.components.neural_networks.GenerativeNetwork.train "qiskit.aqua.components.neural_networks.GenerativeNetwork.train")(\[quantum\_instance, shots])                       | Perform one training step w\.r.t to the generator’s parameters                      |

## Attributes

|                                                                                                                                                                              |                                         |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------- |
| [`parameter_values`](#qiskit.aqua.components.neural_networks.GenerativeNetwork.parameter_values "qiskit.aqua.components.neural_networks.GenerativeNetwork.parameter_values") | Get parameter values from the generator |

### get\_output

<span id="qiskit.aqua.components.neural_networks.GenerativeNetwork.get_output" />

`abstract get_output(quantum_instance, params, shots)`

Apply quantum/classical neural network to given input and get the respective output

**Parameters**

*   **quantum\_instance** ([*QuantumInstance*](qiskit.aqua.QuantumInstance "qiskit.aqua.QuantumInstance")) – Quantum Instance, used to run the generator circuit.
*   **params** (*numpy.ndarray*) – parameters which should be used to run the generator, if None use self.\_params
*   **shots** (*int*) – if not None use a number of shots that is different from the number set in quantum\_instance

**Returns**

Neural network output

**Raises**

**NotImplementedError** – not implemented

### loss

<span id="qiskit.aqua.components.neural_networks.GenerativeNetwork.loss" />

`abstract loss()`

Loss function used for optimization

### parameter\_values

<span id="qiskit.aqua.components.neural_networks.GenerativeNetwork.parameter_values" />

`abstract property parameter_values`

Get parameter values from the generator

**Raises**

**NotImplementedError** – not implemented

### set\_discriminator

<span id="qiskit.aqua.components.neural_networks.GenerativeNetwork.set_discriminator" />

`abstract set_discriminator(discriminator)`

Set discriminator network.

**Parameters**

**discriminator** (*Discriminator*) – Discriminator used to compute the loss function.

**Raises**

**NotImplementedError** – not implemented

### set\_seed

<span id="qiskit.aqua.components.neural_networks.GenerativeNetwork.set_seed" />

`abstract set_seed(seed)`

Set seed.

**Parameters**

**seed** (*int*) – seed

**Raises**

**NotImplementedError** – not implemented

### train

<span id="qiskit.aqua.components.neural_networks.GenerativeNetwork.train" />

`abstract train(quantum_instance=None, shots=None)`

Perform one training step w\.r.t to the generator’s parameters

**Parameters**

*   **quantum\_instance** ([*QuantumInstance*](qiskit.aqua.QuantumInstance "qiskit.aqua.QuantumInstance")) – used to run generator network. Ignored for a classical network.
*   **shots** (*int*) – Number of shots for hardware or qasm execution. Ignored for classical network

**Returns**

generator loss and updated parameters.

**Return type**

dict

**Raises**

**NotImplementedError** – not implemented

