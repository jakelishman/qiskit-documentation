---
title: QuantumCircuit
description: API reference for qiskit.circuit.QuantumCircuit
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.QuantumCircuit
---

# QuantumCircuit

<span id="qiskit.circuit.QuantumCircuit" />

`QuantumCircuit(*regs, name=None, global_phase=0, metadata=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Bases: `object`

Create a new circuit.

A circuit is a list of instructions bound to some registers.

**Parameters**

*   **regs** (list(`Register`) or list(`int`) or list(list(`Bit`))) –

    The registers to be included in the circuit.

    *   If a list of `Register` objects, represents the [`QuantumRegister`](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister") and/or [`ClassicalRegister`](qiskit.circuit.ClassicalRegister "qiskit.circuit.ClassicalRegister") objects to include in the circuit.

        For example:

        > *   `QuantumCircuit(QuantumRegister(4))`
        > *   `QuantumCircuit(QuantumRegister(4), ClassicalRegister(3))`
        > *   `QuantumCircuit(QuantumRegister(4, 'qr0'), QuantumRegister(2, 'qr1'))`

    *   If a list of `int`, the amount of qubits and/or classical bits to include in the circuit. It can either be a single int for just the number of quantum bits, or 2 ints for the number of quantum bits and classical bits, respectively.

        For example:

        > *   `QuantumCircuit(4) # A QuantumCircuit with 4 qubits`
        > *   `QuantumCircuit(4, 3) # A QuantumCircuit with 4 qubits and 3 classical bits`

    *   If a list of python lists containing `Bit` objects, a collection of `Bit` s to be added to the circuit.

*   **name** (*str*) – the name of the quantum circuit. If not set, an automatically generated string will be assigned.

*   **global\_phase** (*float or* [*ParameterExpression*](qiskit.circuit.ParameterExpression "qiskit.circuit.ParameterExpression")) – The global phase of the circuit in radians.

