---
title: RealAmplitudes
description: API reference for qiskit.circuit.library.RealAmplitudes
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.RealAmplitudes
---

# RealAmplitudes

<span id="qiskit.circuit.library.RealAmplitudes" />

`RealAmplitudes(num_qubits=None, entanglement='reverse_linear', reps=3, skip_unentangled_qubits=False, skip_final_rotation_layer=False, parameter_prefix='θ', insert_barriers=False, initial_state=None, name='RealAmplitudes')`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/circuit/library/n_local/real_amplitudes.py "view source code")

Bases: [`TwoLocal`](qiskit.circuit.library.TwoLocal "qiskit.circuit.library.n_local.two_local.TwoLocal")

The real-amplitudes 2-local circuit.

The `RealAmplitudes` circuit is a heuristic trial wave function used as Ansatz in chemistry applications or classification circuits in machine learning. The circuit consists of of alternating layers of $Y$ rotations and $CX$ entanglements. The entanglement pattern can be user-defined or selected from a predefined set. It is called `RealAmplitudes` since the prepared quantum states will only have real amplitudes, the complex part is always 0.

For example a `RealAmplitudes` circuit with 2 repetitions on 3 qubits with `'reverse_linear'` entanglement is

```python
┌──────────┐ ░            ░ ┌──────────┐ ░            ░ ┌──────────┐
┤ Ry(θ[0]) ├─░────────■───░─┤ Ry(θ[3]) ├─░────────■───░─┤ Ry(θ[6]) ├
├──────────┤ ░      ┌─┴─┐ ░ ├──────────┤ ░      ┌─┴─┐ ░ ├──────────┤
┤ Ry(θ[1]) ├─░───■──┤ X ├─░─┤ Ry(θ[4]) ├─░───■──┤ X ├─░─┤ Ry(θ[7]) ├
├──────────┤ ░ ┌─┴─┐└───┘ ░ ├──────────┤ ░ ┌─┴─┐└───┘ ░ ├──────────┤
┤ Ry(θ[2]) ├─░─┤ X ├──────░─┤ Ry(θ[5]) ├─░─┤ X ├──────░─┤ Ry(θ[8]) ├
└──────────┘ ░ └───┘      ░ └──────────┘ ░ └───┘      ░ └──────────┘
```

The entanglement can be set using the `entanglement` keyword as string or a list of index-pairs. See the documentation of [`TwoLocal`](qiskit.circuit.library.TwoLocal "qiskit.circuit.library.TwoLocal") and `NLocal` for more detail. Additional options that can be set include the number of repetitions, skipping rotation gates on qubits that are not entangled, leaving out the final rotation layer and inserting barriers in between the rotation and entanglement layers.

If some qubits are not entangled with other qubits it makes sense to not apply rotation gates on these qubits, since a sequence of $Y$ rotations can be reduced to a single $Y$ rotation with summed rotation angles.

## Examples

```python
>>> ansatz = RealAmplitudes(3, reps=2)  # create the circuit on 3 qubits
>>> print(ansatz)
     ┌──────────┐                 ┌──────────┐                 ┌──────────┐
q_0: ┤ Ry(θ[0]) ├──────────■──────┤ Ry(θ[3]) ├──────────■──────┤ Ry(θ[6]) ├
     ├──────────┤        ┌─┴─┐    ├──────────┤        ┌─┴─┐    ├──────────┤
q_1: ┤ Ry(θ[1]) ├──■─────┤ X ├────┤ Ry(θ[4]) ├──■─────┤ X ├────┤ Ry(θ[7]) ├
     ├──────────┤┌─┴─┐┌──┴───┴───┐└──────────┘┌─┴─┐┌──┴───┴───┐└──────────┘
q_2: ┤ Ry(θ[2]) ├┤ X ├┤ Ry(θ[5]) ├────────────┤ X ├┤ Ry(θ[8]) ├────────────
     └──────────┘└───┘└──────────┘            └───┘└──────────┘
```

