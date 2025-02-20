---
title: CDKMRippleCarryAdder
description: API reference for qiskit.circuit.library.CDKMRippleCarryAdder
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.CDKMRippleCarryAdder
---

# CDKMRippleCarryAdder

<span id="qiskit.circuit.library.CDKMRippleCarryAdder" />

`CDKMRippleCarryAdder(num_state_qubits, kind='full', name='CDKMRippleCarryAdder')`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/library/arithmetic/adders/cdkm_ripple_carry_adder.py "view source code")

Bases: `qiskit.circuit.library.arithmetic.adders.adder.Adder`

A ripple-carry circuit to perform in-place addition on two qubit registers.

As an example, a ripple-carry adder circuit that performs addition on two 3-qubit sized registers with a carry-in bit (`kind="full"`) is as follows:

```python
        ┌──────┐                                     ┌──────┐
 cin_0: ┤2     ├─────────────────────────────────────┤2     ├
        │      │┌──────┐                     ┌──────┐│      │
   a_0: ┤0     ├┤2     ├─────────────────────┤2     ├┤0     ├
        │      ││      │┌──────┐     ┌──────┐│      ││      │
   a_1: ┤  MAJ ├┤0     ├┤2     ├─────┤2     ├┤0     ├┤  UMA ├
        │      ││      ││      │     │      ││      ││      │
   a_2: ┤      ├┤  MAJ ├┤0     ├──■──┤0     ├┤  UMA ├┤      ├
        │      ││      ││      │  │  │      ││      ││      │
   b_0: ┤1     ├┤      ├┤  MAJ ├──┼──┤  UMA ├┤      ├┤1     ├
        └──────┘│      ││      │  │  │      ││      │└──────┘
   b_1: ────────┤1     ├┤      ├──┼──┤      ├┤1     ├────────
                └──────┘│      │  │  │      │└──────┘
   b_2: ────────────────┤1     ├──┼──┤1     ├────────────────
                        └──────┘┌─┴─┐└──────┘
cout_0: ────────────────────────┤ X ├────────────────────────
                                └───┘
```

Here *MAJ* and *UMA* gates correspond to the gates introduced in \[1]. Note that in this implementation the input register qubits are ordered as all qubits from the first input register, followed by all qubits from the second input register.

Two different kinds of adders are supported. By setting the `kind` argument, you can also choose a half-adder, which doesn’t have a carry-in, and a fixed-sized-adder, which has neither carry-in nor carry-out, and thus acts on fixed register sizes. Unlike the full-adder, these circuits need one additional helper qubit.

The circuit diagram for the fixed-point adder (`kind="fixed"`) on 3-qubit sized inputs is

```python
        ┌──────┐┌──────┐                ┌──────┐┌──────┐
   a_0: ┤0     ├┤2     ├────────────────┤2     ├┤0     ├
        │      ││      │┌──────┐┌──────┐│      ││      │
   a_1: ┤      ├┤0     ├┤2     ├┤2     ├┤0     ├┤      ├
        │      ││      ││      ││      ││      ││      │
   a_2: ┤      ├┤  MAJ ├┤0     ├┤0     ├┤  UMA ├┤      ├
        │      ││      ││      ││      ││      ││      │
   b_0: ┤1 MAJ ├┤      ├┤  MAJ ├┤  UMA ├┤      ├┤1 UMA ├
        │      ││      ││      ││      ││      ││      │
   b_1: ┤      ├┤1     ├┤      ├┤      ├┤1     ├┤      ├
        │      │└──────┘│      ││      │└──────┘│      │
   b_2: ┤      ├────────┤1     ├┤1     ├────────┤      ├
        │      │        └──────┘└──────┘        │      │
help_0: ┤2     ├────────────────────────────────┤2     ├
        └──────┘                                └──────┘
```

It has one less qubit than the full-adder since it doesn’t have the carry-out, but uses a helper qubit instead of the carry-in, so it only has one less qubit, not two.

**References:**

