---
title: InnerProduct
description: API reference for qiskit.circuit.library.InnerProduct
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.InnerProduct
---

<span id="qiskit-circuit-library-innerproduct" />

# qiskit.circuit.library.InnerProduct

<span id="qiskit.circuit.library.InnerProduct" />

`InnerProduct(num_qubits)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.16/qiskit/circuit/library/boolean_logic/inner_product.py "view source code")

An n\_qubit circuit that computes the inner product of two registers.

Return a circuit to compute the inner product of 2 n-qubit registers.

This implementation uses CZ gates.

**Parameters**

**num\_qubits** (`int`) – width of top and bottom registers (half total circuit width)

**Reference Circuit:**

### \_\_init\_\_

<span id="qiskit.circuit.library.InnerProduct.__init__" />

`__init__(num_qubits)`

Return a circuit to compute the inner product of 2 n-qubit registers.

This implementation uses CZ gates.

**Parameters**

**num\_qubits** (`int`) – width of top and bottom registers (half total circuit width)

**Reference Circuit:**

## Methods

|                                                                                                                                                                                     |                                                                                                                                     |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.circuit.library.InnerProduct.__init__ "qiskit.circuit.library.InnerProduct.__init__")(num\_qubits)                                                             | Return a circuit to compute the inner product of 2 n-qubit registers.                                                               |
| [`add_calibration`](#qiskit.circuit.library.InnerProduct.add_calibration "qiskit.circuit.library.InnerProduct.add_calibration")(gate, qubits, schedule\[, params])                  | Register a low-level, custom pulse definition for the given gate.                                                                   |
| [`add_register`](#qiskit.circuit.library.InnerProduct.add_register "qiskit.circuit.library.InnerProduct.add_register")(\*regs)                                                      | Add registers.                                                                                                                      |
| [`append`](#qiskit.circuit.library.InnerProduct.append "qiskit.circuit.library.InnerProduct.append")(instruction\[, qargs, cargs])                                                  | Append one or more instructions to the end of the circuit, modifying the circuit in place.                                          |
| [`assign_parameters`](#qiskit.circuit.library.InnerProduct.assign_parameters "qiskit.circuit.library.InnerProduct.assign_parameters")(param\_dict\[, inplace])                      | Assign parameters to new parameters or values.                                                                                      |
| [`barrier`](#qiskit.circuit.library.InnerProduct.barrier "qiskit.circuit.library.InnerProduct.barrier")(\*qargs)                                                                    | Apply `Barrier`.                                                                                                                    |
| [`bind_parameters`](#qiskit.circuit.library.InnerProduct.bind_parameters "qiskit.circuit.library.InnerProduct.bind_parameters")(value\_dict)                                        | Assign numeric parameters to values yielding a new circuit.                                                                         |
| [`cast`](#qiskit.circuit.library.InnerProduct.cast "qiskit.circuit.library.InnerProduct.cast")(value, \_type)                                                                       | Best effort to cast value to type.                                                                                                  |
| [`cbit_argument_conversion`](#qiskit.circuit.library.InnerProduct.cbit_argument_conversion "qiskit.circuit.library.InnerProduct.cbit_argument_conversion")(clbit\_representation)   | Converts several classical bit representations (such as indexes, range, etc.) into a list of classical bits.                        |
| [`ccx`](#qiskit.circuit.library.InnerProduct.ccx "qiskit.circuit.library.InnerProduct.ccx")(control\_qubit1, control\_qubit2, target\_qubit)                                        | Apply [`CCXGate`](qiskit.circuit.library.CCXGate "qiskit.circuit.library.CCXGate").                                                 |
| [`ch`](#qiskit.circuit.library.InnerProduct.ch "qiskit.circuit.library.InnerProduct.ch")(control\_qubit, target\_qubit\[, label, …])                                                | Apply [`CHGate`](qiskit.circuit.library.CHGate "qiskit.circuit.library.CHGate").                                                    |
| [`cls_instances`](#qiskit.circuit.library.InnerProduct.cls_instances "qiskit.circuit.library.InnerProduct.cls_instances")()                                                         | Return the current number of instances of this class, useful for auto naming.                                                       |
| [`cls_prefix`](#qiskit.circuit.library.InnerProduct.cls_prefix "qiskit.circuit.library.InnerProduct.cls_prefix")()                                                                  | Return the prefix to use for auto naming.                                                                                           |
| [`cnot`](#qiskit.circuit.library.InnerProduct.cnot "qiskit.circuit.library.InnerProduct.cnot")(control\_qubit, target\_qubit\[, label, …])                                          | Apply [`CXGate`](qiskit.circuit.library.CXGate "qiskit.circuit.library.CXGate").                                                    |
| [`combine`](#qiskit.circuit.library.InnerProduct.combine "qiskit.circuit.library.InnerProduct.combine")(rhs)                                                                        | Append rhs to self if self contains compatible registers.                                                                           |
| [`compose`](#qiskit.circuit.library.InnerProduct.compose "qiskit.circuit.library.InnerProduct.compose")(other\[, qubits, clbits, front, inplace])                                   | Compose circuit with `other` circuit or instruction, optionally permuting wires.                                                    |
| [`control`](#qiskit.circuit.library.InnerProduct.control "qiskit.circuit.library.InnerProduct.control")(\[num\_ctrl\_qubits, label, ctrl\_state])                                   | Control this circuit on `num_ctrl_qubits` qubits.                                                                                   |
| [`copy`](#qiskit.circuit.library.InnerProduct.copy "qiskit.circuit.library.InnerProduct.copy")(\[name])                                                                             | Copy the circuit.                                                                                                                   |
| [`count_ops`](#qiskit.circuit.library.InnerProduct.count_ops "qiskit.circuit.library.InnerProduct.count_ops")()                                                                     | Count each operation kind in the circuit.                                                                                           |
| [`cp`](#qiskit.circuit.library.InnerProduct.cp "qiskit.circuit.library.InnerProduct.cp")(theta, control\_qubit, target\_qubit\[, …])                                                | Apply [`CPhaseGate`](qiskit.circuit.library.CPhaseGate "qiskit.circuit.library.CPhaseGate").                                        |
| [`crx`](#qiskit.circuit.library.InnerProduct.crx "qiskit.circuit.library.InnerProduct.crx")(theta, control\_qubit, target\_qubit\[, …])                                             | Apply [`CRXGate`](qiskit.circuit.library.CRXGate "qiskit.circuit.library.CRXGate").                                                 |
| [`cry`](#qiskit.circuit.library.InnerProduct.cry "qiskit.circuit.library.InnerProduct.cry")(theta, control\_qubit, target\_qubit\[, …])                                             | Apply [`CRYGate`](qiskit.circuit.library.CRYGate "qiskit.circuit.library.CRYGate").                                                 |
| [`crz`](#qiskit.circuit.library.InnerProduct.crz "qiskit.circuit.library.InnerProduct.crz")(theta, control\_qubit, target\_qubit\[, …])                                             | Apply [`CRZGate`](qiskit.circuit.library.CRZGate "qiskit.circuit.library.CRZGate").                                                 |
| [`cswap`](#qiskit.circuit.library.InnerProduct.cswap "qiskit.circuit.library.InnerProduct.cswap")(control\_qubit, target\_qubit1, …\[, …])                                          | Apply [`CSwapGate`](qiskit.circuit.library.CSwapGate "qiskit.circuit.library.CSwapGate").                                           |
| [`csx`](#qiskit.circuit.library.InnerProduct.csx "qiskit.circuit.library.InnerProduct.csx")(control\_qubit, target\_qubit\[, label, …])                                             | Apply [`CSXGate`](qiskit.circuit.library.CSXGate "qiskit.circuit.library.CSXGate").                                                 |
| [`cu`](#qiskit.circuit.library.InnerProduct.cu "qiskit.circuit.library.InnerProduct.cu")(theta, phi, lam, gamma, control\_qubit, …)                                                 | Apply [`CUGate`](qiskit.circuit.library.CUGate "qiskit.circuit.library.CUGate").                                                    |
| [`cu1`](#qiskit.circuit.library.InnerProduct.cu1 "qiskit.circuit.library.InnerProduct.cu1")(theta, control\_qubit, target\_qubit\[, …])                                             | Apply [`CU1Gate`](qiskit.circuit.library.CU1Gate "qiskit.circuit.library.CU1Gate").                                                 |
| [`cu3`](#qiskit.circuit.library.InnerProduct.cu3 "qiskit.circuit.library.InnerProduct.cu3")(theta, phi, lam, control\_qubit, target\_qubit)                                         | Apply [`CU3Gate`](qiskit.circuit.library.CU3Gate "qiskit.circuit.library.CU3Gate").                                                 |
| [`cx`](#qiskit.circuit.library.InnerProduct.cx "qiskit.circuit.library.InnerProduct.cx")(control\_qubit, target\_qubit\[, label, …])                                                | Apply [`CXGate`](qiskit.circuit.library.CXGate "qiskit.circuit.library.CXGate").                                                    |
| [`cy`](#qiskit.circuit.library.InnerProduct.cy "qiskit.circuit.library.InnerProduct.cy")(control\_qubit, target\_qubit\[, label, …])                                                | Apply [`CYGate`](qiskit.circuit.library.CYGate "qiskit.circuit.library.CYGate").                                                    |
| [`cz`](#qiskit.circuit.library.InnerProduct.cz "qiskit.circuit.library.InnerProduct.cz")(control\_qubit, target\_qubit\[, label, …])                                                | Apply [`CZGate`](qiskit.circuit.library.CZGate "qiskit.circuit.library.CZGate").                                                    |
| [`dcx`](#qiskit.circuit.library.InnerProduct.dcx "qiskit.circuit.library.InnerProduct.dcx")(qubit1, qubit2)                                                                         | Apply [`DCXGate`](qiskit.circuit.library.DCXGate "qiskit.circuit.library.DCXGate").                                                 |
| [`decompose`](#qiskit.circuit.library.InnerProduct.decompose "qiskit.circuit.library.InnerProduct.decompose")()                                                                     | Call a decomposition pass on this circuit, to decompose one level (shallow decompose).                                              |
| [`delay`](#qiskit.circuit.library.InnerProduct.delay "qiskit.circuit.library.InnerProduct.delay")(duration\[, qarg, unit])                                                          | Apply [`Delay`](qiskit.circuit.Delay "qiskit.circuit.Delay").                                                                       |
| [`depth`](#qiskit.circuit.library.InnerProduct.depth "qiskit.circuit.library.InnerProduct.depth")()                                                                                 | Return circuit depth (i.e., length of critical path).                                                                               |
| [`diag_gate`](#qiskit.circuit.library.InnerProduct.diag_gate "qiskit.circuit.library.InnerProduct.diag_gate")(diag, qubit)                                                          | Deprecated version of QuantumCircuit.diagonal.                                                                                      |
| [`diagonal`](#qiskit.circuit.library.InnerProduct.diagonal "qiskit.circuit.library.InnerProduct.diagonal")(diag, qubit)                                                             | Attach a diagonal gate to a circuit.                                                                                                |
| [`draw`](#qiskit.circuit.library.InnerProduct.draw "qiskit.circuit.library.InnerProduct.draw")(\[output, scale, filename, style, …])                                                | Draw the quantum circuit.                                                                                                           |
| [`extend`](#qiskit.circuit.library.InnerProduct.extend "qiskit.circuit.library.InnerProduct.extend")(rhs)                                                                           | Append QuantumCircuit to the right hand side if it contains compatible registers.                                                   |
| [`fredkin`](#qiskit.circuit.library.InnerProduct.fredkin "qiskit.circuit.library.InnerProduct.fredkin")(control\_qubit, target\_qubit1, …)                                          | Apply [`CSwapGate`](qiskit.circuit.library.CSwapGate "qiskit.circuit.library.CSwapGate").                                           |
| [`from_qasm_file`](#qiskit.circuit.library.InnerProduct.from_qasm_file "qiskit.circuit.library.InnerProduct.from_qasm_file")(path)                                                  | Take in a QASM file and generate a QuantumCircuit object.                                                                           |
| [`from_qasm_str`](#qiskit.circuit.library.InnerProduct.from_qasm_str "qiskit.circuit.library.InnerProduct.from_qasm_str")(qasm\_str)                                                | Take in a QASM string and generate a QuantumCircuit object.                                                                         |
| [`h`](#qiskit.circuit.library.InnerProduct.h "qiskit.circuit.library.InnerProduct.h")(qubit)                                                                                        | Apply [`HGate`](qiskit.circuit.library.HGate "qiskit.circuit.library.HGate").                                                       |
| [`hamiltonian`](#qiskit.circuit.library.InnerProduct.hamiltonian "qiskit.circuit.library.InnerProduct.hamiltonian")(operator, time, qubits\[, label])                               | Apply hamiltonian evolution to to qubits.                                                                                           |
| [`has_register`](#qiskit.circuit.library.InnerProduct.has_register "qiskit.circuit.library.InnerProduct.has_register")(register)                                                    | Test if this circuit has the register r.                                                                                            |
| [`i`](#qiskit.circuit.library.InnerProduct.i "qiskit.circuit.library.InnerProduct.i")(qubit)                                                                                        | Apply [`IGate`](qiskit.circuit.library.IGate "qiskit.circuit.library.IGate").                                                       |
| [`id`](#qiskit.circuit.library.InnerProduct.id "qiskit.circuit.library.InnerProduct.id")(qubit)                                                                                     | Apply [`IGate`](qiskit.circuit.library.IGate "qiskit.circuit.library.IGate").                                                       |
| [`initialize`](#qiskit.circuit.library.InnerProduct.initialize "qiskit.circuit.library.InnerProduct.initialize")(params, qubits)                                                    | Apply initialize to circuit.                                                                                                        |
| [`inverse`](#qiskit.circuit.library.InnerProduct.inverse "qiskit.circuit.library.InnerProduct.inverse")()                                                                           | Invert (take adjoint of) this circuit.                                                                                              |
| [`iso`](#qiskit.circuit.library.InnerProduct.iso "qiskit.circuit.library.InnerProduct.iso")(isometry, q\_input, q\_ancillas\_for\_output)                                           | Attach an arbitrary isometry from m to n qubits to a circuit.                                                                       |
| [`isometry`](#qiskit.circuit.library.InnerProduct.isometry "qiskit.circuit.library.InnerProduct.isometry")(isometry, q\_input, …\[, …])                                             | Attach an arbitrary isometry from m to n qubits to a circuit.                                                                       |
| [`iswap`](#qiskit.circuit.library.InnerProduct.iswap "qiskit.circuit.library.InnerProduct.iswap")(qubit1, qubit2)                                                                   | Apply [`iSwapGate`](qiskit.circuit.library.iSwapGate "qiskit.circuit.library.iSwapGate").                                           |
| [`mcmt`](#qiskit.circuit.library.InnerProduct.mcmt "qiskit.circuit.library.InnerProduct.mcmt")(gate, control\_qubits, target\_qubits\[, …])                                         | Apply a multi-control, multi-target using a generic gate.                                                                           |
| [`mcp`](#qiskit.circuit.library.InnerProduct.mcp "qiskit.circuit.library.InnerProduct.mcp")(lam, control\_qubits, target\_qubit)                                                    | Apply [`MCPhaseGate`](qiskit.circuit.library.MCPhaseGate "qiskit.circuit.library.MCPhaseGate").                                     |
| [`mcrx`](#qiskit.circuit.library.InnerProduct.mcrx "qiskit.circuit.library.InnerProduct.mcrx")(theta, q\_controls, q\_target\[, …])                                                 | Apply Multiple-Controlled X rotation gate                                                                                           |
| [`mcry`](#qiskit.circuit.library.InnerProduct.mcry "qiskit.circuit.library.InnerProduct.mcry")(theta, q\_controls, q\_target, q\_ancillae)                                          | Apply Multiple-Controlled Y rotation gate                                                                                           |
| [`mcrz`](#qiskit.circuit.library.InnerProduct.mcrz "qiskit.circuit.library.InnerProduct.mcrz")(lam, q\_controls, q\_target\[, …])                                                   | Apply Multiple-Controlled Z rotation gate                                                                                           |
| [`mct`](#qiskit.circuit.library.InnerProduct.mct "qiskit.circuit.library.InnerProduct.mct")(control\_qubits, target\_qubit\[, …])                                                   | Apply [`MCXGate`](qiskit.circuit.library.MCXGate "qiskit.circuit.library.MCXGate").                                                 |
| [`mcu1`](#qiskit.circuit.library.InnerProduct.mcu1 "qiskit.circuit.library.InnerProduct.mcu1")(lam, control\_qubits, target\_qubit)                                                 | Apply `MCU1Gate`.                                                                                                                   |
| [`mcx`](#qiskit.circuit.library.InnerProduct.mcx "qiskit.circuit.library.InnerProduct.mcx")(control\_qubits, target\_qubit\[, …])                                                   | Apply [`MCXGate`](qiskit.circuit.library.MCXGate "qiskit.circuit.library.MCXGate").                                                 |
| [`measure`](#qiskit.circuit.library.InnerProduct.measure "qiskit.circuit.library.InnerProduct.measure")(qubit, cbit)                                                                | Measure quantum bit into classical bit (tuples).                                                                                    |
| [`measure_active`](#qiskit.circuit.library.InnerProduct.measure_active "qiskit.circuit.library.InnerProduct.measure_active")(\[inplace])                                            | Adds measurement to all non-idle qubits.                                                                                            |
| [`measure_all`](#qiskit.circuit.library.InnerProduct.measure_all "qiskit.circuit.library.InnerProduct.measure_all")(\[inplace])                                                     | Adds measurement to all qubits.                                                                                                     |
| [`mirror`](#qiskit.circuit.library.InnerProduct.mirror "qiskit.circuit.library.InnerProduct.mirror")()                                                                              | DEPRECATED: use circuit.reverse\_ops().                                                                                             |
| [`ms`](#qiskit.circuit.library.InnerProduct.ms "qiskit.circuit.library.InnerProduct.ms")(theta, qubits)                                                                             | Apply [`MSGate`](qiskit.circuit.library.MSGate "qiskit.circuit.library.MSGate").                                                    |
| [`num_connected_components`](#qiskit.circuit.library.InnerProduct.num_connected_components "qiskit.circuit.library.InnerProduct.num_connected_components")(\[unitary\_only])        | How many non-entangled subcircuits can the circuit be factored to.                                                                  |
| [`num_nonlocal_gates`](#qiskit.circuit.library.InnerProduct.num_nonlocal_gates "qiskit.circuit.library.InnerProduct.num_nonlocal_gates")()                                          | Return number of non-local gates (i.e.                                                                                              |
| [`num_tensor_factors`](#qiskit.circuit.library.InnerProduct.num_tensor_factors "qiskit.circuit.library.InnerProduct.num_tensor_factors")()                                          | Computes the number of tensor factors in the unitary (quantum) part of the circuit only.                                            |
| [`num_unitary_factors`](#qiskit.circuit.library.InnerProduct.num_unitary_factors "qiskit.circuit.library.InnerProduct.num_unitary_factors")()                                       | Computes the number of tensor factors in the unitary (quantum) part of the circuit only.                                            |
| [`p`](#qiskit.circuit.library.InnerProduct.p "qiskit.circuit.library.InnerProduct.p")(theta, qubit)                                                                                 | Apply [`PhaseGate`](qiskit.circuit.library.PhaseGate "qiskit.circuit.library.PhaseGate").                                           |
| [`power`](#qiskit.circuit.library.InnerProduct.power "qiskit.circuit.library.InnerProduct.power")(power\[, matrix\_power])                                                          | Raise this circuit to the power of `power`.                                                                                         |
| [`qasm`](#qiskit.circuit.library.InnerProduct.qasm "qiskit.circuit.library.InnerProduct.qasm")(\[formatted, filename])                                                              | Return OpenQASM string.                                                                                                             |
| [`qbit_argument_conversion`](#qiskit.circuit.library.InnerProduct.qbit_argument_conversion "qiskit.circuit.library.InnerProduct.qbit_argument_conversion")(qubit\_representation)   | Converts several qubit representations (such as indexes, range, etc.) into a list of qubits.                                        |
| [`qubit_duration`](#qiskit.circuit.library.InnerProduct.qubit_duration "qiskit.circuit.library.InnerProduct.qubit_duration")(\*qubits)                                              | Return the duration between the start and stop time of the first and last instructions, excluding delays, over the supplied qubits. |
| [`qubit_start_time`](#qiskit.circuit.library.InnerProduct.qubit_start_time "qiskit.circuit.library.InnerProduct.qubit_start_time")(\*qubits)                                        | Return the start time of the first instruction, excluding delays, over the supplied qubits.                                         |
| [`qubit_stop_time`](#qiskit.circuit.library.InnerProduct.qubit_stop_time "qiskit.circuit.library.InnerProduct.qubit_stop_time")(\*qubits)                                           | Return the stop time of the last instruction, excluding delays, over the supplied qubits.                                           |
| [`r`](#qiskit.circuit.library.InnerProduct.r "qiskit.circuit.library.InnerProduct.r")(theta, phi, qubit)                                                                            | Apply `RGate`.                                                                                                                      |
| [`rcccx`](#qiskit.circuit.library.InnerProduct.rcccx "qiskit.circuit.library.InnerProduct.rcccx")(control\_qubit1, control\_qubit2, …)                                              | Apply [`RC3XGate`](qiskit.circuit.library.RC3XGate "qiskit.circuit.library.RC3XGate").                                              |
| [`rccx`](#qiskit.circuit.library.InnerProduct.rccx "qiskit.circuit.library.InnerProduct.rccx")(control\_qubit1, control\_qubit2, …)                                                 | Apply [`RCCXGate`](qiskit.circuit.library.RCCXGate "qiskit.circuit.library.RCCXGate").                                              |
| [`remove_final_measurements`](#qiskit.circuit.library.InnerProduct.remove_final_measurements "qiskit.circuit.library.InnerProduct.remove_final_measurements")(\[inplace])           | Removes final measurement on all qubits if they are present.                                                                        |
| [`repeat`](#qiskit.circuit.library.InnerProduct.repeat "qiskit.circuit.library.InnerProduct.repeat")(reps)                                                                          | Repeat this circuit `reps` times.                                                                                                   |
| [`reset`](#qiskit.circuit.library.InnerProduct.reset "qiskit.circuit.library.InnerProduct.reset")(qubit)                                                                            | Reset q.                                                                                                                            |
| [`reverse_bits`](#qiskit.circuit.library.InnerProduct.reverse_bits "qiskit.circuit.library.InnerProduct.reverse_bits")()                                                            | Return a circuit with the opposite order of wires.                                                                                  |
| [`reverse_ops`](#qiskit.circuit.library.InnerProduct.reverse_ops "qiskit.circuit.library.InnerProduct.reverse_ops")()                                                               | Reverse the circuit by reversing the order of instructions.                                                                         |
| [`rx`](#qiskit.circuit.library.InnerProduct.rx "qiskit.circuit.library.InnerProduct.rx")(theta, qubit\[, label])                                                                    | Apply [`RXGate`](qiskit.circuit.library.RXGate "qiskit.circuit.library.RXGate").                                                    |
| [`rxx`](#qiskit.circuit.library.InnerProduct.rxx "qiskit.circuit.library.InnerProduct.rxx")(theta, qubit1, qubit2)                                                                  | Apply [`RXXGate`](qiskit.circuit.library.RXXGate "qiskit.circuit.library.RXXGate").                                                 |
| [`ry`](#qiskit.circuit.library.InnerProduct.ry "qiskit.circuit.library.InnerProduct.ry")(theta, qubit\[, label])                                                                    | Apply [`RYGate`](qiskit.circuit.library.RYGate "qiskit.circuit.library.RYGate").                                                    |
| [`ryy`](#qiskit.circuit.library.InnerProduct.ryy "qiskit.circuit.library.InnerProduct.ryy")(theta, qubit1, qubit2)                                                                  | Apply [`RYYGate`](qiskit.circuit.library.RYYGate "qiskit.circuit.library.RYYGate").                                                 |
| [`rz`](#qiskit.circuit.library.InnerProduct.rz "qiskit.circuit.library.InnerProduct.rz")(phi, qubit)                                                                                | Apply [`RZGate`](qiskit.circuit.library.RZGate "qiskit.circuit.library.RZGate").                                                    |
| [`rzx`](#qiskit.circuit.library.InnerProduct.rzx "qiskit.circuit.library.InnerProduct.rzx")(theta, qubit1, qubit2)                                                                  | Apply [`RZXGate`](qiskit.circuit.library.RZXGate "qiskit.circuit.library.RZXGate").                                                 |
| [`rzz`](#qiskit.circuit.library.InnerProduct.rzz "qiskit.circuit.library.InnerProduct.rzz")(theta, qubit1, qubit2)                                                                  | Apply [`RZZGate`](qiskit.circuit.library.RZZGate "qiskit.circuit.library.RZZGate").                                                 |
| [`s`](#qiskit.circuit.library.InnerProduct.s "qiskit.circuit.library.InnerProduct.s")(qubit)                                                                                        | Apply [`SGate`](qiskit.circuit.library.SGate "qiskit.circuit.library.SGate").                                                       |
| [`sdg`](#qiskit.circuit.library.InnerProduct.sdg "qiskit.circuit.library.InnerProduct.sdg")(qubit)                                                                                  | Apply [`SdgGate`](qiskit.circuit.library.SdgGate "qiskit.circuit.library.SdgGate").                                                 |
| [`size`](#qiskit.circuit.library.InnerProduct.size "qiskit.circuit.library.InnerProduct.size")()                                                                                    | Returns total number of gate operations in circuit.                                                                                 |
| [`snapshot`](#qiskit.circuit.library.InnerProduct.snapshot "qiskit.circuit.library.InnerProduct.snapshot")(label\[, snapshot\_type, qubits, params])                                | Take a statevector snapshot of the internal simulator representation.                                                               |
| [`snapshot_density_matrix`](#qiskit.circuit.library.InnerProduct.snapshot_density_matrix "qiskit.circuit.library.InnerProduct.snapshot_density_matrix")(label\[, qubits])           | Take a density matrix snapshot of simulator state.                                                                                  |
| [`snapshot_expectation_value`](#qiskit.circuit.library.InnerProduct.snapshot_expectation_value "qiskit.circuit.library.InnerProduct.snapshot_expectation_value")(label, op, qubits) | Take a snapshot of expectation value \<O> of an Operator.                                                                           |
| [`snapshot_probabilities`](#qiskit.circuit.library.InnerProduct.snapshot_probabilities "qiskit.circuit.library.InnerProduct.snapshot_probabilities")(label, qubits\[, variance])    | Take a probability snapshot of the simulator state.                                                                                 |
| [`snapshot_stabilizer`](#qiskit.circuit.library.InnerProduct.snapshot_stabilizer "qiskit.circuit.library.InnerProduct.snapshot_stabilizer")(label)                                  | Take a stabilizer snapshot of the simulator state.                                                                                  |
| [`snapshot_statevector`](#qiskit.circuit.library.InnerProduct.snapshot_statevector "qiskit.circuit.library.InnerProduct.snapshot_statevector")(label)                               | Take a statevector snapshot of the simulator state.                                                                                 |
| [`squ`](#qiskit.circuit.library.InnerProduct.squ "qiskit.circuit.library.InnerProduct.squ")(unitary\_matrix, qubit\[, mode, …])                                                     | Decompose an arbitrary 2\*2 unitary into three rotation gates.                                                                      |
| [`swap`](#qiskit.circuit.library.InnerProduct.swap "qiskit.circuit.library.InnerProduct.swap")(qubit1, qubit2)                                                                      | Apply [`SwapGate`](qiskit.circuit.library.SwapGate "qiskit.circuit.library.SwapGate").                                              |
| [`sx`](#qiskit.circuit.library.InnerProduct.sx "qiskit.circuit.library.InnerProduct.sx")(qubit)                                                                                     | Apply [`SXGate`](qiskit.circuit.library.SXGate "qiskit.circuit.library.SXGate").                                                    |
| [`sxdg`](#qiskit.circuit.library.InnerProduct.sxdg "qiskit.circuit.library.InnerProduct.sxdg")(qubit)                                                                               | Apply [`SXdgGate`](qiskit.circuit.library.SXdgGate "qiskit.circuit.library.SXdgGate").                                              |
| [`t`](#qiskit.circuit.library.InnerProduct.t "qiskit.circuit.library.InnerProduct.t")(qubit)                                                                                        | Apply [`TGate`](qiskit.circuit.library.TGate "qiskit.circuit.library.TGate").                                                       |
| [`tdg`](#qiskit.circuit.library.InnerProduct.tdg "qiskit.circuit.library.InnerProduct.tdg")(qubit)                                                                                  | Apply [`TdgGate`](qiskit.circuit.library.TdgGate "qiskit.circuit.library.TdgGate").                                                 |
| [`to_gate`](#qiskit.circuit.library.InnerProduct.to_gate "qiskit.circuit.library.InnerProduct.to_gate")(\[parameter\_map, label])                                                   | Create a Gate out of this circuit.                                                                                                  |
| [`to_instruction`](#qiskit.circuit.library.InnerProduct.to_instruction "qiskit.circuit.library.InnerProduct.to_instruction")(\[parameter\_map])                                     | Create an Instruction out of this circuit.                                                                                          |
| [`toffoli`](#qiskit.circuit.library.InnerProduct.toffoli "qiskit.circuit.library.InnerProduct.toffoli")(control\_qubit1, control\_qubit2, …)                                        | Apply [`CCXGate`](qiskit.circuit.library.CCXGate "qiskit.circuit.library.CCXGate").                                                 |
| [`u`](#qiskit.circuit.library.InnerProduct.u "qiskit.circuit.library.InnerProduct.u")(theta, phi, lam, qubit)                                                                       | Apply [`UGate`](qiskit.circuit.library.UGate "qiskit.circuit.library.UGate").                                                       |
| [`u1`](#qiskit.circuit.library.InnerProduct.u1 "qiskit.circuit.library.InnerProduct.u1")(theta, qubit)                                                                              | Apply [`U1Gate`](qiskit.circuit.library.U1Gate "qiskit.circuit.library.U1Gate").                                                    |
| [`u2`](#qiskit.circuit.library.InnerProduct.u2 "qiskit.circuit.library.InnerProduct.u2")(phi, lam, qubit)                                                                           | Apply [`U2Gate`](qiskit.circuit.library.U2Gate "qiskit.circuit.library.U2Gate").                                                    |
| [`u3`](#qiskit.circuit.library.InnerProduct.u3 "qiskit.circuit.library.InnerProduct.u3")(theta, phi, lam, qubit)                                                                    | Apply [`U3Gate`](qiskit.circuit.library.U3Gate "qiskit.circuit.library.U3Gate").                                                    |
| [`uc`](#qiskit.circuit.library.InnerProduct.uc "qiskit.circuit.library.InnerProduct.uc")(gate\_list, q\_controls, q\_target\[, …])                                                  | Attach a uniformly controlled gates (also called multiplexed gates) to a circuit.                                                   |
| [`ucrx`](#qiskit.circuit.library.InnerProduct.ucrx "qiskit.circuit.library.InnerProduct.ucrx")(angle\_list, q\_controls, q\_target)                                                 | Attach a uniformly controlled (also called multiplexed) Rx rotation gate to a circuit.                                              |
| [`ucry`](#qiskit.circuit.library.InnerProduct.ucry "qiskit.circuit.library.InnerProduct.ucry")(angle\_list, q\_controls, q\_target)                                                 | Attach a uniformly controlled (also called multiplexed) Ry rotation gate to a circuit.                                              |
| [`ucrz`](#qiskit.circuit.library.InnerProduct.ucrz "qiskit.circuit.library.InnerProduct.ucrz")(angle\_list, q\_controls, q\_target)                                                 | Attach a uniformly controlled (also called multiplexed gates) Rz rotation gate to a circuit.                                        |
| [`unitary`](#qiskit.circuit.library.InnerProduct.unitary "qiskit.circuit.library.InnerProduct.unitary")(obj, qubits\[, label])                                                      | Apply unitary gate to q.                                                                                                            |
| [`width`](#qiskit.circuit.library.InnerProduct.width "qiskit.circuit.library.InnerProduct.width")()                                                                                 | Return number of qubits plus clbits in circuit.                                                                                     |
| [`x`](#qiskit.circuit.library.InnerProduct.x "qiskit.circuit.library.InnerProduct.x")(qubit\[, label])                                                                              | Apply [`XGate`](qiskit.circuit.library.XGate "qiskit.circuit.library.XGate").                                                       |
| [`y`](#qiskit.circuit.library.InnerProduct.y "qiskit.circuit.library.InnerProduct.y")(qubit)                                                                                        | Apply [`YGate`](qiskit.circuit.library.YGate "qiskit.circuit.library.YGate").                                                       |
| [`z`](#qiskit.circuit.library.InnerProduct.z "qiskit.circuit.library.InnerProduct.z")(qubit)                                                                                        | Apply [`ZGate`](qiskit.circuit.library.ZGate "qiskit.circuit.library.ZGate").                                                       |

## Attributes

|                                                                                                                              |                                                                              |
| ---------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| [`ancillas`](#qiskit.circuit.library.InnerProduct.ancillas "qiskit.circuit.library.InnerProduct.ancillas")                   | Returns a list of ancilla bits in the order that the registers were added.   |
| [`calibrations`](#qiskit.circuit.library.InnerProduct.calibrations "qiskit.circuit.library.InnerProduct.calibrations")       | Return calibration dictionary.                                               |
| [`clbits`](#qiskit.circuit.library.InnerProduct.clbits "qiskit.circuit.library.InnerProduct.clbits")                         | Returns a list of classical bits in the order that the registers were added. |
| [`data`](#qiskit.circuit.library.InnerProduct.data "qiskit.circuit.library.InnerProduct.data")                               | Return the circuit data (instructions and context).                          |
| `extension_lib`                                                                                                              |                                                                              |
| [`global_phase`](#qiskit.circuit.library.InnerProduct.global_phase "qiskit.circuit.library.InnerProduct.global_phase")       | Return the global phase of the circuit in radians.                           |
| `header`                                                                                                                     |                                                                              |
| `instances`                                                                                                                  |                                                                              |
| [`num_ancillas`](#qiskit.circuit.library.InnerProduct.num_ancillas "qiskit.circuit.library.InnerProduct.num_ancillas")       | Return the number of ancilla qubits.                                         |
| [`num_clbits`](#qiskit.circuit.library.InnerProduct.num_clbits "qiskit.circuit.library.InnerProduct.num_clbits")             | Return number of classical bits.                                             |
| [`num_parameters`](#qiskit.circuit.library.InnerProduct.num_parameters "qiskit.circuit.library.InnerProduct.num_parameters") | Convenience function to get the number of parameter objects in the circuit.  |
| [`num_qubits`](#qiskit.circuit.library.InnerProduct.num_qubits "qiskit.circuit.library.InnerProduct.num_qubits")             | Return number of qubits.                                                     |
| [`parameters`](#qiskit.circuit.library.InnerProduct.parameters "qiskit.circuit.library.InnerProduct.parameters")             | Convenience function to get the parameters defined in the parameter table.   |
| `prefix`                                                                                                                     |                                                                              |
| [`qubits`](#qiskit.circuit.library.InnerProduct.qubits "qiskit.circuit.library.InnerProduct.qubits")                         | Returns a list of quantum bits in the order that the registers were added.   |

### add\_calibration

<span id="qiskit.circuit.library.InnerProduct.add_calibration" />

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

<span id="qiskit.circuit.library.InnerProduct.add_register" />

`add_register(*regs)`

Add registers.

### ancillas

<span id="qiskit.circuit.library.InnerProduct.ancillas" />

`property ancillas`

Returns a list of ancilla bits in the order that the registers were added.

### append

<span id="qiskit.circuit.library.InnerProduct.append" />

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

<span id="qiskit.circuit.library.InnerProduct.assign_parameters" />

`assign_parameters(param_dict, inplace=False)`

Assign parameters to new parameters or values.

The keys of the parameter dictionary must be Parameter instances in the current circuit. The values of the dictionary can either be numeric values or new parameter objects. The values can be assigned to the current circuit object or to a copy of it.

**Parameters**

*   **param\_dict** (*dict*) – A dictionary specifying the mapping from `current_parameter` to `new_parameter`, where `new_parameter` can be a new parameter object or a numeric value.
*   **inplace** (*bool*) – If False, a copy of the circuit with the bound parameters is returned. If True the circuit instance itself is modified.

**Raises**

**CircuitError** – If param\_dict contains parameters not present in the circuit

**Returns**

A copy of the circuit with bound parameters, if `inplace` is True, otherwise None.

**Return type**

Optional([QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit"))

## Examples

```python
>>> from qiskit.circuit import QuantumCircuit, Parameter
>>> circuit = QuantumCircuit(2)
>>> params = [Parameter('A'), Parameter('B'), Parameter('C')]
>>> circuit.ry(params[0], 0)
>>> circuit.crx(params[1], 0, 1)
>>> circuit.draw()
        ┌───────┐
