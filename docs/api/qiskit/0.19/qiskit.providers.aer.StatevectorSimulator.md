---
title: StatevectorSimulator
description: API reference for qiskit.providers.aer.StatevectorSimulator
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.aer.StatevectorSimulator
---

# StatevectorSimulator

<span id="qiskit.providers.aer.StatevectorSimulator" />

`StatevectorSimulator(configuration=None, provider=None)`[GitHub](https://github.com/qiskit/qiskit-aer/tree/stable/0.5/qiskit/providers/aer/backends/statevector_simulator.py "view source code")

Ideal quantum circuit statevector simulator

**Backend options**

The following backend options may be used with in the `backend_options` kwarg for [`StatevectorSimulator.run()`](qiskit.providers.aer.StatevectorSimulator#run "qiskit.providers.aer.StatevectorSimulator.run") or `qiskit.execute`.

*   `"zero_threshold"` (double): Sets the threshold for truncating small values to zero in the result data (Default: 1e-10).
*   `"validation_threshold"` (double): Sets the threshold for checking if the initial statevector is valid (Default: 1e-8).
*   `"max_parallel_threads"` (int): Sets the maximum number of CPU cores used by OpenMP for parallelization. If set to 0 the maximum will be set to the number of CPU cores (Default: 0).
*   `"max_parallel_experiments"` (int): Sets the maximum number of qobj experiments that may be executed in parallel up to the max\_parallel\_threads value. If set to 1 parallel circuit execution will be disabled. If set to 0 the maximum will be automatically set to max\_parallel\_threads (Default: 1).
*   `"max_memory_mb"` (int): Sets the maximum size of memory to store a state vector. If a state vector needs more, an error is thrown. In general, a state vector of n-qubits uses 2^n complex values (16 Bytes). If set to 0, the maximum will be automatically set to half the system memory size (Default: 0).
*   `"statevector_parallel_threshold"` (int): Sets the threshold that “n\_qubits” must be greater than to enable OpenMP parallelization for matrix multiplication during execution of an experiment. If parallel circuit or shot execution is enabled this will only use unallocated CPU cores up to max\_parallel\_threads. Note that setting this too low can reduce performance (Default: 14).

Aer class for backends.

This method should initialize the module and its configuration, and raise an exception if a component of the module is not available.

**Parameters**

*   **controller** (*function*) – Aer controller to be executed
*   **configuration** ([*BackendConfiguration*](qiskit.providers.models.BackendConfiguration "qiskit.providers.models.BackendConfiguration")) – backend configuration
*   **provider** ([*BaseProvider*](qiskit.providers.BaseProvider "qiskit.providers.BaseProvider")) – provider responsible for this backend

**Raises**

*   **FileNotFoundError if backend executable is not available.** –
*   [**AerError**](qiskit.providers.aer.AerError "qiskit.providers.aer.AerError") – if there is no name in the configuration

## Attributes

### DEFAULT\_CONFIGURATION

<span id="qiskit.providers.aer.StatevectorSimulator.DEFAULT_CONFIGURATION" />

`= {'backend_name': 'statevector_simulator', 'backend_version': '0.5.2', 'basis_gates': ['u1', 'u2', 'u3', 'cx', 'cz', 'id', 'x', 'y', 'z', 'h', 's', 'sdg', 't', 'tdg', 'swap', 'ccx', 'unitary', 'diagonal', 'initialize', 'cu1', 'cu2', 'cu3', 'cswap', 'mcx', 'mcy', 'mcz', 'mcu1', 'mcu2', 'mcu3', 'mcswap', 'multiplexer'], 'conditional': True, 'coupling_map': None, 'description': 'A C++ statevector simulator for QASM Qobj files', 'gates': [{'name': 'u1', 'parameters': ['lam'], 'conditional': True, 'description': 'Single-qubit gate [[1, 0], [0, exp(1j*lam)]]', 'qasm_def': 'gate u1(lam) q { U(0,0,lam) q; }'}, {'name': 'u2', 'parameters': ['phi', 'lam'], 'conditional': True, 'description': 'Single-qubit gate [[1, -exp(1j*lam)], [exp(1j*phi), exp(1j*(phi+lam))]]/sqrt(2)', 'qasm_def': 'gate u2(phi,lam) q { U(pi/2,phi,lam) q; }'}, {'name': 'u3', 'parameters': ['theta', 'phi', 'lam'], 'conditional': True, 'description': 'Single-qubit gate with three rotation angles', 'qasm_def': 'gate u3(theta,phi,lam) q { U(theta,phi,lam) q; }'}, {'name': 'cx', 'parameters': [], 'conditional': True, 'description': 'Two-qubit Controlled-NOT gate', 'qasm_def': 'gate cx c,t { CX c,t; }'}, {'name': 'cz', 'parameters': [], 'conditional': True, 'description': 'Two-qubit Controlled-Z gate', 'qasm_def': 'gate cz a,b { h b; cx a,b; h b; }'}, {'name': 'id', 'parameters': [], 'conditional': True, 'description': 'Single-qubit identity gate', 'qasm_def': 'gate id a { U(0,0,0) a; }'}, {'name': 'x', 'parameters': [], 'conditional': True, 'description': 'Single-qubit Pauli-X gate', 'qasm_def': 'gate x a { U(pi,0,pi) a; }'}, {'name': 'y', 'parameters': [], 'conditional': True, 'description': 'Single-qubit Pauli-Y gate', 'qasm_def': 'TODO'}, {'name': 'z', 'parameters': [], 'conditional': True, 'description': 'Single-qubit Pauli-Z gate', 'qasm_def': 'TODO'}, {'name': 'h', 'parameters': [], 'conditional': True, 'description': 'Single-qubit Hadamard gate', 'qasm_def': 'TODO'}, {'name': 's', 'parameters': [], 'conditional': True, 'description': 'Single-qubit phase gate', 'qasm_def': 'TODO'}, {'name': 'sdg', 'parameters': [], 'conditional': True, 'description': 'Single-qubit adjoint phase gate', 'qasm_def': 'TODO'}, {'name': 't', 'parameters': [], 'conditional': True, 'description': 'Single-qubit T gate', 'qasm_def': 'TODO'}, {'name': 'tdg', 'parameters': [], 'conditional': True, 'description': 'Single-qubit adjoint T gate', 'qasm_def': 'TODO'}, {'name': 'swap', 'parameters': [], 'conditional': True, 'description': 'Two-qubit SWAP gate', 'qasm_def': 'TODO'}, {'name': 'ccx', 'parameters': [], 'conditional': True, 'description': 'Three-qubit Toffoli gate', 'qasm_def': 'TODO'}, {'name': 'cswap', 'parameters': [], 'conditional': True, 'description': 'Three-qubit Fredkin (controlled-SWAP) gate', 'qasm_def': 'TODO'}, {'name': 'unitary', 'parameters': ['matrix'], 'conditional': True, 'description': 'N-qubit arbitrary unitary gate. The parameter is the N-qubit matrix to apply.', 'qasm_def': 'unitary(matrix) q1, q2,...'}, {'name': 'diagonal', 'parameters': ['diag_elements'], 'conditional': True, 'description': 'N-qubit diagonal unitary gate. The parameters are the diagonal entries of the N-qubit matrix to apply.', 'qasm_def': 'TODO'}, {'name': 'initialize', 'parameters': ['vector'], 'conditional': False, 'description': 'N-qubit state initialize. Resets qubits then sets statevector to the parameter vector.', 'qasm_def': 'initialize(vector) q1, q2,...'}, {'name': 'cu1', 'parameters': ['lam'], 'conditional': True, 'description': 'Two-qubit Controlled-u1 gate', 'qasm_def': 'TODO'}, {'name': 'cu2', 'parameters': ['phi', 'lam'], 'conditional': True, 'description': 'Two-qubit Controlled-u2 gate', 'qasm_def': 'TODO'}, {'name': 'cu3', 'parameters': ['theta', 'phi', 'lam'], 'conditional': True, 'description': 'Two-qubit Controlled-u3 gate', 'qasm_def': 'TODO'}, {'name': 'mcx', 'parameters': [], 'conditional': True, 'description': 'N-qubit multi-controlled-X gate', 'qasm_def': 'TODO'}, {'name': 'mcy', 'parameters': [], 'conditional': True, 'description': 'N-qubit multi-controlled-Y gate', 'qasm_def': 'TODO'}, {'name': 'mcz', 'parameters': [], 'conditional': True, 'description': 'N-qubit multi-controlled-Z gate', 'qasm_def': 'TODO'}, {'name': 'mcu1', 'parameters': ['lam'], 'conditional': True, 'description': 'N-qubit multi-controlled-u1 gate', 'qasm_def': 'TODO'}, {'name': 'mcu2', 'parameters': ['phi', 'lam'], 'conditional': True, 'description': 'N-qubit multi-controlled-u2 gate', 'qasm_def': 'TODO'}, {'name': 'mcu3', 'parameters': ['theta', 'phi', 'lam'], 'conditional': True, 'description': 'N-qubit multi-controlled-u3 gate', 'qasm_def': 'TODO'}, {'name': 'mcswap', 'parameters': [], 'conditional': True, 'description': 'N-qubit multi-controlled-SWAP gate', 'qasm_def': 'TODO'}, {'name': 'multiplexer', 'parameters': ['mat1', 'mat2', '...'], 'conditional': True, 'description': 'N-qubit multi-plexer gate. The input parameters are the gates for each value.', 'qasm_def': 'TODO'}], 'local': True, 'max_shots': 1000000, 'memory': True, 'n_qubits': 32, 'open_pulse': False, 'simulator': True, 'url': 'https://github.com/Qiskit/qiskit-aer'}`

### MAX\_QUBIT\_MEMORY

<span id="qiskit.providers.aer.StatevectorSimulator.MAX_QUBIT_MEMORY" />

`= 32`

## Methods

### configuration

<span id="qiskit.providers.aer.StatevectorSimulator.configuration" />

`StatevectorSimulator.configuration()`

Return the backend configuration.

**Returns**

the configuration for the backend.

**Return type**

[BackendConfiguration](qiskit.providers.models.BackendConfiguration "qiskit.providers.models.BackendConfiguration")

### name

<span id="qiskit.providers.aer.StatevectorSimulator.name" />

`StatevectorSimulator.name()`

Return the backend name.

**Returns**

the name of the backend.

**Return type**

str

### properties

<span id="qiskit.providers.aer.StatevectorSimulator.properties" />

`StatevectorSimulator.properties()`

Return the backend properties.

**Returns**

the configuration for the backend. If the backend does not support properties, it returns `None`.

**Return type**

[BackendProperties](qiskit.providers.models.BackendProperties "qiskit.providers.models.BackendProperties")

### provider

<span id="qiskit.providers.aer.StatevectorSimulator.provider" />

`StatevectorSimulator.provider()`

Return the backend Provider.

**Returns**

the Provider responsible for the backend.

**Return type**

[BaseProvider](qiskit.providers.BaseProvider "qiskit.providers.BaseProvider")

### run

<span id="qiskit.providers.aer.StatevectorSimulator.run" />

`StatevectorSimulator.run(qobj, backend_options=None, noise_model=None, validate=False)`

Run a qobj on the backend.

**Parameters**

*   **qobj** ([*QasmQobj*](qiskit.qobj.QasmQobj "qiskit.qobj.QasmQobj")) – The Qobj to be executed.
*   **backend\_options** (*dict or None*) – dictionary of backend options for the execution (default: None).
*   **noise\_model** ([*NoiseModel*](qiskit.providers.aer.noise.NoiseModel "qiskit.providers.aer.noise.NoiseModel") *or None*) – noise model to use for simulation (default: None).
*   **validate** (*bool*) – validate the Qobj before running (default: True).

**Returns**

The simulation job.

**Return type**

[AerJob](qiskit.providers.aer.AerJob "qiskit.providers.aer.AerJob")

#### Additional Information:

*   The entries in the `backend_options` will be combined with the `Qobj.config` dictionary with the values of entries in `backend_options` taking precedence.
*   If present the `noise_model` will override any noise model specified in the `backend_options` or `Qobj.config`.

### status

<span id="qiskit.providers.aer.StatevectorSimulator.status" />

`StatevectorSimulator.status()`

Return backend status.

**Returns**

the status of the backend.

**Return type**

[BackendStatus](qiskit.providers.models.BackendStatus "qiskit.providers.models.BackendStatus")

### version

<span id="qiskit.providers.aer.StatevectorSimulator.version" />

`StatevectorSimulator.version()`

Return the backend version.

**Returns**

the X.X.X version of the backend.

**Return type**

str

