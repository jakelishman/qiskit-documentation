---
title: RYRZ
description: API reference for qiskit.aqua.components.variational_forms.RYRZ
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.components.variational_forms.RYRZ
---

# RYRZ

<span id="qiskit.aqua.components.variational_forms.RYRZ" />

`RYRZ(num_qubits, depth=3, entangler_map=None, entanglement='full', initial_state=None, entanglement_gate='cz', skip_unentangled_qubits=False)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/components/variational_forms/ryrz.py "view source code")

DEPRECATED. The RYRZ Variational Form.

The RYRZ trial wave function is layers of $y$ plus $z$ rotations with entanglements. When none of qubits are unentangled to other qubits, the number of optimizer parameters this form creates and uses is given by $q \times (d + 1) \times 2$, where $q$ is the total number of qubits and $d$ is the depth of the circuit. Nonetheless, in some cases, if an entangler\_map does not include all qubits, that is, some qubits are not entangled by other qubits. The number of parameters is reduced by $d \times q' \times 2$ where $q'$ is the number of unentangled qubits. This is because adding more parameters to the unentangled qubits only introduce overhead without bringing any benefit; furthermore, theoretically, applying multiple Ry and Rz gates in a row can be reduced to a single Ry gate and one Rz gate with the summed rotation angles.

See [`RY`](qiskit.aqua.components.variational_forms.RY "qiskit.aqua.components.variational_forms.RY") for more detail on entangler\_map and entanglement which apply here too but note RYRZ only supports ‘full’ and ‘linear’ values.

**Parameters**

*   **num\_qubits** (`int`) – Number of qubits, has a minimum value of 1.
*   **depth** (`int`) – Number of rotation layers, has a minimum value of 1.
*   **entangler\_map** (`Optional`\[`List`\[`List`\[`int`]]]) – Describe the connectivity of qubits, each list pair describes \[source, target], or None for as defined by entanglement. Note that the order is the list is the order of applying the two-qubit gate.
*   **entanglement** (`str`) – (‘full’ | ‘linear’) overridden by ‘entangler\_map\` if its provided. ‘full’ is all-to-all entanglement, ‘linear’ is nearest-neighbor.
*   **initial\_state** (`Optional`\[[`InitialState`](qiskit.aqua.components.initial_states.InitialState "qiskit.aqua.components.initial_states.initial_state.InitialState")]) – An initial state object
*   **entanglement\_gate** (`str`) – (‘cz’ | ‘cx’)
*   **skip\_unentangled\_qubits** (`bool`) – Skip the qubits not in the entangler\_map

## Attributes

### num\_parameters

Number of parameters of the variational form.

**Returns**

An integer indicating the number of parameters.

**Return type**

int

### num\_qubits

Number of qubits of the variational form.

**Returns**

An integer indicating the number of qubits.

**Return type**

int

### parameter\_bounds

Parameter bounds.

**Returns**

A list of pairs indicating the bounds, as (lower, upper). None indicates an unbounded parameter in the corresponding direction. If None is returned, problem is fully unbounded.

**Return type**

list

### preferred\_init\_points

Return preferred init points.

If an initial state is provided then the variational form may provide back this set of parameters which when used on the variational form should result in the overall state being that defined by the initial state

### setting

### support\_parameterized\_circuit

Whether or not the sub-class support parameterized circuit.

**Returns**

indicate the sub-class support parameterized circuit

**Return type**

boolean

## Methods

### construct\_circuit

<span id="qiskit.aqua.components.variational_forms.RYRZ.construct_circuit" />

`RYRZ.construct_circuit(parameters, q=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/components/variational_forms/ryrz.py "view source code")

Construct the variational form, given its parameters.

**Parameters**

*   **parameters** (*Union(numpy.ndarray, list\[*[*Parameter*](qiskit.circuit.Parameter "qiskit.circuit.Parameter")*],* [*ParameterVector*](qiskit.circuit.ParameterVector "qiskit.circuit.ParameterVector")*)*) – circuit parameters
*   **q** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")) – Quantum Register for the circuit.

**Returns**

a quantum circuit with given parameters

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ValueError** – the number of parameters is incorrect.

### get\_entangler\_map

<span id="qiskit.aqua.components.variational_forms.RYRZ.get_entangler_map" />

`static RYRZ.get_entangler_map(map_type, num_qubits, offset=0)`

returns entangler map

### validate\_entangler\_map

<span id="qiskit.aqua.components.variational_forms.RYRZ.validate_entangler_map" />

`static RYRZ.validate_entangler_map(entangler_map, num_qubits)`

validate entangler map