q_0: |0>┤ Ry(A) ├────■────
        └───────┘┌───┴───┐
q_1: |0>─────────┤ Rx(B) ├
                 └───────┘
>>> circuit.assign_parameters({params[0]: params[2]}, inplace=True)
>>> circuit.draw()
        ┌───────┐
q_0: |0>┤ Ry(C) ├────■────
        └───────┘┌───┴───┐
q_1: |0>─────────┤ Rx(B) ├
                 └───────┘
>>> bound_circuit = circuit.assign_parameters({params[1]: 1, params[2]: 2})
>>> bound_circuit.draw()
        ┌───────┐
q_0: |0>┤ Ry(2) ├────■────
        └───────┘┌───┴───┐
q_1: |0>─────────┤ Rx(1) ├
                 └───────┘
>>> bound_circuit.parameters  # this one has no free parameters anymore
set()
>>> circuit.parameters  # the original one is still parameterized
{Parameter(A), Parameter(C)}
```

### barrier

<span id="qiskit.circuit.library.InnerProduct.barrier" />

`barrier(*qargs)`

Apply `Barrier`. If qargs is None, applies to all.

### bind\_parameters

<span id="qiskit.circuit.library.InnerProduct.bind_parameters" />

`bind_parameters(value_dict)`

Assign numeric parameters to values yielding a new circuit.

To assign new Parameter objects or bind the values in-place, without yielding a new circuit, use the [`assign_parameters()`](#qiskit.circuit.library.InnerProduct.assign_parameters "qiskit.circuit.library.InnerProduct.assign_parameters") method.

**Parameters**

**value\_dict** (*dict*) – \{parameter: value, …}

**Raises**

*   **CircuitError** – If value\_dict contains parameters not present in the circuit
*   **TypeError** – If value\_dict contains a ParameterExpression in the values.

**Returns**

copy of self with assignment substitution.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### calibrations

<span id="qiskit.circuit.library.InnerProduct.calibrations" />

`property calibrations`

Return calibration dictionary.

**The custom pulse definition of a given gate is of the form**

\{‘gate\_name’: \{(qubits, params): schedule}}

### cast

<span id="qiskit.circuit.library.InnerProduct.cast" />

`static cast(value, _type)`

Best effort to cast value to type. Otherwise, returns the value.

### cbit\_argument\_conversion

<span id="qiskit.circuit.library.InnerProduct.cbit_argument_conversion" />

`cbit_argument_conversion(clbit_representation)`

Converts several classical bit representations (such as indexes, range, etc.) into a list of classical bits.

**Parameters**

**clbit\_representation** (*Object*) – representation to expand

**Returns**

Where each tuple is a classical bit.

**Return type**

List(tuple)

### ccx

<span id="qiskit.circuit.library.InnerProduct.ccx" />

`ccx(control_qubit1, control_qubit2, target_qubit)`

Apply [`CCXGate`](qiskit.circuit.library.CCXGate "qiskit.circuit.library.CCXGate").

### ch

<span id="qiskit.circuit.library.InnerProduct.ch" />

`ch(control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CHGate`](qiskit.circuit.library.CHGate "qiskit.circuit.library.CHGate").

### clbits

<span id="qiskit.circuit.library.InnerProduct.clbits" />

`property clbits`

Returns a list of classical bits in the order that the registers were added.

### cls\_instances

<span id="qiskit.circuit.library.InnerProduct.cls_instances" />

`classmethod cls_instances()`

Return the current number of instances of this class, useful for auto naming.

### cls\_prefix

<span id="qiskit.circuit.library.InnerProduct.cls_prefix" />

`classmethod cls_prefix()`

Return the prefix to use for auto naming.

### cnot

<span id="qiskit.circuit.library.InnerProduct.cnot" />

`cnot(control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CXGate`](qiskit.circuit.library.CXGate "qiskit.circuit.library.CXGate").

### combine

<span id="qiskit.circuit.library.InnerProduct.combine" />

`combine(rhs)`

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

<span id="qiskit.circuit.library.InnerProduct.compose" />

`compose(other, qubits=None, clbits=None, front=False, inplace=False)`

Compose circuit with `other` circuit or instruction, optionally permuting wires.

`other` can be narrower or of equal width to `self`.

**Parameters**

*   **other** ([*qiskit.circuit.Instruction*](qiskit.circuit.Instruction "qiskit.circuit.Instruction")  *or*[*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit") *or BaseOperator*) – (sub)circuit to compose onto self.
*   **qubits** (*list\[Qubit|int]*) – qubits of self to compose onto.
*   **clbits** (*list\[Clbit|int]*) – clbits of self to compose onto.
*   **front** (*bool*) – If True, front composition will be performed (not implemented yet).
*   **inplace** (*bool*) – If True, modify the object. Otherwise return composed circuit.

**Returns**

the composed circuit (returns None if inplace==True).

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

*   **CircuitError** – if composing on the front.
*   **QiskitError** – if `other` is wider or there are duplicate edge mappings.

## Examples

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

### control

<span id="qiskit.circuit.library.InnerProduct.control" />

`control(num_ctrl_qubits=1, label=None, ctrl_state=None)`

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

<span id="qiskit.circuit.library.InnerProduct.copy" />

`copy(name=None)`

Copy the circuit.

**Parameters**

**name** (*str*) – name to be given to the copied circuit. If None, then the name stays the same

**Returns**

a deepcopy of the current circuit, with the specified name

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### count\_ops

<span id="qiskit.circuit.library.InnerProduct.count_ops" />

`count_ops()`

Count each operation kind in the circuit.

**Returns**

a breakdown of how many operations of each kind, sorted by amount.

**Return type**

OrderedDict

### cp

<span id="qiskit.circuit.library.InnerProduct.cp" />

`cp(theta, control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CPhaseGate`](qiskit.circuit.library.CPhaseGate "qiskit.circuit.library.CPhaseGate").

### crx

<span id="qiskit.circuit.library.InnerProduct.crx" />

`crx(theta, control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CRXGate`](qiskit.circuit.library.CRXGate "qiskit.circuit.library.CRXGate").

### cry

<span id="qiskit.circuit.library.InnerProduct.cry" />

`cry(theta, control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CRYGate`](qiskit.circuit.library.CRYGate "qiskit.circuit.library.CRYGate").

### crz

<span id="qiskit.circuit.library.InnerProduct.crz" />

`crz(theta, control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CRZGate`](qiskit.circuit.library.CRZGate "qiskit.circuit.library.CRZGate").

### cswap

<span id="qiskit.circuit.library.InnerProduct.cswap" />

`cswap(control_qubit, target_qubit1, target_qubit2, label=None, ctrl_state=None)`

Apply [`CSwapGate`](qiskit.circuit.library.CSwapGate "qiskit.circuit.library.CSwapGate").

### csx

<span id="qiskit.circuit.library.InnerProduct.csx" />

`csx(control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CSXGate`](qiskit.circuit.library.CSXGate "qiskit.circuit.library.CSXGate").

### cu

<span id="qiskit.circuit.library.InnerProduct.cu" />

`cu(theta, phi, lam, gamma, control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CUGate`](qiskit.circuit.library.CUGate "qiskit.circuit.library.CUGate").

### cu1

<span id="qiskit.circuit.library.InnerProduct.cu1" />

`cu1(theta, control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CU1Gate`](qiskit.circuit.library.CU1Gate "qiskit.circuit.library.CU1Gate").

### cu3

<span id="qiskit.circuit.library.InnerProduct.cu3" />

`cu3(theta, phi, lam, control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CU3Gate`](qiskit.circuit.library.CU3Gate "qiskit.circuit.library.CU3Gate").

### cx

<span id="qiskit.circuit.library.InnerProduct.cx" />

`cx(control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CXGate`](qiskit.circuit.library.CXGate "qiskit.circuit.library.CXGate").

### cy

<span id="qiskit.circuit.library.InnerProduct.cy" />

`cy(control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CYGate`](qiskit.circuit.library.CYGate "qiskit.circuit.library.CYGate").

### cz

<span id="qiskit.circuit.library.InnerProduct.cz" />

`cz(control_qubit, target_qubit, label=None, ctrl_state=None)`

Apply [`CZGate`](qiskit.circuit.library.CZGate "qiskit.circuit.library.CZGate").

### data

<span id="qiskit.circuit.library.InnerProduct.data" />

`property data`

Return the circuit data (instructions and context).

**Returns**

a list-like object containing the tuples for the circuit’s data.

Each tuple is in the format `(instruction, qargs, cargs)`, where instruction is an Instruction (or subclass) object, qargs is a list of Qubit objects, and cargs is a list of Clbit objects.

**Return type**

QuantumCircuitData

### dcx

<span id="qiskit.circuit.library.InnerProduct.dcx" />

`dcx(qubit1, qubit2)`

Apply [`DCXGate`](qiskit.circuit.library.DCXGate "qiskit.circuit.library.DCXGate").

### decompose

<span id="qiskit.circuit.library.InnerProduct.decompose" />

`decompose()`

Call a decomposition pass on this circuit, to decompose one level (shallow decompose).

**Returns**

a circuit one level decomposed

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### delay

<span id="qiskit.circuit.library.InnerProduct.delay" />

`delay(duration, qarg=None, unit='dt')`

Apply [`Delay`](qiskit.circuit.Delay "qiskit.circuit.Delay"). If qarg is None, applies to all qubits. When applying to multiple qubits, delays with the same duration will be created.

**Parameters**

*   **duration** (*int or float*) – duration of the delay.
*   **qarg** (*Object*) – qubit argument to apply this delay.
*   **unit** (*str*) – unit of the duration. Supported units: ‘s’, ‘ms’, ‘us’, ‘ns’, ‘ps’, ‘dt’. Default is `dt`, i.e. integer time unit depending on the target backend.

**Returns**

the attached delay instruction.

**Return type**

qiskit.Instruction

**Raises**

**CircuitError** – if arguments have bad format.

### depth

<span id="qiskit.circuit.library.InnerProduct.depth" />

`depth()`

Return circuit depth (i.e., length of critical path). This does not include compiler or simulator directives such as ‘barrier’ or ‘snapshot’.

**Returns**

Depth of circuit.

**Return type**

int

## Notes

The circuit depth and the DAG depth need not be the same.

### diag\_gate

<span id="qiskit.circuit.library.InnerProduct.diag_gate" />

`diag_gate(diag, qubit)`

Deprecated version of QuantumCircuit.diagonal.

### diagonal

<span id="qiskit.circuit.library.InnerProduct.diagonal" />

`diagonal(diag, qubit)`

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

<span id="qiskit.circuit.library.InnerProduct.draw" />

`draw(output=None, scale=None, filename=None, style=None, interactive=False, plot_barriers=True, reverse_bits=False, justify=None, vertical_compression='medium', idle_wires=True, with_layout=True, fold=None, ax=None, initial_state=False, cregbundle=True)`

Draw the quantum circuit.

**text**: ASCII art TextDrawing that can be printed in the console.

**latex**: high-quality images compiled via LaTeX.

**latex\_source**: raw uncompiled LaTeX output.

**matplotlib**: images with color rendered purely in Python.

**Parameters**

*   **output** (*str*) – Select the output method to use for drawing the circuit. Valid choices are `text`, `latex`, `latex_source`, or `mpl`. By default the ‘text’ drawer is used unless a user config file has an alternative backend set as the default. If the output kwarg is set, that backend will always be used over the default in a user config file.
*   **scale** (*float*) – scale of image to draw (shrink if \< 1)
*   **filename** (*str*) – file path to save image to
*   **style** (*dict or str*) – dictionary of style or file name of style file. This option is only used by the `mpl` output type. If a str is passed in that is the path to a json file which contains a dictionary of style, then that will be opened, parsed, and used as the input dict. See: [Style Dict Doc](qiskit.circuit.library.ZZFeatureMap#style-dict-circ-doc) for more information on the contents.
*   **interactive** (*bool*) – when set true show the circuit in a new window (for mpl this depends on the matplotlib backend being used supporting this). Note when used with either the text or the latex\_source output type this has no effect and will be silently ignored.
*   **reverse\_bits** (*bool*) – When set to True, reverse the bit order inside registers for the output visualization.
*   **plot\_barriers** (*bool*) – Enable/disable drawing barriers in the output circuit. Defaults to True.
*   **justify** (*string*) – Options are `left`, `right` or `none`. If anything else is supplied it defaults to left justified. It refers to where gates should be placed in the output circuit if there is an option. `none` results in each gate being placed in its own column.
*   **vertical\_compression** (*string*) – `high`, `medium` or `low`. It merges the lines generated by the `text` output so the drawing will take less vertical room. Default is `medium`. Only used by the `text` output, will be silently ignored otherwise.
*   **idle\_wires** (*bool*) – Include idle wires (wires with no circuit elements) in output visualization. Default is True.
*   **with\_layout** (*bool*) – Include layout information, with labels on the physical layout. Default is True.
*   **fold** (*int*) – Sets pagination. It can be disabled using -1. In text, sets the length of the lines. This is useful when the drawing does not fit in the console. If None (default), it will try to guess the console width using `shutil. get_terminal_size()`. However, if running in jupyter, the default line length is set to 80 characters. In `mpl` is the number of (visual) layers before folding. Default is 25.
*   **ax** (*matplotlib.axes.Axes*) – An optional Axes object to be used for the visualization output. If none is specified, a new matplotlib Figure will be created and used. Additionally, if specified, there will be no returned Figure since it is redundant. This is only used when the `output` kwarg is set to use the `mpl` backend. It will be silently ignored with all other outputs.
*   **initial\_state** (*bool*) – Optional. Adds `|0>` in the beginning of the wire. Only used by the `text`, `latex` and `latex_source` outputs. Default: `False`.
*   **cregbundle** (*bool*) – Optional. If set True bundle classical registers. Not used by the `matplotlib` output. Default: `True`.

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

*   **name** (*str*) – The name of the style. The name can be set to ‘iqx’, ‘bw’, or ‘default’. This overrides the setting in the ‘\~/.qiskit/settings.conf’ file.

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

    The color codes to use for each circuit element in the form (gate\_color, text\_color). The default values are:

    ```python
    {
        'u1': ('#FA74A6', '#000000'),
        'u2': ('#FA74A6', '#000000'),
        'u3': ('#FA74A6', '#000000'),
        'id': ('#05BAB6', '#000000'),
        'x': ('#05BAB6', '#000000'),
        'y': ('#05BAB6', '#000000'),
        'z': ('#05BAB6', '#000000'),
        'h': ('#6FA4FF', '#000000'),
        'cx': ('#6FA4FF', '#000000'),
        'cy': ('#6FA4FF', '#000000'),
        'cz': ('#6FA4FF', '#000000'),
        'swap': ('#6FA4FF', '#000000'),
        's': ('#6FA4FF', '#000000'),
        'sdg': ('#6FA4FF', '#000000'),
        'dcx': ('#6FA4FF', '#000000'),
        'iswap': ('#6FA4FF', '#000000'),
        't': ('#BB8BFF', '#000000'),
        'tdg': ('#BB8BFF', '#000000'),
        'r': ('#BB8BFF', '#000000'),
        'rx': ('#BB8BFF', '#000000'),
        'ry': ('#BB8BFF', '#000000'),
        'rz': ('#BB8BFF', '#000000'),
        'rxx': ('#BB8BFF', '#000000'),
        'ryy': ('#BB8BFF', '#000000'),
        'rzx': ('#BB8BFF', '#000000'),
        'reset': ('#000000', #FFFFFF'),
        'target': ('#FFFFFF, '#FFFFFF'),
        'measure': ('#000000', '#FFFFFF'),
        'ccx': ('#BB8BFF', '#000000'),
        'cdcx': ('#BB8BFF', '#000000'),
        'ccdcx': ('#BB8BFF', '#000000'),
        'cswap': ('#BB8BFF', '#000000'),
        'ccswap': ('#BB8BFF', '#000000'),
        'mcx': ('#BB8BFF', '#000000'),
        'mcx_gray': ('#BB8BFF', '#000000),
        'u': ('#BB8BFF', '#000000'),
        'p': ('#BB8BFF', '#000000'),
        'sx': ('#BB8BFF', '#000000'),
        'sxdg': ('#BB8BFF', '#000000')
    }
    ```

    Colors can also be entered without the text color, such as ‘u1’: ‘#FA74A6’, in which case the text color will always be ‘gatetextcolor’. The ‘displaycolor’ dict can contain any number of elements from one to the entire dict above.

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

<span id="qiskit.circuit.library.InnerProduct.extend" />

`extend(rhs)`

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

<span id="qiskit.circuit.library.InnerProduct.fredkin" />

`fredkin(control_qubit, target_qubit1, target_qubit2)`

Apply [`CSwapGate`](qiskit.circuit.library.CSwapGate "qiskit.circuit.library.CSwapGate").

### from\_qasm\_file

<span id="qiskit.circuit.library.InnerProduct.from_qasm_file" />

`static from_qasm_file(path)`

Take in a QASM file and generate a QuantumCircuit object.

**Parameters**

**path** (*str*) – Path to the file for a QASM program

**Returns**

The QuantumCircuit object for the input QASM

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### from\_qasm\_str

<span id="qiskit.circuit.library.InnerProduct.from_qasm_str" />

`static from_qasm_str(qasm_str)`

Take in a QASM string and generate a QuantumCircuit object.

**Parameters**

**qasm\_str** (*str*) – A QASM program string

**Returns**

The QuantumCircuit object for the input QASM

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### global\_phase

<span id="qiskit.circuit.library.InnerProduct.global_phase" />

`property global_phase`

Return the global phase of the circuit in radians.

### h

<span id="qiskit.circuit.library.InnerProduct.h" />

`h(qubit)`

Apply [`HGate`](qiskit.circuit.library.HGate "qiskit.circuit.library.HGate").

### hamiltonian

<span id="qiskit.circuit.library.InnerProduct.hamiltonian" />

`hamiltonian(operator, time, qubits, label=None)`

Apply hamiltonian evolution to to qubits.

### has\_register

<span id="qiskit.circuit.library.InnerProduct.has_register" />

`has_register(register)`

Test if this circuit has the register r.

**Parameters**

**register** (*Register*) – a quantum or classical register.

**Returns**

True if the register is contained in this circuit.

**Return type**

bool

### i

<span id="qiskit.circuit.library.InnerProduct.i" />

`i(qubit)`

Apply [`IGate`](qiskit.circuit.library.IGate "qiskit.circuit.library.IGate").

### id

<span id="qiskit.circuit.library.InnerProduct.id" />

`id(qubit)`

Apply [`IGate`](qiskit.circuit.library.IGate "qiskit.circuit.library.IGate").

### initialize

<span id="qiskit.circuit.library.InnerProduct.initialize" />

`initialize(params, qubits)`

Apply initialize to circuit.

### inverse

<span id="qiskit.circuit.library.InnerProduct.inverse" />

`inverse()`

Invert (take adjoint of) this circuit.

This is done by recursively inverting all gates.

**Returns**

the inverted circuit

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

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

<span id="qiskit.circuit.library.InnerProduct.iso" />

`iso(isometry, q_input, q_ancillas_for_output, q_ancillas_zero=None, q_ancillas_dirty=None)`

Attach an arbitrary isometry from m to n qubits to a circuit. In particular, this allows to attach arbitrary unitaries on n qubits (m=n) or to prepare any state on n qubits (m=0). The decomposition used here was introduced by Iten et al. in [https://arxiv.org/abs/1501.06911](https://arxiv.org/abs/1501.06911).

**Parameters**

*   **isometry** (*ndarray*) – an isometry from m to n qubits, i.e., a (complex) ndarray of dimension 2^n×2^m with orthonormal columns (given in the computational basis specified by the order of the ancillas and the input qubits, where the ancillas are considered to be more significant than the input qubits.).
*   **q\_input** (*QuantumRegister|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of m qubits where the input to the isometry is fed in (empty list for state preparation).
*   **q\_ancillas\_for\_output** (*QuantumRegister|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of n-m ancilla qubits that are used for the output of the isometry and which are assumed to start in the zero state. The qubits are listed with increasing significance.
*   **q\_ancillas\_zero** (*QuantumRegister|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of ancilla qubits which are assumed to start in the zero state. Default is q\_ancillas\_zero = None.
*   **q\_ancillas\_dirty** (*QuantumRegister|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of ancilla qubits which can start in an arbitrary state. Default is q\_ancillas\_dirty = None.

**Returns**

the isometry is attached to the quantum circuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the array is not an isometry of the correct size corresponding to the provided number of qubits.

### isometry

<span id="qiskit.circuit.library.InnerProduct.isometry" />

`isometry(isometry, q_input, q_ancillas_for_output, q_ancillas_zero=None, q_ancillas_dirty=None)`

Attach an arbitrary isometry from m to n qubits to a circuit. In particular, this allows to attach arbitrary unitaries on n qubits (m=n) or to prepare any state on n qubits (m=0). The decomposition used here was introduced by Iten et al. in [https://arxiv.org/abs/1501.06911](https://arxiv.org/abs/1501.06911).

**Parameters**

*   **isometry** (*ndarray*) – an isometry from m to n qubits, i.e., a (complex) ndarray of dimension 2^n×2^m with orthonormal columns (given in the computational basis specified by the order of the ancillas and the input qubits, where the ancillas are considered to be more significant than the input qubits.).
*   **q\_input** (*QuantumRegister|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of m qubits where the input to the isometry is fed in (empty list for state preparation).
*   **q\_ancillas\_for\_output** (*QuantumRegister|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of n-m ancilla qubits that are used for the output of the isometry and which are assumed to start in the zero state. The qubits are listed with increasing significance.
*   **q\_ancillas\_zero** (*QuantumRegister|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of ancilla qubits which are assumed to start in the zero state. Default is q\_ancillas\_zero = None.
*   **q\_ancillas\_dirty** (*QuantumRegister|list\[*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*]*) – list of ancilla qubits which can start in an arbitrary state. Default is q\_ancillas\_dirty = None.

**Returns**

the isometry is attached to the quantum circuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the array is not an isometry of the correct size corresponding to the provided number of qubits.

### iswap

<span id="qiskit.circuit.library.InnerProduct.iswap" />

`iswap(qubit1, qubit2)`

Apply [`iSwapGate`](qiskit.circuit.library.iSwapGate "qiskit.circuit.library.iSwapGate").

### mcmt

<span id="qiskit.circuit.library.InnerProduct.mcmt" />

`mcmt(gate, control_qubits, target_qubits, ancilla_qubits=None, mode='noancilla', *, single_control_gate_fun=None, q_controls=None, q_ancillae=None, q_targets=None)`

Apply a multi-control, multi-target using a generic gate.

This can also be used to implement a generic multi-control gate, as the target could also be of length 1.

### mcp

<span id="qiskit.circuit.library.InnerProduct.mcp" />

`mcp(lam, control_qubits, target_qubit)`

Apply [`MCPhaseGate`](qiskit.circuit.library.MCPhaseGate "qiskit.circuit.library.MCPhaseGate").

### mcrx

<span id="qiskit.circuit.library.InnerProduct.mcrx" />

`mcrx(theta, q_controls, q_target, use_basis_gates=False)`

Apply Multiple-Controlled X rotation gate

**Parameters**

*   **self** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – The QuantumCircuit object to apply the mcrx gate on.
*   **theta** (*float*) – angle theta
*   **q\_controls** (*list(*[*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")*)*) – The list of control qubits
*   **q\_target** ([*Qubit*](qiskit.circuit.Qubit "qiskit.circuit.Qubit")) – The target qubit
*   **use\_basis\_gates** (*bool*) – use p, u, cx

**Raises**

**QiskitError** – parameter errors

### mcry

<span id="qiskit.circuit.library.InnerProduct.mcry" />

`mcry(theta, q_controls, q_target, q_ancillae, mode=None, use_basis_gates=False)`

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

<span id="qiskit.circuit.library.InnerProduct.mcrz" />

`mcrz(lam, q_controls, q_target, use_basis_gates=False)`

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

<span id="qiskit.circuit.library.InnerProduct.mct" />

`mct(control_qubits, target_qubit, ancilla_qubits=None, mode='noancilla')`

Apply [`MCXGate`](qiskit.circuit.library.MCXGate "qiskit.circuit.library.MCXGate").

### mcu1

<span id="qiskit.circuit.library.InnerProduct.mcu1" />

`mcu1(lam, control_qubits, target_qubit)`

Apply `MCU1Gate`.

### mcx

<span id="qiskit.circuit.library.InnerProduct.mcx" />

`mcx(control_qubits, target_qubit, ancilla_qubits=None, mode='noancilla')`

Apply [`MCXGate`](qiskit.circuit.library.MCXGate "qiskit.circuit.library.MCXGate").

The multi-cX gate can be implemented using different techniques, which use different numbers of ancilla qubits and have varying circuit depth. These modes are: - ‘no-ancilla’: Requires 0 ancilla qubits. - ‘recursion’: Requires 1 ancilla qubit if more than 4 controls are used, otherwise 0. - ‘v-chain’: Requires 2 less ancillas than the number of control qubits. - ‘v-chain-dirty’: Same as for the clean ancillas (but the circuit will be longer).

### measure

<span id="qiskit.circuit.library.InnerProduct.measure" />

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

<span id="qiskit.circuit.library.InnerProduct.measure_active" />

`measure_active(inplace=True)`

Adds measurement to all non-idle qubits. Creates a new ClassicalRegister with a size equal to the number of non-idle qubits being measured.

Returns a new circuit with measurements if inplace=False.

**Parameters**

**inplace** (*bool*) – All measurements inplace or return new circuit.

**Returns**

Returns circuit with measurements when inplace = False.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### measure\_all

<span id="qiskit.circuit.library.InnerProduct.measure_all" />

`measure_all(inplace=True)`

Adds measurement to all qubits. Creates a new ClassicalRegister with a size equal to the number of qubits being measured.

Returns a new circuit with measurements if inplace=False.

**Parameters**

**inplace** (*bool*) – All measurements inplace or return new circuit.

**Returns**

Returns circuit with measurements when inplace = False.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### mirror

<span id="qiskit.circuit.library.InnerProduct.mirror" />

`mirror()`

DEPRECATED: use circuit.reverse\_ops().

**Returns**

the reversed circuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### ms

<span id="qiskit.circuit.library.InnerProduct.ms" />

`ms(theta, qubits)`

Apply [`MSGate`](qiskit.circuit.library.MSGate "qiskit.circuit.library.MSGate").

### num\_ancillas

<span id="qiskit.circuit.library.InnerProduct.num_ancillas" />

`property num_ancillas`

Return the number of ancilla qubits.

### num\_clbits

<span id="qiskit.circuit.library.InnerProduct.num_clbits" />

`property num_clbits`

Return number of classical bits.

### num\_connected\_components

<span id="qiskit.circuit.library.InnerProduct.num_connected_components" />

`num_connected_components(unitary_only=False)`

How many non-entangled subcircuits can the circuit be factored to.

**Parameters**

**unitary\_only** (*bool*) – Compute only unitary part of graph.

**Returns**

Number of connected components in circuit.

**Return type**

int

### num\_nonlocal\_gates

<span id="qiskit.circuit.library.InnerProduct.num_nonlocal_gates" />

`num_nonlocal_gates()`

Return number of non-local gates (i.e. involving 2+ qubits).

Conditional nonlocal gates are also included.

### num\_parameters

<span id="qiskit.circuit.library.InnerProduct.num_parameters" />

`property num_parameters`

Convenience function to get the number of parameter objects in the circuit.

### num\_qubits

<span id="qiskit.circuit.library.InnerProduct.num_qubits" />

`property num_qubits`

Return number of qubits.

### num\_tensor\_factors

<span id="qiskit.circuit.library.InnerProduct.num_tensor_factors" />

`num_tensor_factors()`

Computes the number of tensor factors in the unitary (quantum) part of the circuit only.

## Notes

This is here for backwards compatibility, and will be removed in a future release of Qiskit. You should call num\_unitary\_factors instead.

### num\_unitary\_factors

<span id="qiskit.circuit.library.InnerProduct.num_unitary_factors" />

`num_unitary_factors()`

Computes the number of tensor factors in the unitary (quantum) part of the circuit only.

### p

<span id="qiskit.circuit.library.InnerProduct.p" />

`p(theta, qubit)`

Apply [`PhaseGate`](qiskit.circuit.library.PhaseGate "qiskit.circuit.library.PhaseGate").

### parameters

<span id="qiskit.circuit.library.InnerProduct.parameters" />

`property parameters`

Convenience function to get the parameters defined in the parameter table.

### power

<span id="qiskit.circuit.library.InnerProduct.power" />

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

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### qasm

<span id="qiskit.circuit.library.InnerProduct.qasm" />

`qasm(formatted=False, filename=None)`

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

<span id="qiskit.circuit.library.InnerProduct.qbit_argument_conversion" />

`qbit_argument_conversion(qubit_representation)`

Converts several qubit representations (such as indexes, range, etc.) into a list of qubits.

**Parameters**

**qubit\_representation** (*Object*) – representation to expand

**Returns**

Where each tuple is a qubit.

**Return type**

List(tuple)

### qubit\_duration

<span id="qiskit.circuit.library.InnerProduct.qubit_duration" />

`qubit_duration(*qubits)`

Return the duration between the start and stop time of the first and last instructions, excluding delays, over the supplied qubits. Its time unit is `self.unit`.

**Parameters**

**\*qubits** – Qubits within `self` to include.

**Return type**

`Union`\[`int`, `float`]

**Returns**

Return the duration between the first start and last stop time of non-delay instructions

### qubit\_start\_time

<span id="qiskit.circuit.library.InnerProduct.qubit_start_time" />

`qubit_start_time(*qubits)`

Return the start time of the first instruction, excluding delays, over the supplied qubits. Its time unit is `self.unit`.

Return 0 if there are no instructions over qubits

**Parameters**

*   **\*qubits** – Qubits within `self` to include. Integers are allowed for qubits, indicating
*   **of self.qubits.** (*indices*) –

**Return type**

`Union`\[`int`, `float`]

**Returns**

Return the start time of the first instruction, excluding delays, over the qubits

**Raises**

**CircuitError** – if `self` is a not-yet scheduled circuit.

### qubit\_stop\_time

<span id="qiskit.circuit.library.InnerProduct.qubit_stop_time" />

`qubit_stop_time(*qubits)`

Return the stop time of the last instruction, excluding delays, over the supplied qubits. Its time unit is `self.unit`.

Return 0 if there are no instructions over qubits

**Parameters**

*   **\*qubits** – Qubits within `self` to include. Integers are allowed for qubits, indicating
*   **of self.qubits.** (*indices*) –

**Return type**

`Union`\[`int`, `float`]

**Returns**

Return the stop time of the last instruction, excluding delays, over the qubits

**Raises**

**CircuitError** – if `self` is a not-yet scheduled circuit.

### qubits

<span id="qiskit.circuit.library.InnerProduct.qubits" />

`property qubits`

Returns a list of quantum bits in the order that the registers were added.

### r

<span id="qiskit.circuit.library.InnerProduct.r" />

`r(theta, phi, qubit)`

Apply `RGate`.

### rcccx

<span id="qiskit.circuit.library.InnerProduct.rcccx" />

`rcccx(control_qubit1, control_qubit2, control_qubit3, target_qubit)`

Apply [`RC3XGate`](qiskit.circuit.library.RC3XGate "qiskit.circuit.library.RC3XGate").

### rccx

<span id="qiskit.circuit.library.InnerProduct.rccx" />

`rccx(control_qubit1, control_qubit2, target_qubit)`

Apply [`RCCXGate`](qiskit.circuit.library.RCCXGate "qiskit.circuit.library.RCCXGate").

### remove\_final\_measurements

<span id="qiskit.circuit.library.InnerProduct.remove_final_measurements" />

`remove_final_measurements(inplace=True)`

Removes final measurement on all qubits if they are present. Deletes the ClassicalRegister that was used to store the values from these measurements if it is idle.

Returns a new circuit without measurements if inplace=False.

**Parameters**

**inplace** (*bool*) – All measurements removed inplace or return new circuit.

**Returns**

Returns circuit with measurements removed when inplace = False.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### repeat

<span id="qiskit.circuit.library.InnerProduct.repeat" />

`repeat(reps)`

Repeat this circuit `reps` times.

**Parameters**

**reps** (*int*) – How often this circuit should be repeated.

**Returns**

A circuit containing `reps` repetitions of this circuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### reset

<span id="qiskit.circuit.library.InnerProduct.reset" />

`reset(qubit)`

Reset q.

### reverse\_bits

<span id="qiskit.circuit.library.InnerProduct.reverse_bits" />

`reverse_bits()`

Return a circuit with the opposite order of wires.

The circuit is “vertically” flipped. If a circuit is defined over multiple registers, the resulting circuit will have the same registers but with their order flipped.

This method is useful for converting a circuit written in little-endian convention to the big-endian equivalent, and vice versa.

**Returns**

the circuit with reversed bit order.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

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

<span id="qiskit.circuit.library.InnerProduct.reverse_ops" />

`reverse_ops()`

Reverse the circuit by reversing the order of instructions.

This is done by recursively reversing all instructions. It does not invert (adjoint) any gate.

**Returns**

the reversed circuit.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

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

### rx

<span id="qiskit.circuit.library.InnerProduct.rx" />

`rx(theta, qubit, label=None)`

Apply [`RXGate`](qiskit.circuit.library.RXGate "qiskit.circuit.library.RXGate").

### rxx

<span id="qiskit.circuit.library.InnerProduct.rxx" />

`rxx(theta, qubit1, qubit2)`

Apply [`RXXGate`](qiskit.circuit.library.RXXGate "qiskit.circuit.library.RXXGate").

### ry

<span id="qiskit.circuit.library.InnerProduct.ry" />

`ry(theta, qubit, label=None)`

Apply [`RYGate`](qiskit.circuit.library.RYGate "qiskit.circuit.library.RYGate").

### ryy

<span id="qiskit.circuit.library.InnerProduct.ryy" />

`ryy(theta, qubit1, qubit2)`

Apply [`RYYGate`](qiskit.circuit.library.RYYGate "qiskit.circuit.library.RYYGate").

### rz

<span id="qiskit.circuit.library.InnerProduct.rz" />

`rz(phi, qubit)`

Apply [`RZGate`](qiskit.circuit.library.RZGate "qiskit.circuit.library.RZGate").

### rzx

<span id="qiskit.circuit.library.InnerProduct.rzx" />

`rzx(theta, qubit1, qubit2)`

Apply [`RZXGate`](qiskit.circuit.library.RZXGate "qiskit.circuit.library.RZXGate").

### rzz

<span id="qiskit.circuit.library.InnerProduct.rzz" />

`rzz(theta, qubit1, qubit2)`

Apply [`RZZGate`](qiskit.circuit.library.RZZGate "qiskit.circuit.library.RZZGate").

### s

<span id="qiskit.circuit.library.InnerProduct.s" />

`s(qubit)`

Apply [`SGate`](qiskit.circuit.library.SGate "qiskit.circuit.library.SGate").

### sdg

<span id="qiskit.circuit.library.InnerProduct.sdg" />

`sdg(qubit)`

Apply [`SdgGate`](qiskit.circuit.library.SdgGate "qiskit.circuit.library.SdgGate").

### size

<span id="qiskit.circuit.library.InnerProduct.size" />

`size()`

Returns total number of gate operations in circuit.

**Returns**

Total number of gate operations.

**Return type**

int

### snapshot

<span id="qiskit.circuit.library.InnerProduct.snapshot" />

`snapshot(label, snapshot_type='statevector', qubits=None, params=None)`

Take a statevector snapshot of the internal simulator representation. Works on all qubits, and prevents reordering (like barrier). :param label: a snapshot label to report the result :type label: str :param snapshot\_type: the type of the snapshot. :type snapshot\_type: str :param qubits: the qubits to apply snapshot to \[Default: None]. :type qubits: list or None :param params: the parameters for snapshot\_type \[Default: None]. :type params: list or None

**Returns**

with attached command

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – malformed command

### snapshot\_density\_matrix

<span id="qiskit.circuit.library.InnerProduct.snapshot_density_matrix" />

`snapshot_density_matrix(label, qubits=None)`

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

<span id="qiskit.circuit.library.InnerProduct.snapshot_expectation_value" />

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

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – if snapshot is invalid.

### snapshot\_probabilities

<span id="qiskit.circuit.library.InnerProduct.snapshot_probabilities" />

`snapshot_probabilities(label, qubits, variance=False)`

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

<span id="qiskit.circuit.library.InnerProduct.snapshot_stabilizer" />

`snapshot_stabilizer(label)`

Take a stabilizer snapshot of the simulator state.

**Parameters**

**label** (*str*) – a snapshot label to report the result.

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – if snapshot is invalid.

**Additional Information:**

This snapshot is always performed on all qubits in a circuit. The number of qubits parameter specifies the size of the instruction as a barrier and should be set to the number of qubits in the circuit.

### snapshot\_statevector

<span id="qiskit.circuit.library.InnerProduct.snapshot_statevector" />

`snapshot_statevector(label)`

Take a statevector snapshot of the simulator state.

**Parameters**

**label** (*str*) – a snapshot label to report the result.

**Returns**

with attached instruction.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**ExtensionError** – if snapshot is invalid.

**Additional Information:**

This snapshot is always performed on all qubits in a circuit. The number of qubits parameter specifies the size of the instruction as a barrier and should be set to the number of qubits in the circuit.

### squ

<span id="qiskit.circuit.library.InnerProduct.squ" />

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

<span id="qiskit.circuit.library.InnerProduct.swap" />

`swap(qubit1, qubit2)`

Apply [`SwapGate`](qiskit.circuit.library.SwapGate "qiskit.circuit.library.SwapGate").

### sx

<span id="qiskit.circuit.library.InnerProduct.sx" />

`sx(qubit)`

Apply [`SXGate`](qiskit.circuit.library.SXGate "qiskit.circuit.library.SXGate").

### sxdg

<span id="qiskit.circuit.library.InnerProduct.sxdg" />

`sxdg(qubit)`

Apply [`SXdgGate`](qiskit.circuit.library.SXdgGate "qiskit.circuit.library.SXdgGate").

### t

<span id="qiskit.circuit.library.InnerProduct.t" />

`t(qubit)`

Apply [`TGate`](qiskit.circuit.library.TGate "qiskit.circuit.library.TGate").

### tdg

<span id="qiskit.circuit.library.InnerProduct.tdg" />

`tdg(qubit)`

Apply [`TdgGate`](qiskit.circuit.library.TdgGate "qiskit.circuit.library.TdgGate").

### to\_gate

<span id="qiskit.circuit.library.InnerProduct.to_gate" />

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

<span id="qiskit.circuit.library.InnerProduct.to_instruction" />

`to_instruction(parameter_map=None)`

Create an Instruction out of this circuit.

**Parameters**

**parameter\_map** (*dict*) – For parameterized circuits, a mapping from parameters in the circuit to parameters to be used in the instruction. If None, existing circuit parameters will also parameterize the instruction.

**Returns**

a composite instruction encapsulating this circuit (can be decomposed back)

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

### toffoli

<span id="qiskit.circuit.library.InnerProduct.toffoli" />

`toffoli(control_qubit1, control_qubit2, target_qubit)`

Apply [`CCXGate`](qiskit.circuit.library.CCXGate "qiskit.circuit.library.CCXGate").

### u

<span id="qiskit.circuit.library.InnerProduct.u" />

`u(theta, phi, lam, qubit)`

Apply [`UGate`](qiskit.circuit.library.UGate "qiskit.circuit.library.UGate").

### u1

<span id="qiskit.circuit.library.InnerProduct.u1" />

`u1(theta, qubit)`

Apply [`U1Gate`](qiskit.circuit.library.U1Gate "qiskit.circuit.library.U1Gate").

### u2

<span id="qiskit.circuit.library.InnerProduct.u2" />

`u2(phi, lam, qubit)`

Apply [`U2Gate`](qiskit.circuit.library.U2Gate "qiskit.circuit.library.U2Gate").

### u3

<span id="qiskit.circuit.library.InnerProduct.u3" />

`u3(theta, phi, lam, qubit)`

Apply [`U3Gate`](qiskit.circuit.library.U3Gate "qiskit.circuit.library.U3Gate").

### uc

<span id="qiskit.circuit.library.InnerProduct.uc" />

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

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the list number of control qubits does not correspond to the provided number of single-qubit unitaries; if an input is of the wrong type

### ucrx

<span id="qiskit.circuit.library.InnerProduct.ucrx" />

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

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the list number of control qubits does not correspond to the provided number of single-qubit unitaries; if an input is of the wrong type

### ucry

<span id="qiskit.circuit.library.InnerProduct.ucry" />

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

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the list number of control qubits does not correspond to the provided number of single-qubit unitaries; if an input is of the wrong type

### ucrz

<span id="qiskit.circuit.library.InnerProduct.ucrz" />

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

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if the list number of control qubits does not correspond to the provided number of single-qubit unitaries; if an input is of the wrong type

### unitary

<span id="qiskit.circuit.library.InnerProduct.unitary" />

`unitary(obj, qubits, label=None)`

Apply unitary gate to q.

### width

<span id="qiskit.circuit.library.InnerProduct.width" />

`width()`

Return number of qubits plus clbits in circuit.

**Returns**

Width of circuit.

**Return type**

int

### x

<span id="qiskit.circuit.library.InnerProduct.x" />

`x(qubit, label=None)`

Apply [`XGate`](qiskit.circuit.library.XGate "qiskit.circuit.library.XGate").

### y

<span id="qiskit.circuit.library.InnerProduct.y" />

`y(qubit)`

Apply [`YGate`](qiskit.circuit.library.YGate "qiskit.circuit.library.YGate").

### z

<span id="qiskit.circuit.library.InnerProduct.z" />

`z(qubit)`

Apply [`ZGate`](qiskit.circuit.library.ZGate "qiskit.circuit.library.ZGate").

