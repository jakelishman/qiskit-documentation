---
title: Oracle
description: API reference for qiskit.aqua.components.oracles.Oracle
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.components.oracles.Oracle
---

<span id="qiskit-aqua-components-oracles-oracle" />

# qiskit.aqua.components.oracles.Oracle

<span id="qiskit.aqua.components.oracles.Oracle" />

`Oracle(*args, **kwargs)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.8/qiskit/aqua/components/oracles/oracle.py "view source code")

Base class for oracles.

This method should initialize the module and use an exception if a component of the module is not available.

**Parameters**

*   **args** (*list*) – args
*   **kwargs** (*dict*) – kwargs

### \_\_init\_\_

<span id="qiskit.aqua.components.oracles.Oracle.__init__" />

`abstract __init__(*args, **kwargs)`

Initialize self. See help(type(self)) for accurate signature.

## Methods

|                                                                                                                                             |                               |
| ------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------- |
| [`__init__`](#qiskit.aqua.components.oracles.Oracle.__init__ "qiskit.aqua.components.oracles.Oracle.__init__")(\*args, \*\*kwargs)          | Initialize self.              |
| [`construct_circuit`](#qiskit.aqua.components.oracles.Oracle.construct_circuit "qiskit.aqua.components.oracles.Oracle.construct_circuit")() | Construct the oracle circuit. |

## Attributes

|                                                                                                                                              |                            |
| -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------- |
| [`ancillary_register`](#qiskit.aqua.components.oracles.Oracle.ancillary_register "qiskit.aqua.components.oracles.Oracle.ancillary_register") | returns ancillary register |
| [`circuit`](#qiskit.aqua.components.oracles.Oracle.circuit "qiskit.aqua.components.oracles.Oracle.circuit")                                  |                            |
| [`output_register`](#qiskit.aqua.components.oracles.Oracle.output_register "qiskit.aqua.components.oracles.Oracle.output_register")          | returns output register    |
| [`variable_register`](#qiskit.aqua.components.oracles.Oracle.variable_register "qiskit.aqua.components.oracles.Oracle.variable_register")    | returns variable register  |

### ancillary\_register

<span id="qiskit.aqua.components.oracles.Oracle.ancillary_register" />

`abstract property ancillary_register`

returns ancillary register

### circuit

<span id="qiskit.aqua.components.oracles.Oracle.circuit" />

`property circuit`

### construct\_circuit

<span id="qiskit.aqua.components.oracles.Oracle.construct_circuit" />

`abstract construct_circuit()`

Construct the oracle circuit.

**Returns**

A quantum circuit for the oracle.

### output\_register

<span id="qiskit.aqua.components.oracles.Oracle.output_register" />

`abstract property output_register`

returns output register

### variable\_register

<span id="qiskit.aqua.components.oracles.Oracle.variable_register" />

`abstract property variable_register`

returns variable register

