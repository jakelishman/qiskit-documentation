---
title: Sampler
description: API reference for qiskit.primitives.Sampler
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.primitives.Sampler
---

# Sampler

<span id="qiskit.primitives.Sampler" />

`qiskit.primitives.Sampler(*, options=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/primitives/sampler.py "view source code")

Bases: [`BaseSampler`](qiskit.primitives.BaseSampler "qiskit.primitives.base.base_sampler.BaseSampler")\[`PrimitiveJob`\[[`SamplerResult`](qiskit.primitives.SamplerResult "qiskit.primitives.base.sampler_result.SamplerResult")]]

Sampler class.

[`Sampler`](#qiskit.primitives.Sampler "qiskit.primitives.Sampler") is a reference implementation of [`BaseSampler`](qiskit.primitives.BaseSampler "qiskit.primitives.BaseSampler").

**Run Options**

*   **shots** (None or int) – The number of shots. If None, it calculates the probabilities. Otherwise, it samples from multinomial distributions.
*   **seed** (np.random.Generator or int) – Set a fixed seed or generator for the multinomial distribution. If shots is None, this option is ignored.

**Parameters**

**options** ([*dict*](https://docs.python.org/3/library/stdtypes.html#dict "(in Python v3.12)") *| None*) – Default options.

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if some classical bits are not used for measurements.

## Attributes

<span id="qiskit.primitives.Sampler.circuits" />

### circuits

Quantum circuits to be sampled.

**Returns**

The quantum circuits to be sampled.

<span id="qiskit.primitives.Sampler.options" />

### options

Return options values for the estimator.

**Returns**

options

<span id="qiskit.primitives.Sampler.parameters" />

### parameters

Parameters of quantum circuits.

**Returns**

List of the parameters in each quantum circuit.

## Methods

### run

<span id="qiskit.primitives.Sampler.run" />

`run(circuits, parameter_values=None, **run_options)`

Run the job of the sampling of bitstrings.

**Parameters**

*   **circuits** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit") *| Sequence\[*[*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")*]*) – One of more circuit objects.
*   **parameter\_values** (*Sequence\[*[*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")*] | Sequence\[Sequence\[*[*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")*]] | None*) – Parameters to be bound to the circuit.
*   **run\_options** – Backend runtime options used for circuit execution.

**Returns**

The job object of the result of the sampler. The i-th result corresponds to `circuits[i]` evaluated with parameters bound as `parameter_values[i]`.

**Raises**

[**ValueError**](https://docs.python.org/3/library/exceptions.html#ValueError "(in Python v3.12)") – Invalid arguments are given.

**Return type**

T

### set\_options

<span id="qiskit.primitives.Sampler.set_options" />

`set_options(**fields)`

Set options values for the estimator.

**Parameters**

**\*\*fields** – The fields to update the options

