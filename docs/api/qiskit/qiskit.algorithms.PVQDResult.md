---
title: PVQDResult
description: API reference for qiskit.algorithms.PVQDResult
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.PVQDResult
---

# PVQDResult

<span id="qiskit.algorithms.PVQDResult" />

`qiskit.algorithms.PVQDResult(evolved_state, aux_ops_evaluated=None, times=None, parameters=None, fidelities=None, estimated_error=None, observables=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/algorithms/time_evolvers/pvqd/pvqd_result.py "view source code")

Bases: [`TimeEvolutionResult`](qiskit.algorithms.TimeEvolutionResult "qiskit.algorithms.time_evolvers.time_evolution_result.TimeEvolutionResult")

The result object for the p-VQD algorithm.

**Parameters**

*   **evolved\_state** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – An evolved quantum state.
*   **aux\_ops\_evaluated** ([*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")*\[*[*tuple*](https://docs.python.org/3/library/stdtypes.html#tuple "(in Python v3.12)")*\[*[*complex*](https://docs.python.org/3/library/functions.html#complex "(in Python v3.12)")*,* [*complex*](https://docs.python.org/3/library/functions.html#complex "(in Python v3.12)")*]] | None*) – Optional list of observables for which expected values on an evolved state are calculated. These values are in fact tuples formatted as (mean, standard deviation).
*   **times** ([*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")*\[*[*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")*] | None*) – The times evaluated during the time integration.
*   **parameters** ([*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")*\[np.ndarray] | None*) – The parameter values at each evaluation time.
*   **fidelities** (*Sequence\[*[*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")*] | None*) – The fidelity of the Trotter step and variational update at each iteration.
*   **estimated\_error** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)") *| None*) – The overall estimated error evaluated as one minus the product of all fidelities.
*   **observables** ([*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")*\[*[*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")*\[*[*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")*]] | None*) – The value of the observables evaluated at each iteration.

## Methods

### combine

<span id="qiskit.algorithms.PVQDResult.combine" />

`combine(result)`

Any property from the argument that exists in the receiver is updated. :param result: Argument result with properties to be set.

**Raises**

[**TypeError**](https://docs.python.org/3/library/exceptions.html#TypeError "(in Python v3.12)") – Argument is None