*   **metadata** (*dict*) – Arbitrary key value metadata to associate with the circuit. This gets stored as free-form data in a dict in the [`metadata`](#qiskit.circuit.QuantumCircuit.metadata "qiskit.circuit.QuantumCircuit.metadata") attribute. It will not be directly used in the circuit.

**Raises**

**CircuitError** – if the circuit name, if given, is not valid.

## Examples

Construct a simple Bell state circuit.

```python
from qiskit import QuantumCircuit

qc = QuantumCircuit(2, 2)
qc.h(0)
qc.cx(0, 1)
qc.measure([0, 1], [0, 1])
qc.draw()
```

```python
     ┌───┐     ┌─┐   
q_0: ┤ H ├──■──┤M├───
     └───┘┌─┴─┐└╥┘┌─┐
q_1: ─────┤ X ├─╫─┤M├
          └───┘ ║ └╥┘
c: 2/═══════════╩══╩═
                0  1 
```

Construct a 5-qubit GHZ circuit.

```python
from qiskit import QuantumCircuit

qc = QuantumCircuit(5)
qc.h(0)
qc.cx(0, range(1, 5))
qc.measure_all()
```

Construct a 4-qubit Bernstein-Vazirani circuit using registers.

```python
from qiskit import QuantumRegister, ClassicalRegister, QuantumCircuit

qr = QuantumRegister(3, 'q')
anc = QuantumRegister(1, 'ancilla')
cr = ClassicalRegister(3, 'c')
qc = QuantumCircuit(qr, anc, cr)

qc.x(anc[0])
qc.h(anc[0])
qc.h(qr[0:3])
qc.cx(qr[0:3], anc[0])
qc.h(qr[0:3])
qc.barrier(qr)
qc.measure(qr, cr)

qc.draw()
```

```python
         ┌───┐          ┌───┐           ░ ┌─┐      
    q_0: ┤ H ├───────■──┤ H ├───────────░─┤M├──────
         ├───┤       │  └───┘┌───┐      ░ └╥┘┌─┐   
    q_1: ┤ H ├───────┼────■──┤ H ├──────░──╫─┤M├───
         ├───┤       │    │  └───┘┌───┐ ░  ║ └╥┘┌─┐
    q_2: ┤ H ├───────┼────┼────■──┤ H ├─░──╫──╫─┤M├
         ├───┤┌───┐┌─┴─┐┌─┴─┐┌─┴─┐└───┘ ░  ║  ║ └╥┘
ancilla: ┤ X ├┤ H ├┤ X ├┤ X ├┤ X ├─────────╫──╫──╫─
         └───┘└───┘└───┘└───┘└───┘         ║  ║  ║ 
    c: 3/══════════════════════════════════╩══╩══╩═
                                           0  1  2 
```

## Methods

### add\_bits

<span id="qiskit.circuit.QuantumCircuit.add_bits" />

`QuantumCircuit.add_bits(bits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Add Bits to the circuit.

**Return type**

`None`

### add\_calibration

<span id="qiskit.circuit.QuantumCircuit.add_calibration" />

`QuantumCircuit.add_calibration(gate, qubits, schedule, params=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Register a low-level, custom pulse definition for the given gate.

**Parameters**

*   **gate** (*Union\[*[*Gate*](qiskit.circuit.Gate "qiskit.circuit.Gate")*, str]*) – Gate information.
*   **qubits** (*Union\[int, Tuple\[int]]*) – List of qubits to be measured.
*   **schedule** ([*Schedule*](qiskit.pulse.Schedule "qiskit.pulse.Schedule")) – Schedule information.
*   **params** (*Optional\[List\[Union\[float,* [*Parameter*](qiskit.circuit.Parameter "qiskit.circuit.Parameter")*]]]*) – A list of parameters.

**Raises**

**Exception** – if the gate is of type string and params is None.

**Return type**

`None`

### add\_register

<span id="qiskit.circuit.QuantumCircuit.add_register" />

`QuantumCircuit.add_register(*regs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Add registers.

**Return type**

`None`

### append

<span id="qiskit.circuit.QuantumCircuit.append" />

`QuantumCircuit.append(instruction, qargs=None, cargs=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Append one or more instructions to the end of the circuit, modifying the circuit in place. Expands qargs and cargs.

**Parameters**

*   **instruction** ([*qiskit.circuit.Instruction*](qiskit.circuit.Instruction "qiskit.circuit.Instruction")) – Instruction instance to append
*   **qargs** (*list(argument)*) – qubits to attach instruction to
*   **cargs** (*list(argument)*) – clbits to attach instruction to

**Returns**

a handle to the instruction that was just added

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

**Raises**

*   **CircuitError** – if object passed is a subclass of Instruction
*   **CircuitError** – if object passed is neither subclass nor an instance of Instruction

### assign\_parameters

<span id="qiskit.circuit.QuantumCircuit.assign_parameters" />

`QuantumCircuit.assign_parameters(parameters, inplace=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Assign parameters to new parameters or values.

The keys of the parameter dictionary must be Parameter instances in the current circuit. The values of the dictionary can either be numeric values or new parameter objects. The values can be assigned to the current circuit object or to a copy of it.

**Parameters**

*   **parameters** (*dict or iterable*) – Either a dictionary or iterable specifying the new parameter values. If a dict, it specifies the mapping from `current_parameter` to `new_parameter`, where `new_parameter` can be a new parameter object or a numeric value. If an iterable, the elements are assigned to the existing parameters in the order of `QuantumCircuit.parameters`.
*   **inplace** (*bool*) – If False, a copy of the circuit with the bound parameters is returned. If True the circuit instance itself is modified.

**Raises**

*   **CircuitError** – If parameters is a dict and contains parameters not present in the circuit.
*   **ValueError** – If parameters is a list/array and the length mismatches the number of free parameters in the circuit.

**Returns**

A copy of the circuit with bound parameters, if `inplace` is False, otherwise None.

**Return type**

Optional([QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit"))

#### Examples

Create a parameterized circuit and assign the parameters in-place.

```python
from qiskit.circuit import QuantumCircuit, Parameter

circuit = QuantumCircuit(2)
params = [Parameter('A'), Parameter('B'), Parameter('C')]
circuit.ry(params[0], 0)
circuit.crx(params[1], 0, 1)

print('Original circuit:')
print(circuit.draw())

circuit.assign_parameters({params[0]: params[2]}, inplace=True)

print('Assigned in-place:')
print(circuit.draw())
```

```python
Original circuit:
```

```python
     ┌───────┐         
q_0: ┤ Ry(A) ├────■────
     └───────┘┌───┴───┐
q_1: ─────────┤ Rx(B) ├
              └───────┘
Assigned in-place:
     ┌───────┐         
q_0: ┤ Ry(C) ├────■────
     └───────┘┌───┴───┐
q_1: ─────────┤ Rx(B) ├
              └───────┘
```

Bind the values out-of-place and get a copy of the original circuit.

```python
from qiskit.circuit import QuantumCircuit, ParameterVector

circuit = QuantumCircuit(2)
params = ParameterVector('P', 2)
circuit.ry(params[0], 0)
circuit.crx(params[1], 0, 1)

bound_circuit = circuit.assign_parameters({params[0]: 1, params[1]: 2})
print('Bound circuit:')
print(bound_circuit.draw())

print('The original circuit is unchanged:')
print(circuit.draw())
```

```python
Bound circuit:
     ┌───────┐         
q_0: ┤ Ry(1) ├────■────
     └───────┘┌───┴───┐
q_1: ─────────┤ Rx(2) ├
              └───────┘
The original circuit is unchanged:
     ┌──────────┐            
q_0: ┤ Ry(P[0]) ├─────■──────
     └──────────┘┌────┴─────┐
q_1: ────────────┤ Rx(P[1]) ├
                 └──────────┘
```

### barrier

<span id="qiskit.circuit.QuantumCircuit.barrier" />

`QuantumCircuit.barrier(*qargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`Barrier`](qiskit.circuit.Barrier "qiskit.circuit.Barrier"). If qargs is empty, applies to all qubits in the circuit.

**Returns**

handle to the added instructions.

**Return type**

[qiskit.circuit.InstructionSet](qiskit.circuit.InstructionSet "qiskit.circuit.InstructionSet")

### bind\_parameters

<span id="qiskit.circuit.QuantumCircuit.bind_parameters" />

`QuantumCircuit.bind_parameters(values)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Assign numeric parameters to values yielding a new circuit.

To assign new Parameter objects or bind the values in-place, without yielding a new circuit, use the [`assign_parameters()`](qiskit.circuit.QuantumCircuit#assign_parameters "qiskit.circuit.QuantumCircuit.assign_parameters") method.

**Parameters**

**values** (*dict or iterable*) – \{parameter: value, …} or \[value1, value2, …]

**Raises**

*   **CircuitError** – If values is a dict and contains parameters not present in the circuit.
*   **TypeError** – If values contains a ParameterExpression.

**Returns**

copy of self with assignment substitution.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### break\_loop

<span id="qiskit.circuit.QuantumCircuit.break_loop" />

`QuantumCircuit.break_loop()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply `BreakLoopOp`.

<Admonition title="Warning" type="caution">
  If you are using the context-manager “builder” forms of [`if_test()`](qiskit.circuit.QuantumCircuit#if_test "qiskit.circuit.QuantumCircuit.if_test"), [`for_loop()`](qiskit.circuit.QuantumCircuit#for_loop "qiskit.circuit.QuantumCircuit.for_loop") or [`while_loop()`](qiskit.circuit.QuantumCircuit#while_loop "qiskit.circuit.QuantumCircuit.while_loop"), you can only call this method if you are within a loop context, because otherwise the “resource width” of the operation cannot be determined. This would quickly lead to invalid circuits, and so if you are trying to construct a reusable loop body (without the context managers), you must also use the non-context-manager form of [`if_test()`](qiskit.circuit.QuantumCircuit#if_test "qiskit.circuit.QuantumCircuit.if_test") and [`if_else()`](qiskit.circuit.QuantumCircuit#if_else "qiskit.circuit.QuantumCircuit.if_else"). Take care that the [`BreakLoopOp`](qiskit.circuit.BreakLoopOp "qiskit.circuit.BreakLoopOp") instruction must span all the resources of its containing loop, not just the immediate scope.
</Admonition>

**Return type**

`InstructionSet`

**Returns**

A handle to the instruction created.

**Raises**

**CircuitError** – if this method was called within a builder context, but not contained within a loop.

### cast

<span id="qiskit.circuit.QuantumCircuit.cast" />

`static QuantumCircuit.cast(value, type_)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Best effort to cast value to type. Otherwise, returns the value.

**Return type**

`Union`\[\~S, \~T]

### cbit\_argument\_conversion

<span id="qiskit.circuit.QuantumCircuit.cbit_argument_conversion" />

`QuantumCircuit.cbit_argument_conversion(clbit_representation)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Converts several classical bit representations (such as indexes, range, etc.) into a list of classical bits.

**Parameters**

**clbit\_representation** (*Object*) – representation to expand

**Returns**

Where each tuple is a classical bit.

**Return type**

List(tuple)

### ccx

<span id="qiskit.circuit.QuantumCircuit.ccx" />

`QuantumCircuit.ccx(control_qubit1, control_qubit2, target_qubit, ctrl_state=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`CCXGate`](qiskit.circuit.library.CCXGate "qiskit.circuit.library.CCXGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **control\_qubit1** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) used as the first control.
*   **control\_qubit2** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) used as the second control.
*   **target\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) targeted by the gate.
*   **ctrl\_state** (`Union`\[`int`, `str`, `None`]) – The control state in decimal, or as a bitstring (e.g. ‘1’). Defaults to controlling on the ‘1’ state.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### ch

<span id="qiskit.circuit.QuantumCircuit.ch" />

`QuantumCircuit.ch(control_qubit, target_qubit, label=None, ctrl_state=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`CHGate`](qiskit.circuit.library.CHGate "qiskit.circuit.library.CHGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **control\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) used as the control.
*   **target\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) targeted by the gate.
*   **label** (`Optional`\[`str`]) – The string label of the gate in the circuit.
*   **ctrl\_state** (`Union`\[`int`, `str`, `None`]) – The control state in decimal, or as a bitstring (e.g. ‘1’). Defaults to controlling on the ‘1’ state.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### cls\_instances

<span id="qiskit.circuit.QuantumCircuit.cls_instances" />

`classmethod QuantumCircuit.cls_instances()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Return the current number of instances of this class, useful for auto naming.

**Return type**

`int`

### cls\_prefix

<span id="qiskit.circuit.QuantumCircuit.cls_prefix" />

`classmethod QuantumCircuit.cls_prefix()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Return the prefix to use for auto naming.

**Return type**

`str`

### cnot

<span id="qiskit.circuit.QuantumCircuit.cnot" />

`QuantumCircuit.cnot(control_qubit, target_qubit, label=None, ctrl_state=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`CXGate`](qiskit.circuit.library.CXGate "qiskit.circuit.library.CXGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **control\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) used as the control.
*   **target\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) targeted by the gate.
*   **label** (`Optional`\[`str`]) – The string label of the gate in the circuit.
*   **ctrl\_state** (`Union`\[`int`, `str`, `None`]) – The control state in decimal, or as a bitstring (e.g. ‘1’). Defaults to controlling on the ‘1’ state.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

<Admonition title="See also" type="note">
  QuantumCircuit.cx: the same function with a different name.
</Admonition>

### combine

<span id="qiskit.circuit.QuantumCircuit.combine" />

`QuantumCircuit.combine(rhs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

DEPRECATED - Returns rhs appended to self if self contains compatible registers.

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

<span id="qiskit.circuit.QuantumCircuit.compose" />

`QuantumCircuit.compose(other, qubits=None, clbits=None, front=False, inplace=False, wrap=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Compose circuit with `other` circuit or instruction, optionally permuting wires.

`other` can be narrower or of equal width to `self`.

**Parameters**

*   **other** ([*qiskit.circuit.Instruction*](qiskit.circuit.Instruction "qiskit.circuit.Instruction")  *or*[*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – (sub)circuit or instruction to compose onto self. If not a [`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit"), this can be anything that [`append`](qiskit.circuit.QuantumCircuit#append "qiskit.circuit.QuantumCircuit.append") will accept.
*   **qubits** (*list\[Qubit|int]*) – qubits of self to compose onto.
*   **clbits** (*list\[Clbit|int]*) – clbits of self to compose onto.
*   **front** (*bool*) – If True, front composition will be performed (not implemented yet).
*   **inplace** (*bool*) – If True, modify the object. Otherwise return composed circuit.
*   **wrap** (*bool*) – If True, wraps the other circuit into a gate (or instruction, depending on whether it contains only unitary instructions) before composing it onto self.

**Returns**

the composed circuit (returns None if inplace==True).

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

*   **CircuitError** – if composing on the front.
*   **QiskitError** – if `other` is wider or there are duplicate edge mappings.

Examples:

```python
lhs.compose(rhs, qubits=[3, 2], inplace=True)

.. parsed-literal::

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

### continue\_loop

<span id="qiskit.circuit.QuantumCircuit.continue_loop" />

`QuantumCircuit.continue_loop()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply `ContinueLoopOp`.

<Admonition title="Warning" type="caution">
  If you are using the context-manager “builder” forms of [`if_test()`](qiskit.circuit.QuantumCircuit#if_test "qiskit.circuit.QuantumCircuit.if_test"), [`for_loop()`](qiskit.circuit.QuantumCircuit#for_loop "qiskit.circuit.QuantumCircuit.for_loop") or [`while_loop()`](qiskit.circuit.QuantumCircuit#while_loop "qiskit.circuit.QuantumCircuit.while_loop"), you can only call this method if you are within a loop context, because otherwise the “resource width” of the operation cannot be determined. This would quickly lead to invalid circuits, and so if you are trying to construct a reusable loop body (without the context managers), you must also use the non-context-manager form of [`if_test()`](qiskit.circuit.QuantumCircuit#if_test "qiskit.circuit.QuantumCircuit.if_test") and [`if_else()`](qiskit.circuit.QuantumCircuit#if_else "qiskit.circuit.QuantumCircuit.if_else"). Take care that the [`ContinueLoopOp`](qiskit.circuit.ContinueLoopOp "qiskit.circuit.ContinueLoopOp") instruction must span all the resources of its containing loop, not just the immediate scope.
</Admonition>

**Return type**

`InstructionSet`

**Returns**

A handle to the instruction created.

**Raises**

**CircuitError** – if this method was called within a builder context, but not contained within a loop.

### control

<span id="qiskit.circuit.QuantumCircuit.control" />

`QuantumCircuit.control(num_ctrl_qubits=1, label=None, ctrl_state=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Control this circuit on `num_ctrl_qubits` qubits.

**Parameters**

*   **num\_ctrl\_qubits** (*int*) – The number of control qubits.
*   **label** (*str*) – An optional label to give the controlled operation for visualization.
*   **ctrl\_state** (*str or int*) – The control state in decimal or as a bitstring (e.g. ‘111’). If None, use `2**num_ctrl_qubits - 1`.

**Returns**

The controlled version of this circuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**CircuitError** – If the circuit contains a non-unitary operation and cannot be controlled.

### copy

<span id="qiskit.circuit.QuantumCircuit.copy" />

`QuantumCircuit.copy(name=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Copy the circuit.

**Parameters**

**name** (*str*) – name to be given to the copied circuit. If None, then the name stays the same

**Returns**

a deepcopy of the current circuit, with the specified name

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### count\_ops

<span id="qiskit.circuit.QuantumCircuit.count_ops" />

`QuantumCircuit.count_ops()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Count each operation kind in the circuit.

**Returns**

a breakdown of how many operations of each kind, sorted by amount.

**Return type**

OrderedDict

### cp

<span id="qiskit.circuit.QuantumCircuit.cp" />

`QuantumCircuit.cp(theta, control_qubit, target_qubit, label=None, ctrl_state=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`CPhaseGate`](qiskit.circuit.library.CPhaseGate "qiskit.circuit.library.CPhaseGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **theta** (`Union`\[`ParameterExpression`, `float`]) – The angle of the rotation.
*   **control\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) used as the control.
*   **target\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) targeted by the gate.
*   **label** (`Optional`\[`str`]) – The string label of the gate in the circuit.
*   **ctrl\_state** (`Union`\[`int`, `str`, `None`]) – The control state in decimal, or as a bitstring (e.g. ‘1’). Defaults to controlling on the ‘1’ state.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### crx

<span id="qiskit.circuit.QuantumCircuit.crx" />

`QuantumCircuit.crx(theta, control_qubit, target_qubit, label=None, ctrl_state=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`CRXGate`](qiskit.circuit.library.CRXGate "qiskit.circuit.library.CRXGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **theta** (`Union`\[`ParameterExpression`, `float`]) – The angle of the rotation.
*   **control\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) used as the control.
*   **target\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) targeted by the gate.
*   **label** (`Optional`\[`str`]) – The string label of the gate in the circuit.
*   **ctrl\_state** (`Union`\[`int`, `str`, `None`]) – The control state in decimal, or as a bitstring (e.g. ‘1’). Defaults to controlling on the ‘1’ state.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### cry

<span id="qiskit.circuit.QuantumCircuit.cry" />

`QuantumCircuit.cry(theta, control_qubit, target_qubit, label=None, ctrl_state=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`CRYGate`](qiskit.circuit.library.CRYGate "qiskit.circuit.library.CRYGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **theta** (`Union`\[`ParameterExpression`, `float`]) – The angle of the rotation.
*   **control\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) used as the control.
*   **target\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) targeted by the gate.
*   **label** (`Optional`\[`str`]) – The string label of the gate in the circuit.
*   **ctrl\_state** (`Union`\[`int`, `str`, `None`]) – The control state in decimal, or as a bitstring (e.g. ‘1’). Defaults to controlling on the ‘1’ state.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### crz

<span id="qiskit.circuit.QuantumCircuit.crz" />

`QuantumCircuit.crz(theta, control_qubit, target_qubit, label=None, ctrl_state=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`CRZGate`](qiskit.circuit.library.CRZGate "qiskit.circuit.library.CRZGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **theta** (`Union`\[`ParameterExpression`, `float`]) – The angle of the rotation.
*   **control\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) used as the control.
*   **target\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) targeted by the gate.
*   **label** (`Optional`\[`str`]) – The string label of the gate in the circuit.
*   **ctrl\_state** (`Union`\[`int`, `str`, `None`]) – The control state in decimal, or as a bitstring (e.g. ‘1’). Defaults to controlling on the ‘1’ state.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### cswap

<span id="qiskit.circuit.QuantumCircuit.cswap" />

`QuantumCircuit.cswap(control_qubit, target_qubit1, target_qubit2, label=None, ctrl_state=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`CSwapGate`](qiskit.circuit.library.CSwapGate "qiskit.circuit.library.CSwapGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **control\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) used as the control.
*   **target\_qubit1** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) targeted by the gate.
*   **target\_qubit2** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) targeted by the gate.
*   **label** (`Optional`\[`str`]) – The string label of the gate in the circuit.
*   **ctrl\_state** (`Union`\[`int`, `str`, `None`]) – The control state in decimal, or as a bitstring (e.g. ‘1’). Defaults to controlling on the ‘1’ state.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### csx

<span id="qiskit.circuit.QuantumCircuit.csx" />

`QuantumCircuit.csx(control_qubit, target_qubit, label=None, ctrl_state=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`CSXGate`](qiskit.circuit.library.CSXGate "qiskit.circuit.library.CSXGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **control\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) used as the control.
*   **target\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) targeted by the gate.
*   **label** (`Optional`\[`str`]) – The string label of the gate in the circuit.
*   **ctrl\_state** (`Union`\[`int`, `str`, `None`]) – The control state in decimal, or as a bitstring (e.g. ‘1’). Defaults to controlling on the ‘1’ state.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### cu

<span id="qiskit.circuit.QuantumCircuit.cu" />

`QuantumCircuit.cu(theta, phi, lam, gamma, control_qubit, target_qubit, label=None, ctrl_state=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`CUGate`](qiskit.circuit.library.CUGate "qiskit.circuit.library.CUGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **theta** (`Union`\[`ParameterExpression`, `float`]) – The $\theta$ rotation angle of the gate.
*   **phi** (`Union`\[`ParameterExpression`, `float`]) – The $\phi$ rotation angle of the gate.
*   **lam** (`Union`\[`ParameterExpression`, `float`]) – The $\lambda$ rotation angle of the gate.
*   **gamma** (`Union`\[`ParameterExpression`, `float`]) – The global phase applied of the U gate, if applied.
*   **control\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) used as the control.
*   **target\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) targeted by the gate.
*   **label** (`Optional`\[`str`]) – The string label of the gate in the circuit.
*   **ctrl\_state** (`Union`\[`int`, `str`, `None`]) – The control state in decimal, or as a bitstring (e.g. ‘1’). Defaults to controlling on the ‘1’ state.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### cu1

<span id="qiskit.circuit.QuantumCircuit.cu1" />

`QuantumCircuit.cu1(theta, control_qubit, target_qubit, label=None, ctrl_state=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`CU1Gate`](qiskit.circuit.library.CU1Gate "qiskit.circuit.library.CU1Gate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **theta** (`Union`\[`ParameterExpression`, `float`]) – The $\theta$ rotation angle of the gate.
*   **control\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) used as the control.
*   **target\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) targeted by the gate.
*   **label** (`Optional`\[`str`]) – The string label of the gate in the circuit.
*   **ctrl\_state** (`Union`\[`int`, `str`, `None`]) – The control state in decimal, or as a bitstring (e.g. ‘1’). Defaults to controlling on the ‘1’ state.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### cu3

<span id="qiskit.circuit.QuantumCircuit.cu3" />

`QuantumCircuit.cu3(theta, phi, lam, control_qubit, target_qubit, label=None, ctrl_state=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`CU3Gate`](qiskit.circuit.library.CU3Gate "qiskit.circuit.library.CU3Gate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **theta** (`Union`\[`ParameterExpression`, `float`]) – The $\theta$ rotation angle of the gate.
*   **phi** (`Union`\[`ParameterExpression`, `float`]) – The $\phi$ rotation angle of the gate.
*   **lam** (`Union`\[`ParameterExpression`, `float`]) – The $\lambda$ rotation angle of the gate.
*   **control\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) used as the control.
*   **target\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) targeted by the gate.
*   **label** (`Optional`\[`str`]) – The string label of the gate in the circuit.
*   **ctrl\_state** (`Union`\[`int`, `str`, `None`]) – The control state in decimal, or as a bitstring (e.g. ‘1’). Defaults to controlling on the ‘1’ state.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### cx

<span id="qiskit.circuit.QuantumCircuit.cx" />

`QuantumCircuit.cx(control_qubit, target_qubit, label=None, ctrl_state=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`CXGate`](qiskit.circuit.library.CXGate "qiskit.circuit.library.CXGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **control\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) used as the control.
*   **target\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) targeted by the gate.
*   **label** (`Optional`\[`str`]) – The string label of the gate in the circuit.
*   **ctrl\_state** (`Union`\[`int`, `str`, `None`]) – The control state in decimal, or as a bitstring (e.g. ‘1’). Defaults to controlling on the ‘1’ state.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### cy

<span id="qiskit.circuit.QuantumCircuit.cy" />

`QuantumCircuit.cy(control_qubit, target_qubit, label=None, ctrl_state=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`CYGate`](qiskit.circuit.library.CYGate "qiskit.circuit.library.CYGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **control\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) used as the controls.
*   **target\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) targeted by the gate.
*   **label** (`Optional`\[`str`]) – The string label of the gate in the circuit.
*   **ctrl\_state** (`Union`\[`int`, `str`, `None`]) – The control state in decimal, or as a bitstring (e.g. ‘1’). Defaults to controlling on the ‘1’ state.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### cz

<span id="qiskit.circuit.QuantumCircuit.cz" />

`QuantumCircuit.cz(control_qubit, target_qubit, label=None, ctrl_state=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`CZGate`](qiskit.circuit.library.CZGate "qiskit.circuit.library.CZGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **control\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) used as the controls.
*   **target\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) targeted by the gate.
*   **label** (`Optional`\[`str`]) – The string label of the gate in the circuit.
*   **ctrl\_state** (`Union`\[`int`, `str`, `None`]) – The control state in decimal, or as a bitstring (e.g. ‘1’). Defaults to controlling on the ‘1’ state.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### dcx

<span id="qiskit.circuit.QuantumCircuit.dcx" />

`QuantumCircuit.dcx(qubit1, qubit2)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`DCXGate`](qiskit.circuit.library.DCXGate "qiskit.circuit.library.DCXGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **qubit1** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.
*   **qubit2** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### decompose

<span id="qiskit.circuit.QuantumCircuit.decompose" />

`QuantumCircuit.decompose(gates_to_decompose=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Call a decomposition pass on this circuit, to decompose one level (shallow decompose).

**Parameters**

**gates\_to\_decompose** (*str or list(str)*) – optional subset of gates to decompose. Defaults to all gates in circuit.

**Returns**

a circuit one level decomposed

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### delay

<span id="qiskit.circuit.QuantumCircuit.delay" />

`QuantumCircuit.delay(duration, qarg=None, unit='dt')`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`Delay`](qiskit.circuit.Delay "qiskit.circuit.Delay"). If qarg is None, applies to all qubits. When applying to multiple qubits, delays with the same duration will be created.

**Parameters**

*   **duration** (*int or float or* [*ParameterExpression*](qiskit.circuit.ParameterExpression "qiskit.circuit.ParameterExpression")) – duration of the delay.
*   **qarg** (*Object*) – qubit argument to apply this delay.
*   **unit** (*str*) – unit of the duration. Supported units: ‘s’, ‘ms’, ‘us’, ‘ns’, ‘ps’, ‘dt’. Default is `dt`, i.e. integer time unit depending on the target backend.

**Returns**

handle to the added instructions.

**Return type**

[qiskit.circuit.InstructionSet](qiskit.circuit.InstructionSet "qiskit.circuit.InstructionSet")

**Raises**

**CircuitError** – if arguments have bad format.

### depth

<span id="qiskit.circuit.QuantumCircuit.depth" />

`QuantumCircuit.depth(filter_function=<function QuantumCircuit.<lambda>>)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Return circuit depth (i.e., length of critical path).

**Parameters**

**filter\_function** (*callable*) – a function to filter out some instructions. Should take as input a tuple of (Instruction, list(Qubit), list(Clbit)). By default filters out “directives”, such as barrier or snapshot.

**Returns**

Depth of circuit.

**Return type**

int

#### Notes

The circuit depth and the DAG depth need not be the same.

### diagonal

<span id="qiskit.circuit.QuantumCircuit.diagonal" />

`QuantumCircuit.diagonal(diag, qubit)`

Attach a diagonal gate to a circuit.

The decomposition is based on Theorem 7 given in “Synthesis of Quantum Logic Circuits” by Shende et al. ([https://arxiv.org/pdf/quant-ph/0406176.pdf](https://arxiv.org/pdf/quant-ph/0406176.pdf)).

**Parameters**

*   **diag** (*list*) – list of the 2^k diagonal entries (for a diagonal gate on k qubits). Must contain at least two entries
*   **qubit** (*QuantumRegister|list*) – list of k qubits the diagonal is acting on (the order of the qubits specifies the computational basis in which the diagonal gate is provided: the first element in diag acts on the state where all the qubits in q are in the state 0, the second entry acts on the state where all the qubits q\[1],…,q\[k-1] are in the state zero and q\[0] is in the state 1, and so on)

**Returns**

the diagonal gate which was attached to the circuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the list of the diagonal entries or the qubit list is in bad format; if the number of diagonal entries is not 2^k, where k denotes the number of qubits

### draw

<span id="qiskit.circuit.QuantumCircuit.draw" />

`QuantumCircuit.draw(output=None, scale=None, filename=None, style=None, interactive=False, plot_barriers=True, reverse_bits=False, justify=None, vertical_compression='medium', idle_wires=True, with_layout=True, fold=None, ax=None, initial_state=False, cregbundle=True)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Draw the quantum circuit. Use the output parameter to choose the drawing format:

**text**: ASCII art TextDrawing that can be printed in the console.

**matplotlib**: images with color rendered purely in Python.

**latex**: high-quality images compiled via latex.

**latex\_source**: raw uncompiled latex output.

**Parameters**

*   **output** (*str*) – select the output method to use for drawing the circuit. Valid choices are `text`, `mpl`, `latex`, `latex_source`. By default the text drawer is used unless the user config file (usually `~/.qiskit/settings.conf`) has an alternative backend set as the default. For example, `circuit_drawer = latex`. If the output kwarg is set, that backend will always be used over the default in the user config file.
*   **scale** (*float*) – scale of image to draw (shrink if \< 1.0). Only used by the mpl, latex and latex\_source outputs. Defaults to 1.0.
*   **filename** (*str*) – file path to save image to. Defaults to None.
*   **style** (*dict or str*) – dictionary of style or file name of style json file. This option is only used by the mpl or latex output type. If style is a str, it is used as the path to a json file which contains a style dict. The file will be opened, parsed, and then any style elements in the dict will replace the default values in the input dict. A file to be loaded must end in `.json`, but the name entered here can omit `.json`. For example, `style='iqx.json'` or `style='iqx'`. If style is a dict and the `'name'` key is set, that name will be used to load a json file, followed by loading the other items in the style dict. For example, `style={'name': 'iqx'}`. If style is not a str and name is not a key in the style dict, then the default value from the user config file (usually `~/.qiskit/settings.conf`) will be used, for example, `circuit_mpl_style = iqx`. If none of these are set, the default style will be used. The search path for style json files can be specified in the user config, for example, `circuit_mpl_style_path = /home/user/styles:/home/user`. See: [`DefaultStyle`](qiskit.visualization.qcstyle.DefaultStyle "qiskit.visualization.qcstyle.DefaultStyle") for more information on the contents.
*   **interactive** (*bool*) – when set to true, show the circuit in a new window (for mpl this depends on the matplotlib backend being used supporting this). Note when used with either the text or the latex\_source output type this has no effect and will be silently ignored. Defaults to False.
*   **reverse\_bits** (*bool*) – when set to True, reverse the bit order inside registers for the output visualization. Defaults to False.
*   **plot\_barriers** (*bool*) – enable/disable drawing barriers in the output circuit. Defaults to True.
*   **justify** (*string*) – options are `left`, `right` or `none`. If anything else is supplied, it defaults to left justified. It refers to where gates should be placed in the output circuit if there is an option. `none` results in each gate being placed in its own column.
*   **vertical\_compression** (*string*) – `high`, `medium` or `low`. It merges the lines generated by the text output so the drawing will take less vertical room. Default is `medium`. Only used by the text output, will be silently ignored otherwise.
*   **idle\_wires** (*bool*) – include idle wires (wires with no circuit elements) in output visualization. Default is True.
*   **with\_layout** (*bool*) – include layout information, with labels on the physical layout. Default is True.
*   **fold** (*int*) – sets pagination. It can be disabled using -1. In text, sets the length of the lines. This is useful when the drawing does not fit in the console. If None (default), it will try to guess the console width using `shutil.get_terminal_size()`. However, if running in jupyter, the default line length is set to 80 characters. In mpl, it is the number of (visual) layers before folding. Default is 25.
*   **ax** (*matplotlib.axes.Axes*) – Only used by the mpl backend. An optional Axes object to be used for the visualization output. If none is specified, a new matplotlib Figure will be created and used. Additionally, if specified there will be no returned Figure since it is redundant.
*   **initial\_state** (*bool*) – optional. Adds `|0>` in the beginning of the wire. Default is False.
*   **cregbundle** (*bool*) – optional. If set True, bundle classical registers. Default is True.

**Returns**

`TextDrawing` or `matplotlib.figure` or `PIL.Image` or `str`:

*   **TextDrawing (output=’text’)**

    A drawing that can be printed as ascii art.

*   **matplotlib.figure.Figure (output=’mpl’)**

    A matplotlib figure object for the circuit diagram.

*   **PIL.Image (output=’latex’)**

    An in-memory representation of the image of the circuit diagram.

*   **str (output=’latex\_source’)**

    The LaTeX source code for visualizing the circuit diagram.

**Raises**

*   [**VisualizationError**](qiskit.visualization.VisualizationError "qiskit.visualization.VisualizationError") – when an invalid output method is selected
*   **ImportError** – when the output methods requires non-installed libraries.

#### Example

```python
from qiskit import QuantumRegister, ClassicalRegister, QuantumCircuit
from qiskit.tools.visualization import circuit_drawer
q = QuantumRegister(1)
c = ClassicalRegister(1)
qc = QuantumCircuit(q, c)
qc.h(q)
qc.measure(q, c)
qc.draw(output='mpl', style={'backgroundcolor': '#EEEEEE'})
```

![../\_images/qiskit.circuit.QuantumCircuit.draw\_0\_0.png](/images/api/qiskit/0.35/qiskit.circuit.QuantumCircuit.draw_0_0.png)

### ecr

<span id="qiskit.circuit.QuantumCircuit.ecr" />

`QuantumCircuit.ecr(qubit1, qubit2)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`ECRGate`](qiskit.circuit.library.ECRGate "qiskit.circuit.library.ECRGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **qubit1** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubits to apply the gate to.
*   **qubit2** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubits to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### extend

<span id="qiskit.circuit.QuantumCircuit.extend" />

`QuantumCircuit.extend(rhs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

DEPRECATED - Append QuantumCircuit to the RHS if it contains compatible registers.

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

### find\_bit

<span id="qiskit.circuit.QuantumCircuit.find_bit" />

`QuantumCircuit.find_bit(bit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Find locations in the circuit which can be used to reference a given `Bit`.

**Parameters**

**bit** (*Bit*) – The bit to locate.

**Returns**

**A 2-tuple. The first element (`index`)**

contains the index at which the `Bit` can be found (in either [`qubits`](qiskit.circuit.QuantumCircuit#qubits "qiskit.circuit.QuantumCircuit.qubits"), [`clbits`](qiskit.circuit.QuantumCircuit#clbits "qiskit.circuit.QuantumCircuit.clbits"), depending on its type). The second element (`registers`) is a list of `(register, index)` pairs with an entry for each `Register` in the circuit which contains the `Bit` (and the index in the `Register` at which it can be found).

**Return type**

namedtuple(int, List\[Tuple(Register, int)])

#### Notes

The circuit index of an [`AncillaQubit`](qiskit.circuit.AncillaQubit "qiskit.circuit.AncillaQubit") will be its index in [`qubits`](qiskit.circuit.QuantumCircuit#qubits "qiskit.circuit.QuantumCircuit.qubits"), not [`ancillas`](qiskit.circuit.QuantumCircuit#ancillas "qiskit.circuit.QuantumCircuit.ancillas").

**Raises**

*   **CircuitError** – If the supplied `Bit` was of an unknown type.
*   **CircuitError** – If the supplied `Bit` could not be found on the circuit.

### for\_loop

##### for\_loop

<span id="qiskit.circuit.QuantumCircuit.for_loop" />

`QuantumCircuit.for_loop(indexset: Iterable[int], loop_parameter: Optional[qiskit.circuit.parameter.Parameter], body: None, qubits: None, clbits: None, *, label: Optional[str]) → qiskit.circuit.controlflow.for_loop.ForLoopContext`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

<span id="qiskit.circuit.QuantumCircuit.for_loop" />

`QuantumCircuit.for_loop(indexset: Iterable[int], loop_parameter: Optional[qiskit.circuit.parameter.Parameter], body: QuantumCircuit, qubits: Sequence[Union[qiskit.circuit.quantumregister.Qubit, qiskit.circuit.quantumregister.QuantumRegister, int, slice, Sequence[Union[qiskit.circuit.quantumregister.Qubit, int]]]], clbits: Sequence[Union[qiskit.circuit.classicalregister.Clbit, qiskit.circuit.classicalregister.ClassicalRegister, int, slice, Sequence[Union[qiskit.circuit.classicalregister.Clbit, int]]]], *, label: Optional[str]) → qiskit.circuit.instructionset.InstructionSet`

Create a `for` loop on this circuit.

There are two forms for calling this function. If called with all its arguments (with the possible exception of `label`), it will create a `ForLoopOp` with the given `body`. If `body` (and `qubits` and `clbits`) are *not* passed, then this acts as a context manager, which, when entered, provides a loop variable (unless one is given, in which case it will be reused) and will automatically build a `ForLoopOp` when the scope finishes. In this form, you do not need to keep track of the qubits or clbits you are using, because the scope will handle it for you.

For example:

```python
from qiskit import QuantumCircuit
qc = QuantumCircuit(2, 1)

with qc.for_loop(range(5)) as i:
    qc.h(0)
    qc.cx(0, 1)
    qc.measure(0, 0)
    qc.break_loop().c_if(0, True)
```

**Parameters**

*   **indexset** (*Iterable\[int]*) – A collection of integers to loop over. Always necessary.

*   **loop\_parameter** (*Optional\[*[*Parameter*](qiskit.circuit.Parameter "qiskit.circuit.Parameter")*]*) –

    The parameter used within `body` to which the values from `indexset` will be assigned. In the context-manager form, if this argument is not supplied, then a loop parameter will be allocated for you and returned as the value of the `with` statement. This will only be bound into the circuit if it is used within the body.

    If this argument is `None` in the manual form of this method, `body` will be repeated once for each of the items in `indexset` but their values will be ignored.

*   **body** (*Optional\[*[*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")*]*) – The loop body to be repeatedly executed. Omit this to use the context-manager mode.

*   **qubits** (*Optional\[Sequence\[QubitSpecifier]]*) – The circuit qubits over which the loop body should be run. Omit this to use the context-manager mode.

*   **clbits** (*Optional\[Sequence\[ClbitSpecifier]]*) – The circuit clbits over which the loop body should be run. Omit this to use the context-manager mode.

*   **label** (*Optional\[str]*) – The string label of the instruction in the circuit.

**Returns**

depending on the call signature, either a context manager for creating the for loop (it will automatically be added to the circuit at the end of the block), or an [`InstructionSet`](qiskit.circuit.InstructionSet "qiskit.circuit.InstructionSet") handle to the appended loop operation.

**Return type**

[InstructionSet](qiskit.circuit.InstructionSet "qiskit.circuit.InstructionSet") or ForLoopContext

**Raises**

**CircuitError** – if an incorrect calling convention is used.

### fredkin

<span id="qiskit.circuit.QuantumCircuit.fredkin" />

`QuantumCircuit.fredkin(control_qubit, target_qubit1, target_qubit2)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`CSwapGate`](qiskit.circuit.library.CSwapGate "qiskit.circuit.library.CSwapGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **control\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) used as the control.
*   **target\_qubit1** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) targeted by the gate.
*   **target\_qubit2** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) targeted by the gate.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

<Admonition title="See also" type="note">
  QuantumCircuit.cswap: the same function with a different name.
</Admonition>

### from\_qasm\_file

<span id="qiskit.circuit.QuantumCircuit.from_qasm_file" />

`static QuantumCircuit.from_qasm_file(path)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Take in a QASM file and generate a QuantumCircuit object.

**Parameters**

**path** (*str*) – Path to the file for a QASM program

**Returns**

The QuantumCircuit object for the input QASM

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### from\_qasm\_str

<span id="qiskit.circuit.QuantumCircuit.from_qasm_str" />

`static QuantumCircuit.from_qasm_str(qasm_str)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Take in a QASM string and generate a QuantumCircuit object.

**Parameters**

**qasm\_str** (*str*) – A QASM program string

**Returns**

The QuantumCircuit object for the input QASM

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### get\_instructions

<span id="qiskit.circuit.QuantumCircuit.get_instructions" />

`QuantumCircuit.get_instructions(name)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Get instructions matching name.

**Parameters**

**name** (*str*) – The name of instruction to.

**Returns**

list of (instruction, qargs, cargs).

**Return type**

list(tuple)

### h

<span id="qiskit.circuit.QuantumCircuit.h" />

`QuantumCircuit.h(qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`HGate`](qiskit.circuit.library.HGate "qiskit.circuit.library.HGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

**qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### hamiltonian

<span id="qiskit.circuit.QuantumCircuit.hamiltonian" />

`QuantumCircuit.hamiltonian(operator, time, qubits, label=None)`

Apply hamiltonian evolution to qubits.

### has\_register

<span id="qiskit.circuit.QuantumCircuit.has_register" />

`QuantumCircuit.has_register(register)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Test if this circuit has the register r.

**Parameters**

**register** (*Register*) – a quantum or classical register.

**Returns**

True if the register is contained in this circuit.

**Return type**

bool

### i

<span id="qiskit.circuit.QuantumCircuit.i" />

`QuantumCircuit.i(qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`IGate`](qiskit.circuit.library.IGate "qiskit.circuit.library.IGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

**qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### id

<span id="qiskit.circuit.QuantumCircuit.id" />

`QuantumCircuit.id(qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`IGate`](qiskit.circuit.library.IGate "qiskit.circuit.library.IGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

**qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

<Admonition title="See also" type="note">
  QuantumCircuit.i: the same function.
</Admonition>

### if\_else

<span id="qiskit.circuit.QuantumCircuit.if_else" />

`QuantumCircuit.if_else(condition, true_body, false_body, qubits, clbits, label=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply `IfElseOp`.

<Admonition title="Note" type="note">
  This method does not have an associated context-manager form, because it is already handled by the [`if_test()`](qiskit.circuit.QuantumCircuit#if_test "qiskit.circuit.QuantumCircuit.if_test") method. You can use the `else` part of that with something such as:

  ```python
  from qiskit.circuit import QuantumCircuit, Qubit, Clbit
  bits = [Qubit(), Qubit(), Clbit()]
  qc = QuantumCircuit(bits)
  qc.h(0)
  qc.cx(0, 1)
  qc.measure(0, 0)
  with qc.if_test((bits[2], 0)) as else_:
      qc.h(0)
  with else_:
      qc.x(0)
  ```
</Admonition>

**Parameters**

*   **condition** (`Union`\[`Tuple`\[`ClassicalRegister`, `int`], `Tuple`\[`Clbit`, `int`], `Tuple`\[`Clbit`, `bool`]]) – A condition to be evaluated at circuit runtime which, if true, will trigger the evaluation of `true_body`. Can be specified as either a tuple of a `ClassicalRegister` to be tested for equality with a given `int`, or as a tuple of a `Clbit` to be compared to either a `bool` or an `int`.
*   **true\_body** (`QuantumCircuit`) – The circuit body to be run if `condition` is true.
*   **false\_body** (`QuantumCircuit`) – The circuit to be run if `condition` is false.
*   **qubits** (`Sequence`\[`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]]) – The circuit qubits over which the if/else should be run.
*   **clbits** (`Sequence`\[`Union`\[`Clbit`, `ClassicalRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Clbit`, `int`]]]]) – The circuit clbits over which the if/else should be run.
*   **label** (`Optional`\[`str`]) – The string label of the instruction in the circuit.

**Raises**

**CircuitError** – If the provided condition references Clbits outside the enclosing circuit.

**Return type**

`InstructionSet`

**Returns**

A handle to the instruction created.

### if\_test

##### if\_test

<span id="qiskit.circuit.QuantumCircuit.if_test" />

`QuantumCircuit.if_test(condition: Tuple[Union[qiskit.circuit.classicalregister.ClassicalRegister, qiskit.circuit.classicalregister.Clbit], int], true_body: None, qubits: None, clbits: None, *, label: Optional[str]) → qiskit.circuit.controlflow.if_else.IfContext`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

<span id="qiskit.circuit.QuantumCircuit.if_test" />

`QuantumCircuit.if_test(condition: Tuple[Union[qiskit.circuit.classicalregister.ClassicalRegister, qiskit.circuit.classicalregister.Clbit], int], true_body: QuantumCircuit, qubits: Sequence[Union[qiskit.circuit.quantumregister.Qubit, qiskit.circuit.quantumregister.QuantumRegister, int, slice, Sequence[Union[qiskit.circuit.quantumregister.Qubit, int]]]], clbits: Sequence[Union[qiskit.circuit.classicalregister.Clbit, qiskit.circuit.classicalregister.ClassicalRegister, int, slice, Sequence[Union[qiskit.circuit.classicalregister.Clbit, int]]]], *, label: Optional[str] = 'None') → qiskit.circuit.instructionset.InstructionSet`

Create an `if` statement on this circuit.

There are two forms for calling this function. If called with all its arguments (with the possible exception of `label`), it will create a `IfElseOp` with the given `true_body`, and there will be no branch for the `false` condition (see also the [`if_else()`](qiskit.circuit.QuantumCircuit#if_else "qiskit.circuit.QuantumCircuit.if_else") method). However, if `true_body` (and `qubits` and `clbits`) are *not* passed, then this acts as a context manager, which can be used to build `if` statements. The return value of the `with` statement is a chainable context manager, which can be used to create subsequent `else` blocks. In this form, you do not need to keep track of the qubits or clbits you are using, because the scope will handle it for you.

For example:

```python
from qiskit.circuit import QuantumCircuit, Qubit, Clbit
bits = [Qubit(), Qubit(), Qubit(), Clbit(), Clbit()]
qc = QuantumCircuit(bits)

qc.h(0)
qc.cx(0, 1)
qc.measure(0, 0)
qc.h(0)
qc.cx(0, 1)
qc.measure(0, 1)

with qc.if_test((bits[3], 0)) as else_:
    qc.x(2)
with else_:
    qc.h(2)
    qc.z(2)
```

**Parameters**

*   **condition** (*Tuple\[Union\[*[*ClassicalRegister*](qiskit.circuit.ClassicalRegister "qiskit.circuit.ClassicalRegister")*,* [*Clbit*](qiskit.circuit.Clbit "qiskit.circuit.Clbit")*], int]*) – A condition to be evaluated at circuit runtime which, if true, will trigger the evaluation of `true_body`. Can be specified as either a tuple of a `ClassicalRegister` to be tested for equality with a given `int`, or as a tuple of a `Clbit` to be compared to either a `bool` or an `int`.
*   **true\_body** (*Optional\[*[*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")*]*) – The circuit body to be run if `condition` is true.
*   **qubits** (*Optional\[Sequence\[QubitSpecifier]]*) – The circuit qubits over which the if/else should be run.
*   **clbits** (*Optional\[Sequence\[ClbitSpecifier]]*) – The circuit clbits over which the if/else should be run.
*   **label** (*Optional\[str]*) – The string label of the instruction in the circuit.

**Returns**

depending on the call signature, either a context manager for creating the `if` block (it will automatically be added to the circuit at the end of the block), or an [`InstructionSet`](qiskit.circuit.InstructionSet "qiskit.circuit.InstructionSet") handle to the appended conditional operation.

**Return type**

[InstructionSet](qiskit.circuit.InstructionSet "qiskit.circuit.InstructionSet") or IfContext

**Raises**

*   **CircuitError** – If the provided condition references Clbits outside the enclosing circuit.
*   **CircuitError** – if an incorrect calling convention is used.

**Returns**

A handle to the instruction created.

### initialize

<span id="qiskit.circuit.QuantumCircuit.initialize" />

`QuantumCircuit.initialize(params, qubits=None)`

Initialize qubits in a specific state.

Qubit initialization is done by first resetting the qubits to $|0\rangle$ followed by calling `qiskit.extensions.StatePreparation` class to prepare the qubits in a specified state. Both these steps are included in the [`qiskit.extensions.Initialize`](qiskit.extensions.Initialize "qiskit.extensions.Initialize") instruction.

**Parameters**

*   **params** (*str or list or int*) –

    *   str: labels of basis states of the Pauli eigenstates Z, X, Y. See [`Statevector.from_label()`](qiskit.quantum_info.Statevector#from_label "qiskit.quantum_info.Statevector.from_label"). Notice the order of the labels is reversed with respect to the qubit index to be applied to. Example label ‘01’ initializes the qubit zero to $|1\rangle$ and the qubit one to $|0\rangle$.
    *   list: vector of complex amplitudes to initialize to.
    *   int: an integer that is used as a bitmap indicating which qubits to initialize to $|1\rangle$. Example: setting params to 5 would initialize qubit 0 and qubit 2 to $|1\rangle$ and qubit 1 to $|0\rangle$.

*   **qubits** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister") *or int*) –

    *   QuantumRegister: A list of qubits to be initialized \[Default: None].
    *   int: Index of qubit to be initialized \[Default: None].
    *   list: Indexes of qubits to be initialized \[Default: None].

**Returns**

a handle to the instruction that was just initialized

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

#### Examples

Prepare a qubit in the state $(|0\rangle - |1\rangle) / \sqrt{2}$.

```python
import numpy as np
from qiskit import QuantumCircuit

circuit = QuantumCircuit(1)
circuit.initialize([1/np.sqrt(2), -1/np.sqrt(2)], 0)
circuit.draw()
```

```python
   ┌──────────────────────────────┐
q: ┤ Initialize(0.70711,-0.70711) ├
   └──────────────────────────────┘
```

output:

```python
     ┌──────────────────────────────┐
q_0: ┤ Initialize(0.70711,-0.70711) ├
     └──────────────────────────────┘
```

Initialize from a string two qubits in the state $|10\rangle$. The order of the labels is reversed with respect to qubit index. More information about labels for basis states are in [`Statevector.from_label()`](qiskit.quantum_info.Statevector#from_label "qiskit.quantum_info.Statevector.from_label").

```python
import numpy as np
from qiskit import QuantumCircuit

circuit = QuantumCircuit(2)
circuit.initialize('01', circuit.qubits)
circuit.draw()
```

```python
     ┌──────────────────┐
q_0: ┤0                 ├
     │  Initialize(0,1) │
q_1: ┤1                 ├
     └──────────────────┘
```

output:

```python
     ┌──────────────────┐
q_0: ┤0                 ├
     │  Initialize(0,1) │
q_1: ┤1                 ├
     └──────────────────┘
```

Initialize two qubits from an array of complex amplitudes .. jupyter-execute:

```python
import numpy as np
from qiskit import QuantumCircuit

circuit = QuantumCircuit(2)
circuit.initialize([0, 1/np.sqrt(2), -1.j/np.sqrt(2), 0], circuit.qubits)
circuit.draw()
```

output:

```python
     ┌────────────────────────────────────┐
q_0: ┤0                                   ├
     │  Initialize(0,0.70711,-0.70711j,0) │
q_1: ┤1                                   ├
     └────────────────────────────────────┘
```

### inverse

<span id="qiskit.circuit.QuantumCircuit.inverse" />

`QuantumCircuit.inverse()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Invert (take adjoint of) this circuit.

This is done by recursively inverting all gates.

**Returns**

the inverted circuit

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**CircuitError** – if the circuit cannot be inverted.

#### Examples

input:

```python
     ┌───┐
q_0: ┤ H ├─────■──────
     └───┘┌────┴─────┐
q_1: ─────┤ RX(1.57) ├
          └──────────┘
```

output:

```python
                  ┌───┐
q_0: ──────■──────┤ H ├
     ┌─────┴─────┐└───┘
q_1: ┤ RX(-1.57) ├─────
     └───────────┘
```

### iso

<span id="qiskit.circuit.QuantumCircuit.iso" />

`QuantumCircuit.iso(isometry, q_input, q_ancillas_for_output, q_ancillas_zero=None, q_ancillas_dirty=None, epsilon=1e-10)`

Attach an arbitrary isometry from m to n qubits to a circuit. In particular, this allows to attach arbitrary unitaries on n qubits (m=n) or to prepare any state on n qubits (m=0). The decomposition used here was introduced by Iten et al. in [https://arxiv.org/abs/1501.06911](https://arxiv.org/abs/1501.06911).

**Parameters**

*   **isometry** (*ndarray*) – an isometry from m to n qubits, i.e., a (complex) ndarray of dimension 2^n×2^m with orthonormal columns (given in the computational basis specified by the order of the ancillas and the input qubits, where the ancillas are considered to be more significant than the input qubits.).
*   **q\_input** (*QuantumRegister|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of m qubits where the input to the isometry is fed in (empty list for state preparation).
*   **q\_ancillas\_for\_output** (*QuantumRegister|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of n-m ancilla qubits that are used for the output of the isometry and which are assumed to start in the zero state. The qubits are listed with increasing significance.
*   **q\_ancillas\_zero** (*QuantumRegister|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of ancilla qubits which are assumed to start in the zero state. Default is q\_ancillas\_zero = None.
*   **q\_ancillas\_dirty** (*QuantumRegister|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of ancilla qubits which can start in an arbitrary state. Default is q\_ancillas\_dirty = None.
*   **epsilon** (*float*) – error tolerance of calculations. Default is epsilon = \_EPS.

**Returns**

the isometry is attached to the quantum circuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the array is not an isometry of the correct size corresponding to the provided number of qubits.

### isometry

<span id="qiskit.circuit.QuantumCircuit.isometry" />

`QuantumCircuit.isometry(isometry, q_input, q_ancillas_for_output, q_ancillas_zero=None, q_ancillas_dirty=None, epsilon=1e-10)`

Attach an arbitrary isometry from m to n qubits to a circuit. In particular, this allows to attach arbitrary unitaries on n qubits (m=n) or to prepare any state on n qubits (m=0). The decomposition used here was introduced by Iten et al. in [https://arxiv.org/abs/1501.06911](https://arxiv.org/abs/1501.06911).

**Parameters**

*   **isometry** (*ndarray*) – an isometry from m to n qubits, i.e., a (complex) ndarray of dimension 2^n×2^m with orthonormal columns (given in the computational basis specified by the order of the ancillas and the input qubits, where the ancillas are considered to be more significant than the input qubits.).
*   **q\_input** (*QuantumRegister|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of m qubits where the input to the isometry is fed in (empty list for state preparation).
*   **q\_ancillas\_for\_output** (*QuantumRegister|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of n-m ancilla qubits that are used for the output of the isometry and which are assumed to start in the zero state. The qubits are listed with increasing significance.
*   **q\_ancillas\_zero** (*QuantumRegister|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of ancilla qubits which are assumed to start in the zero state. Default is q\_ancillas\_zero = None.
*   **q\_ancillas\_dirty** (*QuantumRegister|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of ancilla qubits which can start in an arbitrary state. Default is q\_ancillas\_dirty = None.
*   **epsilon** (*float*) – error tolerance of calculations. Default is epsilon = \_EPS.

**Returns**

the isometry is attached to the quantum circuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the array is not an isometry of the correct size corresponding to the provided number of qubits.

### iswap

<span id="qiskit.circuit.QuantumCircuit.iswap" />

`QuantumCircuit.iswap(qubit1, qubit2)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`iSwapGate`](qiskit.circuit.library.iSwapGate "qiskit.circuit.library.iSwapGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **qubit1** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubits to apply the gate to.
*   **qubit2** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubits to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### mcp

<span id="qiskit.circuit.QuantumCircuit.mcp" />

`QuantumCircuit.mcp(lam, control_qubits, target_qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`MCPhaseGate`](qiskit.circuit.library.MCPhaseGate "qiskit.circuit.library.MCPhaseGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **lam** (`Union`\[`ParameterExpression`, `float`]) – The angle of the rotation.
*   **control\_qubits** (`Sequence`\[`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]]) – The qubits used as the controls.
*   **target\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) targeted by the gate.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### mcrx

<span id="qiskit.circuit.QuantumCircuit.mcrx" />

`QuantumCircuit.mcrx(theta, q_controls, q_target, use_basis_gates=False)`

Apply Multiple-Controlled X rotation gate

**Parameters**

*   **self** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – The QuantumCircuit object to apply the mcrx gate on.
*   **theta** (*float*) – angle theta
*   **q\_controls** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister") *or list(*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*)*) – The list of control qubits
*   **q\_target** ([*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")) – The target qubit
*   **use\_basis\_gates** (*bool*) – use p, u, cx

**Raises**

**QiskitError** – parameter errors

### mcry

<span id="qiskit.circuit.QuantumCircuit.mcry" />

`QuantumCircuit.mcry(theta, q_controls, q_target, q_ancillae=None, mode=None, use_basis_gates=False)`

Apply Multiple-Controlled Y rotation gate

**Parameters**

*   **self** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – The QuantumCircuit object to apply the mcry gate on.
*   **theta** (*float*) – angle theta
*   **q\_controls** (*list(*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*)*) – The list of control qubits
*   **q\_target** ([*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")) – The target qubit
*   **q\_ancillae** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister") *or tuple(*[*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*, int)*) – The list of ancillary qubits.
*   **mode** (*string*) – The implementation mode to use
*   **use\_basis\_gates** (*bool*) – use p, u, cx

**Raises**

**QiskitError** – parameter errors

### mcrz

<span id="qiskit.circuit.QuantumCircuit.mcrz" />

`QuantumCircuit.mcrz(lam, q_controls, q_target, use_basis_gates=False)`

Apply Multiple-Controlled Z rotation gate

**Parameters**

*   **self** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – The QuantumCircuit object to apply the mcrz gate on.
*   **lam** (*float*) – angle lambda
*   **q\_controls** (*list(*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*)*) – The list of control qubits
*   **q\_target** ([*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")) – The target qubit
*   **use\_basis\_gates** (*bool*) – use p, u, cx

**Raises**

**QiskitError** – parameter errors

### mct

<span id="qiskit.circuit.QuantumCircuit.mct" />

`QuantumCircuit.mct(control_qubits, target_qubit, ancilla_qubits=None, mode='noancilla')`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`MCXGate`](qiskit.circuit.library.MCXGate "qiskit.circuit.library.MCXGate").

The multi-cX gate can be implemented using different techniques, which use different numbers of ancilla qubits and have varying circuit depth. These modes are:

*   ‘noancilla’: Requires 0 ancilla qubits.
*   ‘recursion’: Requires 1 ancilla qubit if more than 4 controls are used, otherwise 0.
*   ‘v-chain’: Requires 2 less ancillas than the number of control qubits.
*   ‘v-chain-dirty’: Same as for the clean ancillas (but the circuit will be longer).

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **control\_qubits** (`Sequence`\[`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]]) – The qubits used as the controls.
*   **target\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) targeted by the gate.
*   **ancilla\_qubits** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]], `Sequence`\[`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]], `None`]) – The qubits used as the ancillae, if the mode requires them.
*   **mode** (`str`) – The choice of mode, explained further above.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

**Raises**

*   **ValueError** – if the given mode is not known, or if too few ancilla qubits are passed.
*   **AttributeError** – if no ancilla qubits are passed, but some are needed.

<Admonition title="See also" type="note">
  QuantumCircuit.mcx: the same gate with a different name.
</Admonition>

### mcu1

<span id="qiskit.circuit.QuantumCircuit.mcu1" />

`QuantumCircuit.mcu1(lam, control_qubits, target_qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply `MCU1Gate`.

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **lam** (`Union`\[`ParameterExpression`, `float`]) – The $\lambda$ rotation angle of the gate.
*   **control\_qubits** (`Sequence`\[`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]]) – The qubits used as the controls.
*   **target\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) targeted by the gate.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### mcx

<span id="qiskit.circuit.QuantumCircuit.mcx" />

`QuantumCircuit.mcx(control_qubits, target_qubit, ancilla_qubits=None, mode='noancilla')`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`MCXGate`](qiskit.circuit.library.MCXGate "qiskit.circuit.library.MCXGate").

The multi-cX gate can be implemented using different techniques, which use different numbers of ancilla qubits and have varying circuit depth. These modes are:

*   ‘noancilla’: Requires 0 ancilla qubits.
*   ‘recursion’: Requires 1 ancilla qubit if more than 4 controls are used, otherwise 0.
*   ‘v-chain’: Requires 2 less ancillas than the number of control qubits.
*   ‘v-chain-dirty’: Same as for the clean ancillas (but the circuit will be longer).

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **control\_qubits** (`Sequence`\[`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]]) – The qubits used as the controls.
*   **target\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) targeted by the gate.
*   **ancilla\_qubits** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]], `Sequence`\[`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]], `None`]) – The qubits used as the ancillae, if the mode requires them.
*   **mode** (`str`) – The choice of mode, explained further above.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

**Raises**

*   **ValueError** – if the given mode is not known, or if too few ancilla qubits are passed.
*   **AttributeError** – if no ancilla qubits are passed, but some are needed.

### measure

<span id="qiskit.circuit.QuantumCircuit.measure" />

`QuantumCircuit.measure(qubit, cbit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Measure quantum bit into classical bit (tuples).

**Parameters**

*   **qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – qubit to measure.
*   **cbit** (`Union`\[`Clbit`, `ClassicalRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Clbit`, `int`]]]) – classical bit to place the measurement in.

**Returns**

handle to the added instructions.

**Return type**

[qiskit.circuit.InstructionSet](qiskit.circuit.InstructionSet "qiskit.circuit.InstructionSet")

**Raises**

**CircuitError** – if arguments have bad format.

### measure\_active

<span id="qiskit.circuit.QuantumCircuit.measure_active" />

`QuantumCircuit.measure_active(inplace=True)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Adds measurement to all non-idle qubits. Creates a new ClassicalRegister with a size equal to the number of non-idle qubits being measured.

Returns a new circuit with measurements if inplace=False.

**Parameters**

**inplace** (*bool*) – All measurements inplace or return new circuit.

**Returns**

Returns circuit with measurements when inplace = False.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### measure\_all

<span id="qiskit.circuit.QuantumCircuit.measure_all" />

`QuantumCircuit.measure_all(inplace=True, add_bits=True)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Adds measurement to all qubits.

By default, adds new classical bits in a [`ClassicalRegister`](qiskit.circuit.ClassicalRegister "qiskit.circuit.ClassicalRegister") to store these measurements. If `add_bits=False`, the results of the measurements will instead be stored in the already existing classical bits, with qubit `n` being measured into classical bit `n`.

Returns a new circuit with measurements if `inplace=False`.

**Parameters**

*   **inplace** (*bool*) – All measurements inplace or return new circuit.
*   **add\_bits** (*bool*) – Whether to add new bits to store the results.

**Returns**

Returns circuit with measurements when `inplace=False`.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**CircuitError** – if `add_bits=False` but there are not enough classical bits.

### ms

<span id="qiskit.circuit.QuantumCircuit.ms" />

`QuantumCircuit.ms(theta, qubits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply `MSGate`.

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **theta** (`Union`\[`ParameterExpression`, `float`]) – The angle of the rotation.
*   **qubits** (`Sequence`\[`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]]) – The qubits to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### num\_connected\_components

<span id="qiskit.circuit.QuantumCircuit.num_connected_components" />

`QuantumCircuit.num_connected_components(unitary_only=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

How many non-entangled subcircuits can the circuit be factored to.

**Parameters**

**unitary\_only** (*bool*) – Compute only unitary part of graph.

**Returns**

Number of connected components in circuit.

**Return type**

int

### num\_nonlocal\_gates

<span id="qiskit.circuit.QuantumCircuit.num_nonlocal_gates" />

`QuantumCircuit.num_nonlocal_gates()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Return number of non-local gates (i.e. involving 2+ qubits).

Conditional nonlocal gates are also included.

**Return type**

`int`

### num\_tensor\_factors

<span id="qiskit.circuit.QuantumCircuit.num_tensor_factors" />

`QuantumCircuit.num_tensor_factors()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Computes the number of tensor factors in the unitary (quantum) part of the circuit only.

#### Notes

This is here for backwards compatibility, and will be removed in a future release of Qiskit. You should call num\_unitary\_factors instead.

**Return type**

`int`

### num\_unitary\_factors

<span id="qiskit.circuit.QuantumCircuit.num_unitary_factors" />

`QuantumCircuit.num_unitary_factors()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Computes the number of tensor factors in the unitary (quantum) part of the circuit only.

**Return type**

`int`

### p

<span id="qiskit.circuit.QuantumCircuit.p" />

`QuantumCircuit.p(theta, qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`PhaseGate`](qiskit.circuit.library.PhaseGate "qiskit.circuit.library.PhaseGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **theta** (`Union`\[`ParameterExpression`, `float`]) – THe angle of the rotation.
*   **qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### pauli

<span id="qiskit.circuit.QuantumCircuit.pauli" />

`QuantumCircuit.pauli(pauli_string, qubits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`PauliGate`](qiskit.circuit.library.PauliGate "qiskit.circuit.library.PauliGate").

**Parameters**

*   **pauli\_string** (`str`) – A string representing the Pauli operator to apply, e.g. ‘XX’.
*   **qubits** (`Sequence`\[`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]]) – The qubits to apply this gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### power

<span id="qiskit.circuit.QuantumCircuit.power" />

`QuantumCircuit.power(power, matrix_power=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Raise this circuit to the power of `power`.

If `power` is a positive integer and `matrix_power` is `False`, this implementation defaults to calling `repeat`. Otherwise, if the circuit is unitary, the matrix is computed to calculate the matrix power.

**Parameters**

*   **power** (*float*) – The power to raise this circuit to.
*   **matrix\_power** (*bool*) – If True, the circuit is converted to a matrix and then the matrix power is computed. If False, and `power` is a positive integer, the implementation defaults to `repeat`.

**Raises**

**CircuitError** – If the circuit needs to be converted to a gate but it is not unitary.

**Returns**

A circuit implementing this circuit raised to the power of `power`.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### prepare\_state

<span id="qiskit.circuit.QuantumCircuit.prepare_state" />

`QuantumCircuit.prepare_state(state, qubits=None, label=None)`

Prepare qubits in a specific state.

This class implements a state preparing unitary. Unlike [`qiskit.extensions.Initialize`](qiskit.extensions.Initialize "qiskit.extensions.Initialize") it does not reset the qubits first.

**Parameters**

*   **state** (*str or list or int or* [*Statevector*](qiskit.quantum_info.Statevector "qiskit.quantum_info.Statevector")) –

    *   Statevector: Statevector to initialize to.
    *   str: labels of basis states of the Pauli eigenstates Z, X, Y. See [`Statevector.from_label()`](qiskit.quantum_info.Statevector#from_label "qiskit.quantum_info.Statevector.from_label"). Notice the order of the labels is reversed with respect to the qubit index to be applied to. Example label ‘01’ initializes the qubit zero to $|1\rangle$ and the qubit one to $|0\rangle$.
    *   list: vector of complex amplitudes to initialize to.
    *   int: an integer that is used as a bitmap indicating which qubits to initialize to $|1\rangle$. Example: setting params to 5 would initialize qubit 0 and qubit 2 to $|1\rangle$ and qubit 1 to $|0\rangle$.

*   **qubits** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister") *or int*) –

    *   QuantumRegister: A list of qubits to be initialized \[Default: None].
    *   int: Index of qubit to be initialized \[Default: None].
    *   list: Indexes of qubits to be initialized \[Default: None].

*   **label** (*str*) – An optional label for the gate

**Returns**

a handle to the instruction that was just initialized

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

#### Examples

Prepare a qubit in the state $(|0\rangle - |1\rangle) / \sqrt{2}$.

```python
import numpy as np
from qiskit import QuantumCircuit

circuit = QuantumCircuit(1)
circuit.prepare_state([1/np.sqrt(2), -1/np.sqrt(2)], 0)
circuit.draw()
```

```python
   ┌─────────────────────────────────────┐
q: ┤ State Preparation(0.70711,-0.70711) ├
   └─────────────────────────────────────┘
```

output:

```python
     ┌─────────────────────────────────────┐
q_0: ┤ State Preparation(0.70711,-0.70711) ├
     └─────────────────────────────────────┘
```

Prepare from a string two qubits in the state $|10\rangle$. The order of the labels is reversed with respect to qubit index. More information about labels for basis states are in [`Statevector.from_label()`](qiskit.quantum_info.Statevector#from_label "qiskit.quantum_info.Statevector.from_label").

```python
import numpy as np
from qiskit import QuantumCircuit

circuit = QuantumCircuit(2)
circuit.prepare_state('01', circuit.qubits)
circuit.draw()
```

```python
     ┌─────────────────────────┐
q_0: ┤0                        ├
     │  State Preparation(0,1) │
q_1: ┤1                        ├
     └─────────────────────────┘
```

output:

```python
     ┌─────────────────────────┐
q_0: ┤0                        ├
     │  State Preparation(0,1) │
q_1: ┤1                        ├
     └─────────────────────────┘
```

Initialize two qubits from an array of complex amplitudes .. jupyter-execute:

```python
import numpy as np
from qiskit import QuantumCircuit

circuit = QuantumCircuit(2)
circuit.prepare_state([0, 1/np.sqrt(2), -1.j/np.sqrt(2), 0], circuit.qubits)
circuit.draw()
```

output:

```python
     ┌───────────────────────────────────────────┐
q_0: ┤0                                          ├
     │  State Preparation(0,0.70711,-0.70711j,0) │
q_1: ┤1                                          ├
     └───────────────────────────────────────────┘
```

### qasm

<span id="qiskit.circuit.QuantumCircuit.qasm" />

`QuantumCircuit.qasm(formatted=False, filename=None, encoding=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Return OpenQASM string.

**Parameters**

*   **formatted** (*bool*) – Return formatted Qasm string.
*   **filename** (*str*) – Save Qasm to file with name ‘filename’.
*   **encoding** (*str*) – Optionally specify the encoding to use for the output file if `filename` is specified. By default this is set to the system’s default encoding (ie whatever `locale.getpreferredencoding()` returns) and can be set to any valid codec or alias from stdlib’s [codec module](https://docs.python.org/3/library/codecs.html#standard-encodings)

**Returns**

If formatted=False.

**Return type**

str

**Raises**

*   **MissingOptionalLibraryError** – If pygments is not installed and `formatted` is `True`.
*   [**QasmError**](qiskit.qasm.QasmError "qiskit.qasm.QasmError") – If circuit has free parameters.

### qbit\_argument\_conversion

<span id="qiskit.circuit.QuantumCircuit.qbit_argument_conversion" />

`QuantumCircuit.qbit_argument_conversion(qubit_representation)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Converts several qubit representations (such as indexes, range, etc.) into a list of qubits.

**Parameters**

**qubit\_representation** (*Object*) – representation to expand

**Returns**

the resolved instances of the qubits.

**Return type**

List([Qubit](qiskit.circuit.Qubit "qiskit.circuit.Qubit"))

### qubit\_duration

<span id="qiskit.circuit.QuantumCircuit.qubit_duration" />

`QuantumCircuit.qubit_duration(*qubits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Return the duration between the start and stop time of the first and last instructions, excluding delays, over the supplied qubits. Its time unit is `self.unit`.

**Parameters**

**\*qubits** – Qubits within `self` to include.

**Return type**

`float`

**Returns**

Return the duration between the first start and last stop time of non-delay instructions

### qubit\_start\_time

<span id="qiskit.circuit.QuantumCircuit.qubit_start_time" />

`QuantumCircuit.qubit_start_time(*qubits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Return the start time of the first instruction, excluding delays, over the supplied qubits. Its time unit is `self.unit`.

Return 0 if there are no instructions over qubits

**Parameters**

*   **\*qubits** – Qubits within `self` to include. Integers are allowed for qubits, indicating
*   **of self.qubits.** (*indices*) –

**Return type**

`float`

**Returns**

Return the start time of the first instruction, excluding delays, over the qubits

**Raises**

**CircuitError** – if `self` is a not-yet scheduled circuit.

### qubit\_stop\_time

<span id="qiskit.circuit.QuantumCircuit.qubit_stop_time" />

`QuantumCircuit.qubit_stop_time(*qubits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Return the stop time of the last instruction, excluding delays, over the supplied qubits. Its time unit is `self.unit`.

Return 0 if there are no instructions over qubits

**Parameters**

*   **\*qubits** – Qubits within `self` to include. Integers are allowed for qubits, indicating
*   **of self.qubits.** (*indices*) –

**Return type**

`float`

**Returns**

Return the stop time of the last instruction, excluding delays, over the qubits

**Raises**

**CircuitError** – if `self` is a not-yet scheduled circuit.

### r

<span id="qiskit.circuit.QuantumCircuit.r" />

`QuantumCircuit.r(theta, phi, qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`RGate`](qiskit.circuit.library.RGate "qiskit.circuit.library.RGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **theta** (`Union`\[`ParameterExpression`, `float`]) – The angle of the rotation.
*   **phi** (`Union`\[`ParameterExpression`, `float`]) – The angle of the axis of rotation in the x-y plane.
*   **qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### rcccx

<span id="qiskit.circuit.QuantumCircuit.rcccx" />

`QuantumCircuit.rcccx(control_qubit1, control_qubit2, control_qubit3, target_qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`RC3XGate`](qiskit.circuit.library.RC3XGate "qiskit.circuit.library.RC3XGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **control\_qubit1** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) used as the first control.
*   **control\_qubit2** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) used as the second control.
*   **control\_qubit3** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) used as the third control.
*   **target\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) targeted by the gate.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### rccx

<span id="qiskit.circuit.QuantumCircuit.rccx" />

`QuantumCircuit.rccx(control_qubit1, control_qubit2, target_qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`RCCXGate`](qiskit.circuit.library.RCCXGate "qiskit.circuit.library.RCCXGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **control\_qubit1** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) used as the first control.
*   **control\_qubit2** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) used as the second control.
*   **target\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) targeted by the gate.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### remove\_final\_measurements

<span id="qiskit.circuit.QuantumCircuit.remove_final_measurements" />

`QuantumCircuit.remove_final_measurements(inplace=True)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Removes final measurements and barriers on all qubits if they are present. Deletes the classical registers that were used to store the values from these measurements that become idle as a result of this operation, and deletes classical bits that are referenced only by removed registers, or that aren’t referenced at all but have become idle as a result of this operation.

Measurements and barriers are considered final if they are followed by no other operations (aside from other measurements or barriers.)

**Parameters**

**inplace** (*bool*) – All measurements removed inplace or return new circuit.

**Returns**

Returns the resulting circuit when `inplace=False`, else None.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### repeat

<span id="qiskit.circuit.QuantumCircuit.repeat" />

`QuantumCircuit.repeat(reps)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Repeat this circuit `reps` times.

**Parameters**

**reps** (*int*) – How often this circuit should be repeated.

**Returns**

A circuit containing `reps` repetitions of this circuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### reset

<span id="qiskit.circuit.QuantumCircuit.reset" />

`QuantumCircuit.reset(qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Reset the quantum bit(s) to their default state.

**Parameters**

**qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – qubit(s) to reset.

**Returns**

handle to the added instruction.

**Return type**

[qiskit.circuit.InstructionSet](qiskit.circuit.InstructionSet "qiskit.circuit.InstructionSet")

### reverse\_bits

<span id="qiskit.circuit.QuantumCircuit.reverse_bits" />

`QuantumCircuit.reverse_bits()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Return a circuit with the opposite order of wires.

The circuit is “vertically” flipped. If a circuit is defined over multiple registers, the resulting circuit will have the same registers but with their order flipped.

This method is useful for converting a circuit written in little-endian convention to the big-endian equivalent, and vice versa.

**Returns**

the circuit with reversed bit order.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

#### Examples

input:

```python
     ┌───┐
q_0: ┤ H ├─────■──────
     └───┘┌────┴─────┐
q_1: ─────┤ RX(1.57) ├
          └──────────┘
```

output:

```python
          ┌──────────┐
q_0: ─────┤ RX(1.57) ├
     ┌───┐└────┬─────┘
q_1: ┤ H ├─────■──────
     └───┘
```

### reverse\_ops

<span id="qiskit.circuit.QuantumCircuit.reverse_ops" />

`QuantumCircuit.reverse_ops()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Reverse the circuit by reversing the order of instructions.

This is done by recursively reversing all instructions. It does not invert (adjoint) any gate.

**Returns**

the reversed circuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

#### Examples

input:

```python
     ┌───┐
q_0: ┤ H ├─────■──────
     └───┘┌────┴─────┐
q_1: ─────┤ RX(1.57) ├
          └──────────┘
```

output:

```python
                 ┌───┐
q_0: ─────■──────┤ H ├
     ┌────┴─────┐└───┘
q_1: ┤ RX(1.57) ├─────
     └──────────┘
```

### rv

<span id="qiskit.circuit.QuantumCircuit.rv" />

`QuantumCircuit.rv(vx, vy, vz, qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`RVGate`](qiskit.circuit.library.RVGate "qiskit.circuit.library.RVGate").

For the full matrix form of this gate, see the underlying gate documentation.

Rotation around an arbitrary rotation axis $v$, where $|v|$ is the angle of rotation in radians.

**Parameters**

*   **vx** (`Union`\[`ParameterExpression`, `float`]) – x-compenent of the rotation axis.
*   **vy** (`Union`\[`ParameterExpression`, `float`]) – y-compenent of the rotation axis.
*   **vz** (`Union`\[`ParameterExpression`, `float`]) – z-compenent of the rotation axis.
*   **qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### rx

<span id="qiskit.circuit.QuantumCircuit.rx" />

`QuantumCircuit.rx(theta, qubit, label=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`RXGate`](qiskit.circuit.library.RXGate "qiskit.circuit.library.RXGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **theta** (`Union`\[`ParameterExpression`, `float`]) – The rotation angle of the gate.
*   **qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.
*   **label** (`Optional`\[`str`]) – The string label of the gate in the circuit.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### rxx

<span id="qiskit.circuit.QuantumCircuit.rxx" />

`QuantumCircuit.rxx(theta, qubit1, qubit2)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`RXXGate`](qiskit.circuit.library.RXXGate "qiskit.circuit.library.RXXGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **theta** (`Union`\[`ParameterExpression`, `float`]) – The angle of the rotation.
*   **qubit1** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.
*   **qubit2** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### ry

<span id="qiskit.circuit.QuantumCircuit.ry" />

`QuantumCircuit.ry(theta, qubit, label=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`RYGate`](qiskit.circuit.library.RYGate "qiskit.circuit.library.RYGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **theta** (`Union`\[`ParameterExpression`, `float`]) – The rotation angle of the gate.
*   **qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.
*   **label** (`Optional`\[`str`]) – The string label of the gate in the circuit.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### ryy

<span id="qiskit.circuit.QuantumCircuit.ryy" />

`QuantumCircuit.ryy(theta, qubit1, qubit2)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`RYYGate`](qiskit.circuit.library.RYYGate "qiskit.circuit.library.RYYGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **theta** (`Union`\[`ParameterExpression`, `float`]) – The rotation angle of the gate.
*   **qubit1** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.
*   **qubit2** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### rz

<span id="qiskit.circuit.QuantumCircuit.rz" />

`QuantumCircuit.rz(phi, qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`RZGate`](qiskit.circuit.library.RZGate "qiskit.circuit.library.RZGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **phi** (`Union`\[`ParameterExpression`, `float`]) – The rotation angle of the gate.
*   **qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### rzx

<span id="qiskit.circuit.QuantumCircuit.rzx" />

`QuantumCircuit.rzx(theta, qubit1, qubit2)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`RZXGate`](qiskit.circuit.library.RZXGate "qiskit.circuit.library.RZXGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **theta** (`Union`\[`ParameterExpression`, `float`]) – The rotation angle of the gate.
*   **qubit1** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.
*   **qubit2** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### rzz

<span id="qiskit.circuit.QuantumCircuit.rzz" />

`QuantumCircuit.rzz(theta, qubit1, qubit2)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`RZZGate`](qiskit.circuit.library.RZZGate "qiskit.circuit.library.RZZGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **theta** (`Union`\[`ParameterExpression`, `float`]) – The rotation angle of the gate.
*   **qubit1** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.
*   **qubit2** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### s

<span id="qiskit.circuit.QuantumCircuit.s" />

`QuantumCircuit.s(qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`SGate`](qiskit.circuit.library.SGate "qiskit.circuit.library.SGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

**qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### save\_amplitudes

<span id="qiskit.circuit.QuantumCircuit.save_amplitudes" />

`QuantumCircuit.save_amplitudes(params, label='amplitudes', pershot=False, conditional=False)`

Save complex statevector amplitudes.

**Parameters**

*   **params** (*List\[int] or List\[str]*) – the basis states to return amplitudes for.
*   **label** (*str*) – the key for retrieving saved data from results.
*   **pershot** (*bool*) – if True save a list of amplitudes vectors for each shot of the simulation rather than the a single amplitude vector \[Default: False].
*   **conditional** (*bool*) – if True save the amplitudes vector conditional on the current classical register values \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – if params is invalid for the specified number of qubits.

### save\_amplitudes\_squared

<span id="qiskit.circuit.QuantumCircuit.save_amplitudes_squared" />

`QuantumCircuit.save_amplitudes_squared(params, label='amplitudes_squared', unnormalized=False, pershot=False, conditional=False)`

Save squared statevector amplitudes (probabilities).

**Parameters**

*   **params** (*List\[int] or List\[str]*) – the basis states to return amplitudes for.
*   **label** (*str*) – the key for retrieving saved data from results.
*   **unnormalized** (*bool*) – If True return save the unnormalized accumulated probabilities over all shots \[Default: False].
*   **pershot** (*bool*) – if True save a list of probability vectors for each shot of the simulation rather than the a single amplitude vector \[Default: False].
*   **conditional** (*bool*) – if True save the probability vector conditional on the current classical register values \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – if params is invalid for the specified number of qubits.

### save\_clifford

<span id="qiskit.circuit.QuantumCircuit.save_clifford" />

`QuantumCircuit.save_clifford(label='clifford', pershot=False)`

Save the current stabilizer simulator quantum state as a Clifford.

**Parameters**

*   **label** (*str*) – the key for retrieving saved data from results.
*   **pershot** (*bool*) – if True save a list of Cliffords for each shot of the simulation \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

<Admonition title="Note" type="note">
  This instruction is always defined across all qubits in a circuit.
</Admonition>

### save\_density\_matrix

<span id="qiskit.circuit.QuantumCircuit.save_density_matrix" />

`QuantumCircuit.save_density_matrix(qubits=None, label='density_matrix', unnormalized=False, pershot=False, conditional=False)`

Save the current simulator quantum state as a density matrix.

**Parameters**

*   **qubits** (*list or None*) – the qubits to save reduced density matrix on. If None the full density matrix of qubits will be saved \[Default: None].
*   **label** (*str*) – the key for retrieving saved data from results.
*   **unnormalized** (*bool*) – If True return save the unnormalized accumulated or conditional accumulated density matrix over all shots \[Default: False].
*   **pershot** (*bool*) – if True save a list of density matrices for each shot of the simulation rather than the average over all shots \[Default: False].
*   **conditional** (*bool*) – if True save the average or pershot data conditional on the current classical register values \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### save\_expectation\_value

<span id="qiskit.circuit.QuantumCircuit.save_expectation_value" />

`QuantumCircuit.save_expectation_value(operator, qubits, label='expectation_value', unnormalized=False, pershot=False, conditional=False)`

Save the expectation value of a Hermitian operator.

**Parameters**

*   **operator** ([*Pauli*](qiskit.quantum_info.Pauli "qiskit.quantum_info.Pauli")  *or*[*SparsePauliOp*](qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp")  *or*[*Operator*](qiskit.quantum_info.Operator "qiskit.quantum_info.Operator")) – a Hermitian operator.
*   **qubits** (*list*) – circuit qubits to apply instruction.
*   **label** (*str*) – the key for retrieving saved data from results.
*   **unnormalized** (*bool*) – If True return save the unnormalized accumulated or conditional accumulated expectation value over all shot \[Default: False].
*   **pershot** (*bool*) – if True save a list of expectation values for each shot of the simulation rather than the average over all shots \[Default: False].
*   **conditional** (*bool*) – if True save the average or pershot data conditional on the current classical register values \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – if the input operator is invalid or not Hermitian.

<Admonition title="Note" type="note">
  This method appends a `SaveExpectationValue` instruction to the quantum circuit.
</Admonition>

### save\_expectation\_value\_variance

<span id="qiskit.circuit.QuantumCircuit.save_expectation_value_variance" />

`QuantumCircuit.save_expectation_value_variance(operator, qubits, label='expectation_value_variance', unnormalized=False, pershot=False, conditional=False)`

Save the expectation value of a Hermitian operator.

**Parameters**

*   **operator** ([*Pauli*](qiskit.quantum_info.Pauli "qiskit.quantum_info.Pauli")  *or*[*SparsePauliOp*](qiskit.quantum_info.SparsePauliOp "qiskit.quantum_info.SparsePauliOp")  *or*[*Operator*](qiskit.quantum_info.Operator "qiskit.quantum_info.Operator")) – a Hermitian operator.
*   **qubits** (*list*) – circuit qubits to apply instruction.
*   **label** (*str*) – the key for retrieving saved data from results.
*   **unnormalized** (*bool*) – If True return save the unnormalized accumulated or conditional accumulated expectation value and variance over all shot \[Default: False].
*   **pershot** (*bool*) – if True save a list of expectation values and variances for each shot of the simulation rather than the average over all shots \[Default: False].
*   **conditional** (*bool*) – if True save the data conditional on the current classical register values \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – if the input operator is invalid or not Hermitian.

<Admonition title="Note" type="note">
  This method appends a `SaveExpectationValueVariance` instruction to the quantum circuit.
</Admonition>

### save\_matrix\_product\_state

<span id="qiskit.circuit.QuantumCircuit.save_matrix_product_state" />

`QuantumCircuit.save_matrix_product_state(label='matrix_product_state', pershot=False, conditional=False)`

Save the current simulator quantum state as a matrix product state.

**Parameters**

*   **label** (*str*) – the key for retrieving saved data from results.
*   **pershot** (*bool*) – if True save the mps for each shot of the simulation \[Default: False].
*   **conditional** (*bool*) – if True save pershot data conditional on the current classical register values \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### save\_probabilities

<span id="qiskit.circuit.QuantumCircuit.save_probabilities" />

`QuantumCircuit.save_probabilities(qubits=None, label='probabilities', unnormalized=False, pershot=False, conditional=False)`

Save measurement outcome probabilities vector.

**Parameters**

*   **qubits** (*list or None*) – the qubits to apply snapshot to. If None all qubits will be snapshot \[Default: None].
*   **label** (*str*) – the key for retrieving saved data from results.
*   **unnormalized** (*bool*) – If True return save the unnormalized accumulated probabilities over all shots \[Default: False].
*   **pershot** (*bool*) – if True save a list of probabilities for each shot of the simulation rather than the average over all shots \[Default: False].
*   **conditional** (*bool*) – if True save the probabilities data conditional on the current classical register values \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### save\_probabilities\_dict

<span id="qiskit.circuit.QuantumCircuit.save_probabilities_dict" />

`QuantumCircuit.save_probabilities_dict(qubits=None, label='probabilities', unnormalized=False, pershot=False, conditional=False)`

Save measurement outcome probabilities vector.

**Parameters**

*   **qubits** (*list or None*) – the qubits to apply snapshot to. If None all qubits will be snapshot \[Default: None].
*   **label** (*str*) – the key for retrieving saved data from results.
*   **unnormalized** (*bool*) – If True return save the unnormalized accumulated probabilities over all shots \[Default: False].
*   **pershot** (*bool*) – if True save a list of probabilities for each shot of the simulation rather than the average over all shots \[Default: False].
*   **conditional** (*bool*) – if True save the probabilities data conditional on the current classical register values \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### save\_stabilizer

<span id="qiskit.circuit.QuantumCircuit.save_stabilizer" />

`QuantumCircuit.save_stabilizer(label='stabilizer', pershot=False, conditional=False)`

Save the current stabilizer simulator quantum state as a StabilizerState.

**Parameters**

*   **label** (*str*) – the key for retrieving saved data from results.
*   **pershot** (*bool*) – if True save a list of StabilizerStates for each shot of the simulation \[Default: False].
*   **conditional** (*bool*) – if True save pershot data conditional on the current classical register values \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

<Admonition title="Note" type="note">
  This instruction is always defined across all qubits in a circuit.
</Admonition>

### save\_state

<span id="qiskit.circuit.QuantumCircuit.save_state" />

`QuantumCircuit.save_state(label=None, pershot=False, conditional=False)`

Save the current simulator quantum state.

**Parameters**

*   **label** (*str or None*) – Optional, the key for retrieving saved data from results. If None the key will be the state type of the simulator.
*   **pershot** (*bool*) – if True save a list of statevectors for each shot of the simulation \[Default: False].
*   **conditional** (*bool*) – if True save pershot data conditional on the current classical register values \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### save\_statevector

<span id="qiskit.circuit.QuantumCircuit.save_statevector" />

`QuantumCircuit.save_statevector(label='statevector', pershot=False, conditional=False)`

Save the current simulator quantum state as a statevector.

**Parameters**

*   **pershot** (*bool*) – if True save a list of statevectors for each shot of the simulation \[Default: False].
*   **label** (*str*) – the key for retrieving saved data from results.
*   **conditional** (*bool*) – if True save pershot data conditional on the current classical register values \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

<Admonition title="Note" type="note">
  This instruction is always defined across all qubits in a circuit.
</Admonition>

### save\_statevector\_dict

<span id="qiskit.circuit.QuantumCircuit.save_statevector_dict" />

`QuantumCircuit.save_statevector_dict(label='statevector', pershot=False, conditional=False)`

Save the current simulator quantum state as a statevector as a dict.

**Parameters**

*   **label** (*str*) – the key for retrieving saved data from results.
*   **pershot** (*bool*) – if True save a list of statevectors for each shot of the simulation \[Default: False].
*   **conditional** (*bool*) – if True save pershot data conditional on the current classical register values \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

<Admonition title="Note" type="note">
  This instruction is always defined across all qubits in a circuit.
</Admonition>

### save\_superop

<span id="qiskit.circuit.QuantumCircuit.save_superop" />

`QuantumCircuit.save_superop(label='superop', pershot=False)`

Save the current state of the superop simulator.

**Parameters**

*   **label** (*str*) – the key for retrieving saved data from results.
*   **pershot** (*bool*) – if True save a list of SuperOp matrices for each shot of the simulation \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

<Admonition title="Note" type="note">
  This instruction is always defined across all qubits in a circuit.
</Admonition>

### save\_unitary

<span id="qiskit.circuit.QuantumCircuit.save_unitary" />

`QuantumCircuit.save_unitary(label='unitary', pershot=False)`

Save the current state of the unitary simulator.

**Parameters**

*   **label** (*str*) – the key for retrieving saved data from results.
*   **pershot** (*bool*) – if True save a list of unitaries for each shot of the simulation \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

<Admonition title="Note" type="note">
  This instruction is always defined across all qubits in a circuit.
</Admonition>

### sdg

<span id="qiskit.circuit.QuantumCircuit.sdg" />

`QuantumCircuit.sdg(qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`SdgGate`](qiskit.circuit.library.SdgGate "qiskit.circuit.library.SdgGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

**qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### set\_density\_matrix

<span id="qiskit.circuit.QuantumCircuit.set_density_matrix" />

`QuantumCircuit.set_density_matrix(state)`

Set the density matrix state of the simulator.

**Parameters**

**state** ([*DensityMatrix*](qiskit.quantum_info.DensityMatrix "qiskit.quantum_info.DensityMatrix")) – a density matrix.

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – If the density matrix is the incorrect size for the current circuit.

### set\_matrix\_product\_state

<span id="qiskit.circuit.QuantumCircuit.set_matrix_product_state" />

`QuantumCircuit.set_matrix_product_state(state)`

Set the matrix product state of the simulator.

**Parameters**

**state** (*Tuple\[List\[Tuple\[np.array\[complex\_t]]]], List\[List\[float]]*) – A matrix\_product\_state.

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – If the structure of the state is incorrect

### set\_stabilizer

<span id="qiskit.circuit.QuantumCircuit.set_stabilizer" />

`QuantumCircuit.set_stabilizer(state)`

Set the Clifford stabilizer state of the simulator.

**Parameters**

**state** ([*Clifford*](qiskit.quantum_info.Clifford "qiskit.quantum_info.Clifford")) – A clifford operator.

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – If the state is the incorrect size for the current circuit.

### set\_statevector

<span id="qiskit.circuit.QuantumCircuit.set_statevector" />

`QuantumCircuit.set_statevector(state)`

Set the statevector state of the simulator.

**Parameters**

**state** ([*Statevector*](qiskit.quantum_info.Statevector "qiskit.quantum_info.Statevector")) – A state matrix.

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – If the state is the incorrect size for the current circuit.

### set\_superop

<span id="qiskit.circuit.QuantumCircuit.set_superop" />

`QuantumCircuit.set_superop(state)`

Set the superop state of the simulator.

**Parameters**

**state** (*QuantumChannel*) – A CPTP quantum channel.

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

*   **ExtensionError** – If the state is the incorrect size for the current circuit.
*   **ExtensionError** – if the input QuantumChannel is not CPTP.

### set\_unitary

<span id="qiskit.circuit.QuantumCircuit.set_unitary" />

`QuantumCircuit.set_unitary(state)`

Set the state state of the simulator.

**Parameters**

**state** ([*Operator*](qiskit.quantum_info.Operator "qiskit.quantum_info.Operator")) – A state matrix.

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

*   **ExtensionError** – If the state is the incorrect size for the current circuit.
*   **ExtensionError** – if the input matrix is not unitary.

### size

<span id="qiskit.circuit.QuantumCircuit.size" />

`QuantumCircuit.size(filter_function=<function QuantumCircuit.<lambda>>)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Returns total number of instructions in circuit.

**Parameters**

**filter\_function** (*callable*) – a function to filter out some instructions. Should take as input a tuple of (Instruction, list(Qubit), list(Clbit)). By default filters out “directives”, such as barrier or snapshot.

**Returns**

Total number of gate operations.

**Return type**

int

### snapshot

<span id="qiskit.circuit.QuantumCircuit.snapshot" />

`QuantumCircuit.snapshot(label, snapshot_type='statevector', qubits=None, params=None)`

Take a statevector snapshot of the internal simulator representation. Works on all qubits, and prevents reordering (like barrier). :param label: a snapshot label to report the result :type label: str :param snapshot\_type: the type of the snapshot. :type snapshot\_type: str :param qubits: the qubits to apply snapshot to \[Default: None]. :type qubits: list or None :param params: the parameters for snapshot\_type \[Default: None]. :type params: list or None

**Returns**

with attached command

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – malformed command

### snapshot\_density\_matrix

<span id="qiskit.circuit.QuantumCircuit.snapshot_density_matrix" />

`QuantumCircuit.snapshot_density_matrix(label, qubits=None)`

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

<Admonition title="Deprecated since version 0.9.0" type="danger">
  This instruction has been deprecated and will be removed no earlier than 3 months from the 0.9.0 release date. It has been superseded by the [`qiskit.providers.aer.library.save_density_matrix`](qiskit.providers.aer.library.save_density_matrix "qiskit.providers.aer.library.save_density_matrix") circuit method.
</Admonition>

### snapshot\_expectation\_value

<span id="qiskit.circuit.QuantumCircuit.snapshot_expectation_value" />

`QuantumCircuit.snapshot_expectation_value(label, op, qubits, single_shot=False, variance=False)`

Take a snapshot of expectation value \<O> of an Operator.

**Parameters**

*   **label** (*str*) – a snapshot label to report the result
*   **op** ([*Operator*](qiskit.quantum_info.Operator "qiskit.quantum_info.Operator")) – operator to snapshot
*   **qubits** (*list*) – the qubits to snapshot.
*   **single\_shot** (*bool*) – return list for each shot rather than average \[Default: False]
*   **variance** (*bool*) – compute variance of values \[Default: False]

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – if snapshot is invalid.

<Admonition title="Deprecated since version 0.9.0" type="danger">
  This instruction has been deprecated and will be removed no earlier than 3 months from the 0.9.0 release date. It has been superseded by the [`qiskit.providers.aer.library.save_expectation_value()`](qiskit.providers.aer.library.save_expectation_value "qiskit.providers.aer.library.save_expectation_value") and [`qiskit.providers.aer.library.save_expectation_value_variance()`](qiskit.providers.aer.library.save_expectation_value_variance "qiskit.providers.aer.library.save_expectation_value_variance") circuit methods.
</Admonition>

### snapshot\_probabilities

<span id="qiskit.circuit.QuantumCircuit.snapshot_probabilities" />

`QuantumCircuit.snapshot_probabilities(label, qubits, variance=False)`

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

<Admonition title="Deprecated since version 0.9.0" type="danger">
  This instruction has been deprecated and will be removed no earlier than 3 months from the 0.9.0 release date. It has been superseded by the [`qiskit.providers.aer.library.save_probabilities()`](qiskit.providers.aer.library.save_probabilities "qiskit.providers.aer.library.save_probabilities") and [`qiskit.providers.aer.library.save_probabilities_dict()`](qiskit.providers.aer.library.save_probabilities_dict "qiskit.providers.aer.library.save_probabilities_dict") circuit methods.
</Admonition>

### snapshot\_stabilizer

<span id="qiskit.circuit.QuantumCircuit.snapshot_stabilizer" />

`QuantumCircuit.snapshot_stabilizer(label)`

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

<Admonition title="Deprecated since version 0.9.0" type="danger">
  This instruction has been deprecated and will be removed no earlier than 3 months from the 0.9.0 release date. It has been superseded by the [`qiskit.providers.aer.library.save_stabilizer()`](qiskit.providers.aer.library.save_stabilizer "qiskit.providers.aer.library.save_stabilizer") circuit method.
</Admonition>

### snapshot\_statevector

<span id="qiskit.circuit.QuantumCircuit.snapshot_statevector" />

`QuantumCircuit.snapshot_statevector(label)`

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

<Admonition title="Deprecated since version 0.9.0" type="danger">
  This instruction has been deprecated and will be removed no earlier than 3 months from the 0.9.0 release date. It has been superseded by the [`qiskit.providers.aer.library.save_statevector`](qiskit.providers.aer.library.save_statevector "qiskit.providers.aer.library.save_statevector") circuit method.
</Admonition>

### squ

<span id="qiskit.circuit.QuantumCircuit.squ" />

`QuantumCircuit.squ(unitary_matrix, qubit, mode='ZYZ', up_to_diagonal=False)`

Decompose an arbitrary 2\*2 unitary into three rotation gates.

Note that the decomposition is up to a global phase shift. (This is a well known decomposition, which can be found for example in Nielsen and Chuang’s book “Quantum computation and quantum information”.)

**Parameters**

*   **unitary\_matrix** (*ndarray*) – 2\*2 unitary (given as a (complex) ndarray).
*   **qubit** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")  *or*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")) – The qubit which the gate is acting on.
*   **mode** (*string*) – determines the used decomposition by providing the rotation axes. The allowed modes are: “ZYZ” (default)
*   **up\_to\_diagonal** (*bool*) – if set to True, the single-qubit unitary is decomposed up to a diagonal matrix, i.e. a unitary u’ is implemented such that there exists a 2\*2 diagonal gate d with u = d.dot(u’)

**Returns**

The single-qubit unitary instruction attached to the circuit.

**Return type**

[InstructionSet](qiskit.circuit.InstructionSet "qiskit.circuit.InstructionSet")

**Raises**

**QiskitError** – if the format is wrong; if the array u is not unitary

### swap

<span id="qiskit.circuit.QuantumCircuit.swap" />

`QuantumCircuit.swap(qubit1, qubit2)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`SwapGate`](qiskit.circuit.library.SwapGate "qiskit.circuit.library.SwapGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **qubit1** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubits to apply the gate to.
*   **qubit2** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubits to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### sx

<span id="qiskit.circuit.QuantumCircuit.sx" />

`QuantumCircuit.sx(qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`SXGate`](qiskit.circuit.library.SXGate "qiskit.circuit.library.SXGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

**qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### sxdg

<span id="qiskit.circuit.QuantumCircuit.sxdg" />

`QuantumCircuit.sxdg(qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`SXdgGate`](qiskit.circuit.library.SXdgGate "qiskit.circuit.library.SXdgGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

**qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### t

<span id="qiskit.circuit.QuantumCircuit.t" />

`QuantumCircuit.t(qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`TGate`](qiskit.circuit.library.TGate "qiskit.circuit.library.TGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

**qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### tdg

<span id="qiskit.circuit.QuantumCircuit.tdg" />

`QuantumCircuit.tdg(qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`TdgGate`](qiskit.circuit.library.TdgGate "qiskit.circuit.library.TdgGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

**qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### tensor

<span id="qiskit.circuit.QuantumCircuit.tensor" />

`QuantumCircuit.tensor(other, inplace=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Tensor `self` with `other`.

Remember that in the little-endian convention the leftmost operation will be at the bottom of the circuit. See also \[the docs]\(qiskit.org/documentation/tutorials/circuits/3\_summary\_of\_quantum\_operations.html) for more information.

```python
     ┌────────┐         ┌─────┐          ┌─────┐
q_0: ┤ bottom ├ ⊗ q_0: ┤ top ├  = q_0: ─┤ top ├──
     └────────┘         └─────┘         ┌┴─────┴─┐
                                   q_1: ┤ bottom ├
                                        └────────┘
```

**Parameters**

*   **other** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – The other circuit to tensor this circuit with.
*   **inplace** (*bool*) – If True, modify the object. Otherwise return composed circuit.

#### Examples

```python
from qiskit import QuantumCircuit
top = QuantumCircuit(1)
top.x(0);
bottom = QuantumCircuit(2)
bottom.cry(0.2, 0, 1);
tensored = bottom.tensor(top)
print(tensored.draw())
```

```python
        ┌───┐   
q_0: ───┤ X ├───
        └───┘   
q_1: ─────■─────
     ┌────┴────┐
q_2: ┤ Ry(0.2) ├
     └─────────┘
```

**Returns**

The tensored circuit (returns None if inplace==True).

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### to\_gate

<span id="qiskit.circuit.QuantumCircuit.to_gate" />

`QuantumCircuit.to_gate(parameter_map=None, label=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Create a Gate out of this circuit.

**Parameters**

*   **parameter\_map** (*dict*) – For parameterized circuits, a mapping from parameters in the circuit to parameters to be used in the gate. If None, existing circuit parameters will also parameterize the gate.
*   **label** (*str*) – Optional gate label.

**Returns**

a composite gate encapsulating this circuit (can be decomposed back)

**Return type**

[Gate](qiskit.circuit.Gate "qiskit.circuit.Gate")

### to\_instruction

<span id="qiskit.circuit.QuantumCircuit.to_instruction" />

`QuantumCircuit.to_instruction(parameter_map=None, label=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Create an Instruction out of this circuit.

**Parameters**

*   **parameter\_map** (*dict*) – For parameterized circuits, a mapping from parameters in the circuit to parameters to be used in the instruction. If None, existing circuit parameters will also parameterize the instruction.
*   **label** (*str*) – Optional gate label.

**Returns**

a composite instruction encapsulating this circuit (can be decomposed back)

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

### toffoli

<span id="qiskit.circuit.QuantumCircuit.toffoli" />

`QuantumCircuit.toffoli(control_qubit1, control_qubit2, target_qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`CCXGate`](qiskit.circuit.library.CCXGate "qiskit.circuit.library.CCXGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **control\_qubit1** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) used as the first control.
*   **control\_qubit2** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) used as the second control.
*   **target\_qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) targeted by the gate.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

<Admonition title="See also" type="note">
  QuantumCircuit.ccx: the same gate with a different name.
</Admonition>

### u

<span id="qiskit.circuit.QuantumCircuit.u" />

`QuantumCircuit.u(theta, phi, lam, qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`UGate`](qiskit.circuit.library.UGate "qiskit.circuit.library.UGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **theta** (`Union`\[`ParameterExpression`, `float`]) – The $\theta$ rotation angle of the gate.
*   **phi** (`Union`\[`ParameterExpression`, `float`]) – The $\phi$ rotation angle of the gate.
*   **lam** (`Union`\[`ParameterExpression`, `float`]) – The $\lambda$ rotation angle of the gate.
*   **qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### u1

<span id="qiskit.circuit.QuantumCircuit.u1" />

`QuantumCircuit.u1(theta, qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`U1Gate`](qiskit.circuit.library.U1Gate "qiskit.circuit.library.U1Gate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **theta** (`Union`\[`ParameterExpression`, `float`]) – The $\theta$ rotation angle of the gate.
*   **qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### u2

<span id="qiskit.circuit.QuantumCircuit.u2" />

`QuantumCircuit.u2(phi, lam, qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`U2Gate`](qiskit.circuit.library.U2Gate "qiskit.circuit.library.U2Gate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **phi** (`Union`\[`ParameterExpression`, `float`]) – The $\phi$ rotation angle of the gate.
*   **lam** (`Union`\[`ParameterExpression`, `float`]) – The $\lambda$ rotation angle of the gate.
*   **qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### u3

<span id="qiskit.circuit.QuantumCircuit.u3" />

`QuantumCircuit.u3(theta, phi, lam, qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`U3Gate`](qiskit.circuit.library.U3Gate "qiskit.circuit.library.U3Gate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **theta** (`Union`\[`ParameterExpression`, `float`]) – The $\theta$ rotation angle of the gate.
*   **phi** (`Union`\[`ParameterExpression`, `float`]) – The $\phi$ rotation angle of the gate.
*   **lam** (`Union`\[`ParameterExpression`, `float`]) – The $\lambda$ rotation angle of the gate.
*   **qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### uc

<span id="qiskit.circuit.QuantumCircuit.uc" />

`QuantumCircuit.uc(gate_list, q_controls, q_target, up_to_diagonal=False)`

Attach a uniformly controlled gates (also called multiplexed gates) to a circuit.

The decomposition was introduced by Bergholm et al. in [https://arxiv.org/pdf/quant-ph/0410066.pdf](https://arxiv.org/pdf/quant-ph/0410066.pdf).

**Parameters**

*   **gate\_list** (*list\[ndarray]*) – list of two qubit unitaries \[U\_0,…,U\_\{2^k-1}], where each single-qubit unitary U\_i is a given as a 2\*2 array
*   **q\_controls** (*QuantumRegister|list\[(*[*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*,int)]*) – list of k control qubits. The qubits are ordered according to their significance in the computational basis. For example if q\_controls=\[q\[1],q\[2]] (with q = QuantumRegister(2)), the unitary U\_0 is performed if q\[1] and q\[2] are in the state zero, U\_1 is performed if q\[2] is in the state zero and q\[1] is in the state one, and so on
*   **q\_target** (*QuantumRegister|(*[*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister")*,int)*) – target qubit, where we act on with the single-qubit gates.
*   **up\_to\_diagonal** (*bool*) – If set to True, the uniformly controlled gate is decomposed up to a diagonal gate, i.e. a unitary u’ is implemented such that there exists a diagonal gate d with u = d.dot(u’), where the unitary u describes the uniformly controlled gate

**Returns**

the uniformly controlled gate is attached to the circuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the list number of control qubits does not correspond to the provided number of single-qubit unitaries; if an input is of the wrong type

### ucrx

<span id="qiskit.circuit.QuantumCircuit.ucrx" />

`QuantumCircuit.ucrx(angle_list, q_controls, q_target)`

Attach a uniformly controlled (also called multiplexed) Rx rotation gate to a circuit.

The decomposition is base on [https://arxiv.org/pdf/quant-ph/0406176.pdf](https://arxiv.org/pdf/quant-ph/0406176.pdf) by Shende et al.

**Parameters**

*   **angle\_list** (*list*) – list of (real) rotation angles $[a_0,...,a_{2^k-1}]$
*   **q\_controls** (*QuantumRegister|list*) – list of k control qubits (or empty list if no controls). The control qubits are ordered according to their significance in increasing order: For example if `q_controls=[q[0],q[1]]` (with `q = QuantumRegister(2)`), the rotation `Rx(a_0)` is performed if `q[0]` and `q[1]` are in the state zero, the rotation `Rx(a_1)` is performed if `q[0]` is in the state one and `q[1]` is in the state zero, and so on
*   **q\_target** (*QuantumRegister|Qubit*) – target qubit, where we act on with the single-qubit rotation gates

**Returns**

the uniformly controlled rotation gate is attached to the circuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the list number of control qubits does not correspond to the provided number of single-qubit unitaries; if an input is of the wrong type

### ucry

<span id="qiskit.circuit.QuantumCircuit.ucry" />

`QuantumCircuit.ucry(angle_list, q_controls, q_target)`

Attach a uniformly controlled (also called multiplexed) Ry rotation gate to a circuit.

The decomposition is base on [https://arxiv.org/pdf/quant-ph/0406176.pdf](https://arxiv.org/pdf/quant-ph/0406176.pdf) by Shende et al.

**Parameters**

*   **angle\_list** (*list\[numbers*) – list of (real) rotation angles $[a_0,...,a_{2^k-1}]$
*   **q\_controls** (*QuantumRegister|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of k control qubits (or empty list if no controls). The control qubits are ordered according to their significance in increasing order: For example if `q_controls=[q[0],q[1]]` (with `q = QuantumRegister(2)`), the rotation `Ry(a_0)` is performed if `q[0]` and `q[1]` are in the state zero, the rotation `Ry(a_1)` is performed if `q[0]` is in the state one and `q[1]` is in the state zero, and so on
*   **q\_target** (*QuantumRegister|Qubit*) – target qubit, where we act on with the single-qubit rotation gates

**Returns**

the uniformly controlled rotation gate is attached to the circuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the list number of control qubits does not correspond to the provided number of single-qubit unitaries; if an input is of the wrong type

### ucrz

<span id="qiskit.circuit.QuantumCircuit.ucrz" />

`QuantumCircuit.ucrz(angle_list, q_controls, q_target)`

Attach a uniformly controlled (also called multiplexed gates) Rz rotation gate to a circuit.

The decomposition is base on [https://arxiv.org/pdf/quant-ph/0406176.pdf](https://arxiv.org/pdf/quant-ph/0406176.pdf) by Shende et al.

**Parameters**

*   **angle\_list** (*list\[numbers*) – list of (real) rotation angles \[a\_0,…,a\_\{2^k-1}]
*   **q\_controls** (*QuantumRegister|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of k control qubits (or empty list if no controls). The control qubits are ordered according to their significance in increasing order: For example if q\_controls=\[q\[1],q\[2]] (with q = QuantumRegister(2)), the rotation Rz(a\_0)is performed if q\[1] and q\[2] are in the state zero, the rotation Rz(a\_1) is performed if q\[1] is in the state one and q\[2] is in the state zero, and so on
*   **q\_target** (*QuantumRegister|Qubit*) – target qubit, where we act on with the single-qubit rotation gates

**Returns**

the uniformly controlled rotation gate is attached to the circuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the list number of control qubits does not correspond to the provided number of single-qubit unitaries; if an input is of the wrong type

### unitary

<span id="qiskit.circuit.QuantumCircuit.unitary" />

`QuantumCircuit.unitary(obj, qubits, label=None)`

Apply unitary gate to q.

### while\_loop

##### while\_loop

<span id="qiskit.circuit.QuantumCircuit.while_loop" />

`QuantumCircuit.while_loop(condition: Tuple[Union[qiskit.circuit.classicalregister.ClassicalRegister, qiskit.circuit.classicalregister.Clbit], int], body: None, qubits: None, clbits: None, *, label: Optional[str]) → qiskit.circuit.controlflow.while_loop.WhileLoopContext`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

<span id="qiskit.circuit.QuantumCircuit.while_loop" />

`QuantumCircuit.while_loop(condition: Tuple[Union[qiskit.circuit.classicalregister.ClassicalRegister, qiskit.circuit.classicalregister.Clbit], int], body: QuantumCircuit, qubits: Sequence[Union[qiskit.circuit.quantumregister.Qubit, qiskit.circuit.quantumregister.QuantumRegister, int, slice, Sequence[Union[qiskit.circuit.quantumregister.Qubit, int]]]], clbits: Sequence[Union[qiskit.circuit.classicalregister.Clbit, qiskit.circuit.classicalregister.ClassicalRegister, int, slice, Sequence[Union[qiskit.circuit.classicalregister.Clbit, int]]]], *, label: Optional[str]) → qiskit.circuit.instructionset.InstructionSet`

Create a `while` loop on this circuit.

There are two forms for calling this function. If called with all its arguments (with the possible exception of `label`), it will create a `WhileLoopOp` with the given `body`. If `body` (and `qubits` and `clbits`) are *not* passed, then this acts as a context manager, which will automatically build a `WhileLoopOp` when the scope finishes. In this form, you do not need to keep track of the qubits or clbits you are using, because the scope will handle it for you.

Example usage:

```python
from qiskit.circuit import QuantumCircuit, Clbit, Qubit
bits = [Qubit(), Qubit(), Clbit()]
qc = QuantumCircuit(bits)

with qc.while_loop((bits[2], 0)):
    qc.h(0)
    qc.cx(0, 1)
    qc.measure(0, 0)
```

**Parameters**

*   **condition** (*Tuple\[Union\[*[*ClassicalRegister*](qiskit.circuit.ClassicalRegister "qiskit.circuit.ClassicalRegister")*,* [*Clbit*](qiskit.circuit.Clbit "qiskit.circuit.Clbit")*], int]*) – An equality condition to be checked prior to executing `body`. The left-hand side of the condition must be a [`ClassicalRegister`](qiskit.circuit.ClassicalRegister "qiskit.circuit.ClassicalRegister") or a [`Clbit`](qiskit.circuit.Clbit "qiskit.circuit.Clbit"), and the right-hand side must be an integer or boolean.
*   **body** (*Optional\[*[*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")*]*) – The loop body to be repeatedly executed. Omit this to use the context-manager mode.
*   **qubits** (*Optional\[Sequence\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]]*) – The circuit qubits over which the loop body should be run. Omit this to use the context-manager mode.
*   **clbits** (*Optional\[Sequence\[*[*Clbit*](qiskit.circuit.Clbit "qiskit.circuit.Clbit")*]]*) – The circuit clbits over which the loop body should be run. Omit this to use the context-manager mode.
*   **label** (*Optional\[str]*) – The string label of the instruction in the circuit.

**Returns**

If used in context-manager mode, then this should be used as a `with` resource, which will infer the block content and operands on exit. If the full form is used, then this returns a handle to the instructions created.

**Return type**

[InstructionSet](qiskit.circuit.InstructionSet "qiskit.circuit.InstructionSet") or WhileLoopContext

**Raises**

**CircuitError** – if an incorrect calling convention is used.

### width

<span id="qiskit.circuit.QuantumCircuit.width" />

`QuantumCircuit.width()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Return number of qubits plus clbits in circuit.

**Returns**

Width of circuit.

**Return type**

int

### x

<span id="qiskit.circuit.QuantumCircuit.x" />

`QuantumCircuit.x(qubit, label=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`XGate`](qiskit.circuit.library.XGate "qiskit.circuit.library.XGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

*   **qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.
*   **label** (`Optional`\[`str`]) – The string label of the gate in the circuit.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### y

<span id="qiskit.circuit.QuantumCircuit.y" />

`QuantumCircuit.y(qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`YGate`](qiskit.circuit.library.YGate "qiskit.circuit.library.YGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

**qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

### z

<span id="qiskit.circuit.QuantumCircuit.z" />

`QuantumCircuit.z(qubit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.20/qiskit/circuit/quantumcircuit.py "view source code")

Apply [`ZGate`](qiskit.circuit.library.ZGate "qiskit.circuit.library.ZGate").

For the full matrix form of this gate, see the underlying gate documentation.

**Parameters**

**qubit** (`Union`\[`Qubit`, `QuantumRegister`, `int`, `slice`, `Sequence`\[`Union`\[`Qubit`, `int`]]]) – The qubit(s) to apply the gate to.

**Return type**

`InstructionSet`

**Returns**

A handle to the instructions created.

## Attributes

<span id="qiskit.circuit.QuantumCircuit.ancillas" />

### ancillas

Returns a list of ancilla bits in the order that the registers were added.

**Return type**

`List`\[`AncillaQubit`]

<span id="qiskit.circuit.QuantumCircuit.calibrations" />

### calibrations

Return calibration dictionary.

**The custom pulse definition of a given gate is of the form**

\{‘gate\_name’: \{(qubits, params): schedule}}

**Return type**

`dict`

<span id="qiskit.circuit.QuantumCircuit.clbits" />

### clbits

Returns a list of classical bits in the order that the registers were added.

**Return type**

`List`\[`Clbit`]

<span id="qiskit.circuit.QuantumCircuit.data" />

### data

Return the circuit data (instructions and context).

**Returns**

a list-like object containing the tuples for the circuit’s data.

Each tuple is in the format `(instruction, qargs, cargs)`, where instruction is an Instruction (or subclass) object, qargs is a list of Qubit objects, and cargs is a list of Clbit objects.

**Return type**

QuantumCircuitData

<span id="qiskit.circuit.QuantumCircuit.extension_lib" />

### extension\_lib

`= 'include "qelib1.inc";'`

<span id="qiskit.circuit.QuantumCircuit.global_phase" />

### global\_phase

Return the global phase of the circuit in radians.

**Return type**

`Union`\[`ParameterExpression`, `float`]

<span id="qiskit.circuit.QuantumCircuit.header" />

### header

`= 'OPENQASM 2.0;'`

<span id="qiskit.circuit.QuantumCircuit.instances" />

### instances

`= 9`

<span id="qiskit.circuit.QuantumCircuit.metadata" />

### metadata

The user provided metadata associated with the circuit

The metadata for the circuit is a user provided `dict` of metadata for the circuit. It will not be used to influence the execution or operation of the circuit, but it is expected to be passed between all transforms of the circuit (ie transpilation) and that providers will associate any circuit metadata with the results it returns from execution of that circuit.

**Return type**

`dict`

<span id="qiskit.circuit.QuantumCircuit.num_ancillas" />

### num\_ancillas

Return the number of ancilla qubits.

**Return type**

`int`

<span id="qiskit.circuit.QuantumCircuit.num_clbits" />

### num\_clbits

Return number of classical bits.

**Return type**

`int`

<span id="qiskit.circuit.QuantumCircuit.num_parameters" />

### num\_parameters

Convenience function to get the number of parameter objects in the circuit.

**Return type**

`int`

<span id="qiskit.circuit.QuantumCircuit.num_qubits" />

### num\_qubits

Return number of qubits.

**Return type**

`int`

<span id="qiskit.circuit.QuantumCircuit.parameters" />

### parameters

Convenience function to get the parameters defined in the parameter table.

**Return type**

`ParameterView`

<span id="qiskit.circuit.QuantumCircuit.prefix" />

### prefix

`= 'circuit'`

<span id="qiskit.circuit.QuantumCircuit.qubits" />

### qubits

Returns a list of quantum bits in the order that the registers were added.

**Return type**

`List`\[`Qubit`]

