---
title: PauliFeatureMap
description: API reference for qiskit.circuit.library.PauliFeatureMap
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.PauliFeatureMap
---

# PauliFeatureMap

<span id="qiskit.circuit.library.PauliFeatureMap" />

`PauliFeatureMap(feature_dimension=None, reps=2, entanglement='full', paulis=None, data_map_func=None, parameter_prefix='x', insert_barriers=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/circuit/library/data_preparation/pauli_feature_map.py "view source code")

The Pauli Expansion circuit.

The Pauli Expansion circuit is a data encoding circuit that transforms input data $\vec{x} \in \mathbb{R}^n$ as

$$
U_{\Phi(\vec{x})}=\exp\left(i\sum_{S\subseteq [n]}
\phi_S(\vec{x})\prod_{i\in S} P_i\right)
$$

The circuit contains `reps` repetitions of this transformation. The variable $P_i \in \{ I, X, Y, Z \}$ denotes the Pauli matrices. The index $S$ describes connectivities between different qubits or datapoints: $S \in \{\binom{n}{k}\ combinations,\ k = 1,... n \}$. Per default the data-mapping $\phi_S$ is

$$
\begin{split}\phi_S(\vec{x}) = \begin{cases}
    x_0 \text{ if } k = 1 \\
    \prod_{j \in S} (\pi - x_j)\end{split}
$$

For example, if the Pauli strings are chosen to be $P_0 = Z$ and $P_{0,1} = YY$ on 2 qubits and with 1 repetition using the default data-mapping, the Pauli evolution feature map is represented by:

```python
┌───┐┌──────────────┐┌──────────┐                                             ┌───────────┐
┤ H ├┤ U1(2.0*x[0]) ├┤ RX(pi/2) ├──■───────────────────────────────────────■──┤ RX(-pi/2) ├
├───┤├──────────────┤├──────────┤┌─┴─┐┌─────────────────────────────────┐┌─┴─┐├───────────┤
┤ H ├┤ U1(2.0*x[1]) ├┤ RX(pi/2) ├┤ X ├┤ U1(2.0*(pi - x[0])*(pi - x[1])) ├┤ X ├┤ RX(-pi/2) ├
└───┘└──────────────┘└──────────┘└───┘└─────────────────────────────────┘└───┘└───────────┘
```

Please refer to [`ZFeatureMap`](qiskit.circuit.library.ZFeatureMap "qiskit.circuit.library.ZFeatureMap") for the case $k = 1$, $P_0 = Z$ and to [`ZZFeatureMap`](qiskit.circuit.library.ZZFeatureMap "qiskit.circuit.library.ZZFeatureMap") for the case $k = 2$, $P_0 = Z$ and $P_{0,1} = ZZ$.

## Examples

```python
>>> prep = PauliFeatureMap(2, reps=1, paulis=['ZZ'])
>>> print(prep)
     ┌───┐
q_0: ┤ H ├──■───────────────────────────────────────■──
     ├───┤┌─┴─┐┌─────────────────────────────────┐┌─┴─┐
q_1: ┤ H ├┤ X ├┤ U1(2.0*(pi - x[0])*(pi - x[1])) ├┤ X ├
     └───┘└───┘└─────────────────────────────────┘└───┘
```

```python
>>> prep = PauliFeatureMap(2, reps=1, paulis=['Z', 'XX'])
>>> print(prep)
     ┌───┐┌──────────────┐┌───┐                                             ┌───┐
q_0: ┤ H ├┤ U1(2.0*x[0]) ├┤ H ├──■───────────────────────────────────────■──┤ H ├
     ├───┤├──────────────┤├───┤┌─┴─┐┌─────────────────────────────────┐┌─┴─┐├───┤
q_1: ┤ H ├┤ U1(2.0*x[1]) ├┤ H ├┤ X ├┤ U1(2.0*(pi - x[0])*(pi - x[1])) ├┤ X ├┤ H ├
     └───┘└──────────────┘└───┘└───┘└─────────────────────────────────┘└───┘└───┘
```

```python
>>> prep = PauliFeatureMap(2, reps=1, paulis=['ZY'])
>>> print(prep)
     ┌───┐┌──────────┐                                             ┌───────────┐
q_0: ┤ H ├┤ RX(pi/2) ├──■───────────────────────────────────────■──┤ RX(-pi/2) ├
     ├───┤└──────────┘┌─┴─┐┌─────────────────────────────────┐┌─┴─┐└───────────┘
q_1: ┤ H ├────────────┤ X ├┤ U1(2.0*(pi - x[0])*(pi - x[1])) ├┤ X ├─────────────
     └───┘            └───┘└─────────────────────────────────┘└───┘
