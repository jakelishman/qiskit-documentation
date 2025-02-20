---
title: Estimator
description: API reference for qiskit_ibm_runtime.Estimator
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit_ibm_runtime.Estimator
---

# Estimator

<span id="qiskit_ibm_runtime.Estimator" />

`Estimator(backend=None, session=None, options=None)`[GitHub](https://github.com/qiskit/qiskit-ibm-runtime/tree/stable/0.17/qiskit_ibm_runtime/estimator.py "view source code")

Class for interacting with Qiskit Runtime Estimator primitive service.

Qiskit Runtime Estimator primitive service estimates expectation values of quantum circuits and observables.

The [`run()`](#qiskit_ibm_runtime.Estimator.run "qiskit_ibm_runtime.Estimator.run") can be used to submit circuits, observables, and parameters to the Estimator primitive.

You are encouraged to use [`Session`](qiskit_ibm_runtime.Session "qiskit_ibm_runtime.Session") to open a session, during which you can invoke one or more primitives. Jobs submitted within a session are prioritized by the scheduler, and data is cached for efficiency.

Example:

```python
from qiskit.circuit.library import RealAmplitudes
from qiskit.quantum_info import SparsePauliOp

from qiskit_ibm_runtime import QiskitRuntimeService, Estimator

service = QiskitRuntimeService(channel="ibm_cloud")

psi1 = RealAmplitudes(num_qubits=2, reps=2)

H1 = SparsePauliOp.from_list([("II", 1), ("IZ", 2), ("XI", 3)])
H2 = SparsePauliOp.from_list([("IZ", 1)])
H3 = SparsePauliOp.from_list([("ZI", 1), ("ZZ", 1)])

with Session(service=service, backend="ibmq_qasm_simulator") as session:
    estimator = Estimator(session=session)

    theta1 = [0, 1, 1, 2, 3, 5]

    # calculate [ <psi1(theta1)|H1|psi1(theta1)> ]
    psi1_H1 = estimator.run(circuits=[psi1], observables=[H1], parameter_values=[theta1])
    print(psi1_H1.result())

    # calculate [ <psi1(theta1)|H2|psi1(theta1)>, <psi1(theta1)|H3|psi1(theta1)> ]
    psi1_H23 = estimator.run(
        circuits=[psi1, psi1],
        observables=[H2, H3],
        parameter_values=[theta1]*2
    )
    print(psi1_H23.result())
```

Initializes the Estimator primitive.

**Parameters**

*   **backend** (`Union`\[`str`, [`IBMBackend`](qiskit_ibm_runtime.IBMBackend "qiskit_ibm_runtime.ibm_backend.IBMBackend"), `None`]) – Backend to run the primitive. This can be a backend name or an [`IBMBackend`](qiskit_ibm_runtime.IBMBackend "qiskit_ibm_runtime.IBMBackend") instance. If a name is specified, the default account (e.g. `QiskitRuntimeService()`) is used.

*   **session** (`Union`\[[`Session`](qiskit_ibm_runtime.Session "qiskit_ibm_runtime.session.Session"), `str`, [`IBMBackend`](qiskit_ibm_runtime.IBMBackend "qiskit_ibm_runtime.ibm_backend.IBMBackend"), `None`]) –

    Session in which to call the primitive.

    If both `session` and `backend` are specified, `session` takes precedence. If neither is specified, and the primitive is created inside a [`qiskit_ibm_runtime.Session`](qiskit_ibm_runtime.Session "qiskit_ibm_runtime.Session") context manager, then the session is used. Otherwise if IBM Cloud channel is used, a default backend is selected.

*   **options** (`Union`\[`Dict`, [`Options`](qiskit_ibm_runtime.options.Options "qiskit_ibm_runtime.options.options.Options"), `None`]) – Primitive options, see `Options` for detailed description. The `backend` keyword is still supported but is deprecated.

## Attributes

<span id="qiskit_ibm_runtime.Estimator.circuits" />

### circuits

Quantum circuits that represents quantum states.

**Return type**

`tuple`\[`QuantumCircuit`, `...`]

**Returns**

The quantum circuits.

<span id="qiskit_ibm_runtime.Estimator.observables" />

### observables

Observables to be estimated.

**Return type**

`tuple`\[`SparsePauliOp`, `...`]

**Returns**

The observables.

<span id="qiskit_ibm_runtime.Estimator.options" />

### options

Return options values for the sampler.

**Return type**

`Options`

**Returns**

options

<span id="qiskit_ibm_runtime.Estimator.parameters" />

### parameters

Parameters of the quantum circuits.

**Return type**

`tuple`\[`ParameterView`, `...`]

**Returns**

Parameters, where `parameters[i][j]` is the j-th parameter of the i-th circuit.

<span id="qiskit_ibm_runtime.Estimator.session" />

### session

Return session used by this primitive.

**Return type**

`Optional`\[[`Session`](qiskit_ibm_runtime.Session "qiskit_ibm_runtime.session.Session")]

**Returns**

Session used by this primitive, or `None` if session is not used.

## Methods

### run

<span id="qiskit_ibm_runtime.Estimator.run" />

`run(circuits, observables, parameter_values=None, **kwargs)`

Submit a request to the estimator primitive.

**Parameters**

*   **circuits** (*QuantumCircuit | Sequence\[QuantumCircuit]*) – a (parameterized) `QuantumCircuit` or a list of (parameterized) `QuantumCircuit`.
*   **observables** (*BaseOperator | PauliSumOp | Sequence\[BaseOperator | PauliSumOp]*) – Observable objects.
*   **parameter\_values** (*Sequence\[float] | Sequence\[Sequence\[float]] | None*) – Concrete parameters to be bound.
*   **\*\*kwargs** – Individual options to overwrite the default primitive options. These include the runtime options in [`qiskit_ibm_runtime.RuntimeOptions`](qiskit_ibm_runtime.RuntimeOptions "qiskit_ibm_runtime.RuntimeOptions").

**Return type**

[RuntimeJob](qiskit_ibm_runtime.RuntimeJob "qiskit_ibm_runtime.RuntimeJob")

**Returns**

Submitted job. The result of the job is an instance of `qiskit.primitives.EstimatorResult`.

**Raises**

**ValueError** – Invalid arguments are given.

### set\_options

<span id="qiskit_ibm_runtime.Estimator.set_options" />

`set_options(**fields)`

Set options values for the sampler.

**Parameters**

**\*\*fields** – The fields to update the options

**Return type**

`None`