```python
>>> ansatz = RealAmplitudes(3, entanglement='full', reps=2)  # it is the same unitary as above
>>> print(ansatz)
     ┌──────────┐          ┌──────────┐                      ┌──────────┐
q_0: ┤ RY(θ[0]) ├──■────■──┤ RY(θ[3]) ├──────────────■────■──┤ RY(θ[6]) ├────────────
     ├──────────┤┌─┴─┐  │  └──────────┘┌──────────┐┌─┴─┐  │  └──────────┘┌──────────┐
q_1: ┤ RY(θ[1]) ├┤ X ├──┼───────■──────┤ RY(θ[4]) ├┤ X ├──┼───────■──────┤ RY(θ[7]) ├
     ├──────────┤└───┘┌─┴─┐   ┌─┴─┐    ├──────────┤└───┘┌─┴─┐   ┌─┴─┐    ├──────────┤
q_2: ┤ RY(θ[2]) ├─────┤ X ├───┤ X ├────┤ RY(θ[5]) ├─────┤ X ├───┤ X ├────┤ RY(θ[8]) ├
     └──────────┘     └───┘   └───┘    └──────────┘     └───┘   └───┘    └──────────┘
```

```python
>>> ansatz = RealAmplitudes(3, entanglement='linear', reps=2, insert_barriers=True)
>>> qc = QuantumCircuit(3)  # create a circuit and append the RY variational form
>>> qc.compose(ansatz, inplace=True)
>>> qc.draw()
     ┌──────────┐ ░            ░ ┌──────────┐ ░            ░ ┌──────────┐
q_0: ┤ RY(θ[0]) ├─░───■────────░─┤ RY(θ[3]) ├─░───■────────░─┤ RY(θ[6]) ├
     ├──────────┤ ░ ┌─┴─┐      ░ ├──────────┤ ░ ┌─┴─┐      ░ ├──────────┤
q_1: ┤ RY(θ[1]) ├─░─┤ X ├──■───░─┤ RY(θ[4]) ├─░─┤ X ├──■───░─┤ RY(θ[7]) ├
     ├──────────┤ ░ └───┘┌─┴─┐ ░ ├──────────┤ ░ └───┘┌─┴─┐ ░ ├──────────┤
q_2: ┤ RY(θ[2]) ├─░──────┤ X ├─░─┤ RY(θ[5]) ├─░──────┤ X ├─░─┤ RY(θ[8]) ├
     └──────────┘ ░      └───┘ ░ └──────────┘ ░      └───┘ ░ └──────────┘
```

```python
>>> ansatz = RealAmplitudes(4, reps=1, entanglement='circular', insert_barriers=True)
>>> print(ansatz)
     ┌──────────┐ ░ ┌───┐                ░ ┌──────────┐
q_0: ┤ RY(θ[0]) ├─░─┤ X ├──■─────────────░─┤ RY(θ[4]) ├
     ├──────────┤ ░ └─┬─┘┌─┴─┐           ░ ├──────────┤
q_1: ┤ RY(θ[1]) ├─░───┼──┤ X ├──■────────░─┤ RY(θ[5]) ├
     ├──────────┤ ░   │  └───┘┌─┴─┐      ░ ├──────────┤
q_2: ┤ RY(θ[2]) ├─░───┼───────┤ X ├──■───░─┤ RY(θ[6]) ├
     ├──────────┤ ░   │       └───┘┌─┴─┐ ░ ├──────────┤
q_3: ┤ RY(θ[3]) ├─░───■────────────┤ X ├─░─┤ RY(θ[7]) ├
     └──────────┘ ░                └───┘ ░ └──────────┘
```

```python
>>> ansatz = RealAmplitudes(4, reps=2, entanglement=[[0,3], [0,2]],
... skip_unentangled_qubits=True)
>>> print(ansatz)
     ┌──────────┐                 ┌──────────┐                 ┌──────────┐
q_0: ┤ RY(θ[0]) ├──■───────■──────┤ RY(θ[3]) ├──■───────■──────┤ RY(θ[6]) ├
     └──────────┘  │       │      └──────────┘  │       │      └──────────┘
q_1: ──────────────┼───────┼────────────────────┼───────┼──────────────────
     ┌──────────┐  │     ┌─┴─┐    ┌──────────┐  │     ┌─┴─┐    ┌──────────┐
q_2: ┤ RY(θ[1]) ├──┼─────┤ X ├────┤ RY(θ[4]) ├──┼─────┤ X ├────┤ RY(θ[7]) ├
     ├──────────┤┌─┴─┐┌──┴───┴───┐└──────────┘┌─┴─┐┌──┴───┴───┐└──────────┘
q_3: ┤ RY(θ[2]) ├┤ X ├┤ RY(θ[5]) ├────────────┤ X ├┤ RY(θ[8]) ├────────────
     └──────────┘└───┘└──────────┘            └───┘└──────────┘
```