\[1] Cuccaro et al., A new quantum ripple-carry addition circuit, 2004. [arXiv:quant-ph/0410184](https://arxiv.org/pdf/quant-ph/0410184.pdf)

\[2] Vedral et al., Quantum Networks for Elementary Arithmetic Operations, 1995. [arXiv:quant-ph/9511018](https://arxiv.org/pdf/quant-ph/9511018.pdf)

**Parameters**

*   **num\_state\_qubits** (`int`) – The number of qubits in either input register for state $|a\rangle$ or $|b\rangle$. The two input registers must have the same number of qubits.
*   **kind** (`str`) – The kind of adder, can be `'full'` for a full adder, `'half'` for a half adder, or `'fixed'` for a fixed-sized adder. A full adder includes both carry-in and carry-out, a half only carry-out, and a fixed-sized adder neither carry-in nor carry-out.
*   **name** (`str`) – The name of the circuit object.

**Raises**

**ValueError** – If `num_state_qubits` is lower than 1.

## Attributes

<span id="qiskit.circuit.library.CDKMRippleCarryAdder.ancillas" />

### ancillas

Returns a list of ancilla bits in the order that the registers were added.

**Return type**

`List`\[`AncillaQubit`]

<span id="qiskit.circuit.library.CDKMRippleCarryAdder.calibrations" />

### calibrations

Return calibration dictionary.

**The custom pulse definition of a given gate is of the form**

\{‘gate\_name’: \{(qubits, params): schedule}}

**Return type**

`dict`

<span id="qiskit.circuit.library.CDKMRippleCarryAdder.clbits" />

### clbits

Returns a list of classical bits in the order that the registers were added.

**Return type**

`List`\[`Clbit`]

<span id="qiskit.circuit.library.CDKMRippleCarryAdder.data" />

### data

Return the circuit data (instructions and context).

**Returns**

a list-like object containing the tuples for the circuit’s data.

Each tuple is in the format `(instruction, qargs, cargs)`, where instruction is an Instruction (or subclass) object, qargs is a list of Qubit objects, and cargs is a list of Clbit objects.

**Return type**

QuantumCircuitData

<span id="qiskit.circuit.library.CDKMRippleCarryAdder.extension_lib" />

### extension\_lib

`= 'include "qelib1.inc";'`

<span id="qiskit.circuit.library.CDKMRippleCarryAdder.global_phase" />

### global\_phase

Return the global phase of the circuit in radians.

**Return type**

`Union`\[`ParameterExpression`, `float`]

<span id="qiskit.circuit.library.CDKMRippleCarryAdder.header" />

### header

`= 'OPENQASM 2.0;'`

<span id="qiskit.circuit.library.CDKMRippleCarryAdder.instances" />

### instances

`= 9`

<span id="qiskit.circuit.library.CDKMRippleCarryAdder.metadata" />

### metadata

The user provided metadata associated with the circuit

The metadata for the circuit is a user provided `dict` of metadata for the circuit. It will not be used to influence the execution or operation of the circuit, but it is expected to be passed between all transforms of the circuit (ie transpilation) and that providers will associate any circuit metadata with the results it returns from execution of that circuit.

**Return type**

`dict`

<span id="qiskit.circuit.library.CDKMRippleCarryAdder.num_ancillas" />

### num\_ancillas

Return the number of ancilla qubits.

**Return type**

`int`

<span id="qiskit.circuit.library.CDKMRippleCarryAdder.num_clbits" />

### num\_clbits

Return number of classical bits.

**Return type**

`int`

<span id="qiskit.circuit.library.CDKMRippleCarryAdder.num_parameters" />

### num\_parameters

Convenience function to get the number of parameter objects in the circuit.

**Return type**

`int`

<span id="qiskit.circuit.library.CDKMRippleCarryAdder.num_qubits" />

### num\_qubits

Return number of qubits.

**Return type**

`int`

<span id="qiskit.circuit.library.CDKMRippleCarryAdder.num_state_qubits" />

### num\_state\_qubits

The number of state qubits, i.e. the number of bits in each input register.

**Return type**

`int`

**Returns**

The number of state qubits.

<span id="qiskit.circuit.library.CDKMRippleCarryAdder.parameters" />

### parameters

Convenience function to get the parameters defined in the parameter table.

**Return type**

`ParameterView`

<span id="qiskit.circuit.library.CDKMRippleCarryAdder.prefix" />

### prefix

`= 'circuit'`

<span id="qiskit.circuit.library.CDKMRippleCarryAdder.qubits" />

### qubits

Returns a list of quantum bits in the order that the registers were added.

**Return type**

`List`\[`Qubit`]

