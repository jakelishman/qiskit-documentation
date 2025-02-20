---
title: QuantumCircuit
description: API reference for qiskit.circuit.QuantumCircuit
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.QuantumCircuit
---

# qiskit.circuit.QuantumCircuit

<span id="qiskit.circuit.QuantumCircuit" />

`QuantumCircuit(*regs, name=None, global_phase=0, metadata=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/circuit/quantumcircuit.py "view source code")

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
ancilla_0: ┤ X ├┤ H ├┤ X ├┤ X ├┤ X ├─────────╫──╫──╫─
           └───┘└───┘└───┘└───┘└───┘         ║  ║  ║ 
      c: 3/══════════════════════════════════╩══╩══╩═
                                             0  1  2 
```

### \_\_init\_\_

<span id="qiskit.circuit.QuantumCircuit.__init__" />

`__init__(*regs, name=None, global_phase=0, metadata=None)`

Initialize self. See help(type(self)) for accurate signature.

## Methods

|                                                                                                                                                                                       |                                                                                                                                     |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.circuit.QuantumCircuit.__init__ "qiskit.circuit.QuantumCircuit.__init__")(\*regs\[, name, global\_phase, metadata])                                              | Initialize self.                                                                                                                    |
| [`add_bits`](#qiskit.circuit.QuantumCircuit.add_bits "qiskit.circuit.QuantumCircuit.add_bits")(bits)                                                                                  | Add Bits to the circuit.                                                                                                            |
| [`add_calibration`](#qiskit.circuit.QuantumCircuit.add_calibration "qiskit.circuit.QuantumCircuit.add_calibration")(gate, qubits, schedule\[, params])                                | Register a low-level, custom pulse definition for the given gate.                                                                   |
| [`add_register`](#qiskit.circuit.QuantumCircuit.add_register "qiskit.circuit.QuantumCircuit.add_register")(\*regs)                                                                    | Add registers.                                                                                                                      |
| [`append`](#qiskit.circuit.QuantumCircuit.append "qiskit.circuit.QuantumCircuit.append")(instruction\[, qargs, cargs])                                                                | Append one or more instructions to the end of the circuit, modifying the circuit in place.                                          |
| [`assign_parameters`](#qiskit.circuit.QuantumCircuit.assign_parameters "qiskit.circuit.QuantumCircuit.assign_parameters")(parameters\[, inplace, …])                                  | Assign parameters to new parameters or values.                                                                                      |
| [`barrier`](#qiskit.circuit.QuantumCircuit.barrier "qiskit.circuit.QuantumCircuit.barrier")(\*qargs)                                                                                  | Apply `Barrier`.                                                                                                                    |
| [`bind_parameters`](#qiskit.circuit.QuantumCircuit.bind_parameters "qiskit.circuit.QuantumCircuit.bind_parameters")(values\[, value\_dict])                                           | Assign numeric parameters to values yielding a new circuit.                                                                         |
| [`cast`](#qiskit.circuit.QuantumCircuit.cast "qiskit.circuit.QuantumCircuit.cast")(value, \_type)                                                                                     | Best effort to cast value to type.                                                                                                  |
| [`cbit_argument_conversion`](#qiskit.circuit.QuantumCircuit.cbit_argument_conversion "qiskit.circuit.QuantumCircuit.cbit_argument_conversion")(clbit\_representation)                 | Converts several classical bit representations (such as indexes, range, etc.) into a list of classical bits.                        |
| [`ccx`](#qiskit.circuit.QuantumCircuit.ccx "qiskit.circuit.QuantumCircuit.ccx")(control\_qubit1, control\_qubit2, target\_qubit)                                                      | Apply [`CCXGate`](qiskit.circuit.library.CCXGate "qiskit.circuit.library.CCXGate").                                                 |
| [`ch`](#qiskit.circuit.QuantumCircuit.ch "qiskit.circuit.QuantumCircuit.ch")(control\_qubit, target\_qubit\[, label, …])                                                              | Apply [`CHGate`](qiskit.circuit.library.CHGate "qiskit.circuit.library.CHGate").                                                    |
| [`cls_instances`](#qiskit.circuit.QuantumCircuit.cls_instances "qiskit.circuit.QuantumCircuit.cls_instances")()                                                                       | Return the current number of instances of this class, useful for auto naming.                                                       |
| [`cls_prefix`](#qiskit.circuit.QuantumCircuit.cls_prefix "qiskit.circuit.QuantumCircuit.cls_prefix")()                                                                                | Return the prefix to use for auto naming.                                                                                           |
| [`cnot`](#qiskit.circuit.QuantumCircuit.cnot "qiskit.circuit.QuantumCircuit.cnot")(control\_qubit, target\_qubit\[, label, …])                                                        | Apply [`CXGate`](qiskit.circuit.library.CXGate "qiskit.circuit.library.CXGate").                                                    |
| [`combine`](#qiskit.circuit.QuantumCircuit.combine "qiskit.circuit.QuantumCircuit.combine")(rhs)                                                                                      | DEPRECATED - Returns rhs appended to self if self contains compatible registers.                                                    |
| [`compose`](#qiskit.circuit.QuantumCircuit.compose "qiskit.circuit.QuantumCircuit.compose")(other\[, qubits, clbits, front, …])                                                       | Compose circuit with `other` circuit or instruction, optionally permuting wires.                                                    |
| [`control`](#qiskit.circuit.QuantumCircuit.control "qiskit.circuit.QuantumCircuit.control")(\[num\_ctrl\_qubits, label, ctrl\_state])                                                 | Control this circuit on `num_ctrl_qubits` qubits.                                                                                   |
| [`copy`](#qiskit.circuit.QuantumCircuit.copy "qiskit.circuit.QuantumCircuit.copy")(\[name])                                                                                           | Copy the circuit.                                                                                                                   |
| [`count_ops`](#qiskit.circuit.QuantumCircuit.count_ops "qiskit.circuit.QuantumCircuit.count_ops")()                                                                                   | Count each operation kind in the circuit.                                                                                           |
| [`cp`](#qiskit.circuit.QuantumCircuit.cp "qiskit.circuit.QuantumCircuit.cp")(theta, control\_qubit, target\_qubit\[, …])                                                              | Apply [`CPhaseGate`](qiskit.circuit.library.CPhaseGate "qiskit.circuit.library.CPhaseGate").                                        |
| [`crx`](#qiskit.circuit.QuantumCircuit.crx "qiskit.circuit.QuantumCircuit.crx")(theta, control\_qubit, target\_qubit\[, …])                                                           | Apply [`CRXGate`](qiskit.circuit.library.CRXGate "qiskit.circuit.library.CRXGate").                                                 |
| [`cry`](#qiskit.circuit.QuantumCircuit.cry "qiskit.circuit.QuantumCircuit.cry")(theta, control\_qubit, target\_qubit\[, …])                                                           | Apply [`CRYGate`](qiskit.circuit.library.CRYGate "qiskit.circuit.library.CRYGate").                                                 |
| [`crz`](#qiskit.circuit.QuantumCircuit.crz "qiskit.circuit.QuantumCircuit.crz")(theta, control\_qubit, target\_qubit\[, …])                                                           | Apply [`CRZGate`](qiskit.circuit.library.CRZGate "qiskit.circuit.library.CRZGate").                                                 |
| [`cswap`](#qiskit.circuit.QuantumCircuit.cswap "qiskit.circuit.QuantumCircuit.cswap")(control\_qubit, target\_qubit1, …\[, …])                                                        | Apply [`CSwapGate`](qiskit.circuit.library.CSwapGate "qiskit.circuit.library.CSwapGate").                                           |
| [`csx`](#qiskit.circuit.QuantumCircuit.csx "qiskit.circuit.QuantumCircuit.csx")(control\_qubit, target\_qubit\[, label, …])                                                           | Apply [`CSXGate`](qiskit.circuit.library.CSXGate "qiskit.circuit.library.CSXGate").                                                 |
| [`cu`](#qiskit.circuit.QuantumCircuit.cu "qiskit.circuit.QuantumCircuit.cu")(theta, phi, lam, gamma, control\_qubit, …)                                                               | Apply [`CUGate`](qiskit.circuit.library.CUGate "qiskit.circuit.library.CUGate").                                                    |
| [`cu1`](#qiskit.circuit.QuantumCircuit.cu1 "qiskit.circuit.QuantumCircuit.cu1")(theta, control\_qubit, target\_qubit\[, …])                                                           | Apply [`CU1Gate`](qiskit.circuit.library.CU1Gate "qiskit.circuit.library.CU1Gate").                                                 |
| [`cu3`](#qiskit.circuit.QuantumCircuit.cu3 "qiskit.circuit.QuantumCircuit.cu3")(theta, phi, lam, control\_qubit, target\_qubit)                                                       | Apply [`CU3Gate`](qiskit.circuit.library.CU3Gate "qiskit.circuit.library.CU3Gate").                                                 |
| [`cx`](#qiskit.circuit.QuantumCircuit.cx "qiskit.circuit.QuantumCircuit.cx")(control\_qubit, target\_qubit\[, label, …])                                                              | Apply [`CXGate`](qiskit.circuit.library.CXGate "qiskit.circuit.library.CXGate").                                                    |
| [`cy`](#qiskit.circuit.QuantumCircuit.cy "qiskit.circuit.QuantumCircuit.cy")(control\_qubit, target\_qubit\[, label, …])                                                              | Apply [`CYGate`](qiskit.circuit.library.CYGate "qiskit.circuit.library.CYGate").                                                    |
| [`cz`](#qiskit.circuit.QuantumCircuit.cz "qiskit.circuit.QuantumCircuit.cz")(control\_qubit, target\_qubit\[, label, …])                                                              | Apply [`CZGate`](qiskit.circuit.library.CZGate "qiskit.circuit.library.CZGate").                                                    |
| [`dcx`](#qiskit.circuit.QuantumCircuit.dcx "qiskit.circuit.QuantumCircuit.dcx")(qubit1, qubit2)                                                                                       | Apply [`DCXGate`](qiskit.circuit.library.DCXGate "qiskit.circuit.library.DCXGate").                                                 |
| [`decompose`](#qiskit.circuit.QuantumCircuit.decompose "qiskit.circuit.QuantumCircuit.decompose")()                                                                                   | Call a decomposition pass on this circuit, to decompose one level (shallow decompose).                                              |
| [`delay`](#qiskit.circuit.QuantumCircuit.delay "qiskit.circuit.QuantumCircuit.delay")(duration\[, qarg, unit])                                                                        | Apply [`Delay`](qiskit.circuit.Delay "qiskit.circuit.Delay").                                                                       |
| [`depth`](#qiskit.circuit.QuantumCircuit.depth "qiskit.circuit.QuantumCircuit.depth")()                                                                                               | Return circuit depth (i.e., length of critical path).                                                                               |
| [`diagonal`](#qiskit.circuit.QuantumCircuit.diagonal "qiskit.circuit.QuantumCircuit.diagonal")(diag, qubit)                                                                           | Attach a diagonal gate to a circuit.                                                                                                |
| [`draw`](#qiskit.circuit.QuantumCircuit.draw "qiskit.circuit.QuantumCircuit.draw")(\[output, scale, filename, style, …])                                                              | Draw the quantum circuit.                                                                                                           |
| [`ecr`](#qiskit.circuit.QuantumCircuit.ecr "qiskit.circuit.QuantumCircuit.ecr")(qubit1, qubit2)                                                                                       | Apply [`ECRGate`](qiskit.circuit.library.ECRGate "qiskit.circuit.library.ECRGate").                                                 |
| [`extend`](#qiskit.circuit.QuantumCircuit.extend "qiskit.circuit.QuantumCircuit.extend")(rhs)                                                                                         | DEPRECATED - Append QuantumCircuit to the RHS if it contains compatible registers.                                                  |
| [`fredkin`](#qiskit.circuit.QuantumCircuit.fredkin "qiskit.circuit.QuantumCircuit.fredkin")(control\_qubit, target\_qubit1, …)                                                        | Apply [`CSwapGate`](qiskit.circuit.library.CSwapGate "qiskit.circuit.library.CSwapGate").                                           |
| [`from_qasm_file`](#qiskit.circuit.QuantumCircuit.from_qasm_file "qiskit.circuit.QuantumCircuit.from_qasm_file")(path)                                                                | Take in a QASM file and generate a QuantumCircuit object.                                                                           |
| [`from_qasm_str`](#qiskit.circuit.QuantumCircuit.from_qasm_str "qiskit.circuit.QuantumCircuit.from_qasm_str")(qasm\_str)                                                              | Take in a QASM string and generate a QuantumCircuit object.                                                                         |
| [`get_instructions`](#qiskit.circuit.QuantumCircuit.get_instructions "qiskit.circuit.QuantumCircuit.get_instructions")(name)                                                          | Get instructions matching name.                                                                                                     |
| [`h`](#qiskit.circuit.QuantumCircuit.h "qiskit.circuit.QuantumCircuit.h")(qubit)                                                                                                      | Apply [`HGate`](qiskit.circuit.library.HGate "qiskit.circuit.library.HGate").                                                       |
| [`hamiltonian`](#qiskit.circuit.QuantumCircuit.hamiltonian "qiskit.circuit.QuantumCircuit.hamiltonian")(operator, time, qubits\[, label])                                             | Apply hamiltonian evolution to qubits.                                                                                              |
| [`has_register`](#qiskit.circuit.QuantumCircuit.has_register "qiskit.circuit.QuantumCircuit.has_register")(register)                                                                  | Test if this circuit has the register r.                                                                                            |
| [`i`](#qiskit.circuit.QuantumCircuit.i "qiskit.circuit.QuantumCircuit.i")(qubit)                                                                                                      | Apply [`IGate`](qiskit.circuit.library.IGate "qiskit.circuit.library.IGate").                                                       |
| [`id`](#qiskit.circuit.QuantumCircuit.id "qiskit.circuit.QuantumCircuit.id")(qubit)                                                                                                   | Apply [`IGate`](qiskit.circuit.library.IGate "qiskit.circuit.library.IGate").                                                       |
| [`initialize`](#qiskit.circuit.QuantumCircuit.initialize "qiskit.circuit.QuantumCircuit.initialize")(params\[, qubits])                                                               | Initialize qubits in a specific state.                                                                                              |
| [`inverse`](#qiskit.circuit.QuantumCircuit.inverse "qiskit.circuit.QuantumCircuit.inverse")()                                                                                         | Invert (take adjoint of) this circuit.                                                                                              |
| [`iso`](#qiskit.circuit.QuantumCircuit.iso "qiskit.circuit.QuantumCircuit.iso")(isometry, q\_input, q\_ancillas\_for\_output)                                                         | Attach an arbitrary isometry from m to n qubits to a circuit.                                                                       |
| [`isometry`](#qiskit.circuit.QuantumCircuit.isometry "qiskit.circuit.QuantumCircuit.isometry")(isometry, q\_input, …\[, …])                                                           | Attach an arbitrary isometry from m to n qubits to a circuit.                                                                       |
| [`iswap`](#qiskit.circuit.QuantumCircuit.iswap "qiskit.circuit.QuantumCircuit.iswap")(qubit1, qubit2)                                                                                 | Apply [`iSwapGate`](qiskit.circuit.library.iSwapGate "qiskit.circuit.library.iSwapGate").                                           |
| [`mcp`](#qiskit.circuit.QuantumCircuit.mcp "qiskit.circuit.QuantumCircuit.mcp")(lam, control\_qubits, target\_qubit)                                                                  | Apply [`MCPhaseGate`](qiskit.circuit.library.MCPhaseGate "qiskit.circuit.library.MCPhaseGate").                                     |
| [`mcrx`](#qiskit.circuit.QuantumCircuit.mcrx "qiskit.circuit.QuantumCircuit.mcrx")(theta, q\_controls, q\_target\[, …])                                                               | Apply Multiple-Controlled X rotation gate                                                                                           |
| [`mcry`](#qiskit.circuit.QuantumCircuit.mcry "qiskit.circuit.QuantumCircuit.mcry")(theta, q\_controls, q\_target\[, …])                                                               | Apply Multiple-Controlled Y rotation gate                                                                                           |
| [`mcrz`](#qiskit.circuit.QuantumCircuit.mcrz "qiskit.circuit.QuantumCircuit.mcrz")(lam, q\_controls, q\_target\[, …])                                                                 | Apply Multiple-Controlled Z rotation gate                                                                                           |
| [`mct`](#qiskit.circuit.QuantumCircuit.mct "qiskit.circuit.QuantumCircuit.mct")(control\_qubits, target\_qubit\[, …])                                                                 | Apply [`MCXGate`](qiskit.circuit.library.MCXGate "qiskit.circuit.library.MCXGate").                                                 |
| [`mcu1`](#qiskit.circuit.QuantumCircuit.mcu1 "qiskit.circuit.QuantumCircuit.mcu1")(lam, control\_qubits, target\_qubit)                                                               | Apply `MCU1Gate`.                                                                                                                   |
| [`mcx`](#qiskit.circuit.QuantumCircuit.mcx "qiskit.circuit.QuantumCircuit.mcx")(control\_qubits, target\_qubit\[, …])                                                                 | Apply [`MCXGate`](qiskit.circuit.library.MCXGate "qiskit.circuit.library.MCXGate").                                                 |
| [`measure`](#qiskit.circuit.QuantumCircuit.measure "qiskit.circuit.QuantumCircuit.measure")(qubit, cbit)                                                                              | Measure quantum bit into classical bit (tuples).                                                                                    |
| [`measure_active`](#qiskit.circuit.QuantumCircuit.measure_active "qiskit.circuit.QuantumCircuit.measure_active")(\[inplace])                                                          | Adds measurement to all non-idle qubits.                                                                                            |
| [`measure_all`](#qiskit.circuit.QuantumCircuit.measure_all "qiskit.circuit.QuantumCircuit.measure_all")(\[inplace])                                                                   | Adds measurement to all qubits.                                                                                                     |
| [`ms`](#qiskit.circuit.QuantumCircuit.ms "qiskit.circuit.QuantumCircuit.ms")(theta, qubits)                                                                                           | Apply [`MSGate`](qiskit.circuit.library.MSGate "qiskit.circuit.library.MSGate").                                                    |
| [`num_connected_components`](#qiskit.circuit.QuantumCircuit.num_connected_components "qiskit.circuit.QuantumCircuit.num_connected_components")(\[unitary\_only])                      | How many non-entangled subcircuits can the circuit be factored to.                                                                  |
| [`num_nonlocal_gates`](#qiskit.circuit.QuantumCircuit.num_nonlocal_gates "qiskit.circuit.QuantumCircuit.num_nonlocal_gates")()                                                        | Return number of non-local gates (i.e.                                                                                              |
| [`num_tensor_factors`](#qiskit.circuit.QuantumCircuit.num_tensor_factors "qiskit.circuit.QuantumCircuit.num_tensor_factors")()                                                        | Computes the number of tensor factors in the unitary (quantum) part of the circuit only.                                            |
| [`num_unitary_factors`](#qiskit.circuit.QuantumCircuit.num_unitary_factors "qiskit.circuit.QuantumCircuit.num_unitary_factors")()                                                     | Computes the number of tensor factors in the unitary (quantum) part of the circuit only.                                            |
| [`p`](#qiskit.circuit.QuantumCircuit.p "qiskit.circuit.QuantumCircuit.p")(theta, qubit)                                                                                               | Apply [`PhaseGate`](qiskit.circuit.library.PhaseGate "qiskit.circuit.library.PhaseGate").                                           |
| [`pauli`](#qiskit.circuit.QuantumCircuit.pauli "qiskit.circuit.QuantumCircuit.pauli")(pauli\_string, qubits)                                                                          | Apply [`PauliGate`](qiskit.circuit.library.PauliGate "qiskit.circuit.library.PauliGate").                                           |
| [`power`](#qiskit.circuit.QuantumCircuit.power "qiskit.circuit.QuantumCircuit.power")(power\[, matrix\_power])                                                                        | Raise this circuit to the power of `power`.                                                                                         |
| [`qasm`](#qiskit.circuit.QuantumCircuit.qasm "qiskit.circuit.QuantumCircuit.qasm")(\[formatted, filename, encoding])                                                                  | Return OpenQASM string.                                                                                                             |
| [`qbit_argument_conversion`](#qiskit.circuit.QuantumCircuit.qbit_argument_conversion "qiskit.circuit.QuantumCircuit.qbit_argument_conversion")(qubit\_representation)                 | Converts several qubit representations (such as indexes, range, etc.) into a list of qubits.                                        |
| [`qubit_duration`](#qiskit.circuit.QuantumCircuit.qubit_duration "qiskit.circuit.QuantumCircuit.qubit_duration")(\*qubits)                                                            | Return the duration between the start and stop time of the first and last instructions, excluding delays, over the supplied qubits. |
| [`qubit_start_time`](#qiskit.circuit.QuantumCircuit.qubit_start_time "qiskit.circuit.QuantumCircuit.qubit_start_time")(\*qubits)                                                      | Return the start time of the first instruction, excluding delays, over the supplied qubits.                                         |
| [`qubit_stop_time`](#qiskit.circuit.QuantumCircuit.qubit_stop_time "qiskit.circuit.QuantumCircuit.qubit_stop_time")(\*qubits)                                                         | Return the stop time of the last instruction, excluding delays, over the supplied qubits.                                           |
| [`r`](#qiskit.circuit.QuantumCircuit.r "qiskit.circuit.QuantumCircuit.r")(theta, phi, qubit)                                                                                          | Apply [`RGate`](qiskit.circuit.library.RGate "qiskit.circuit.library.RGate").                                                       |
| [`rcccx`](#qiskit.circuit.QuantumCircuit.rcccx "qiskit.circuit.QuantumCircuit.rcccx")(control\_qubit1, control\_qubit2, …)                                                            | Apply [`RC3XGate`](qiskit.circuit.library.RC3XGate "qiskit.circuit.library.RC3XGate").                                              |
| [`rccx`](#qiskit.circuit.QuantumCircuit.rccx "qiskit.circuit.QuantumCircuit.rccx")(control\_qubit1, control\_qubit2, …)                                                               | Apply [`RCCXGate`](qiskit.circuit.library.RCCXGate "qiskit.circuit.library.RCCXGate").                                              |
| [`remove_final_measurements`](#qiskit.circuit.QuantumCircuit.remove_final_measurements "qiskit.circuit.QuantumCircuit.remove_final_measurements")(\[inplace])                         | Removes final measurement on all qubits if they are present.                                                                        |
| [`repeat`](#qiskit.circuit.QuantumCircuit.repeat "qiskit.circuit.QuantumCircuit.repeat")(reps)                                                                                        | Repeat this circuit `reps` times.                                                                                                   |
| [`reset`](#qiskit.circuit.QuantumCircuit.reset "qiskit.circuit.QuantumCircuit.reset")(qubit)                                                                                          | Reset q.                                                                                                                            |
| [`reverse_bits`](#qiskit.circuit.QuantumCircuit.reverse_bits "qiskit.circuit.QuantumCircuit.reverse_bits")()                                                                          | Return a circuit with the opposite order of wires.                                                                                  |
| [`reverse_ops`](#qiskit.circuit.QuantumCircuit.reverse_ops "qiskit.circuit.QuantumCircuit.reverse_ops")()                                                                             | Reverse the circuit by reversing the order of instructions.                                                                         |
| [`rv`](#qiskit.circuit.QuantumCircuit.rv "qiskit.circuit.QuantumCircuit.rv")(vx, vy, vz, qubit)                                                                                       | Apply [`RVGate`](qiskit.circuit.library.RVGate "qiskit.circuit.library.RVGate").                                                    |
| [`rx`](#qiskit.circuit.QuantumCircuit.rx "qiskit.circuit.QuantumCircuit.rx")(theta, qubit\[, label])                                                                                  | Apply [`RXGate`](qiskit.circuit.library.RXGate "qiskit.circuit.library.RXGate").                                                    |
| [`rxx`](#qiskit.circuit.QuantumCircuit.rxx "qiskit.circuit.QuantumCircuit.rxx")(theta, qubit1, qubit2)                                                                                | Apply [`RXXGate`](qiskit.circuit.library.RXXGate "qiskit.circuit.library.RXXGate").                                                 |
| [`ry`](#qiskit.circuit.QuantumCircuit.ry "qiskit.circuit.QuantumCircuit.ry")(theta, qubit\[, label])                                                                                  | Apply [`RYGate`](qiskit.circuit.library.RYGate "qiskit.circuit.library.RYGate").                                                    |
| [`ryy`](#qiskit.circuit.QuantumCircuit.ryy "qiskit.circuit.QuantumCircuit.ryy")(theta, qubit1, qubit2)                                                                                | Apply [`RYYGate`](qiskit.circuit.library.RYYGate "qiskit.circuit.library.RYYGate").                                                 |
| [`rz`](#qiskit.circuit.QuantumCircuit.rz "qiskit.circuit.QuantumCircuit.rz")(phi, qubit)                                                                                              | Apply [`RZGate`](qiskit.circuit.library.RZGate "qiskit.circuit.library.RZGate").                                                    |
| [`rzx`](#qiskit.circuit.QuantumCircuit.rzx "qiskit.circuit.QuantumCircuit.rzx")(theta, qubit1, qubit2)                                                                                | Apply [`RZXGate`](qiskit.circuit.library.RZXGate "qiskit.circuit.library.RZXGate").                                                 |
| [`rzz`](#qiskit.circuit.QuantumCircuit.rzz "qiskit.circuit.QuantumCircuit.rzz")(theta, qubit1, qubit2)                                                                                | Apply [`RZZGate`](qiskit.circuit.library.RZZGate "qiskit.circuit.library.RZZGate").                                                 |
| [`s`](#qiskit.circuit.QuantumCircuit.s "qiskit.circuit.QuantumCircuit.s")(qubit)                                                                                                      | Apply [`SGate`](qiskit.circuit.library.SGate "qiskit.circuit.library.SGate").                                                       |
| [`save_amplitudes`](#qiskit.circuit.QuantumCircuit.save_amplitudes "qiskit.circuit.QuantumCircuit.save_amplitudes")(params\[, label, pershot, …])                                     | Save complex statevector amplitudes.                                                                                                |
| [`save_amplitudes_squared`](#qiskit.circuit.QuantumCircuit.save_amplitudes_squared "qiskit.circuit.QuantumCircuit.save_amplitudes_squared")(params\[, label, …])                      | Save squared statevector amplitudes (probabilities).                                                                                |
| [`save_density_matrix`](#qiskit.circuit.QuantumCircuit.save_density_matrix "qiskit.circuit.QuantumCircuit.save_density_matrix")(\[qubits, label, …])                                  | Save the current simulator quantum state as a density matrix.                                                                       |
| [`save_expectation_value`](#qiskit.circuit.QuantumCircuit.save_expectation_value "qiskit.circuit.QuantumCircuit.save_expectation_value")(operator, qubits\[, …])                      | Save the expectation value of a Hermitian operator.                                                                                 |
| [`save_expectation_value_variance`](#qiskit.circuit.QuantumCircuit.save_expectation_value_variance "qiskit.circuit.QuantumCircuit.save_expectation_value_variance")(operator, qubits) | Save the expectation value of a Hermitian operator.                                                                                 |
| [`save_matrix_product_state`](#qiskit.circuit.QuantumCircuit.save_matrix_product_state "qiskit.circuit.QuantumCircuit.save_matrix_product_state")(\[label, pershot, …])               | Save the current simulator quantum state as a matrix product state.                                                                 |
| [`save_probabilities`](#qiskit.circuit.QuantumCircuit.save_probabilities "qiskit.circuit.QuantumCircuit.save_probabilities")(\[qubits, label, …])                                     | Save measurement outcome probabilities vector.                                                                                      |
| [`save_probabilities_dict`](#qiskit.circuit.QuantumCircuit.save_probabilities_dict "qiskit.circuit.QuantumCircuit.save_probabilities_dict")(\[qubits, label, …])                      | Save measurement outcome probabilities vector.                                                                                      |
| [`save_stabilizer`](#qiskit.circuit.QuantumCircuit.save_stabilizer "qiskit.circuit.QuantumCircuit.save_stabilizer")(\[label, pershot, conditional])                                   | Save the current stabilizer simulator quantum state as a Clifford.                                                                  |
| [`save_state`](#qiskit.circuit.QuantumCircuit.save_state "qiskit.circuit.QuantumCircuit.save_state")(\[label, pershot, conditional])                                                  | Save the current simulator quantum state.                                                                                           |
| [`save_statevector`](#qiskit.circuit.QuantumCircuit.save_statevector "qiskit.circuit.QuantumCircuit.save_statevector")(\[label, pershot, conditional])                                | Save the current simulator quantum state as a statevector.                                                                          |
| [`save_statevector_dict`](#qiskit.circuit.QuantumCircuit.save_statevector_dict "qiskit.circuit.QuantumCircuit.save_statevector_dict")(\[label, pershot, …])                           | Save the current simulator quantum state as a statevector as a dict.                                                                |
| [`save_superop`](#qiskit.circuit.QuantumCircuit.save_superop "qiskit.circuit.QuantumCircuit.save_superop")(\[label, pershot])                                                         | Save the current state of the superop simulator.                                                                                    |
| [`save_unitary`](#qiskit.circuit.QuantumCircuit.save_unitary "qiskit.circuit.QuantumCircuit.save_unitary")(\[label, pershot])                                                         | Save the current state of the unitary simulator.                                                                                    |
| [`sdg`](#qiskit.circuit.QuantumCircuit.sdg "qiskit.circuit.QuantumCircuit.sdg")(qubit)                                                                                                | Apply [`SdgGate`](qiskit.circuit.library.SdgGate "qiskit.circuit.library.SdgGate").                                                 |
| [`set_density_matrix`](#qiskit.circuit.QuantumCircuit.set_density_matrix "qiskit.circuit.QuantumCircuit.set_density_matrix")(state)                                                   | Set the density matrix state of the simulator.                                                                                      |
| [`set_matrix_product_state`](#qiskit.circuit.QuantumCircuit.set_matrix_product_state "qiskit.circuit.QuantumCircuit.set_matrix_product_state")(state)                                 | Set the matrix product state of the simulator.                                                                                      |
| [`set_stabilizer`](#qiskit.circuit.QuantumCircuit.set_stabilizer "qiskit.circuit.QuantumCircuit.set_stabilizer")(state)                                                               | Set the Clifford stabilizer state of the simulator.                                                                                 |
| [`set_statevector`](#qiskit.circuit.QuantumCircuit.set_statevector "qiskit.circuit.QuantumCircuit.set_statevector")(state)                                                            | Set the statevector state of the simulator.                                                                                         |
| [`set_superop`](#qiskit.circuit.QuantumCircuit.set_superop "qiskit.circuit.QuantumCircuit.set_superop")(state)                                                                        | Set the superop state of the simulator.                                                                                             |
| [`set_unitary`](#qiskit.circuit.QuantumCircuit.set_unitary "qiskit.circuit.QuantumCircuit.set_unitary")(state)                                                                        | Set the state state of the simulator.                                                                                               |
| [`size`](#qiskit.circuit.QuantumCircuit.size "qiskit.circuit.QuantumCircuit.size")()                                                                                                  | Returns total number of gate operations in circuit.                                                                                 |
| [`snapshot`](#qiskit.circuit.QuantumCircuit.snapshot "qiskit.circuit.QuantumCircuit.snapshot")(label\[, snapshot\_type, qubits, params])                                              | Take a statevector snapshot of the internal simulator representation.                                                               |
| [`snapshot_density_matrix`](#qiskit.circuit.QuantumCircuit.snapshot_density_matrix "qiskit.circuit.QuantumCircuit.snapshot_density_matrix")(label\[, qubits])                         | Take a density matrix snapshot of simulator state.                                                                                  |
| [`snapshot_expectation_value`](#qiskit.circuit.QuantumCircuit.snapshot_expectation_value "qiskit.circuit.QuantumCircuit.snapshot_expectation_value")(label, op, qubits)               | Take a snapshot of expectation value \<O> of an Operator.                                                                           |
| [`snapshot_probabilities`](#qiskit.circuit.QuantumCircuit.snapshot_probabilities "qiskit.circuit.QuantumCircuit.snapshot_probabilities")(label, qubits\[, variance])                  | Take a probability snapshot of the simulator state.                                                                                 |
| [`snapshot_stabilizer`](#qiskit.circuit.QuantumCircuit.snapshot_stabilizer "qiskit.circuit.QuantumCircuit.snapshot_stabilizer")(label)                                                | Take a stabilizer snapshot of the simulator state.                                                                                  |
| [`snapshot_statevector`](#qiskit.circuit.QuantumCircuit.snapshot_statevector "qiskit.circuit.QuantumCircuit.snapshot_statevector")(label)                                             | Take a statevector snapshot of the simulator state.                                                                                 |
| [`squ`](#qiskit.circuit.QuantumCircuit.squ "qiskit.circuit.QuantumCircuit.squ")(unitary\_matrix, qubit\[, mode, …])                                                                   | Decompose an arbitrary 2\*2 unitary into three rotation gates.                                                                      |
| [`swap`](#qiskit.circuit.QuantumCircuit.swap "qiskit.circuit.QuantumCircuit.swap")(qubit1, qubit2)                                                                                    | Apply [`SwapGate`](qiskit.circuit.library.SwapGate "qiskit.circuit.library.SwapGate").                                              |
| [`sx`](#qiskit.circuit.QuantumCircuit.sx "qiskit.circuit.QuantumCircuit.sx")(qubit)                                                                                                   | Apply [`SXGate`](qiskit.circuit.library.SXGate "qiskit.circuit.library.SXGate").                                                    |
| [`sxdg`](#qiskit.circuit.QuantumCircuit.sxdg "qiskit.circuit.QuantumCircuit.sxdg")(qubit)                                                                                             | Apply [`SXdgGate`](qiskit.circuit.library.SXdgGate "qiskit.circuit.library.SXdgGate").                                              |
| [`t`](#qiskit.circuit.QuantumCircuit.t "qiskit.circuit.QuantumCircuit.t")(qubit)                                                                                                      | Apply [`TGate`](qiskit.circuit.library.TGate "qiskit.circuit.library.TGate").                                                       |
| [`tdg`](#qiskit.circuit.QuantumCircuit.tdg "qiskit.circuit.QuantumCircuit.tdg")(qubit)                                                                                                | Apply [`TdgGate`](qiskit.circuit.library.TdgGate "qiskit.circuit.library.TdgGate").                                                 |
| [`tensor`](#qiskit.circuit.QuantumCircuit.tensor "qiskit.circuit.QuantumCircuit.tensor")(other\[, inplace])                                                                           | Tensor `self` with `other`.                                                                                                         |
| [`to_gate`](#qiskit.circuit.QuantumCircuit.to_gate "qiskit.circuit.QuantumCircuit.to_gate")(\[parameter\_map, label])                                                                 | Create a Gate out of this circuit.                                                                                                  |
| [`to_instruction`](#qiskit.circuit.QuantumCircuit.to_instruction "qiskit.circuit.QuantumCircuit.to_instruction")(\[parameter\_map, label])                                            | Create an Instruction out of this circuit.                                                                                          |
| [`toffoli`](#qiskit.circuit.QuantumCircuit.toffoli "qiskit.circuit.QuantumCircuit.toffoli")(control\_qubit1, control\_qubit2, …)                                                      | Apply [`CCXGate`](qiskit.circuit.library.CCXGate "qiskit.circuit.library.CCXGate").                                                 |
| [`u`](#qiskit.circuit.QuantumCircuit.u "qiskit.circuit.QuantumCircuit.u")(theta, phi, lam, qubit)                                                                                     | Apply [`UGate`](qiskit.circuit.library.UGate "qiskit.circuit.library.UGate").                                                       |
| [`u1`](#qiskit.circuit.QuantumCircuit.u1 "qiskit.circuit.QuantumCircuit.u1")(theta, qubit)                                                                                            | Apply [`U1Gate`](qiskit.circuit.library.U1Gate "qiskit.circuit.library.U1Gate").                                                    |
| [`u2`](#qiskit.circuit.QuantumCircuit.u2 "qiskit.circuit.QuantumCircuit.u2")(phi, lam, qubit)                                                                                         | Apply [`U2Gate`](qiskit.circuit.library.U2Gate "qiskit.circuit.library.U2Gate").                                                    |
| [`u3`](#qiskit.circuit.QuantumCircuit.u3 "qiskit.circuit.QuantumCircuit.u3")(theta, phi, lam, qubit)                                                                                  | Apply [`U3Gate`](qiskit.circuit.library.U3Gate "qiskit.circuit.library.U3Gate").                                                    |
| [`uc`](#qiskit.circuit.QuantumCircuit.uc "qiskit.circuit.QuantumCircuit.uc")(gate\_list, q\_controls, q\_target\[, …])                                                                | Attach a uniformly controlled gates (also called multiplexed gates) to a circuit.                                                   |
| [`ucrx`](#qiskit.circuit.QuantumCircuit.ucrx "qiskit.circuit.QuantumCircuit.ucrx")(angle\_list, q\_controls, q\_target)                                                               | Attach a uniformly controlled (also called multiplexed) Rx rotation gate to a circuit.                                              |
| [`ucry`](#qiskit.circuit.QuantumCircuit.ucry "qiskit.circuit.QuantumCircuit.ucry")(angle\_list, q\_controls, q\_target)                                                               | Attach a uniformly controlled (also called multiplexed) Ry rotation gate to a circuit.                                              |
| [`ucrz`](#qiskit.circuit.QuantumCircuit.ucrz "qiskit.circuit.QuantumCircuit.ucrz")(angle\_list, q\_controls, q\_target)                                                               | Attach a uniformly controlled (also called multiplexed gates) Rz rotation gate to a circuit.                                        |
| [`unitary`](#qiskit.circuit.QuantumCircuit.unitary "qiskit.circuit.QuantumCircuit.unitary")(obj, qubits\[, label])                                                                    | Apply unitary gate to q.                                                                                                            |
| [`width`](#qiskit.circuit.QuantumCircuit.width "qiskit.circuit.QuantumCircuit.width")()                                                                                               | Return number of qubits plus clbits in circuit.                                                                                     |
| [`x`](#qiskit.circuit.QuantumCircuit.x "qiskit.circuit.QuantumCircuit.x")(qubit\[, label])                                                                                            | Apply [`XGate`](qiskit.circuit.library.XGate "qiskit.circuit.library.XGate").                                                       |
| [`y`](#qiskit.circuit.QuantumCircuit.y "qiskit.circuit.QuantumCircuit.y")(qubit)                                                                                                      | Apply [`YGate`](qiskit.circuit.library.YGate "qiskit.circuit.library.YGate").                                                       |
| [`z`](#qiskit.circuit.QuantumCircuit.z "qiskit.circuit.QuantumCircuit.z")(qubit)                                                                                                      | Apply [`ZGate`](qiskit.circuit.library.ZGate "qiskit.circuit.library.ZGate").                                                       |

## Attributes

|                                                                                                                  |                                                                              |
| ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| [`ancillas`](#qiskit.circuit.QuantumCircuit.ancillas "qiskit.circuit.QuantumCircuit.ancillas")                   | Returns a list of ancilla bits in the order that the registers were added.   |
| [`calibrations`](#qiskit.circuit.QuantumCircuit.calibrations "qiskit.circuit.QuantumCircuit.calibrations")       | Return calibration dictionary.                                               |
| [`clbits`](#qiskit.circuit.QuantumCircuit.clbits "qiskit.circuit.QuantumCircuit.clbits")                         | Returns a list of classical bits in the order that the registers were added. |
| [`data`](#qiskit.circuit.QuantumCircuit.data "qiskit.circuit.QuantumCircuit.data")                               | Return the circuit data (instructions and context).                          |
| `extension_lib`                                                                                                  |                                                                              |
| [`global_phase`](#qiskit.circuit.QuantumCircuit.global_phase "qiskit.circuit.QuantumCircuit.global_phase")       | Return the global phase of the circuit in radians.                           |
| `header`                                                                                                         |                                                                              |
| `instances`                                                                                                      |                                                                              |
| [`metadata`](#qiskit.circuit.QuantumCircuit.metadata "qiskit.circuit.QuantumCircuit.metadata")                   | The user provided metadata associated with the circuit                       |
| [`num_ancillas`](#qiskit.circuit.QuantumCircuit.num_ancillas "qiskit.circuit.QuantumCircuit.num_ancillas")       | Return the number of ancilla qubits.                                         |
| [`num_clbits`](#qiskit.circuit.QuantumCircuit.num_clbits "qiskit.circuit.QuantumCircuit.num_clbits")             | Return number of classical bits.                                             |
| [`num_parameters`](#qiskit.circuit.QuantumCircuit.num_parameters "qiskit.circuit.QuantumCircuit.num_parameters") | Convenience function to get the number of parameter objects in the circuit.  |
| [`num_qubits`](#qiskit.circuit.QuantumCircuit.num_qubits "qiskit.circuit.QuantumCircuit.num_qubits")             | Return number of qubits.                                                     |
| [`parameters`](#qiskit.circuit.QuantumCircuit.parameters "qiskit.circuit.QuantumCircuit.parameters")             | Convenience function to get the parameters defined in the parameter table.   |
| `prefix`                                                                                                         |                                                                              |
| [`qubits`](#qiskit.circuit.QuantumCircuit.qubits "qiskit.circuit.QuantumCircuit.qubits")                         | Returns a list of quantum bits in the order that the registers were added.   |

### add\_bits

<span id="qiskit.circuit.QuantumCircuit.add_bits" />

`add_bits(bits)`

Add Bits to the circuit.

### add\_calibration

<span id="qiskit.circuit.QuantumCircuit.add_calibration" />

`add_calibration(gate, qubits, schedule, params=None)`

Register a low-level, custom pulse definition for the given gate.

**Parameters**

*   **gate** (*Union\[*[*Gate*](qiskit.circuit.Gate "qiskit.circuit.Gate")*, str]*) – Gate information.
*   **qubits** (*Union\[int, Tuple\[int]]*) – List of qubits to be measured.
*   **schedule** ([*Schedule*](qiskit.pulse.Schedule "qiskit.pulse.Schedule")) – Schedule information.
*   **params** (*Optional\[List\[Union\[float,* [*Parameter*](qiskit.circuit.Parameter "qiskit.circuit.Parameter")*]]]*) – A list of parameters.

**Raises**

**Exception** – if the gate is of type string and params is None.

### add\_register

<span id="qiskit.circuit.QuantumCircuit.add_register" />

`add_register(*regs)`

Add registers.

### ancillas

<span id="qiskit.circuit.QuantumCircuit.ancillas" />

`property ancillas`

Returns a list of ancilla bits in the order that the registers were added.

### append

<span id="qiskit.circuit.QuantumCircuit.append" />

`append(instruction, qargs=None, cargs=None)`

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

`assign_parameters(parameters, inplace=False, param_dict=None)`

Assign parameters to new parameters or values.

The keys of the parameter dictionary must be Parameter instances in the current circuit. The values of the dictionary can either be numeric values or new parameter objects. The values can be assigned to the current circuit object or to a copy of it.

**Parameters**

*   **parameters** (*dict or iterable*) – Either a dictionary or iterable specifying the new parameter values. If a dict, it specifies the mapping from `current_parameter` to `new_parameter`, where `new_parameter` can be a new parameter object or a numeric value. If an iterable, the elements are assigned to the existing parameters in the order they were inserted. You can call `QuantumCircuit.parameters` to check this order.
*   **inplace** (*bool*) – If False, a copy of the circuit with the bound parameters is returned. If True the circuit instance itself is modified.
*   **param\_dict** (*dict*) – Deprecated, use `parameters` instead.

**Raises**

*   **CircuitError** – If parameters is a dict and contains parameters not present in the circuit.
*   **ValueError** – If parameters is a list/array and the length mismatches the number of free parameters in the circuit.

**Returns**

A copy of the circuit with bound parameters, if `inplace` is False, otherwise None.

**Return type**

Optional([QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit"))

## Examples

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

`barrier(*qargs)`

Apply `Barrier`. If qargs is None, applies to all.

### bind\_parameters

<span id="qiskit.circuit.QuantumCircuit.bind_parameters" />

`bind_parameters(values, value_dict=None)`

Assign numeric parameters to values yielding a new circuit.

To assign new Parameter objects or bind the values in-place, without yielding a new circuit, use the [`assign_parameters()`](#qiskit.circuit.QuantumCircuit.assign_parameters "qiskit.circuit.QuantumCircuit.assign_parameters") method.

**Parameters**

*   **values** (*dict or iterable*) – \{parameter: value, …} or \[value1, value2, …]
*   **value\_dict** (*dict*) – Deprecated, use `values` instead.

**Raises**

*   **CircuitError** – If values is a dict and contains parameters not present in the circuit.
*   **TypeError** – If values contains a ParameterExpression.

**Returns**

copy of self with assignment substitution.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### calibrations

<span id="qiskit.circuit.QuantumCircuit.calibrations" />

`property calibrations`

Return calibration dictionary.

**The custom pulse definition of a given gate is of the form**

\{‘gate\_name’: \{(qubits, params): schedule}}

### cast

<span id="qiskit.circuit.QuantumCircuit.cast" />

`static cast(value, _type)`

Best effort to cast value to type. Otherwise, returns the value.

### cbit\_argument\_conversion

<span id="qiskit.circuit.QuantumCircuit.cbit_argument_conversion" />

`cbit_argument_conversion(clbit_representation)`

Converts several classical bit representations (such as indexes, range, etc.) into a list of classical bits.

**Parameters**

**clbit\_representation** (*Object*) – representation to expand

**Returns**

Where each tuple is a classical bit.

**Return type**

List(tuple)

### ccx

<span id="qiskit.circuit.QuantumCircuit.ccx" />

`ccx(control_qubit1, control_qubit2, target_qubit, ctrl_state=None)`

Apply [`CCXGate`](qiskit.circuit.library.CCXGate "qiskit.circuit.library.CCXGate").

### ch

<span id="qiskit.circuit.QuantumCircuit.ch" />

`ch(control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CHGate`](qiskit.circuit.library.CHGate "qiskit.circuit.library.CHGate").

### clbits

<span id="qiskit.circuit.QuantumCircuit.clbits" />

`property clbits`

Returns a list of classical bits in the order that the registers were added.

### cls\_instances

<span id="qiskit.circuit.QuantumCircuit.cls_instances" />

`classmethod cls_instances()`

Return the current number of instances of this class, useful for auto naming.

### cls\_prefix

<span id="qiskit.circuit.QuantumCircuit.cls_prefix" />

`classmethod cls_prefix()`

Return the prefix to use for auto naming.

### cnot

<span id="qiskit.circuit.QuantumCircuit.cnot" />

`cnot(control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CXGate`](qiskit.circuit.library.CXGate "qiskit.circuit.library.CXGate").

### combine

<span id="qiskit.circuit.QuantumCircuit.combine" />

`combine(rhs)`

DEPRECATED - Returns rhs appended to self if self contains compatible registers.

Two circuits are compatible if they contain the same registers or if they contain different registers with unique names. The returned circuit will contain all unique registers between both circuits.

Return self + rhs as a new object.

**Parameters**

**rhs** ([*QuantumCircuit*](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – The quantum circuit to append to the right hand side.

**Returns**

Returns a new QuantumCircuit object

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the rhs circuit is not compatible

### compose

<span id="qiskit.circuit.QuantumCircuit.compose" />

`compose(other, qubits=None, clbits=None, front=False, inplace=False, wrap=False)`

Compose circuit with `other` circuit or instruction, optionally permuting wires.

`other` can be narrower or of equal width to `self`.

**Parameters**

*   **other** ([*qiskit.circuit.Instruction*](qiskit.circuit.Instruction "qiskit.circuit.Instruction")  *or*[*QuantumCircuit*](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit") *or BaseOperator*) – (sub)circuit to compose onto self.
*   **qubits** (*list\[Qubit|int]*) – qubits of self to compose onto.
*   **clbits** (*list\[Clbit|int]*) – clbits of self to compose onto.
*   **front** (*bool*) – If True, front composition will be performed (not implemented yet).
*   **inplace** (*bool*) – If True, modify the object. Otherwise return composed circuit.
*   **wrap** (*bool*) – If True, wraps the other circuit into a gate (or instruction, depending on whether it contains only unitary instructions) before composing it onto self.

**Returns**

the composed circuit (returns None if inplace==True).

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

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

### control

<span id="qiskit.circuit.QuantumCircuit.control" />

`control(num_ctrl_qubits=1, label=None, ctrl_state=None)`

Control this circuit on `num_ctrl_qubits` qubits.

**Parameters**

*   **num\_ctrl\_qubits** (*int*) – The number of control qubits.
*   **label** (*str*) – An optional label to give the controlled operation for visualization.
*   **ctrl\_state** (*str or int*) – The control state in decimal or as a bitstring (e.g. ‘111’). If None, use `2**num_ctrl_qubits - 1`.

**Returns**

The controlled version of this circuit.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**CircuitError** – If the circuit contains a non-unitary operation and cannot be controlled.

### copy

<span id="qiskit.circuit.QuantumCircuit.copy" />

`copy(name=None)`

Copy the circuit.

**Parameters**

**name** (*str*) – name to be given to the copied circuit. If None, then the name stays the same

**Returns**

a deepcopy of the current circuit, with the specified name

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### count\_ops

<span id="qiskit.circuit.QuantumCircuit.count_ops" />

`count_ops()`

Count each operation kind in the circuit.

**Returns**

a breakdown of how many operations of each kind, sorted by amount.

**Return type**

OrderedDict

### cp

<span id="qiskit.circuit.QuantumCircuit.cp" />

`cp(theta, control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CPhaseGate`](qiskit.circuit.library.CPhaseGate "qiskit.circuit.library.CPhaseGate").

### crx

<span id="qiskit.circuit.QuantumCircuit.crx" />

`crx(theta, control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CRXGate`](qiskit.circuit.library.CRXGate "qiskit.circuit.library.CRXGate").

### cry

<span id="qiskit.circuit.QuantumCircuit.cry" />

`cry(theta, control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CRYGate`](qiskit.circuit.library.CRYGate "qiskit.circuit.library.CRYGate").

### crz

<span id="qiskit.circuit.QuantumCircuit.crz" />

`crz(theta, control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CRZGate`](qiskit.circuit.library.CRZGate "qiskit.circuit.library.CRZGate").

### cswap

<span id="qiskit.circuit.QuantumCircuit.cswap" />

`cswap(control_qubit, target_qubit1, target_qubit2, label=None, ctrl_state=None)`

Apply [`CSwapGate`](qiskit.circuit.library.CSwapGate "qiskit.circuit.library.CSwapGate").

### csx

<span id="qiskit.circuit.QuantumCircuit.csx" />

`csx(control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CSXGate`](qiskit.circuit.library.CSXGate "qiskit.circuit.library.CSXGate").

### cu

<span id="qiskit.circuit.QuantumCircuit.cu" />

`cu(theta, phi, lam, gamma, control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CUGate`](qiskit.circuit.library.CUGate "qiskit.circuit.library.CUGate").

### cu1

<span id="qiskit.circuit.QuantumCircuit.cu1" />

`cu1(theta, control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CU1Gate`](qiskit.circuit.library.CU1Gate "qiskit.circuit.library.CU1Gate").

### cu3

<span id="qiskit.circuit.QuantumCircuit.cu3" />

`cu3(theta, phi, lam, control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CU3Gate`](qiskit.circuit.library.CU3Gate "qiskit.circuit.library.CU3Gate").

### cx

<span id="qiskit.circuit.QuantumCircuit.cx" />

`cx(control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CXGate`](qiskit.circuit.library.CXGate "qiskit.circuit.library.CXGate").

### cy

<span id="qiskit.circuit.QuantumCircuit.cy" />

`cy(control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CYGate`](qiskit.circuit.library.CYGate "qiskit.circuit.library.CYGate").

### cz

<span id="qiskit.circuit.QuantumCircuit.cz" />

`cz(control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CZGate`](qiskit.circuit.library.CZGate "qiskit.circuit.library.CZGate").

### data

<span id="qiskit.circuit.QuantumCircuit.data" />

`property data`

Return the circuit data (instructions and context).

**Returns**

a list-like object containing the tuples for the circuit’s data.

Each tuple is in the format `(instruction, qargs, cargs)`, where instruction is an Instruction (or subclass) object, qargs is a list of Qubit objects, and cargs is a list of Clbit objects.

**Return type**

QuantumCircuitData

### dcx

<span id="qiskit.circuit.QuantumCircuit.dcx" />

`dcx(qubit1, qubit2)`

Apply [`DCXGate`](qiskit.circuit.library.DCXGate "qiskit.circuit.library.DCXGate").

### decompose

<span id="qiskit.circuit.QuantumCircuit.decompose" />

`decompose()`

Call a decomposition pass on this circuit, to decompose one level (shallow decompose).

**Returns**

a circuit one level decomposed

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### delay

<span id="qiskit.circuit.QuantumCircuit.delay" />

`delay(duration, qarg=None, unit='dt')`

Apply [`Delay`](qiskit.circuit.Delay "qiskit.circuit.Delay"). If qarg is None, applies to all qubits. When applying to multiple qubits, delays with the same duration will be created.

**Parameters**

*   **duration** (*int or float or* [*ParameterExpression*](qiskit.circuit.ParameterExpression "qiskit.circuit.ParameterExpression")) – duration of the delay.
*   **qarg** (*Object*) – qubit argument to apply this delay.
*   **unit** (*str*) – unit of the duration. Supported units: ‘s’, ‘ms’, ‘us’, ‘ns’, ‘ps’, ‘dt’. Default is `dt`, i.e. integer time unit depending on the target backend.

**Returns**

the attached delay instruction.

**Return type**

qiskit.Instruction

**Raises**

**CircuitError** – if arguments have bad format.

### depth

<span id="qiskit.circuit.QuantumCircuit.depth" />

`depth()`

Return circuit depth (i.e., length of critical path). This does not include compiler or simulator directives such as ‘barrier’ or ‘snapshot’.

**Returns**

Depth of circuit.

**Return type**

int

## Notes

The circuit depth and the DAG depth need not be the same.

### diagonal

<span id="qiskit.circuit.QuantumCircuit.diagonal" />

`diagonal(diag, qubit)`

Attach a diagonal gate to a circuit.

The decomposition is based on Theorem 7 given in “Synthesis of Quantum Logic Circuits” by Shende et al. ([https://arxiv.org/pdf/quant-ph/0406176.pdf](https://arxiv.org/pdf/quant-ph/0406176.pdf)).

**Parameters**

*   **diag** (*list*) – list of the 2^k diagonal entries (for a diagonal gate on k qubits). Must contain at least two entries
*   **qubit** (*QuantumRegister|list*) – list of k qubits the diagonal is acting on (the order of the qubits specifies the computational basis in which the diagonal gate is provided: the first element in diag acts on the state where all the qubits in q are in the state 0, the second entry acts on the state where all the qubits q\[1],…,q\[k-1] are in the state zero and q\[0] is in the state 1, and so on)

**Returns**

the diagonal gate which was attached to the circuit.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the list of the diagonal entries or the qubit list is in bad format; if the number of diagonal entries is not 2^k, where k denotes the number of qubits

### draw

<span id="qiskit.circuit.QuantumCircuit.draw" />

`draw(output=None, scale=None, filename=None, style=None, interactive=False, plot_barriers=True, reverse_bits=False, justify=None, vertical_compression='medium', idle_wires=True, with_layout=True, fold=None, ax=None, initial_state=False, cregbundle=True)`

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

## Example

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

![../\_images/qiskit.circuit.QuantumCircuit\_5\_0.png](/images/api/qiskit/0.28/qiskit.circuit.QuantumCircuit_5_0.png) ![../\_images/qiskit.circuit.QuantumCircuit\_5\_1.png](/images/api/qiskit/0.28/qiskit.circuit.QuantumCircuit_5_1.png)

### ecr

<span id="qiskit.circuit.QuantumCircuit.ecr" />

`ecr(qubit1, qubit2)`

Apply [`ECRGate`](qiskit.circuit.library.ECRGate "qiskit.circuit.library.ECRGate").

### extend

<span id="qiskit.circuit.QuantumCircuit.extend" />

`extend(rhs)`

DEPRECATED - Append QuantumCircuit to the RHS if it contains compatible registers.

Two circuits are compatible if they contain the same registers or if they contain different registers with unique names. The returned circuit will contain all unique registers between both circuits.

Modify and return self.

**Parameters**

**rhs** ([*QuantumCircuit*](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – The quantum circuit to append to the right hand side.

**Returns**

Returns this QuantumCircuit object (which has been modified)

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the rhs circuit is not compatible

### fredkin

<span id="qiskit.circuit.QuantumCircuit.fredkin" />

`fredkin(control_qubit, target_qubit1, target_qubit2)`

Apply [`CSwapGate`](qiskit.circuit.library.CSwapGate "qiskit.circuit.library.CSwapGate").

### from\_qasm\_file

<span id="qiskit.circuit.QuantumCircuit.from_qasm_file" />

`static from_qasm_file(path)`

Take in a QASM file and generate a QuantumCircuit object.

**Parameters**

**path** (*str*) – Path to the file for a QASM program

**Returns**

The QuantumCircuit object for the input QASM

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### from\_qasm\_str

<span id="qiskit.circuit.QuantumCircuit.from_qasm_str" />

`static from_qasm_str(qasm_str)`

Take in a QASM string and generate a QuantumCircuit object.

**Parameters**

**qasm\_str** (*str*) – A QASM program string

**Returns**

The QuantumCircuit object for the input QASM

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### get\_instructions

<span id="qiskit.circuit.QuantumCircuit.get_instructions" />

`get_instructions(name)`

Get instructions matching name.

**Parameters**

**name** (*str*) – The name of instruction to.

**Returns**

list of (instruction, qargs, cargs).

**Return type**

list(tuple)

### global\_phase

<span id="qiskit.circuit.QuantumCircuit.global_phase" />

`property global_phase`

Return the global phase of the circuit in radians.

### h

<span id="qiskit.circuit.QuantumCircuit.h" />

`h(qubit)`

Apply [`HGate`](qiskit.circuit.library.HGate "qiskit.circuit.library.HGate").

### hamiltonian

<span id="qiskit.circuit.QuantumCircuit.hamiltonian" />

`hamiltonian(operator, time, qubits, label=None)`

Apply hamiltonian evolution to qubits.

### has\_register

<span id="qiskit.circuit.QuantumCircuit.has_register" />

`has_register(register)`

Test if this circuit has the register r.

**Parameters**

**register** (*Register*) – a quantum or classical register.

**Returns**

True if the register is contained in this circuit.

**Return type**

bool

### i

<span id="qiskit.circuit.QuantumCircuit.i" />

`i(qubit)`

Apply [`IGate`](qiskit.circuit.library.IGate "qiskit.circuit.library.IGate").

### id

<span id="qiskit.circuit.QuantumCircuit.id" />

`id(qubit)`

Apply [`IGate`](qiskit.circuit.library.IGate "qiskit.circuit.library.IGate").

### initialize

<span id="qiskit.circuit.QuantumCircuit.initialize" />

`initialize(params, qubits=None)`

Initialize qubits in a specific state.

Qubit initialization is done by first resetting the qubits to $|0\rangle$ followed by an state preparing unitary. Both these steps are included in the Initialize instruction.

**Parameters**

*   **params** (*str or list or int*) –

    *   **str: labels of basis states of the Pauli eigenstates Z, X, Y. See**

        `from_label()`. Notice the order of the labels is reversed with respect to the qubit index to be applied to. Example label ‘01’ initializes the qubit zero to |1> and the qubit one to |0>.

    *   list: vector of complex amplitudes to initialize to.

    *   **int: an integer that is used as a bitmap indicating which qubits to initialize**

        to |1>. Example: setting params to 5 would initialize qubit 0 and qubit 2 to |1> and qubit 1 to |0>.

*   **qubits** ([*QuantumRegister*](qiskit.circuit.QuantumRegister "qiskit.circuit.QuantumRegister") *or int*) –

    *   QuantumRegister: A list of qubits to be initialized \[Default: None].
    *   int: Index of qubit to initialized \[Default: None].

**Returns**

a handle to the instruction that was just initialized

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

## Examples

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
q_0: ┤ Initialize(0.70711,-0.70711) ├
     └──────────────────────────────┘
```

**output:**

┌──────────────────────────────┐

**q\_0: ┤ initialize(0.70711,-0.70711) ├**

└──────────────────────────────┘

Initialize from a string two qubits in the state |10>. The order of the labels is reversed with respect to qubit index. More information about labels for basis states are in `from_label()`.

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

**output:**

┌──────────────────┐

**q\_0: ┤0 ├**

│ initialize(0,1) │

**q\_1: ┤1 ├**

└──────────────────┘

Initialize two qubits from an array of complex amplitudes .. jupyter-execute:

```python
import numpy as np
from qiskit import QuantumCircuit

circuit = QuantumCircuit(2)
circuit.initialize([0, 1/np.sqrt(2), -1.j/np.sqrt(2), 0], circuit.qubits)
circuit.draw()
```

**output:**

┌────────────────────────────────────┐

**q\_0: ┤0 ├**

│ initialize(0,0.70711,-0.70711j,0) │

**q\_1: ┤1 ├**

└────────────────────────────────────┘

### inverse

<span id="qiskit.circuit.QuantumCircuit.inverse" />

`inverse()`

Invert (take adjoint of) this circuit.

This is done by recursively inverting all gates.

**Returns**

the inverted circuit

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**CircuitError** – if the circuit cannot be inverted.

## Examples

**input:**

┌───┐

**q\_0: ┤ H ├─────■──────**

└───┘┌────┴─────┐

**q\_1: ─────┤ RX(1.57) ├**

└──────────┘

**output:**

┌───┐

**q\_0: ──────■──────┤ H ├**

┌─────┴─────┐└───┘

**q\_1: ┤ RX(-1.57) ├─────**

└───────────┘

### iso

<span id="qiskit.circuit.QuantumCircuit.iso" />

`iso(isometry, q_input, q_ancillas_for_output, q_ancillas_zero=None, q_ancillas_dirty=None, epsilon=1e-10)`

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

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the array is not an isometry of the correct size corresponding to the provided number of qubits.

### isometry

<span id="qiskit.circuit.QuantumCircuit.isometry" />

`isometry(isometry, q_input, q_ancillas_for_output, q_ancillas_zero=None, q_ancillas_dirty=None, epsilon=1e-10)`

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

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the array is not an isometry of the correct size corresponding to the provided number of qubits.

### iswap

<span id="qiskit.circuit.QuantumCircuit.iswap" />

`iswap(qubit1, qubit2)`

Apply [`iSwapGate`](qiskit.circuit.library.iSwapGate "qiskit.circuit.library.iSwapGate").

### mcp

<span id="qiskit.circuit.QuantumCircuit.mcp" />

`mcp(lam, control_qubits, target_qubit)`

Apply [`MCPhaseGate`](qiskit.circuit.library.MCPhaseGate "qiskit.circuit.library.MCPhaseGate").

### mcrx

<span id="qiskit.circuit.QuantumCircuit.mcrx" />

`mcrx(theta, q_controls, q_target, use_basis_gates=False)`

Apply Multiple-Controlled X rotation gate

**Parameters**

*   **self** ([*QuantumCircuit*](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – The QuantumCircuit object to apply the mcrx gate on.
*   **theta** (*float*) – angle theta
*   **q\_controls** (*list(*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*)*) – The list of control qubits
*   **q\_target** ([*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")) – The target qubit
*   **use\_basis\_gates** (*bool*) – use p, u, cx

**Raises**

**QiskitError** – parameter errors

### mcry

<span id="qiskit.circuit.QuantumCircuit.mcry" />

`mcry(theta, q_controls, q_target, q_ancillae=None, mode=None, use_basis_gates=False)`

Apply Multiple-Controlled Y rotation gate

**Parameters**

*   **self** ([*QuantumCircuit*](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – The QuantumCircuit object to apply the mcry gate on.
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

`mcrz(lam, q_controls, q_target, use_basis_gates=False)`

Apply Multiple-Controlled Z rotation gate

**Parameters**

*   **self** ([*QuantumCircuit*](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – The QuantumCircuit object to apply the mcrz gate on.
*   **lam** (*float*) – angle lambda
*   **q\_controls** (*list(*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*)*) – The list of control qubits
*   **q\_target** ([*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")) – The target qubit
*   **use\_basis\_gates** (*bool*) – use p, u, cx

**Raises**

**QiskitError** – parameter errors

### mct

<span id="qiskit.circuit.QuantumCircuit.mct" />

`mct(control_qubits, target_qubit, ancilla_qubits=None, mode='noancilla')`

Apply [`MCXGate`](qiskit.circuit.library.MCXGate "qiskit.circuit.library.MCXGate").

### mcu1

<span id="qiskit.circuit.QuantumCircuit.mcu1" />

`mcu1(lam, control_qubits, target_qubit)`

Apply `MCU1Gate`.

### mcx

<span id="qiskit.circuit.QuantumCircuit.mcx" />

`mcx(control_qubits, target_qubit, ancilla_qubits=None, mode='noancilla')`

Apply [`MCXGate`](qiskit.circuit.library.MCXGate "qiskit.circuit.library.MCXGate").

The multi-cX gate can be implemented using different techniques, which use different numbers of ancilla qubits and have varying circuit depth. These modes are: - ‘noancilla’: Requires 0 ancilla qubits. - ‘recursion’: Requires 1 ancilla qubit if more than 4 controls are used, otherwise 0. - ‘v-chain’: Requires 2 less ancillas than the number of control qubits. - ‘v-chain-dirty’: Same as for the clean ancillas (but the circuit will be longer).

### measure

<span id="qiskit.circuit.QuantumCircuit.measure" />

`measure(qubit, cbit)`

Measure quantum bit into classical bit (tuples).

**Parameters**

*   **qubit** (*QuantumRegister|list|tuple*) – quantum register
*   **cbit** (*ClassicalRegister|list|tuple*) – classical register

**Returns**

the attached measure instruction.

**Return type**

qiskit.Instruction

**Raises**

**CircuitError** – if qubit is not in this circuit or bad format; if cbit is not in this circuit or not creg.

### measure\_active

<span id="qiskit.circuit.QuantumCircuit.measure_active" />

`measure_active(inplace=True)`

Adds measurement to all non-idle qubits. Creates a new ClassicalRegister with a size equal to the number of non-idle qubits being measured.

Returns a new circuit with measurements if inplace=False.

**Parameters**

**inplace** (*bool*) – All measurements inplace or return new circuit.

**Returns**

Returns circuit with measurements when inplace = False.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### measure\_all

<span id="qiskit.circuit.QuantumCircuit.measure_all" />

`measure_all(inplace=True)`

Adds measurement to all qubits. Creates a new ClassicalRegister with a size equal to the number of qubits being measured.

Returns a new circuit with measurements if inplace=False.

**Parameters**

**inplace** (*bool*) – All measurements inplace or return new circuit.

**Returns**

Returns circuit with measurements when inplace = False.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### metadata

<span id="qiskit.circuit.QuantumCircuit.metadata" />

`property metadata`

The user provided metadata associated with the circuit

The metadata for the circuit is a user provided `dict` of metadata for the circuit. It will not be used to influence the execution or operation of the circuit, but it is expected to be passed between all transforms of the circuit (ie transpilation) and that providers will associate any circuit metadata with the results it returns from execution of that circuit.

### ms

<span id="qiskit.circuit.QuantumCircuit.ms" />

`ms(theta, qubits)`

Apply [`MSGate`](qiskit.circuit.library.MSGate "qiskit.circuit.library.MSGate").

### num\_ancillas

<span id="qiskit.circuit.QuantumCircuit.num_ancillas" />

`property num_ancillas`

Return the number of ancilla qubits.

### num\_clbits

<span id="qiskit.circuit.QuantumCircuit.num_clbits" />

`property num_clbits`

Return number of classical bits.

### num\_connected\_components

<span id="qiskit.circuit.QuantumCircuit.num_connected_components" />

`num_connected_components(unitary_only=False)`

How many non-entangled subcircuits can the circuit be factored to.

**Parameters**

**unitary\_only** (*bool*) – Compute only unitary part of graph.

**Returns**

Number of connected components in circuit.

**Return type**

int

### num\_nonlocal\_gates

<span id="qiskit.circuit.QuantumCircuit.num_nonlocal_gates" />

`num_nonlocal_gates()`

Return number of non-local gates (i.e. involving 2+ qubits).

Conditional nonlocal gates are also included.

### num\_parameters

<span id="qiskit.circuit.QuantumCircuit.num_parameters" />

`property num_parameters`

Convenience function to get the number of parameter objects in the circuit.

### num\_qubits

<span id="qiskit.circuit.QuantumCircuit.num_qubits" />

`property num_qubits`

Return number of qubits.

### num\_tensor\_factors

<span id="qiskit.circuit.QuantumCircuit.num_tensor_factors" />

`num_tensor_factors()`

Computes the number of tensor factors in the unitary (quantum) part of the circuit only.

## Notes

This is here for backwards compatibility, and will be removed in a future release of Qiskit. You should call num\_unitary\_factors instead.

### num\_unitary\_factors

<span id="qiskit.circuit.QuantumCircuit.num_unitary_factors" />

`num_unitary_factors()`

Computes the number of tensor factors in the unitary (quantum) part of the circuit only.

### p

<span id="qiskit.circuit.QuantumCircuit.p" />

`p(theta, qubit)`

Apply [`PhaseGate`](qiskit.circuit.library.PhaseGate "qiskit.circuit.library.PhaseGate").

### parameters

<span id="qiskit.circuit.QuantumCircuit.parameters" />

`property parameters`

Convenience function to get the parameters defined in the parameter table.

### pauli

<span id="qiskit.circuit.QuantumCircuit.pauli" />

`pauli(pauli_string, qubits)`

Apply [`PauliGate`](qiskit.circuit.library.PauliGate "qiskit.circuit.library.PauliGate").

### power

<span id="qiskit.circuit.QuantumCircuit.power" />

`power(power, matrix_power=False)`

Raise this circuit to the power of `power`.

If `power` is a positive integer and `matrix_power` is `False`, this implementation defaults to calling `repeat`. Otherwise, if the circuit is unitary, the matrix is computed to calculate the matrix power.

**Parameters**

*   **power** (*int*) – The power to raise this circuit to.
*   **matrix\_power** (*bool*) – If True, the circuit is converted to a matrix and then the matrix power is computed. If False, and `power` is a positive integer, the implementation defaults to `repeat`.

**Raises**

**CircuitError** – If the circuit needs to be converted to a gate but it is not unitary.

**Returns**

A circuit implementing this circuit raised to the power of `power`.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### qasm

<span id="qiskit.circuit.QuantumCircuit.qasm" />

`qasm(formatted=False, filename=None, encoding=None)`

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

*   [**MissingOptionalLibraryError**](qiskit.aqua.MissingOptionalLibraryError "qiskit.aqua.MissingOptionalLibraryError") – If pygments is not installed and `formatted` is `True`.
*   [**QasmError**](qiskit.qasm.QasmError "qiskit.qasm.QasmError") – If circuit has free parameters.

### qbit\_argument\_conversion

<span id="qiskit.circuit.QuantumCircuit.qbit_argument_conversion" />

`qbit_argument_conversion(qubit_representation)`

Converts several qubit representations (such as indexes, range, etc.) into a list of qubits.

**Parameters**

**qubit\_representation** (*Object*) – representation to expand

**Returns**

Where each tuple is a qubit.

**Return type**

List(tuple)

### qubit\_duration

<span id="qiskit.circuit.QuantumCircuit.qubit_duration" />

`qubit_duration(*qubits)`

Return the duration between the start and stop time of the first and last instructions, excluding delays, over the supplied qubits. Its time unit is `self.unit`.

**Parameters**

**\*qubits** – Qubits within `self` to include.

**Return type**

`float`

**Returns**

Return the duration between the first start and last stop time of non-delay instructions

### qubit\_start\_time

<span id="qiskit.circuit.QuantumCircuit.qubit_start_time" />

`qubit_start_time(*qubits)`

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

`qubit_stop_time(*qubits)`

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

### qubits

<span id="qiskit.circuit.QuantumCircuit.qubits" />

`property qubits`

Returns a list of quantum bits in the order that the registers were added.

### r

<span id="qiskit.circuit.QuantumCircuit.r" />

`r(theta, phi, qubit)`

Apply [`RGate`](qiskit.circuit.library.RGate "qiskit.circuit.library.RGate").

### rcccx

<span id="qiskit.circuit.QuantumCircuit.rcccx" />

`rcccx(control_qubit1, control_qubit2, control_qubit3, target_qubit)`

Apply [`RC3XGate`](qiskit.circuit.library.RC3XGate "qiskit.circuit.library.RC3XGate").

### rccx

<span id="qiskit.circuit.QuantumCircuit.rccx" />

`rccx(control_qubit1, control_qubit2, target_qubit)`

Apply [`RCCXGate`](qiskit.circuit.library.RCCXGate "qiskit.circuit.library.RCCXGate").

### remove\_final\_measurements

<span id="qiskit.circuit.QuantumCircuit.remove_final_measurements" />

`remove_final_measurements(inplace=True)`

Removes final measurement on all qubits if they are present. Deletes the ClassicalRegister that was used to store the values from these measurements if it is idle.

Returns a new circuit without measurements if inplace=False.

**Parameters**

**inplace** (*bool*) – All measurements removed inplace or return new circuit.

**Returns**

Returns circuit with measurements removed when inplace = False.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### repeat

<span id="qiskit.circuit.QuantumCircuit.repeat" />

`repeat(reps)`

Repeat this circuit `reps` times.

**Parameters**

**reps** (*int*) – How often this circuit should be repeated.

**Returns**

A circuit containing `reps` repetitions of this circuit.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### reset

<span id="qiskit.circuit.QuantumCircuit.reset" />

`reset(qubit)`

Reset q.

### reverse\_bits

<span id="qiskit.circuit.QuantumCircuit.reverse_bits" />

`reverse_bits()`

Return a circuit with the opposite order of wires.

The circuit is “vertically” flipped. If a circuit is defined over multiple registers, the resulting circuit will have the same registers but with their order flipped.

This method is useful for converting a circuit written in little-endian convention to the big-endian equivalent, and vice versa.

**Returns**

the circuit with reversed bit order.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

## Examples

**input:**

┌───┐

**q\_0: ┤ H ├─────■──────**

└───┘┌────┴─────┐

**q\_1: ─────┤ RX(1.57) ├**

└──────────┘

**output:**

┌──────────┐

**q\_0: ─────┤ RX(1.57) ├**

┌───┐└────┬─────┘

**q\_1: ┤ H ├─────■──────**

└───┘

### reverse\_ops

<span id="qiskit.circuit.QuantumCircuit.reverse_ops" />

`reverse_ops()`

Reverse the circuit by reversing the order of instructions.

This is done by recursively reversing all instructions. It does not invert (adjoint) any gate.

**Returns**

the reversed circuit.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

## Examples

**input:**

┌───┐

**q\_0: ┤ H ├─────■──────**

└───┘┌────┴─────┐

**q\_1: ─────┤ RX(1.57) ├**

└──────────┘

**output:**

┌───┐

**q\_0: ─────■──────┤ H ├**

┌────┴─────┐└───┘

**q\_1: ┤ RX(1.57) ├─────**

└──────────┘

### rv

<span id="qiskit.circuit.QuantumCircuit.rv" />

`rv(vx, vy, vz, qubit)`

Apply [`RVGate`](qiskit.circuit.library.RVGate "qiskit.circuit.library.RVGate").

### rx

<span id="qiskit.circuit.QuantumCircuit.rx" />

`rx(theta, qubit, label=None)`

Apply [`RXGate`](qiskit.circuit.library.RXGate "qiskit.circuit.library.RXGate").

### rxx

<span id="qiskit.circuit.QuantumCircuit.rxx" />

`rxx(theta, qubit1, qubit2)`

Apply [`RXXGate`](qiskit.circuit.library.RXXGate "qiskit.circuit.library.RXXGate").

### ry

<span id="qiskit.circuit.QuantumCircuit.ry" />

`ry(theta, qubit, label=None)`

Apply [`RYGate`](qiskit.circuit.library.RYGate "qiskit.circuit.library.RYGate").

### ryy

<span id="qiskit.circuit.QuantumCircuit.ryy" />

`ryy(theta, qubit1, qubit2)`

Apply [`RYYGate`](qiskit.circuit.library.RYYGate "qiskit.circuit.library.RYYGate").

### rz

<span id="qiskit.circuit.QuantumCircuit.rz" />

`rz(phi, qubit)`

Apply [`RZGate`](qiskit.circuit.library.RZGate "qiskit.circuit.library.RZGate").

### rzx

<span id="qiskit.circuit.QuantumCircuit.rzx" />

`rzx(theta, qubit1, qubit2)`

Apply [`RZXGate`](qiskit.circuit.library.RZXGate "qiskit.circuit.library.RZXGate").

### rzz

<span id="qiskit.circuit.QuantumCircuit.rzz" />

`rzz(theta, qubit1, qubit2)`

Apply [`RZZGate`](qiskit.circuit.library.RZZGate "qiskit.circuit.library.RZZGate").

### s

<span id="qiskit.circuit.QuantumCircuit.s" />

`s(qubit)`

Apply [`SGate`](qiskit.circuit.library.SGate "qiskit.circuit.library.SGate").

### save\_amplitudes

<span id="qiskit.circuit.QuantumCircuit.save_amplitudes" />

`save_amplitudes(params, label='amplitudes', pershot=False, conditional=False)`

Save complex statevector amplitudes.

**Parameters**

*   **params** (*List\[int] or List\[str]*) – the basis states to return amplitudes for.
*   **label** (*str*) – the key for retrieving saved data from results.
*   **pershot** (*bool*) – if True save a list of amplitudes vectors for each shot of the simulation rather than the a single amplitude vector \[Default: False].
*   **conditional** (*bool*) – if True save the amplitudes vector conditional on the current classical register values \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – if params is invalid for the specified number of qubits.

### save\_amplitudes\_squared

<span id="qiskit.circuit.QuantumCircuit.save_amplitudes_squared" />

`save_amplitudes_squared(params, label='amplitudes_squared', unnormalized=False, pershot=False, conditional=False)`

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

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – if params is invalid for the specified number of qubits.

### save\_density\_matrix

<span id="qiskit.circuit.QuantumCircuit.save_density_matrix" />

`save_density_matrix(qubits=None, label='density_matrix', unnormalized=False, pershot=False, conditional=False)`

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

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### save\_expectation\_value

<span id="qiskit.circuit.QuantumCircuit.save_expectation_value" />

`save_expectation_value(operator, qubits, label='expectation_value', unnormalized=False, pershot=False, conditional=False)`

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

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – if the input operator is invalid or not Hermitian.

<Admonition title="Note" type="note">
  This method appends a `SaveExpectationValue` instruction to the quantum circuit.
</Admonition>

### save\_expectation\_value\_variance

<span id="qiskit.circuit.QuantumCircuit.save_expectation_value_variance" />

`save_expectation_value_variance(operator, qubits, label='expectation_value_variance', unnormalized=False, pershot=False, conditional=False)`

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

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – if the input operator is invalid or not Hermitian.

<Admonition title="Note" type="note">
  This method appends a `SaveExpectationValueVariance` instruction to the quantum circuit.
</Admonition>

### save\_matrix\_product\_state

<span id="qiskit.circuit.QuantumCircuit.save_matrix_product_state" />

`save_matrix_product_state(label='matrix_product_state', pershot=False, conditional=False)`

Save the current simulator quantum state as a matrix product state.

**Parameters**

*   **label** (*str*) – the key for retrieving saved data from results.
*   **pershot** (*bool*) – if True save the mps for each shot of the simulation \[Default: False].
*   **conditional** (*bool*) – if True save pershot data conditional on the current classical register values \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### save\_probabilities

<span id="qiskit.circuit.QuantumCircuit.save_probabilities" />

`save_probabilities(qubits=None, label='probabilities', unnormalized=False, pershot=False, conditional=False)`

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

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### save\_probabilities\_dict

<span id="qiskit.circuit.QuantumCircuit.save_probabilities_dict" />

`save_probabilities_dict(qubits=None, label='probabilities', unnormalized=False, pershot=False, conditional=False)`

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

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### save\_stabilizer

<span id="qiskit.circuit.QuantumCircuit.save_stabilizer" />

`save_stabilizer(label='stabilizer', pershot=False, conditional=False)`

Save the current stabilizer simulator quantum state as a Clifford.

**Parameters**

*   **label** (*str*) – the key for retrieving saved data from results.
*   **pershot** (*bool*) – if True save a list of Cliffords for each shot of the simulation \[Default: False].
*   **conditional** (*bool*) – if True save pershot data conditional on the current classical register values \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

<Admonition title="Note" type="note">
  This instruction is always defined across all qubits in a circuit.
</Admonition>

### save\_state

<span id="qiskit.circuit.QuantumCircuit.save_state" />

`save_state(label=None, pershot=False, conditional=False)`

Save the current simulator quantum state.

**Parameters**

*   **label** (*str or None*) – Optional, the key for retrieving saved data from results. If None the key will be the state type of the simulator.
*   **pershot** (*bool*) – if True save a list of statevectors for each shot of the simulation \[Default: False].
*   **conditional** (*bool*) – if True save pershot data conditional on the current classical register values \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### save\_statevector

<span id="qiskit.circuit.QuantumCircuit.save_statevector" />

`save_statevector(label='statevector', pershot=False, conditional=False)`

Save the current simulator quantum state as a statevector.

**Parameters**

*   **pershot** (*bool*) – if True save a list of statevectors for each shot of the simulation \[Default: False].
*   **label** (*str*) – the key for retrieving saved data from results.
*   **conditional** (*bool*) – if True save pershot data conditional on the current classical register values \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

<Admonition title="Note" type="note">
  This instruction is always defined across all qubits in a circuit.
</Admonition>

### save\_statevector\_dict

<span id="qiskit.circuit.QuantumCircuit.save_statevector_dict" />

`save_statevector_dict(label='statevector', pershot=False, conditional=False)`

Save the current simulator quantum state as a statevector as a dict.

**Parameters**

*   **label** (*str*) – the key for retrieving saved data from results.
*   **pershot** (*bool*) – if True save a list of statevectors for each shot of the simulation \[Default: False].
*   **conditional** (*bool*) – if True save pershot data conditional on the current classical register values \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

<Admonition title="Note" type="note">
  This instruction is always defined across all qubits in a circuit.
</Admonition>

### save\_superop

<span id="qiskit.circuit.QuantumCircuit.save_superop" />

`save_superop(label='superop', pershot=False)`

Save the current state of the superop simulator.

**Parameters**

*   **label** (*str*) – the key for retrieving saved data from results.
*   **pershot** (*bool*) – if True save a list of SuperOp matrices for each shot of the simulation \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

<Admonition title="Note" type="note">
  This instruction is always defined across all qubits in a circuit.
</Admonition>

### save\_unitary

<span id="qiskit.circuit.QuantumCircuit.save_unitary" />

`save_unitary(label='unitary', pershot=False)`

Save the current state of the unitary simulator.

**Parameters**

*   **label** (*str*) – the key for retrieving saved data from results.
*   **pershot** (*bool*) – if True save a list of unitaries for each shot of the simulation \[Default: False].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

<Admonition title="Note" type="note">
  This instruction is always defined across all qubits in a circuit.
</Admonition>

### sdg

<span id="qiskit.circuit.QuantumCircuit.sdg" />

`sdg(qubit)`

Apply [`SdgGate`](qiskit.circuit.library.SdgGate "qiskit.circuit.library.SdgGate").

### set\_density\_matrix

<span id="qiskit.circuit.QuantumCircuit.set_density_matrix" />

`set_density_matrix(state)`

Set the density matrix state of the simulator.

**Parameters**

**state** ([*DensityMatrix*](qiskit.quantum_info.DensityMatrix "qiskit.quantum_info.DensityMatrix")) – a density matrix.

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – If the density matrix is the incorrect size for the current circuit.

### set\_matrix\_product\_state

<span id="qiskit.circuit.QuantumCircuit.set_matrix_product_state" />

`set_matrix_product_state(state)`

Set the matrix product state of the simulator.

**Parameters**

**state** (*Tuple\[List\[Tuple\[np.array\[complex\_t]]]], List\[List\[float]]*) – A matrix\_product\_state.

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – If the structure of the state is incorrect

### set\_stabilizer

<span id="qiskit.circuit.QuantumCircuit.set_stabilizer" />

`set_stabilizer(state)`

Set the Clifford stabilizer state of the simulator.

**Parameters**

**state** ([*Clifford*](qiskit.quantum_info.Clifford "qiskit.quantum_info.Clifford")) – A clifford operator.

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – If the state is the incorrect size for the current circuit.

### set\_statevector

<span id="qiskit.circuit.QuantumCircuit.set_statevector" />

`set_statevector(state)`

Set the statevector state of the simulator.

**Parameters**

**state** ([*Statevector*](qiskit.quantum_info.Statevector "qiskit.quantum_info.Statevector")) – A state matrix.

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – If the state is the incorrect size for the current circuit.

### set\_superop

<span id="qiskit.circuit.QuantumCircuit.set_superop" />

`set_superop(state)`

Set the superop state of the simulator.

**Parameters**

**state** (*QuantumChannel*) – A CPTP quantum channel.

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

*   **ExtensionError** – If the state is the incorrect size for the current circuit.
*   **ExtensionError** – if the input QuantumChannel is not CPTP.

### set\_unitary

<span id="qiskit.circuit.QuantumCircuit.set_unitary" />

`set_unitary(state)`

Set the state state of the simulator.

**Parameters**

**state** ([*Operator*](qiskit.quantum_info.Operator "qiskit.quantum_info.Operator")) – A state matrix.

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

*   **ExtensionError** – If the state is the incorrect size for the current circuit.
*   **ExtensionError** – if the input matrix is not unitary.

### size

<span id="qiskit.circuit.QuantumCircuit.size" />

`size()`

Returns total number of gate operations in circuit.

**Returns**

Total number of gate operations.

**Return type**

int

### snapshot

<span id="qiskit.circuit.QuantumCircuit.snapshot" />

`snapshot(label, snapshot_type='statevector', qubits=None, params=None)`

Take a statevector snapshot of the internal simulator representation. Works on all qubits, and prevents reordering (like barrier). :param label: a snapshot label to report the result :type label: str :param snapshot\_type: the type of the snapshot. :type snapshot\_type: str :param qubits: the qubits to apply snapshot to \[Default: None]. :type qubits: list or None :param params: the parameters for snapshot\_type \[Default: None]. :type params: list or None

**Returns**

with attached command

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – malformed command

### snapshot\_density\_matrix

<span id="qiskit.circuit.QuantumCircuit.snapshot_density_matrix" />

`snapshot_density_matrix(label, qubits=None)`

Take a density matrix snapshot of simulator state.

**Parameters**

*   **label** (*str*) – a snapshot label to report the result
*   **qubits** (*list or None*) – the qubits to apply snapshot to. If None all qubits will be snapshot \[Default: None].

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – if snapshot is invalid.

<Admonition title="Note" type="note">
  This method will be deprecated after the qiskit-aer 0.8 release. It has been superseded by the [`qiskit.providers.aer.library.save_density_matrix()`](qiskit.providers.aer.library.save_density_matrix "qiskit.providers.aer.library.save_density_matrix") circuit method.
</Admonition>

### snapshot\_expectation\_value

<span id="qiskit.circuit.QuantumCircuit.snapshot_expectation_value" />

`snapshot_expectation_value(label, op, qubits, single_shot=False, variance=False)`

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

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – if snapshot is invalid.

<Admonition title="Note" type="note">
  This method will be deprecated after the qiskit-aer 0.8 release. It has been superseded by the [`qiskit.providers.aer.library.save_expectation_value()`](qiskit.providers.aer.library.save_expectation_value "qiskit.providers.aer.library.save_expectation_value") and [`qiskit.providers.aer.library.save_expectation_value_variance()`](qiskit.providers.aer.library.save_expectation_value_variance "qiskit.providers.aer.library.save_expectation_value_variance") circuit methods.
</Admonition>

### snapshot\_probabilities

<span id="qiskit.circuit.QuantumCircuit.snapshot_probabilities" />

`snapshot_probabilities(label, qubits, variance=False)`

Take a probability snapshot of the simulator state.

**Parameters**

*   **label** (*str*) – a snapshot label to report the result
*   **qubits** (*list*) – the qubits to snapshot.
*   **variance** (*bool*) – compute variance of probabilities \[Default: False]

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – if snapshot is invalid.

<Admonition title="Note" type="note">
  This method will be deprecated after the qiskit-aer 0.8 release. It has been superseded by the [`qiskit.providers.aer.library.save_probabilities()`](qiskit.providers.aer.library.save_probabilities "qiskit.providers.aer.library.save_probabilities") and [`qiskit.providers.aer.library.save_probabilities_dict()`](qiskit.providers.aer.library.save_probabilities_dict "qiskit.providers.aer.library.save_probabilities_dict") circuit methods.
</Admonition>

### snapshot\_stabilizer

<span id="qiskit.circuit.QuantumCircuit.snapshot_stabilizer" />

`snapshot_stabilizer(label)`

Take a stabilizer snapshot of the simulator state.

**Parameters**

**label** (*str*) – a snapshot label to report the result.

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – if snapshot is invalid.

**Additional Information:**

This snapshot is always performed on all qubits in a circuit. The number of qubits parameter specifies the size of the instruction as a barrier and should be set to the number of qubits in the circuit.

<Admonition title="Note" type="note">
  This method will be deprecated after the qiskit-aer 0.8 release. It has been superseded by the [`qiskit.providers.aer.library.save_stabilizer()`](qiskit.providers.aer.library.save_stabilizer "qiskit.providers.aer.library.save_stabilizer") circuit method.
</Admonition>

### snapshot\_statevector

<span id="qiskit.circuit.QuantumCircuit.snapshot_statevector" />

`snapshot_statevector(label)`

Take a statevector snapshot of the simulator state.

**Parameters**

**label** (*str*) – a snapshot label to report the result.

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – if snapshot is invalid.

**Additional Information:**

This snapshot is always performed on all qubits in a circuit. The number of qubits parameter specifies the size of the instruction as a barrier and should be set to the number of qubits in the circuit.

<Admonition title="Note" type="note">
  This method will be deprecated after the qiskit-aer 0.8 release. It has been superseded by the [`qiskit.providers.aer.library.save_statevector()`](qiskit.providers.aer.library.save_statevector "qiskit.providers.aer.library.save_statevector") circuit method.
</Admonition>

### squ

<span id="qiskit.circuit.QuantumCircuit.squ" />

`squ(unitary_matrix, qubit, mode='ZYZ', up_to_diagonal=False, *, u=None)`

Decompose an arbitrary 2\*2 unitary into three rotation gates.

Note that the decomposition is up to a global phase shift. (This is a well known decomposition, which can be found for example in Nielsen and Chuang’s book “Quantum computation and quantum information”.)

**Parameters**

*   **unitary\_matrix** (*ndarray*) – 2\*2 unitary (given as a (complex) ndarray).
*   **qubit** (*QuantumRegister | Qubit*) – The qubit which the gate is acting on.
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

<span id="qiskit.circuit.QuantumCircuit.swap" />

`swap(qubit1, qubit2)`

Apply [`SwapGate`](qiskit.circuit.library.SwapGate "qiskit.circuit.library.SwapGate").

### sx

<span id="qiskit.circuit.QuantumCircuit.sx" />

`sx(qubit)`

Apply [`SXGate`](qiskit.circuit.library.SXGate "qiskit.circuit.library.SXGate").

### sxdg

<span id="qiskit.circuit.QuantumCircuit.sxdg" />

`sxdg(qubit)`

Apply [`SXdgGate`](qiskit.circuit.library.SXdgGate "qiskit.circuit.library.SXdgGate").

### t

<span id="qiskit.circuit.QuantumCircuit.t" />

`t(qubit)`

Apply [`TGate`](qiskit.circuit.library.TGate "qiskit.circuit.library.TGate").

### tdg

<span id="qiskit.circuit.QuantumCircuit.tdg" />

`tdg(qubit)`

Apply [`TdgGate`](qiskit.circuit.library.TdgGate "qiskit.circuit.library.TdgGate").

### tensor

<span id="qiskit.circuit.QuantumCircuit.tensor" />

`tensor(other, inplace=False)`

Tensor `self` with `other`.

Remember that in the little-endian convention the leftmost operation will be at the bottom of the circuit. See also \[the docs]\(qiskit.org/documentation/tutorials/circuits/3\_summary\_of\_quantum\_operations.html) for more information.

```python
     ┌────────┐        ┌─────┐          ┌─────┐
q_0: ┤ bottom ├ ⊗ q_0: ┤ top ├  = q_0: ─┤ top ├──
     └────────┘        └─────┘         ┌┴─────┴─┐
                                  q_1: ┤ bottom ├
                                       └────────┘
```

**Parameters**

*   **other** ([*QuantumCircuit*](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – The other circuit to tensor this circuit with.
*   **inplace** (*bool*) – If True, modify the object. Otherwise return composed circuit.

## Examples

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

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### to\_gate

<span id="qiskit.circuit.QuantumCircuit.to_gate" />

`to_gate(parameter_map=None, label=None)`

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

`to_instruction(parameter_map=None, label=None)`

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

`toffoli(control_qubit1, control_qubit2, target_qubit)`

Apply [`CCXGate`](qiskit.circuit.library.CCXGate "qiskit.circuit.library.CCXGate").

### u

<span id="qiskit.circuit.QuantumCircuit.u" />

`u(theta, phi, lam, qubit)`

Apply [`UGate`](qiskit.circuit.library.UGate "qiskit.circuit.library.UGate").

### u1

<span id="qiskit.circuit.QuantumCircuit.u1" />

`u1(theta, qubit)`

Apply [`U1Gate`](qiskit.circuit.library.U1Gate "qiskit.circuit.library.U1Gate").

### u2

<span id="qiskit.circuit.QuantumCircuit.u2" />

`u2(phi, lam, qubit)`

Apply [`U2Gate`](qiskit.circuit.library.U2Gate "qiskit.circuit.library.U2Gate").

### u3

<span id="qiskit.circuit.QuantumCircuit.u3" />

`u3(theta, phi, lam, qubit)`

Apply [`U3Gate`](qiskit.circuit.library.U3Gate "qiskit.circuit.library.U3Gate").

### uc

<span id="qiskit.circuit.QuantumCircuit.uc" />

`uc(gate_list, q_controls, q_target, up_to_diagonal=False)`

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

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the list number of control qubits does not correspond to the provided number of single-qubit unitaries; if an input is of the wrong type

### ucrx

<span id="qiskit.circuit.QuantumCircuit.ucrx" />

`ucrx(angle_list, q_controls, q_target)`

Attach a uniformly controlled (also called multiplexed) Rx rotation gate to a circuit.

The decomposition is base on [https://arxiv.org/pdf/quant-ph/0406176.pdf](https://arxiv.org/pdf/quant-ph/0406176.pdf) by Shende et al.

**Parameters**

*   **angle\_list** (*list*) – list of (real) rotation angles $[a_0,...,a_{2^k-1}]$
*   **q\_controls** (*QuantumRegister|list*) – list of k control qubits (or empty list if no controls). The control qubits are ordered according to their significance in increasing order: For example if `q_controls=[q[0],q[1]]` (with `q = QuantumRegister(2)`), the rotation `Rx(a_0)` is performed if `q[0]` and `q[1]` are in the state zero, the rotation `Rx(a_1)` is performed if `q[0]` is in the state one and `q[1]` is in the state zero, and so on
*   **q\_target** (*QuantumRegister|Qubit*) – target qubit, where we act on with the single-qubit rotation gates

**Returns**

the uniformly controlled rotation gate is attached to the circuit.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the list number of control qubits does not correspond to the provided number of single-qubit unitaries; if an input is of the wrong type

### ucry

<span id="qiskit.circuit.QuantumCircuit.ucry" />

`ucry(angle_list, q_controls, q_target)`

Attach a uniformly controlled (also called multiplexed) Ry rotation gate to a circuit.

The decomposition is base on [https://arxiv.org/pdf/quant-ph/0406176.pdf](https://arxiv.org/pdf/quant-ph/0406176.pdf) by Shende et al.

**Parameters**

*   **angle\_list** (*list\[numbers*) – list of (real) rotation angles $[a_0,...,a_{2^k-1}]$
*   **q\_controls** (*QuantumRegister|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of k control qubits (or empty list if no controls). The control qubits are ordered according to their significance in increasing order: For example if `q_controls=[q[0],q[1]]` (with `q = QuantumRegister(2)`), the rotation `Ry(a_0)` is performed if `q[0]` and `q[1]` are in the state zero, the rotation `Ry(a_1)` is performed if `q[0]` is in the state one and `q[1]` is in the state zero, and so on
*   **q\_target** (*QuantumRegister|Qubit*) – target qubit, where we act on with the single-qubit rotation gates

**Returns**

the uniformly controlled rotation gate is attached to the circuit.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the list number of control qubits does not correspond to the provided number of single-qubit unitaries; if an input is of the wrong type

### ucrz

<span id="qiskit.circuit.QuantumCircuit.ucrz" />

`ucrz(angle_list, q_controls, q_target)`

Attach a uniformly controlled (also called multiplexed gates) Rz rotation gate to a circuit.

The decomposition is base on [https://arxiv.org/pdf/quant-ph/0406176.pdf](https://arxiv.org/pdf/quant-ph/0406176.pdf) by Shende et al.

**Parameters**

*   **angle\_list** (*list\[numbers*) – list of (real) rotation angles \[a\_0,…,a\_\{2^k-1}]
*   **q\_controls** (*QuantumRegister|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of k control qubits (or empty list if no controls). The control qubits are ordered according to their significance in increasing order: For example if q\_controls=\[q\[1],q\[2]] (with q = QuantumRegister(2)), the rotation Rz(a\_0)is performed if q\[1] and q\[2] are in the state zero, the rotation Rz(a\_1) is performed if q\[1] is in the state one and q\[2] is in the state zero, and so on
*   **q\_target** (*QuantumRegister|Qubit*) – target qubit, where we act on with the single-qubit rotation gates

**Returns**

the uniformly controlled rotation gate is attached to the circuit.

**Return type**

[QuantumCircuit](#qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the list number of control qubits does not correspond to the provided number of single-qubit unitaries; if an input is of the wrong type

### unitary

<span id="qiskit.circuit.QuantumCircuit.unitary" />

`unitary(obj, qubits, label=None)`

Apply unitary gate to q.

### width

<span id="qiskit.circuit.QuantumCircuit.width" />

`width()`

Return number of qubits plus clbits in circuit.

**Returns**

Width of circuit.

**Return type**

int

### x

<span id="qiskit.circuit.QuantumCircuit.x" />

`x(qubit, label=None)`

Apply [`XGate`](qiskit.circuit.library.XGate "qiskit.circuit.library.XGate").

### y

<span id="qiskit.circuit.QuantumCircuit.y" />

`y(qubit)`

Apply [`YGate`](qiskit.circuit.library.YGate "qiskit.circuit.library.YGate").

### z

<span id="qiskit.circuit.QuantumCircuit.z" />

`z(qubit)`

Apply [`ZGate`](qiskit.circuit.library.ZGate "qiskit.circuit.library.ZGate").