Create a new RealAmplitudes 2-local circuit.

**Parameters**

*   **num\_qubits** (*int | None*) – The number of qubits of the RealAmplitudes circuit.
*   **reps** (*int*) – Specifies how often the structure of a rotation layer followed by an entanglement layer is repeated.
*   **entanglement** (*str | List\[List\[int]] | Callable\[\[int], List\[int]]*) – Specifies the entanglement structure. Can be a string (‘full’, ‘linear’ ‘reverse\_linear, ‘circular’ or ‘sca’), a list of integer-pairs specifying the indices of qubits entangled with one another, or a callable returning such a list provided with the index of the entanglement layer. Default to ‘reverse\_linear’ entanglement. Note that ‘reverse\_linear’ entanglement provides the same unitary as ‘full’ with fewer entangling gates. See the Examples section of [`TwoLocal`](qiskit.circuit.library.TwoLocal "qiskit.circuit.library.TwoLocal") for more detail.
*   **initial\_state** (*Any | None*) – A QuantumCircuit object to prepend to the circuit.
*   **skip\_unentangled\_qubits** (*bool*) – If True, the single qubit gates are only applied to qubits that are entangled with another qubit. If False, the single qubit gates are applied to each qubit in the Ansatz. Defaults to False.
*   **skip\_unentangled\_qubits** – If True, the single qubit gates are only applied to qubits that are entangled with another qubit. If False, the single qubit gates are applied to each qubit in the Ansatz. Defaults to False.
*   **skip\_final\_rotation\_layer** (*bool*) – If False, a rotation layer is added at the end of the ansatz. If True, no rotation layer is added.
*   **parameter\_prefix** (*str*) – The parameterized gates require a parameter to be defined, for which we use [`ParameterVector`](qiskit.circuit.ParameterVector "qiskit.circuit.ParameterVector").
*   **insert\_barriers** (*bool*) – If True, barriers are inserted in between each layer. If False, no barriers are inserted.

## Attributes

<span id="qiskit.circuit.library.RealAmplitudes.ancillas" />

### ancillas

Returns a list of ancilla bits in the order that the registers were added.

<span id="qiskit.circuit.library.RealAmplitudes.calibrations" />

### calibrations

Return calibration dictionary.

The custom pulse definition of a given gate is of the form `{'gate_name': {(qubits, params): schedule}}`

<span id="qiskit.circuit.library.RealAmplitudes.clbits" />

### clbits

Returns a list of classical bits in the order that the registers were added.

<span id="qiskit.circuit.library.RealAmplitudes.data" />

### data

<span id="qiskit.circuit.library.RealAmplitudes.entanglement" />

### entanglement

Get the entanglement strategy.

**Returns**

The entanglement strategy, see `get_entangler_map()` for more detail on how the format is interpreted.

<span id="qiskit.circuit.library.RealAmplitudes.entanglement_blocks" />

### entanglement\_blocks

The blocks in the entanglement layers.

**Returns**

The blocks in the entanglement layers.

<span id="qiskit.circuit.library.RealAmplitudes.extension_lib" />

### extension\_lib

`= 'include "qelib1.inc";'`

<span id="qiskit.circuit.library.RealAmplitudes.global_phase" />

### global\_phase

Return the global phase of the circuit in radians.

<span id="qiskit.circuit.library.RealAmplitudes.header" />

### header

`= 'OPENQASM 2.0;'`

<span id="qiskit.circuit.library.RealAmplitudes.initial_state" />

### initial\_state

Return the initial state that is added in front of the n-local circuit.

**Returns**

The initial state.

<span id="qiskit.circuit.library.RealAmplitudes.insert_barriers" />

### insert\_barriers

If barriers are inserted in between the layers or not.

**Returns**

`True`, if barriers are inserted in between the layers, `False` if not.

<span id="qiskit.circuit.library.RealAmplitudes.instances" />

### instances

`= 121`

<span id="qiskit.circuit.library.RealAmplitudes.layout" />

### layout

Return any associated layout information anout the circuit

