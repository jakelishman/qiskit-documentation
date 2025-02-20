---
title: BaseSamplerGradient
description: API reference for qiskit.algorithms.gradients.BaseSamplerGradient
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.gradients.BaseSamplerGradient
---

# BaseSamplerGradient

<span id="qiskit.algorithms.gradients.BaseSamplerGradient" />

`qiskit.algorithms.gradients.BaseSamplerGradient(sampler, options=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/algorithms/gradients/base/base_sampler_gradient.py "view source code")

Bases: [`ABC`](https://docs.python.org/3/library/abc.html#abc.ABC "(in Python v3.12)")

Base class for a `SamplerGradient` to compute the gradients of the sampling probability.

**Parameters**

*   **sampler** ([*BaseSampler*](qiskit.primitives.BaseSampler "qiskit.primitives.BaseSampler")) – The sampler used to compute the gradients.
*   **options** ([*Options*](qiskit.providers.Options "qiskit.providers.Options") *| None*) – Primitive backend runtime options used for circuit execution. The order of priority is: options in `run` method > gradient’s default options > primitive’s default setting. Higher priority setting overrides lower priority setting

## Attributes

<span id="qiskit.algorithms.gradients.BaseSamplerGradient.options" />

### options

Return the union of sampler options setting and gradient default options, where, if the same field is set in both, the gradient’s default options override the primitive’s default setting.

**Returns**

The gradient default + sampler options.

## Methods

### run

<span id="qiskit.algorithms.gradients.BaseSamplerGradient.run" />

`run(circuits, parameter_values, parameters=None, **options)`

Run the job of the sampler gradient on the given circuits.

**Parameters**

*   **circuits** (*Sequence\[*[*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")*]*) – The list of quantum circuits to compute the gradients.
*   **parameter\_values** (*Sequence\[Sequence\[*[*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")*]]*) – The list of parameter values to be bound to the circuit.
*   **parameters** (*Sequence\[Sequence\[*[*Parameter*](qiskit.circuit.Parameter "qiskit.circuit.Parameter")*] | None] | None*) – The sequence of parameters to calculate only the gradients of the specified parameters. Each sequence of parameters corresponds to a circuit in `circuits`. Defaults to None, which means that the gradients of all parameters in each circuit are calculated. None in the sequence means that the gradients of all parameters in the corresponding circuit are calculated.
*   **options** – Primitive backend runtime options used for circuit execution. The order of priority is: options in `run` method > gradient’s default options > primitive’s default setting. Higher priority setting overrides lower priority setting

**Returns**

The job object of the gradients of the sampling probability. The i-th result corresponds to `circuits[i]` evaluated with parameters bound as `parameter_values[i]`. The j-th quasi-probability distribution in the i-th result corresponds to the gradients of the sampling probability for the j-th parameter in `circuits[i]`.

**Raises**

[**ValueError**](https://docs.python.org/3/library/exceptions.html#ValueError "(in Python v3.12)") – Invalid arguments are given.

**Return type**

[AlgorithmJob](qiskit.algorithms.AlgorithmJob "qiskit.algorithms.AlgorithmJob")

### update\_default\_options

<span id="qiskit.algorithms.gradients.BaseSamplerGradient.update_default_options" />

`update_default_options(**options)`

Update the gradient’s default options setting.

**Parameters**

**\*\*options** – The fields to update the default options.

