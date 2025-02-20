---
title: Estimator
description: API reference for qiskit_aer.primitives.Estimator
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit_aer.primitives.Estimator
---

# Estimator

<span id="qiskit_aer.primitives.Estimator" />

`Estimator(circuits: Iterable[QuantumCircuit] | QuantumCircuit, observables: Iterable[SparsePauliOp] | SparsePauliOp, *args, parameters: Iterable[Iterable[Parameter]] | None = None, **kwargs)`[GitHub](https://github.com/qiskit/qiskit-aer/tree/stable/0.11/qiskit_aer/primitives/estimator.py "view source code")

Bases: [`qiskit.primitives.base_estimator.BaseEstimator`](qiskit.primitives.BaseEstimator "qiskit.primitives.base_estimator.BaseEstimator")

Aer implmentation of Estimator.

**Run Options**

*   **shots** (None or int) – The number of shots. If None and approximation is True, it calculates the exact expectation values. Otherwise, it calculates expectation values with sampling.
*   **seed** (int) – Set a fixed seed for the sampling.

<Admonition title="Note" type="note">
  Precedence of seeding for `seed_simulator` is as follows:

  1.  `seed_simulator` in runtime (i.e. in `__call__()`)
  2.  `seed` in runtime (i.e. in `__call__()`)
  3.  `seed_simulator` of `backend_options`.
  4.  default.

  `seed` is also used for sampling from a normal distribution when approximation is True.
</Admonition>

**Parameters**

*   **circuits** – Quantum circuits that represent quantum states.
*   **observables** – Observables.
*   **parameters** – Parameters of quantum circuits, specifying the order in which values will be bound. Defaults to `[circ.parameters for circ in circuits]` The indexing is such that `parameters[i, j]` is the j-th formal parameter of `circuits[i]`.
*   **backend\_options** – Options passed to AerSimulator.
*   **transpile\_options** – Options passed to transpile.
*   **approximation** – If True, it calculates expectation values with normal distribution approximation.
*   **skip\_transpilation** – If True, transpilation is skipped.

## Methods

### close

<span id="qiskit_aer.primitives.Estimator.close" />

`Estimator.close()`[GitHub](https://github.com/qiskit/qiskit-aer/tree/stable/0.11/qiskit_aer/primitives/estimator.py "view source code")

Close the session and free resources

## Attributes

<span id="qiskit_aer.primitives.Estimator.circuits" />

### circuits

Quantum circuits that represents quantum states.

**Returns**

The quantum circuits.

<span id="qiskit_aer.primitives.Estimator.observables" />

### observables

Observables to be estimated.

**Returns**

The observables.

<span id="qiskit_aer.primitives.Estimator.parameters" />

### parameters

Parameters of the quantum circuits.

**Returns**

Parameters, where `parameters[i][j]` is the j-th parameter of the i-th circuit.