```

```python
>>> from qiskit.circuit.library import EfficientSU2
>>> prep = PauliFeatureMap(3, reps=3, paulis=['Z', 'YY', 'ZXZ'])
>>> wavefunction = EfficientSU2(3)
>>> classifier = prep.compose(wavefunction
>>> classifier.num_parameters
27
>>> classifier.count_ops()
OrderedDict([('cx', 39), ('rx', 36), ('u1', 21), ('h', 15), ('ry', 12), ('rz', 12)])
```

## References

**\[1]: Havlicek et al. (2018), Supervised learning with quantum enhanced feature spaces.**

[arXiv:1804.11326](https://arxiv.org/abs/1804.11326)

Create a new Pauli expansion circuit.

**Parameters**

*   **feature\_dimension** (`Optional`\[`int`]) – Number of qubits in the circuit.
*   **reps** (`int`) – The number of repeated circuits.
*   **entanglement** (`Union`\[`str`, `List`\[`List`\[`int`]], `Callable`\[\[`int`], `List`\[`int`]]]) – Specifies the entanglement structure. Refer to [`NLocal`](qiskit.circuit.library.NLocal "qiskit.circuit.library.NLocal") for detail.
*   **paulis** (`Optional`\[`List`\[`str`]]) – A list of strings for to-be-used paulis. If None are provided, `['Z', 'ZZ']` will be used.
*   **data\_map\_func** (`Optional`\[`Callable`\[\[`ndarray`], `float`]]) – A mapping function for data x which can be supplied to override the default mapping from `self_product()`.
*   **parameter\_prefix** (`str`) – The prefix used if default parameters are generated.
*   **insert\_barriers** (`bool`) – If True, barriers are inserted in between the evolution instructions and hadamard layers.

## Attributes

### clbits

Returns a list of classical bits in the order that the registers were added.

### data

Return the circuit data (instructions and context).

**Returns**

a list-like object containing the tuples for the circuit’s data.

Each tuple is in the format `(instruction, qargs, cargs)`, where instruction is an Instruction (or subclass) object, qargs is a list of Qubit objects, and cargs is a list of Clbit objects.

**Return type**

QuantumCircuitData

### entanglement

<span id="qiskit.circuit.library.PauliFeatureMap.entanglement" />

`Union[str, List[str], List[List[str]], List[int], List[List[int]], List[List[List[int]]], List[List[List[List[int]]]], Callable[[int], str], Callable[[int], List[List[int]]]]`

Get the entanglement strategy.

**Return type**

`Union`\[`str`, `List`\[`str`], `List`\[`List`\[`str`]], `List`\[`int`], `List`\[`List`\[`int`]], `List`\[`List`\[`List`\[`int`]]], `List`\[`List`\[`List`\[`List`\[`int`]]]], `Callable`\[\[`int`], `str`], `Callable`\[\[`int`], `List`\[`List`\[`int`]]]]

**Returns**

The entanglement strategy, see [`get_entangler_map()`](qiskit.circuit.library.PauliFeatureMap#get_entangler_map "qiskit.circuit.library.PauliFeatureMap.get_entangler_map") for more detail on how the format is interpreted.

### entanglement\_blocks

The blocks in the entanglement layers.

**Returns**

The blocks in the entanglement layers.

### extension\_lib

<span id="qiskit.circuit.library.PauliFeatureMap.extension_lib" />

`= 'include "qelib1.inc";'`

### feature\_dimension

<span id="qiskit.circuit.library.PauliFeatureMap.feature_dimension" />

`int`

Returns the feature dimension (which is equal to the number of qubits).

**Return type**

`int`

**Returns**

The feature dimension of this feature map.

### header

<span id="qiskit.circuit.library.PauliFeatureMap.header" />

`= 'OPENQASM 2.0;'`

### initial\_state

<span id="qiskit.circuit.library.PauliFeatureMap.initial_state" />

`Any`

Return the initial state that is added in front of the n-local circuit.

**Return type**

`Any`

**Returns**

The initial state.

### insert\_barriers

<span id="qiskit.circuit.library.PauliFeatureMap.insert_barriers" />

`bool`

If barriers are inserted in between the layers or not.

**Return type**

`bool`

**Returns**

True, if barriers are inserted in between the layers, False if not.

### instances

<span id="qiskit.circuit.library.PauliFeatureMap.instances" />

`= 8`

### n\_qubits

Deprecated, use `num_qubits` instead. Return number of qubits.

### num\_clbits

Return number of classical bits.

### num\_layers

<span id="qiskit.circuit.library.PauliFeatureMap.num_layers" />

`int`

Return the number of layers in the n-local circuit.

**Return type**

`int`

**Returns**

The number of layers in the circuit.

### num\_parameters

Convenience function to get the number of parameter objects in the circuit.

### num\_parameters\_settable

The number of distinct parameters.

### num\_qubits

<span id="qiskit.circuit.library.PauliFeatureMap.num_qubits" />

`int`

Returns the number of qubits in this circuit.

**Return type**

`int`

**Returns**

The number of qubits.

### ordered\_parameters

<span id="qiskit.circuit.library.PauliFeatureMap.ordered_parameters" />

`List[qiskit.circuit.parameter.Parameter]`

The parameters used in the underlying circuit.

This includes float values and duplicates.

#### Examples

```python
>>> # prepare circuit ...
>>> print(nlocal)
     ┌───────┐┌──────────┐┌──────────┐┌──────────┐
q_0: ┤ Ry(1) ├┤ Ry(θ[1]) ├┤ Ry(θ[1]) ├┤ Ry(θ[3]) ├
     └───────┘└──────────┘└──────────┘└──────────┘
>>> nlocal.parameters
{Parameter(θ[1]), Parameter(θ[3])}
>>> nlocal.ordered_parameters
[1, Parameter(θ[1]), Parameter(θ[1]), Parameter(θ[3])]
```

**Return type**

`List`\[[`Parameter`](qiskit.circuit.Parameter "qiskit.circuit.parameter.Parameter")]

**Returns**

The parameters objects used in the circuit.

### parameter\_bounds

<span id="qiskit.circuit.library.PauliFeatureMap.parameter_bounds" />

`Optional[List[Tuple[float, float]]]`

The parameter bounds for the unbound parameters in the circuit.

**Return type**

`Optional`\[`List`\[`Tuple`\[`float`, `float`]]]

**Returns**

A list of pairs indicating the bounds, as (lower, upper). None indicates an unbounded parameter in the corresponding direction. If None is returned, problem is fully unbounded.

### parameters

<span id="qiskit.circuit.library.PauliFeatureMap.parameters" />

`Set[qiskit.circuit.parameter.Parameter]`

Get the [`Parameter`](qiskit.circuit.Parameter "qiskit.circuit.Parameter") objects in the circuit.

**Return type**

`Set`\[[`Parameter`](qiskit.circuit.Parameter "qiskit.circuit.parameter.Parameter")]

**Returns**

A set containing the unbound circuit parameters.

### paulis

<span id="qiskit.circuit.library.PauliFeatureMap.paulis" />

`List[str]`

The Pauli strings used in the entanglement of the qubits.

**Return type**

`List`\[`str`]

**Returns**

The Pauli strings as list.

### preferred\_init\_points

<span id="qiskit.circuit.library.PauliFeatureMap.preferred_init_points" />

`Optional[List[float]]`

The initial points for the parameters. Can be stored as initial guess in optimization.

**Return type**

`Optional`\[`List`\[`float`]]

**Returns**

The initial values for the parameters, or None, if none have been set.

### prefix

<span id="qiskit.circuit.library.PauliFeatureMap.prefix" />

`= 'circuit'`

### qregs

A list of the quantum registers associated with the circuit.

### qubits

Returns a list of quantum bits in the order that the registers were added.

### reps

<span id="qiskit.circuit.library.PauliFeatureMap.reps" />

`int`

The number of times rotation and entanglement block are repeated.

**Return type**

`int`

**Returns**

The number of repetitions.

### rotation\_blocks

<span id="qiskit.circuit.library.PauliFeatureMap.rotation_blocks" />

`List[qiskit.circuit.instruction.Instruction]`

The blocks in the rotation layers.

**Return type**

`List`\[[`Instruction`](qiskit.circuit.Instruction "qiskit.circuit.instruction.Instruction")]

**Returns**

The blocks in the rotation layers.

## Methods

### AND

<span id="qiskit.circuit.library.PauliFeatureMap.AND" />

`PauliFeatureMap.AND(qr_variables, qb_target, qr_ancillae, flags=None, mct_mode='no-ancilla')`

Build a collective conjunction (AND) circuit in place using mct.

**Parameters**

*   **self** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – The QuantumCircuit object to build the conjunction on.
*   **qr\_variables** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")) – The QuantumRegister holding the variable qubits.
*   **qb\_target** ([*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")) – The target qubit to hold the conjunction result.
*   **qr\_ancillae** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")) – The ancillary QuantumRegister for building the mct.
*   **flags** (*list\[int]*) – A list of +1/-1/0 to mark negations or omissions of qubits.
*   **mct\_mode** (*str*) – The mct building mode.

### OR

<span id="qiskit.circuit.library.PauliFeatureMap.OR" />

`PauliFeatureMap.OR(qr_variables, qb_target, qr_ancillae, flags=None, mct_mode='basic')`

Build a collective disjunction (OR) circuit in place using mct.

**Parameters**

*   **self** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – The QuantumCircuit object to build the disjunction on.
*   **qr\_variables** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")) – The QuantumRegister holding the variable qubits.
*   **flags** (*list\[int]*) – A list of +1/-1/0 to mark negations or omissions of qubits.
*   **qb\_target** ([*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")) – The target qubit to hold the disjunction result.
*   **qr\_ancillae** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")) – The ancillary QuantumRegister for building the mct.
*   **mct\_mode** (*str*) – The mct building mode.

### \_\_getitem\_\_

<span id="qiskit.circuit.library.PauliFeatureMap.__getitem__" />

`PauliFeatureMap.__getitem__(item)`

Return indexed operation.

### \_\_len\_\_

<span id="qiskit.circuit.library.PauliFeatureMap.__len__" />

`PauliFeatureMap.__len__()`

Return number of operations in circuit.

### add\_layer

<span id="qiskit.circuit.library.PauliFeatureMap.add_layer" />

`PauliFeatureMap.add_layer(other, entanglement=None, front=False)`

Append another layer to the NLocal.

**Parameters**

*   **other** (`Union`\[[`NLocal`](qiskit.circuit.library.NLocal "qiskit.circuit.library.n_local.n_local.NLocal"), [`Instruction`](qiskit.circuit.Instruction "qiskit.circuit.instruction.Instruction"), [`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit")]) – The layer to compose, can be another NLocal, an Instruction or Gate, or a QuantumCircuit.
*   **entanglement** (`Union`\[`List`\[`int`], `str`, `List`\[`List`\[`int`]], `None`]) – The entanglement or qubit indices.
*   **front** (`bool`) – If True, `other` is appended to the front, else to the back.

**Return type**

[`NLocal`](qiskit.circuit.library.NLocal "qiskit.circuit.library.n_local.n_local.NLocal")

**Returns**

self, such that chained composes are possible.

**Raises**

**TypeError** – If other is not compatible, i.e. is no Instruction and does not have a to\_instruction method.

### add\_register

<span id="qiskit.circuit.library.PauliFeatureMap.add_register" />

`PauliFeatureMap.add_register(*regs)`

Add registers.

### append

<span id="qiskit.circuit.library.PauliFeatureMap.append" />

`PauliFeatureMap.append(instruction, qargs=None, cargs=None)`

Append one or more instructions to the end of the circuit, modifying the circuit in place. Expands qargs and cargs.

**Parameters**

*   **instruction** ([*qiskit.circuit.Instruction*](qiskit.circuit.Instruction "qiskit.circuit.Instruction")) – Instruction instance to append
*   **qargs** (*list(argument)*) – qubits to attach instruction to
*   **cargs** (*list(argument)*) – clbits to attach instruction to

**Returns**

a handle to the instruction that was just added

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

### assign\_parameters

<span id="qiskit.circuit.library.PauliFeatureMap.assign_parameters" />

`PauliFeatureMap.assign_parameters(param_dict, inplace=False)`

Assign parameters to the n-local circuit.

This method also supports passing a list instead of a dictionary. If a list is passed, the list must have the same length as the number of unbound parameters in the circuit. The parameters are assigned in the order of the parameters in [`ordered_parameters()`](qiskit.circuit.library.PauliFeatureMap#ordered_parameters "qiskit.circuit.library.PauliFeatureMap.ordered_parameters").

**Return type**

`Optional`\[[`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit")]

**Returns**

A copy of the NLocal circuit with the specified parameters.

**Raises**

**AttributeError** – If the parameters are given as list and do not match the number of parameters.

### barrier

<span id="qiskit.circuit.library.PauliFeatureMap.barrier" />

`PauliFeatureMap.barrier(*qargs)`

Apply `Barrier`. If qargs is None, applies to all.

### bind\_parameters

<span id="qiskit.circuit.library.PauliFeatureMap.bind_parameters" />

`PauliFeatureMap.bind_parameters(value_dict)`

Assign numeric parameters to values yielding a new circuit.

To assign new Parameter objects or bind the values in-place, without yielding a new circuit, use the assign\_parameters method.

**Parameters**

**value\_dict** (*dict*) – \{parameter: value, …}

**Raises**

*   **CircuitError** – If value\_dict contains parameters not present in the circuit
*   **TypeError** – If value\_dict contains a ParameterExpression in the values.

**Returns**

copy of self with assignment substitution.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### cast

<span id="qiskit.circuit.library.PauliFeatureMap.cast" />

`static PauliFeatureMap.cast(value, _type)`

Best effort to cast value to type. Otherwise, returns the value.

### cbit\_argument\_conversion

<span id="qiskit.circuit.library.PauliFeatureMap.cbit_argument_conversion" />

`PauliFeatureMap.cbit_argument_conversion(clbit_representation)`

Converts several classical bit representations (such as indexes, range, etc.) into a list of classical bits.

**Parameters**

**clbit\_representation** (*Object*) – representation to expand

**Returns**

Where each tuple is a classical bit.

**Return type**

List(tuple)

### ccx

<span id="qiskit.circuit.library.PauliFeatureMap.ccx" />

`PauliFeatureMap.ccx(control_qubit1, control_qubit2, target_qubit, *, ctl1=None, ctl2=None, tgt=None)`

Apply [`CCXGate`](qiskit.circuit.library.CCXGate "qiskit.circuit.library.CCXGate").

### ch

<span id="qiskit.circuit.library.PauliFeatureMap.ch" />

`PauliFeatureMap.ch(control_qubit, target_qubit, *, label=None, ctrl_state=None, ctl=None, tgt=None)`

Apply [`CHGate`](qiskit.circuit.library.CHGate "qiskit.circuit.library.CHGate").

### cls\_instances

<span id="qiskit.circuit.library.PauliFeatureMap.cls_instances" />

`classmethod PauliFeatureMap.cls_instances()`

Return the current number of instances of this class, useful for auto naming.

### cls\_prefix

<span id="qiskit.circuit.library.PauliFeatureMap.cls_prefix" />

`classmethod PauliFeatureMap.cls_prefix()`

Return the prefix to use for auto naming.

### cnot

<span id="qiskit.circuit.library.PauliFeatureMap.cnot" />

`PauliFeatureMap.cnot(control_qubit, target_qubit, *, label=None, ctrl_state=None, ctl=None, tgt=None)`

Apply [`CXGate`](qiskit.circuit.library.CXGate "qiskit.circuit.library.CXGate").

### combine

<span id="qiskit.circuit.library.PauliFeatureMap.combine" />

`PauliFeatureMap.combine(rhs)`

Append rhs to self if self contains compatible registers.

Two circuits are compatible if they contain the same registers or if they contain different registers with unique names. The returned circuit will contain all unique registers between both circuits.

Return self + rhs as a new object.

**Parameters**

**rhs** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – The quantum circuit to append to the right hand side.

**Returns**

Returns a new QuantumCircuit object

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the rhs circuit is not compatible

### compose

<span id="qiskit.circuit.library.PauliFeatureMap.compose" />

`PauliFeatureMap.compose(other, qubits=None, clbits=None, front=False, inplace=False)`

Compose circuit with `other` circuit or instruction, optionally permuting wires.

`other` can be narrower or of equal width to `self`.

**Parameters**

*   **other** ([*qiskit.circuit.Instruction*](qiskit.circuit.Instruction "qiskit.circuit.Instruction")  *or*[*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit") *or BaseOperator*) – (sub)circuit to compose onto self.
*   **qubits** (*list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*|int]*) – qubits of self to compose onto.
*   **clbits** (*list\[*[*Clbit*](qiskit.circuit.Clbit "qiskit.circuit.Clbit")*|int]*) – clbits of self to compose onto.
*   **front** (*bool*) – If True, front composition will be performed (not implemented yet).
*   **inplace** (*bool*) – If True, modify the object. Otherwise return composed circuit.

**Returns**

the composed circuit (returns None if inplace==True).

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

*   **CircuitError** – if composing on the front.
*   **QiskitError** – if `other` is wider or there are duplicate edge mappings.

#### Examples

```python
>>> lhs.compose(rhs, qubits=[3, 2], inplace=True)
```

```python
            ┌───┐                   ┌─────┐                ┌───┐
lqr_1_0: ───┤ H ├───    rqr_0: ──■──┤ Tdg ├    lqr_1_0: ───┤ H ├───────────────
            ├───┤              ┌─┴─┐└─────┘                ├───┤
lqr_1_1: ───┤ X ├───    rqr_1: ┤ X ├───────    lqr_1_1: ───┤ X ├───────────────
         ┌──┴───┴──┐           └───┘                    ┌──┴───┴──┐┌───┐
lqr_1_2: ┤ U1(0.1) ├  +                     =  lqr_1_2: ┤ U1(0.1) ├┤ X ├───────
         └─────────┘                                    └─────────┘└─┬─┘┌─────┐
lqr_2_0: ─────■─────                           lqr_2_0: ─────■───────■──┤ Tdg ├
            ┌─┴─┐                                          ┌─┴─┐        └─────┘
lqr_2_1: ───┤ X ├───                           lqr_2_1: ───┤ X ├───────────────
            └───┘                                          └───┘
lcr_0: 0 ═══════════                           lcr_0: 0 ═══════════════════════

lcr_1: 0 ═══════════                           lcr_1: 0 ═══════════════════════
```

### copy

<span id="qiskit.circuit.library.PauliFeatureMap.copy" />

`PauliFeatureMap.copy(name=None)`

Copy the circuit.

**Parameters**

**name** (*str*) – name to be given to the copied circuit. If None, then the name stays the same

**Returns**

a deepcopy of the current circuit, with the specified name

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### count\_ops

<span id="qiskit.circuit.library.PauliFeatureMap.count_ops" />

`PauliFeatureMap.count_ops()`

Count each operation kind in the circuit.

**Returns**

a breakdown of how many operations of each kind, sorted by amount.

**Return type**

OrderedDict

### crx

<span id="qiskit.circuit.library.PauliFeatureMap.crx" />

`PauliFeatureMap.crx(theta, control_qubit, target_qubit, *, label=None, ctrl_state=None, ctl=None, tgt=None)`

Apply [`CRXGate`](qiskit.circuit.library.CRXGate "qiskit.circuit.library.CRXGate").

### cry

<span id="qiskit.circuit.library.PauliFeatureMap.cry" />

`PauliFeatureMap.cry(theta, control_qubit, target_qubit, *, label=None, ctrl_state=None, ctl=None, tgt=None)`

Apply [`CRYGate`](qiskit.circuit.library.CRYGate "qiskit.circuit.library.CRYGate").

### crz

<span id="qiskit.circuit.library.PauliFeatureMap.crz" />

`PauliFeatureMap.crz(theta, control_qubit, target_qubit, *, label=None, ctrl_state=None, ctl=None, tgt=None)`

Apply [`CRZGate`](qiskit.circuit.library.CRZGate "qiskit.circuit.library.CRZGate").

### cswap

<span id="qiskit.circuit.library.PauliFeatureMap.cswap" />

`PauliFeatureMap.cswap(control_qubit, target_qubit1, target_qubit2, *, label=None, ctrl_state=None, ctl=None, tgt1=None, tgt2=None)`

Apply [`CSwapGate`](qiskit.circuit.library.CSwapGate "qiskit.circuit.library.CSwapGate").

### cu1

<span id="qiskit.circuit.library.PauliFeatureMap.cu1" />

`PauliFeatureMap.cu1(theta, control_qubit, target_qubit, *, label=None, ctrl_state=None, ctl=None, tgt=None)`

Apply [`CU1Gate`](qiskit.circuit.library.CU1Gate "qiskit.circuit.library.CU1Gate").

### cu3

<span id="qiskit.circuit.library.PauliFeatureMap.cu3" />

`PauliFeatureMap.cu3(theta, phi, lam, control_qubit, target_qubit, *, label=None, ctrl_state=None, ctl=None, tgt=None)`

Apply [`CU3Gate`](qiskit.circuit.library.CU3Gate "qiskit.circuit.library.CU3Gate").

### cx

<span id="qiskit.circuit.library.PauliFeatureMap.cx" />

`PauliFeatureMap.cx(control_qubit, target_qubit, *, label=None, ctrl_state=None, ctl=None, tgt=None)`

Apply [`CXGate`](qiskit.circuit.library.CXGate "qiskit.circuit.library.CXGate").

### cy

<span id="qiskit.circuit.library.PauliFeatureMap.cy" />

`PauliFeatureMap.cy(control_qubit, target_qubit, *, label=None, ctrl_state=None, ctl=None, tgt=None)`

Apply [`CYGate`](qiskit.circuit.library.CYGate "qiskit.circuit.library.CYGate").

### cz

<span id="qiskit.circuit.library.PauliFeatureMap.cz" />

`PauliFeatureMap.cz(control_qubit, target_qubit, *, label=None, ctrl_state=None, ctl=None, tgt=None)`

Apply [`CZGate`](qiskit.circuit.library.CZGate "qiskit.circuit.library.CZGate").

### dcx

<span id="qiskit.circuit.library.PauliFeatureMap.dcx" />

`PauliFeatureMap.dcx(qubit1, qubit2)`

Apply [`DCXGate`](qiskit.circuit.library.DCXGate "qiskit.circuit.library.DCXGate").

### decompose

<span id="qiskit.circuit.library.PauliFeatureMap.decompose" />

`PauliFeatureMap.decompose()`

Call a decomposition pass on this circuit, to decompose one level (shallow decompose).

**Returns**

a circuit one level decomposed

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### depth

<span id="qiskit.circuit.library.PauliFeatureMap.depth" />

`PauliFeatureMap.depth()`

Return circuit depth (i.e., length of critical path). This does not include compiler or simulator directives such as ‘barrier’ or ‘snapshot’.

**Returns**

Depth of circuit.

**Return type**

int

#### Notes

The circuit depth and the DAG depth need not be the same.

### diag\_gate

<span id="qiskit.circuit.library.PauliFeatureMap.diag_gate" />

`PauliFeatureMap.diag_gate(diag, qubit)`

Deprecated version of QuantumCircuit.diagonal.

### diagonal

<span id="qiskit.circuit.library.PauliFeatureMap.diagonal" />

`PauliFeatureMap.diagonal(diag, qubit)`

Attach a diagonal gate to a circuit.

The decomposition is based on Theorem 7 given in “Synthesis of Quantum Logic Circuits” by Shende et al. ([https://arxiv.org/pdf/quant-ph/0406176.pdf](https://arxiv.org/pdf/quant-ph/0406176.pdf)).

**Parameters**

*   **diag** (*list*) – list of the 2^k diagonal entries (for a diagonal gate on k qubits). Must contain at least two entries
*   **qubit** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*|list*) – list of k qubits the diagonal is acting on (the order of the qubits specifies the computational basis in which the diagonal gate is provided: the first element in diag acts on the state where all the qubits in q are in the state 0, the second entry acts on the state where all the qubits q\[1],…,q\[k-1] are in the state zero and q\[0] is in the state 1, and so on)

**Returns**

the diagonal gate which was attached to the circuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the list of the diagonal entries or the qubit list is in bad format; if the number of diagonal entries is not 2^k, where k denotes the number of qubits

### draw

<span id="qiskit.circuit.library.PauliFeatureMap.draw" />

`PauliFeatureMap.draw(output=None, scale=0.7, filename=None, style=None, interactive=False, line_length=None, plot_barriers=True, reverse_bits=False, justify=None, vertical_compression='medium', idle_wires=True, with_layout=True, fold=None, ax=None, initial_state=False, cregbundle=False)`

Draw the quantum circuit.

**text**: ASCII art TextDrawing that can be printed in the console.

**latex**: high-quality images compiled via LaTeX.

**latex\_source**: raw uncompiled LaTeX output.

**matplotlib**: images with color rendered purely in Python.

**Parameters**

*   **output** (*str*) – Select the output method to use for drawing the circuit. Valid choices are `text`, `latex`, `latex_source`, or `mpl`. By default the ‘text’ drawer is used unless a user config file has an alternative backend set as the default. If the output kwarg is set, that backend will always be used over the default in a user config file.
*   **scale** (*float*) – scale of image to draw (shrink if \< 1)
*   **filename** (*str*) – file path to save image to
*   **style** (*dict or str*) – dictionary of style or file name of style file. This option is only used by the `mpl` output type. If a str is passed in that is the path to a json file which contains a dictionary of style, then that will be opened, parsed, and used as the input dict. See: [Style Dict Doc](qiskit.circuit.library.ZZFeatureMap#draw) for more information on the contents.
*   **interactive** (*bool*) – when set true show the circuit in a new window (for mpl this depends on the matplotlib backend being used supporting this). Note when used with either the text or the latex\_source output type this has no effect and will be silently ignored.
*   **line\_length** (*int*) – Deprecated; see fold which supersedes this option. Sets the length of the lines generated by text output type. This is useful when the drawing does not fit in the console. If None (default), it will try to guess the console width using `shutil.get_terminal_size()`. However, if you’re running in jupyter, the default line length is set to 80 characters. If you don’t want pagination at all, set `line_length=-1`.
*   **reverse\_bits** (*bool*) – When set to True, reverse the bit order inside registers for the output visualization.
*   **plot\_barriers** (*bool*) – Enable/disable drawing barriers in the output circuit. Defaults to True.
*   **justify** (*string*) – Options are `left`, `right` or `none`. If anything else is supplied it defaults to left justified. It refers to where gates should be placed in the output circuit if there is an option. `none` results in each gate being placed in its own column.
*   **vertical\_compression** (*string*) – `high`, `medium` or `low`. It merges the lines generated by the `text` output so the drawing will take less vertical room. Default is `medium`. Only used by the `text` output, will be silently ignored otherwise.
*   **idle\_wires** (*bool*) – Include idle wires (wires with no circuit elements) in output visualization. Default is True.
*   **with\_layout** (*bool*) – Include layout information, with labels on the physical layout. Default is True.
*   **fold** (*int*) – Sets pagination. It can be disabled using -1. In text, sets the length of the lines. This is useful when the drawing does not fit in the console. If None (default), it will try to guess the console width using `shutil. get_terminal_size()`. However, if running in jupyter, the default line length is set to 80 characters. In `mpl` is the number of (visual) layers before folding. Default is 25.
*   **ax** (*matplotlib.axes.Axes*) – An optional Axes object to be used for the visualization output. If none is specified, a new matplotlib Figure will be created and used. Additionally, if specified, there will be no returned Figure since it is redundant. This is only used when the `output` kwarg is set to use the `mpl` backend. It will be silently ignored with all other outputs.
*   **initial\_state** (*bool*) – Optional. Adds `|0>` in the beginning of the wire. Only used by the `text`, `latex` and `latex_source` outputs. Default: `False`.
*   **cregbundle** (*bool*) – Optional. If set True bundle classical registers. Only used by the `text` output. Default: `False`.

**Returns**

`PIL.Image` or `matplotlib.figure` or `str` or `TextDrawing`:

*   **PIL.Image (output=’latex’)**

    an in-memory representation of the image of the circuit diagram.

*   **matplotlib.figure.Figure (output=’mpl’)**

    a matplotlib figure object for the circuit diagram.

*   **str (output=’latex\_source’)**

    The LaTeX source code for visualizing the circuit diagram.

*   **TextDrawing (output=’text’)**

    A drawing that can be printed as ASCII art.

**Raises**

*   [**VisualizationError**](qiskit.visualization.VisualizationError "qiskit.visualization.VisualizationError") – when an invalid output method is selected
*   **ImportError** – when the output methods require non-installed libraries

**Style Dict Details**

The style dict kwarg contains numerous options that define the style of the output circuit visualization. The style dict is only used by the `mpl` output. The options available in the style dict are defined below:

**Parameters**

*   **textcolor** (*str*) – The color code to use for text. Defaults to ‘#000000’

*   **subtextcolor** (*str*) – The color code to use for subtext. Defaults to ‘#000000’

*   **linecolor** (*str*) – The color code to use for lines. Defaults to ‘#000000’

*   **creglinecolor** (*str*) – The color code to use for classical register lines. Defaults to ‘#778899’

*   **gatetextcolor** (*str*) – The color code to use for gate text. Defaults to ‘#000000’

*   **gatefacecolor** (*str*) – The color code to use for gates. Defaults to ‘#ffffff’

*   **barrierfacecolor** (*str*) – The color code to use for barriers. Defaults to ‘#bdbdbd’

*   **backgroundcolor** (*str*) – The color code to use for the background. Defaults to ‘#ffffff’

*   **fontsize** (*int*) – The font size to use for text. Defaults to 13.

*   **subfontsize** (*int*) – The font size to use for subtext. Defaults to 8.

*   **displaytext** (*dict*) –

    A dictionary of the text to use for each element type in the output visualization. The default values are:

    ```python
    {
        'id': 'id',
        'u0': 'U_0',
        'u1': 'U_1',
        'u2': 'U_2',
        'u3': 'U_3',
        'x': 'X',
        'y': 'Y',
        'z': 'Z',
        'h': 'H',
        's': 'S',
        'sdg': 'S^\dagger',
        't': 'T',
        'tdg': 'T^\dagger',
        'rx': 'R_x',
        'ry': 'R_y',
        'rz': 'R_z',
        'reset': '\left|0\right\rangle'
    }
    ```

    You must specify all the necessary values if using this. There is no provision for passing an incomplete dict in.

*   **displaycolor** (*dict*) –

    **The color codes to use for each circuit**

    element. The default values are:

    ```python
    {
        'id': '#F0E442',
        'u0': '#E7AB3B',
        'u1': '#E7AB3B',
        'u2': '#E7AB3B',
        'u3': '#E7AB3B',
        'x': '#58C698',
        'y': '#58C698',
        'z': '#58C698',
        'h': '#70B7EB',
        's': '#E0722D',
        'sdg': '#E0722D',
        't': '#E0722D',
        'tdg': '#E0722D',
        'rx': '#ffffff',
        'ry': '#ffffff',
        'rz': '#ffffff',
        'reset': '#D188B4',
        'target': '#70B7EB',
        'meas': '#D188B4'
    }
    ```

    Also, just like displaytext there is no provision for an incomplete dict passed in.

*   **latexdrawerstyle** (*bool*) – When set to True, enable LaTeX mode, which will draw gates like the latex output modes.

*   **usepiformat** (*bool*) – When set to True, use radians for output.

*   **fold** (*int*) – The number of circuit elements to fold the circuit at. Defaults to 20.

*   **cregbundle** (*bool*) – If set True, bundle classical registers

*   **showindex** (*bool*) – If set True, draw an index.

*   **compress** (*bool*) – If set True, draw a compressed circuit.

*   **figwidth** (*int*) – The maximum width (in inches) for the output figure.

*   **dpi** (*int*) – The DPI to use for the output image. Defaults to 150.

*   **margin** (*list*) – A list of margin values to adjust spacing around output image. Takes a list of 4 ints: \[x left, x right, y bottom, y top].

*   **creglinestyle** (*str*) – The style of line to use for classical registers. Choices are ‘solid’, ‘doublet’, or any valid matplotlib linestyle kwarg value. Defaults to doublet

### extend

<span id="qiskit.circuit.library.PauliFeatureMap.extend" />

`PauliFeatureMap.extend(rhs)`

Append QuantumCircuit to the right hand side if it contains compatible registers.

Two circuits are compatible if they contain the same registers or if they contain different registers with unique names. The returned circuit will contain all unique registers between both circuits.

Modify and return self.

**Parameters**

**rhs** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – The quantum circuit to append to the right hand side.

**Returns**

Returns this QuantumCircuit object (which has been modified)

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the rhs circuit is not compatible

### fredkin

<span id="qiskit.circuit.library.PauliFeatureMap.fredkin" />

`PauliFeatureMap.fredkin(control_qubit, target_qubit1, target_qubit2, *, ctl=None, tgt1=None, tgt2=None)`

Apply [`CSwapGate`](qiskit.circuit.library.CSwapGate "qiskit.circuit.library.CSwapGate").

### from\_qasm\_file

<span id="qiskit.circuit.library.PauliFeatureMap.from_qasm_file" />

`static PauliFeatureMap.from_qasm_file(path)`

Take in a QASM file and generate a QuantumCircuit object.

**Parameters**

**path** (*str*) – Path to the file for a QASM program

**Returns**

The QuantumCircuit object for the input QASM

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### from\_qasm\_str

<span id="qiskit.circuit.library.PauliFeatureMap.from_qasm_str" />

`static PauliFeatureMap.from_qasm_str(qasm_str)`

Take in a QASM string and generate a QuantumCircuit object.

**Parameters**

**qasm\_str** (*str*) – A QASM program string

**Returns**

The QuantumCircuit object for the input QASM

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### get\_entangler\_map

<span id="qiskit.circuit.library.PauliFeatureMap.get_entangler_map" />

`PauliFeatureMap.get_entangler_map(rep_num, block_num, num_block_qubits)`

Get the entangler map for in the repetition `rep_num` and the block `block_num`.

The entangler map for the current block is derived from the value of `self.entanglement`. Below the different cases are listed, where `i` and `j` denote the repetition number and the block number, respectively, and `n` the number of qubits in the block.

entanglement type | entangler map ——————————-+——————————————————– None | \[\[0, …, n - 1]] str (e.g ‘full’) | the specified connectivity on `n` qubits List\[int] | \[`entanglement`] List\[List\[int]] | `entanglement` List\[List\[List\[int]]] | `entanglement[i]` List\[List\[List\[List\[int]]]] | `entanglement[i][j]` List\[str] | the connectivity specified in `entanglement[i]` List\[List\[str]] | the connectivity specified in `entanglement[i][j]` Callable\[int, str] | same as List\[str] Callable\[int, List\[List\[int]]] | same as List\[List\[List\[int]]]

Note that all indices are to be taken modulo the length of the array they act on, i.e. no out-of-bounds index error will be raised but we re-iterate from the beginning of the list.

**Parameters**

*   **rep\_num** (`int`) – The current repetition we are in.
*   **block\_num** (`int`) – The block number within the entanglement layers.
*   **num\_block\_qubits** (`int`) – The number of qubits in the block.

**Return type**

`List`\[`List`\[`int`]]

**Returns**

The entangler map for the current block in the current repetition.

**Raises**

**ValueError** – If the value of `entanglement` could not be cast to a corresponding entangler map.

### get\_unentangled\_qubits

<span id="qiskit.circuit.library.PauliFeatureMap.get_unentangled_qubits" />

`PauliFeatureMap.get_unentangled_qubits()`

Get the indices of unentangled qubits in a set.

**Return type**

`Set`\[`int`]

**Returns**

The unentangled qubits.

### h

<span id="qiskit.circuit.library.PauliFeatureMap.h" />

`PauliFeatureMap.h(qubit, *, q=None)`

Apply [`HGate`](qiskit.circuit.library.HGate "qiskit.circuit.library.HGate").

### hamiltonian

<span id="qiskit.circuit.library.PauliFeatureMap.hamiltonian" />

`PauliFeatureMap.hamiltonian(operator, time, qubits, label=None)`

Apply hamiltonian evolution to to qubits.

### has\_register

<span id="qiskit.circuit.library.PauliFeatureMap.has_register" />

`PauliFeatureMap.has_register(register)`

Test if this circuit has the register r.

**Parameters**

**register** (*Register*) – a quantum or classical register.

**Returns**

True if the register is contained in this circuit.

**Return type**

bool

### i

<span id="qiskit.circuit.library.PauliFeatureMap.i" />

`PauliFeatureMap.i(qubit, *, q=None)`

Apply [`IGate`](qiskit.circuit.library.IGate "qiskit.circuit.library.IGate").

### id

<span id="qiskit.circuit.library.PauliFeatureMap.id" />

`PauliFeatureMap.id(qubit, *, q=None)`

Apply [`IGate`](qiskit.circuit.library.IGate "qiskit.circuit.library.IGate").

### iden

<span id="qiskit.circuit.library.PauliFeatureMap.iden" />

`PauliFeatureMap.iden(qubit, *, q=None)`

Deprecated identity gate.

### initialize

<span id="qiskit.circuit.library.PauliFeatureMap.initialize" />

`PauliFeatureMap.initialize(params, qubits)`

Apply initialize to circuit.

### inverse

<span id="qiskit.circuit.library.PauliFeatureMap.inverse" />

`PauliFeatureMap.inverse()`

Invert this circuit.

This is done by recursively inverting all gates.

**Returns**

the inverted circuit

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**CircuitError** – if the circuit cannot be inverted.

### iso

<span id="qiskit.circuit.library.PauliFeatureMap.iso" />

`PauliFeatureMap.iso(isometry, q_input, q_ancillas_for_output, q_ancillas_zero=None, q_ancillas_dirty=None)`

Attach an arbitrary isometry from m to n qubits to a circuit. In particular, this allows to attach arbitrary unitaries on n qubits (m=n) or to prepare any state on n qubits (m=0). The decomposition used here was introduced by Iten et al. in [https://arxiv.org/abs/1501.06911](https://arxiv.org/abs/1501.06911).

**Parameters**

*   **isometry** (*ndarray*) – an isometry from m to n qubits, i.e., a (complex) ndarray of dimension 2^n×2^m with orthonormal columns (given in the computational basis specified by the order of the ancillas and the input qubits, where the ancillas are considered to be more significant than the input qubits.).
*   **q\_input** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of m qubits where the input to the isometry is fed in (empty list for state preparation).
*   **q\_ancillas\_for\_output** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of n-m ancilla qubits that are used for the output of the isometry and which are assumed to start in the zero state. The qubits are listed with increasing significance.
*   **q\_ancillas\_zero** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of ancilla qubits which are assumed to start in the zero state. Default is q\_ancillas\_zero = None.
*   **q\_ancillas\_dirty** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of ancilla qubits which can start in an arbitrary state. Default is q\_ancillas\_dirty = None.

**Returns**

the isometry is attached to the quantum circuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the array is not an isometry of the correct size corresponding to the provided number of qubits.

### isometry

<span id="qiskit.circuit.library.PauliFeatureMap.isometry" />

`PauliFeatureMap.isometry(isometry, q_input, q_ancillas_for_output, q_ancillas_zero=None, q_ancillas_dirty=None)`

Attach an arbitrary isometry from m to n qubits to a circuit. In particular, this allows to attach arbitrary unitaries on n qubits (m=n) or to prepare any state on n qubits (m=0). The decomposition used here was introduced by Iten et al. in [https://arxiv.org/abs/1501.06911](https://arxiv.org/abs/1501.06911).

**Parameters**

*   **isometry** (*ndarray*) – an isometry from m to n qubits, i.e., a (complex) ndarray of dimension 2^n×2^m with orthonormal columns (given in the computational basis specified by the order of the ancillas and the input qubits, where the ancillas are considered to be more significant than the input qubits.).
*   **q\_input** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of m qubits where the input to the isometry is fed in (empty list for state preparation).
*   **q\_ancillas\_for\_output** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of n-m ancilla qubits that are used for the output of the isometry and which are assumed to start in the zero state. The qubits are listed with increasing significance.
*   **q\_ancillas\_zero** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of ancilla qubits which are assumed to start in the zero state. Default is q\_ancillas\_zero = None.
*   **q\_ancillas\_dirty** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of ancilla qubits which can start in an arbitrary state. Default is q\_ancillas\_dirty = None.

**Returns**

the isometry is attached to the quantum circuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the array is not an isometry of the correct size corresponding to the provided number of qubits.

### iswap

<span id="qiskit.circuit.library.PauliFeatureMap.iswap" />

`PauliFeatureMap.iswap(qubit1, qubit2)`

Apply [`iSwapGate`](qiskit.circuit.library.iSwapGate "qiskit.circuit.library.iSwapGate").

### mcmt

<span id="qiskit.circuit.library.PauliFeatureMap.mcmt" />

`PauliFeatureMap.mcmt(gate, control_qubits, target_qubits, ancilla_qubits=None, mode='no-ancilla', *, single_control_gate_fun=None, q_controls=None, q_ancillae=None, q_targets=None)`

Apply a multi-control, multi-target using a generic gate.

This can also be used to implement a generic multi-control gate, as the target could also be of length 1.

### mcrx

<span id="qiskit.circuit.library.PauliFeatureMap.mcrx" />

`PauliFeatureMap.mcrx(theta, q_controls, q_target, use_basis_gates=False)`

Apply Multiple-Controlled X rotation gate

**Parameters**

*   **self** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – The QuantumCircuit object to apply the mcrx gate on.
*   **theta** (*float*) – angle theta
*   **q\_controls** (*list(*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*)*) – The list of control qubits
*   **q\_target** ([*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")) – The target qubit
*   **use\_basis\_gates** (*bool*) – use u1, u2, u3, cx, id

**Raises**

**QiskitError** – parameter errors

### mcry

<span id="qiskit.circuit.library.PauliFeatureMap.mcry" />

`PauliFeatureMap.mcry(theta, q_controls, q_target, q_ancillae, mode='basic', use_basis_gates=False)`

Apply Multiple-Controlled Y rotation gate

**Parameters**

*   **self** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – The QuantumCircuit object to apply the mcry gate on.
*   **theta** (*float*) – angle theta
*   **q\_controls** (*list(*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*)*) – The list of control qubits
*   **q\_target** ([*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")) – The target qubit
*   **q\_ancillae** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister") *or tuple(*[*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*, int)*) – The list of ancillary qubits.
*   **mode** (*string*) – The implementation mode to use
*   **use\_basis\_gates** (*bool*) – use u1, u2, u3, cx, id

**Raises**

**QiskitError** – parameter errors

### mcrz

<span id="qiskit.circuit.library.PauliFeatureMap.mcrz" />

`PauliFeatureMap.mcrz(lam, q_controls, q_target, use_basis_gates=False)`

Apply Multiple-Controlled Z rotation gate

**Parameters**

*   **self** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – The QuantumCircuit object to apply the mcrz gate on.
*   **lam** (*float*) – angle lambda
*   **q\_controls** (*list(*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*)*) – The list of control qubits
*   **q\_target** ([*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")) – The target qubit
*   **use\_basis\_gates** (*bool*) – use u1, u2, u3, cx, id

**Raises**

**QiskitError** – parameter errors

### mct

<span id="qiskit.circuit.library.PauliFeatureMap.mct" />

`PauliFeatureMap.mct(control_qubits, target_qubit, ancilla_qubits=None, mode='noancilla')`

Apply `MCXGate`.

### mcu1

<span id="qiskit.circuit.library.PauliFeatureMap.mcu1" />

`PauliFeatureMap.mcu1(lam, control_qubits, target_qubit)`

Apply `MCU1Gate`.

### mcx

<span id="qiskit.circuit.library.PauliFeatureMap.mcx" />

`PauliFeatureMap.mcx(control_qubits, target_qubit, ancilla_qubits=None, mode='noancilla')`

Apply `MCXGate`.

The multi-cX gate can be implemented using different techniques, which use different numbers of ancilla qubits and have varying circuit depth. These modes are: - ‘no-ancilla’: Requires 0 ancilla qubits. - ‘recursion’: Requires 1 ancilla qubit if more than 4 controls are used, otherwise 0. - ‘v-chain’: Requires 2 less ancillas than the number of control qubits. - ‘v-chain-dirty’: Same as for the clean ancillas (but the circuit will be longer).

### measure

<span id="qiskit.circuit.library.PauliFeatureMap.measure" />

`PauliFeatureMap.measure(qubit, cbit)`

Measure quantum bit into classical bit (tuples).

**Parameters**

*   **qubit** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*|list|tuple*) – quantum register
*   **cbit** ([*ClassicalRegister*](qiskit.circuit.ClassicalRegister "qiskit.circuit.ClassicalRegister")*|list|tuple*) – classical register

**Returns**

the attached measure instruction.

**Return type**

qiskit.Instruction

**Raises**

**CircuitError** – if qubit is not in this circuit or bad format; if cbit is not in this circuit or not creg.

### measure\_active

<span id="qiskit.circuit.library.PauliFeatureMap.measure_active" />

`PauliFeatureMap.measure_active(inplace=True)`

Adds measurement to all non-idle qubits. Creates a new ClassicalRegister with a size equal to the number of non-idle qubits being measured.

Returns a new circuit with measurements if inplace=False.

**Parameters**

**inplace** (*bool*) – All measurements inplace or return new circuit.

**Returns**

Returns circuit with measurements when inplace = False.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### measure\_all

<span id="qiskit.circuit.library.PauliFeatureMap.measure_all" />

`PauliFeatureMap.measure_all(inplace=True)`

Adds measurement to all qubits. Creates a new ClassicalRegister with a size equal to the number of qubits being measured.

Returns a new circuit with measurements if inplace=False.

**Parameters**

**inplace** (*bool*) – All measurements inplace or return new circuit.

**Returns**

Returns circuit with measurements when inplace = False.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### mirror

<span id="qiskit.circuit.library.PauliFeatureMap.mirror" />

`PauliFeatureMap.mirror()`

Mirror the circuit by reversing the instructions.

This is done by recursively mirroring all instructions. It does not invert any gate.

**Returns**

the mirrored circuit

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### ms

<span id="qiskit.circuit.library.PauliFeatureMap.ms" />

`PauliFeatureMap.ms(theta, qubits)`

Apply [`MSGate`](qiskit.circuit.library.MSGate "qiskit.circuit.library.MSGate").

### num\_connected\_components

<span id="qiskit.circuit.library.PauliFeatureMap.num_connected_components" />

`PauliFeatureMap.num_connected_components(unitary_only=False)`

How many non-entangled subcircuits can the circuit be factored to.

**Parameters**

**unitary\_only** (*bool*) – Compute only unitary part of graph.

**Returns**

Number of connected components in circuit.

**Return type**

int

### num\_nonlocal\_gates

<span id="qiskit.circuit.library.PauliFeatureMap.num_nonlocal_gates" />

`PauliFeatureMap.num_nonlocal_gates()`

Return number of non-local gates (i.e. involving 2+ qubits).

Conditional nonlocal gates are also included.

### num\_tensor\_factors

<span id="qiskit.circuit.library.PauliFeatureMap.num_tensor_factors" />

`PauliFeatureMap.num_tensor_factors()`

Computes the number of tensor factors in the unitary (quantum) part of the circuit only.

#### Notes

This is here for backwards compatibility, and will be removed in a future release of Qiskit. You should call num\_unitary\_factors instead.

### num\_unitary\_factors

<span id="qiskit.circuit.library.PauliFeatureMap.num_unitary_factors" />

`PauliFeatureMap.num_unitary_factors()`

Computes the number of tensor factors in the unitary (quantum) part of the circuit only.

### pauli\_block

<span id="qiskit.circuit.library.PauliFeatureMap.pauli_block" />

`PauliFeatureMap.pauli_block(pauli_string)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/circuit/library/data_preparation/pauli_feature_map.py "view source code")

Get the Pauli block for the feature map circuit.

### pauli\_evolution

<span id="qiskit.circuit.library.PauliFeatureMap.pauli_evolution" />

`PauliFeatureMap.pauli_evolution(pauli_string, time)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.14/qiskit/circuit/library/data_preparation/pauli_feature_map.py "view source code")

Get the evolution block for the given pauli string.

### print\_settings

<span id="qiskit.circuit.library.PauliFeatureMap.print_settings" />

`PauliFeatureMap.print_settings()`

Returns information about the setting.

**Return type**

`str`

**Returns**

The class name and the attributes/parameters of the instance as `str`.

### qasm

<span id="qiskit.circuit.library.PauliFeatureMap.qasm" />

`PauliFeatureMap.qasm(formatted=False, filename=None)`

Return OpenQASM string.

**Parameters**

*   **formatted** (*bool*) – Return formatted Qasm string.
*   **filename** (*str*) – Save Qasm to file with name ‘filename’.

**Returns**

If formatted=False.

**Return type**

str

**Raises**

**ImportError** – If pygments is not installed and `formatted` is `True`.

### qbit\_argument\_conversion

<span id="qiskit.circuit.library.PauliFeatureMap.qbit_argument_conversion" />

`PauliFeatureMap.qbit_argument_conversion(qubit_representation)`

Converts several qubit representations (such as indexes, range, etc.) into a list of qubits.

**Parameters**

**qubit\_representation** (*Object*) – representation to expand

**Returns**

Where each tuple is a qubit.

**Return type**

List(tuple)

### r

<span id="qiskit.circuit.library.PauliFeatureMap.r" />

`PauliFeatureMap.r(theta, phi, qubit, *, q=None)`

Apply `RGate`.

### rcccx

<span id="qiskit.circuit.library.PauliFeatureMap.rcccx" />

`PauliFeatureMap.rcccx(control_qubit1, control_qubit2, control_qubit3, target_qubit)`

Apply [`RC3XGate`](qiskit.circuit.library.RC3XGate "qiskit.circuit.library.RC3XGate").

### rccx

<span id="qiskit.circuit.library.PauliFeatureMap.rccx" />

`PauliFeatureMap.rccx(control_qubit1, control_qubit2, target_qubit)`

Apply [`RCCXGate`](qiskit.circuit.library.RCCXGate "qiskit.circuit.library.RCCXGate").

### remove\_final\_measurements

<span id="qiskit.circuit.library.PauliFeatureMap.remove_final_measurements" />

`PauliFeatureMap.remove_final_measurements(inplace=True)`

Removes final measurement on all qubits if they are present. Deletes the ClassicalRegister that was used to store the values from these measurements if it is idle.

Returns a new circuit without measurements if inplace=False.

**Parameters**

**inplace** (*bool*) – All measurements removed inplace or return new circuit.

**Returns**

Returns circuit with measurements removed when inplace = False.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### reset

<span id="qiskit.circuit.library.PauliFeatureMap.reset" />

`PauliFeatureMap.reset(qubit)`

Reset q.

### rx

<span id="qiskit.circuit.library.PauliFeatureMap.rx" />

`PauliFeatureMap.rx(theta, qubit, *, label=None, q=None)`

Apply [`RXGate`](qiskit.circuit.library.RXGate "qiskit.circuit.library.RXGate").

### rxx

<span id="qiskit.circuit.library.PauliFeatureMap.rxx" />

`PauliFeatureMap.rxx(theta, qubit1, qubit2)`

Apply [`RXXGate`](qiskit.circuit.library.RXXGate "qiskit.circuit.library.RXXGate").

### ry

<span id="qiskit.circuit.library.PauliFeatureMap.ry" />

`PauliFeatureMap.ry(theta, qubit, *, label=None, q=None)`

Apply [`RYGate`](qiskit.circuit.library.RYGate "qiskit.circuit.library.RYGate").

### ryy

<span id="qiskit.circuit.library.PauliFeatureMap.ryy" />

`PauliFeatureMap.ryy(theta, qubit1, qubit2)`

Apply [`RYYGate`](qiskit.circuit.library.RYYGate "qiskit.circuit.library.RYYGate").

### rz

<span id="qiskit.circuit.library.PauliFeatureMap.rz" />

`PauliFeatureMap.rz(phi, qubit, *, q=None)`

Apply [`RZGate`](qiskit.circuit.library.RZGate "qiskit.circuit.library.RZGate").

### rzx

<span id="qiskit.circuit.library.PauliFeatureMap.rzx" />

`PauliFeatureMap.rzx(theta, qubit1, qubit2)`

Apply [`RZXGate`](qiskit.circuit.library.RZXGate "qiskit.circuit.library.RZXGate").

### rzz

<span id="qiskit.circuit.library.PauliFeatureMap.rzz" />

`PauliFeatureMap.rzz(theta, qubit1, qubit2)`

Apply [`RZZGate`](qiskit.circuit.library.RZZGate "qiskit.circuit.library.RZZGate").

### s

<span id="qiskit.circuit.library.PauliFeatureMap.s" />

`PauliFeatureMap.s(qubit, *, q=None)`

Apply [`SGate`](qiskit.circuit.library.SGate "qiskit.circuit.library.SGate").

### sdg

<span id="qiskit.circuit.library.PauliFeatureMap.sdg" />

`PauliFeatureMap.sdg(qubit, *, q=None)`

Apply [`SdgGate`](qiskit.circuit.library.SdgGate "qiskit.circuit.library.SdgGate").

### size

<span id="qiskit.circuit.library.PauliFeatureMap.size" />

`PauliFeatureMap.size()`

Returns total number of gate operations in circuit.

**Returns**

Total number of gate operations.

**Return type**

int

### snapshot

<span id="qiskit.circuit.library.PauliFeatureMap.snapshot" />

`PauliFeatureMap.snapshot(label, snapshot_type='statevector', qubits=None, params=None)`

Take a statevector snapshot of the internal simulator representation. Works on all qubits, and prevents reordering (like barrier). :param label: a snapshot label to report the result :type label: str :param snapshot\_type: the type of the snapshot. :type snapshot\_type: str :param qubits: the qubits to apply snapshot to \[Default: None]. :type qubits: list or None :param params: the parameters for snapshot\_type \[Default: None]. :type params: list or None

**Returns**

with attached command

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – malformed command

### snapshot\_density\_matrix

<span id="qiskit.circuit.library.PauliFeatureMap.snapshot_density_matrix" />

`PauliFeatureMap.snapshot_density_matrix(label, qubits=None)`

Take a density matrix snapshot of simulator state.

**Parameters**

*   **label** (*str*) – a snapshot label to report the result
*   **qubits** (*list or None*) – the qubits to apply snapshot to. If None all qubits will be snapshot \[Default: None].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – if snapshot is invalid.

### snapshot\_expectation\_value

<span id="qiskit.circuit.library.PauliFeatureMap.snapshot_expectation_value" />

`PauliFeatureMap.snapshot_expectation_value(label, op, qubits, single_shot=False, variance=False)`

Take a snapshot of expectation value \<O> of an Operator.

**Parameters**

*   **label** (*str*) – a snapshot label to report the result
*   **op** ([*Operator*](qiskit.quantum_info.Operator "qiskit.quantum_info.Operator")) – operator to snapshot
*   **qubits** (*list*) – the qubits to snapshot.
*   **single\_shot** (*bool*) – return list for each shot rather than average \[Default: False]
*   **variance** (*bool*) – compute variance of probabilities \[Default: False]

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – if snapshot is invalid.

### snapshot\_probabilities

<span id="qiskit.circuit.library.PauliFeatureMap.snapshot_probabilities" />

`PauliFeatureMap.snapshot_probabilities(label, qubits, variance=False)`

Take a probability snapshot of the simulator state.

**Parameters**

*   **label** (*str*) – a snapshot label to report the result
*   **qubits** (*list*) – the qubits to snapshot.
*   **variance** (*bool*) – compute variance of probabilities \[Default: False]

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – if snapshot is invalid.

### snapshot\_stabilizer

<span id="qiskit.circuit.library.PauliFeatureMap.snapshot_stabilizer" />

`PauliFeatureMap.snapshot_stabilizer(label)`

Take a stabilizer snapshot of the simulator state.

**Parameters**

**label** (*str*) – a snapshot label to report the result.

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – if snapshot is invalid.

#### Additional Information:

This snapshot is always performed on all qubits in a circuit. The number of qubits parameter specifies the size of the instruction as a barrier and should be set to the number of qubits in the circuit.

### snapshot\_statevector

<span id="qiskit.circuit.library.PauliFeatureMap.snapshot_statevector" />

`PauliFeatureMap.snapshot_statevector(label)`

Take a statevector snapshot of the simulator state.

**Parameters**

**label** (*str*) – a snapshot label to report the result.

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – if snapshot is invalid.

#### Additional Information:

This snapshot is always performed on all qubits in a circuit. The number of qubits parameter specifies the size of the instruction as a barrier and should be set to the number of qubits in the circuit.

### squ

<span id="qiskit.circuit.library.PauliFeatureMap.squ" />

`PauliFeatureMap.squ(unitary_matrix, qubit, mode='ZYZ', up_to_diagonal=False, *, u=None)`

Decompose an arbitrary 2\*2 unitary into three rotation gates.

Note that the decomposition is up to a global phase shift. (This is a well known decomposition, which can be found for example in Nielsen and Chuang’s book “Quantum computation and quantum information”.)

**Parameters**

*   **unitary\_matrix** (*ndarray*) – 2\*2 unitary (given as a (complex) ndarray).
*   **qubit** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")  *|*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")) – The qubit which the gate is acting on.
*   **mode** (*string*) – determines the used decomposition by providing the rotation axes. The allowed modes are: “ZYZ” (default)
*   **up\_to\_diagonal** (*bool*) – if set to True, the single-qubit unitary is decomposed up to a diagonal matrix, i.e. a unitary u’ is implemented such that there exists a 2\*2 diagonal gate d with u = d.dot(u’)
*   **u** (*ndarray*) – Deprecated, use `unitary_matrix` instead.

**Returns**

The single-qubit unitary instruction attached to the circuit.

**Return type**

[InstructionSet](qiskit.circuit.InstructionSet "qiskit.circuit.InstructionSet")

**Raises**

**QiskitError** – if the format is wrong; if the array u is not unitary

### swap

<span id="qiskit.circuit.library.PauliFeatureMap.swap" />

`PauliFeatureMap.swap(qubit1, qubit2)`

Apply [`SwapGate`](qiskit.circuit.library.SwapGate "qiskit.circuit.library.SwapGate").

### t

<span id="qiskit.circuit.library.PauliFeatureMap.t" />

`PauliFeatureMap.t(qubit, *, q=None)`

Apply [`TGate`](qiskit.circuit.library.TGate "qiskit.circuit.library.TGate").

### tdg

<span id="qiskit.circuit.library.PauliFeatureMap.tdg" />

`PauliFeatureMap.tdg(qubit, *, q=None)`

Apply [`TdgGate`](qiskit.circuit.library.TdgGate "qiskit.circuit.library.TdgGate").

### to\_gate

<span id="qiskit.circuit.library.PauliFeatureMap.to_gate" />

`PauliFeatureMap.to_gate(parameter_map=None)`

Create a Gate out of this circuit.

**Parameters**

**parameter\_map** (*dict*) – For parameterized circuits, a mapping from parameters in the circuit to parameters to be used in the gate. If None, existing circuit parameters will also parameterize the gate.

**Returns**

a composite gate encapsulating this circuit (can be decomposed back)

**Return type**

[Gate](qiskit.circuit.Gate "qiskit.circuit.Gate")

### to\_instruction

<span id="qiskit.circuit.library.PauliFeatureMap.to_instruction" />

`PauliFeatureMap.to_instruction(parameter_map=None)`

Create an Instruction out of this circuit.

**Parameters**

**parameter\_map** (*dict*) – For parameterized circuits, a mapping from parameters in the circuit to parameters to be used in the instruction. If None, existing circuit parameters will also parameterize the instruction.

**Returns**

a composite instruction encapsulating this circuit (can be decomposed back)

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

### toffoli

<span id="qiskit.circuit.library.PauliFeatureMap.toffoli" />

`PauliFeatureMap.toffoli(control_qubit1, control_qubit2, target_qubit, *, ctl1=None, ctl2=None, tgt=None)`

Apply [`CCXGate`](qiskit.circuit.library.CCXGate "qiskit.circuit.library.CCXGate").

### u1

<span id="qiskit.circuit.library.PauliFeatureMap.u1" />

`PauliFeatureMap.u1(theta, qubit, *, q=None)`

Apply [`U1Gate`](qiskit.circuit.library.U1Gate "qiskit.circuit.library.U1Gate").

### u2

<span id="qiskit.circuit.library.PauliFeatureMap.u2" />

`PauliFeatureMap.u2(phi, lam, qubit, *, q=None)`

Apply [`U2Gate`](qiskit.circuit.library.U2Gate "qiskit.circuit.library.U2Gate").

### u3

<span id="qiskit.circuit.library.PauliFeatureMap.u3" />

`PauliFeatureMap.u3(theta, phi, lam, qubit, *, q=None)`

Apply [`U3Gate`](qiskit.circuit.library.U3Gate "qiskit.circuit.library.U3Gate").

### uc

<span id="qiskit.circuit.library.PauliFeatureMap.uc" />

`PauliFeatureMap.uc(gate_list, q_controls, q_target, up_to_diagonal=False)`

Attach a uniformly controlled gates (also called multiplexed gates) to a circuit.

The decomposition was introduced by Bergholm et al. in [https://arxiv.org/pdf/quant-ph/0410066.pdf](https://arxiv.org/pdf/quant-ph/0410066.pdf).

**Parameters**

*   **gate\_list** (*list\[ndarray]*) – list of two qubit unitaries \[U\_0,…,U\_\{2^k-1}], where each single-qubit unitary U\_i is a given as a 2\*2 array
*   **q\_controls** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*|list\[(*[*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*,int)]*) – list of k control qubits. The qubits are ordered according to their significance in the computational basis. For example if q\_controls=\[q\[1],q\[2]] (with q = QuantumRegister(2)), the unitary U\_0 is performed if q\[1] and q\[2] are in the state zero, U\_1 is performed if q\[2] is in the state zero and q\[1] is in the state one, and so on
*   **q\_target** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*|(*[*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*,int)*) – target qubit, where we act on with the single-qubit gates.
*   **up\_to\_diagonal** (*bool*) – If set to True, the uniformly controlled gate is decomposed up to a diagonal gate, i.e. a unitary u’ is implemented such that there exists a diagonal gate d with u = d.dot(u’), where the unitary u describes the uniformly controlled gate

**Returns**

the uniformly controlled gate is attached to the circuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the list number of control qubits does not correspond to the provided number of single-qubit unitaries; if an input is of the wrong type

### ucg

<span id="qiskit.circuit.library.PauliFeatureMap.ucg" />

`PauliFeatureMap.ucg(angle_list, q_controls, q_target, up_to_diagonal=False)`

Deprecated version of uc.

### ucrx

<span id="qiskit.circuit.library.PauliFeatureMap.ucrx" />

`PauliFeatureMap.ucrx(angle_list, q_controls, q_target)`

Attach a uniformly controlled (also called multiplexed) Rx rotation gate to a circuit.

The decomposition is base on [https://arxiv.org/pdf/quant-ph/0406176.pdf](https://arxiv.org/pdf/quant-ph/0406176.pdf) by Shende et al.

**Parameters**

*   **angle\_list** (*list*) – list of (real) rotation angles $[a_0,...,a_{2^k-1}]$
*   **q\_controls** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*|list*) – list of k control qubits (or empty list if no controls). The control qubits are ordered according to their significance in increasing order: For example if `q_controls=[q[0],q[1]]` (with `q = QuantumRegister(2)`), the rotation `Rx(a_0)` is performed if `q[0]` and `q[1]` are in the state zero, the rotation `Rx(a_1)` is performed if `q[0]` is in the state one and `q[1]` is in the state zero, and so on
*   **q\_target** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*|*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")) – target qubit, where we act on with the single-qubit rotation gates

**Returns**

the uniformly controlled rotation gate is attached to the circuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the list number of control qubits does not correspond to the provided number of single-qubit unitaries; if an input is of the wrong type

### ucry

<span id="qiskit.circuit.library.PauliFeatureMap.ucry" />

`PauliFeatureMap.ucry(angle_list, q_controls, q_target)`

Attach a uniformly controlled (also called multiplexed) Ry rotation gate to a circuit.

The decomposition is base on [https://arxiv.org/pdf/quant-ph/0406176.pdf](https://arxiv.org/pdf/quant-ph/0406176.pdf) by Shende et al.

**Parameters**

*   **angle\_list** (*list\[numbers*) – list of (real) rotation angles $[a_0,...,a_{2^k-1}]$
*   **q\_controls** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of k control qubits (or empty list if no controls). The control qubits are ordered according to their significance in increasing order: For example if `q_controls=[q[0],q[1]]` (with `q = QuantumRegister(2)`), the rotation `Ry(a_0)` is performed if `q[0]` and `q[1]` are in the state zero, the rotation `Ry(a_1)` is performed if `q[0]` is in the state one and `q[1]` is in the state zero, and so on
*   **q\_target** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*|*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")) – target qubit, where we act on with the single-qubit rotation gates

**Returns**

the uniformly controlled rotation gate is attached to the circuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the list number of control qubits does not correspond to the provided number of single-qubit unitaries; if an input is of the wrong type

### ucrz

<span id="qiskit.circuit.library.PauliFeatureMap.ucrz" />

`PauliFeatureMap.ucrz(angle_list, q_controls, q_target)`

Attach a uniformly controlled (also called multiplexed gates) Rz rotation gate to a circuit.

The decomposition is base on [https://arxiv.org/pdf/quant-ph/0406176.pdf](https://arxiv.org/pdf/quant-ph/0406176.pdf) by Shende et al.

**Parameters**

*   **angle\_list** (*list\[numbers*) – list of (real) rotation angles \[a\_0,…,a\_\{2^k-1}]
*   **q\_controls** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of k control qubits (or empty list if no controls). The control qubits are ordered according to their significance in increasing order: For example if q\_controls=\[q\[1],q\[2]] (with q = QuantumRegister(2)), the rotation Rz(a\_0)is performed if q\[1] and q\[2] are in the state zero, the rotation Rz(a\_1) is performed if q\[1] is in the state one and q\[2] is in the state zero, and so on
*   **q\_target** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*|*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")) – target qubit, where we act on with the single-qubit rotation gates

**Returns**

the uniformly controlled rotation gate is attached to the circuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the list number of control qubits does not correspond to the provided number of single-qubit unitaries; if an input is of the wrong type

### ucx

<span id="qiskit.circuit.library.PauliFeatureMap.ucx" />

`PauliFeatureMap.ucx(angle_list, q_controls, q_target)`

Deprecated version of ucrx.

### ucy

<span id="qiskit.circuit.library.PauliFeatureMap.ucy" />

`PauliFeatureMap.ucy(angle_list, q_controls, q_target)`

Deprecated version of ucry.

### ucz

<span id="qiskit.circuit.library.PauliFeatureMap.ucz" />

`PauliFeatureMap.ucz(angle_list, q_controls, q_target)`

Deprecated version of ucrz.

### unitary

<span id="qiskit.circuit.library.PauliFeatureMap.unitary" />

`PauliFeatureMap.unitary(obj, qubits, label=None)`

Apply unitary gate to q.

### width

<span id="qiskit.circuit.library.PauliFeatureMap.width" />

`PauliFeatureMap.width()`

Return number of qubits plus clbits in circuit.

**Returns**

Width of circuit.

**Return type**

int

### x

<span id="qiskit.circuit.library.PauliFeatureMap.x" />

`PauliFeatureMap.x(qubit, *, label=None, ctrl_state=None, q=None)`

Apply [`XGate`](qiskit.circuit.library.XGate "qiskit.circuit.library.XGate").

### y

<span id="qiskit.circuit.library.PauliFeatureMap.y" />

`PauliFeatureMap.y(qubit, *, q=None)`

Apply [`YGate`](qiskit.circuit.library.YGate "qiskit.circuit.library.YGate").

### z

<span id="qiskit.circuit.library.PauliFeatureMap.z" />

`PauliFeatureMap.z(qubit, *, q=None)`

Apply [`ZGate`](qiskit.circuit.library.ZGate "qiskit.circuit.library.ZGate").