This attribute contains an optional [`TranspileLayout`](qiskit.transpiler.TranspileLayout "qiskit.transpiler.TranspileLayout") object. This is typically set on the output from [`transpile()`](qiskit.compiler.transpile "qiskit.compiler.transpile") or [`PassManager.run()`](qiskit.transpiler.PassManager#run "qiskit.transpiler.PassManager.run") to retain information about the permutations caused on the input circuit by transpilation.

There are two types of permutations caused by the [`transpile()`](qiskit.compiler.transpile "qiskit.compiler.transpile") function, an initial layout which permutes the qubits based on the selected physical qubits on the [`Target`](qiskit.transpiler.Target "qiskit.transpiler.Target"), and a final layout which is an output permutation caused by [`SwapGate`](qiskit.circuit.library.SwapGate "qiskit.circuit.library.SwapGate")s inserted during routing.

<span id="qiskit.circuit.library.RealAmplitudes.metadata" />

### metadata

The user provided metadata associated with the circuit.

The metadata for the circuit is a user provided `dict` of metadata for the circuit. It will not be used to influence the execution or operation of the circuit, but it is expected to be passed between all transforms of the circuit (ie transpilation) and that providers will associate any circuit metadata with the results it returns from execution of that circuit.

<span id="qiskit.circuit.library.RealAmplitudes.num_ancillas" />

### num\_ancillas

Return the number of ancilla qubits.

<span id="qiskit.circuit.library.RealAmplitudes.num_clbits" />

### num\_clbits

Return number of classical bits.

<span id="qiskit.circuit.library.RealAmplitudes.num_layers" />

### num\_layers

Return the number of layers in the n-local circuit.

**Returns**

The number of layers in the circuit.

<span id="qiskit.circuit.library.RealAmplitudes.num_parameters" />

### num\_parameters

<span id="qiskit.circuit.library.RealAmplitudes.num_parameters_settable" />

### num\_parameters\_settable

The number of total parameters that can be set to distinct values.

This does not change when the parameters are bound or exchanged for same parameters, and therefore is different from `num_parameters` which counts the number of unique [`Parameter`](qiskit.circuit.Parameter "qiskit.circuit.Parameter") objects currently in the circuit.

**Returns**

The number of parameters originally available in the circuit.

<Admonition title="Note" type="note">
  This quantity does not require the circuit to be built yet.
</Admonition>

<span id="qiskit.circuit.library.RealAmplitudes.num_qubits" />

### num\_qubits

Returns the number of qubits in this circuit.

**Returns**

The number of qubits.

<span id="qiskit.circuit.library.RealAmplitudes.op_start_times" />

### op\_start\_times

Return a list of operation start times.

This attribute is enabled once one of scheduling analysis passes runs on the quantum circuit.

**Returns**

List of integers representing instruction start times. The index corresponds to the index of instruction in `QuantumCircuit.data`.

**Raises**

**AttributeError** – When circuit is not scheduled.

<span id="qiskit.circuit.library.RealAmplitudes.ordered_parameters" />

### ordered\_parameters

The parameters used in the underlying circuit.

This includes float values and duplicates.

## Examples

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

**Returns**

The parameters objects used in the circuit.

<span id="qiskit.circuit.library.RealAmplitudes.parameter_bounds" />

### parameter\_bounds

Return the parameter bounds.

**Returns**

The parameter bounds.

<span id="qiskit.circuit.library.RealAmplitudes.parameters" />

### parameters

<span id="qiskit.circuit.library.RealAmplitudes.preferred_init_points" />

### preferred\_init\_points

The initial points for the parameters. Can be stored as initial guess in optimization.

**Returns**

The initial values for the parameters, or None, if none have been set.

<span id="qiskit.circuit.library.RealAmplitudes.prefix" />

### prefix

`= 'circuit'`

<span id="qiskit.circuit.library.RealAmplitudes.qregs" />

### qregs

`list[QuantumRegister]`

A list of the quantum registers associated with the circuit.

<span id="qiskit.circuit.library.RealAmplitudes.qubits" />

### qubits

Returns a list of quantum bits in the order that the registers were added.

<span id="qiskit.circuit.library.RealAmplitudes.reps" />

### reps

The number of times rotation and entanglement block are repeated.

**Returns**

The number of repetitions.

<span id="qiskit.circuit.library.RealAmplitudes.rotation_blocks" />

### rotation\_blocks

The blocks in the rotation layers.

**Returns**

The blocks in the rotation layers.

