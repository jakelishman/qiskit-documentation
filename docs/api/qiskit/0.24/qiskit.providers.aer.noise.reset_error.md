---
title: reset_error
description: API reference for qiskit.providers.aer.noise.reset_error
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.providers.aer.noise.reset_error
---

<span id="qiskit-providers-aer-noise-reset-error" />

# qiskit.providers.aer.noise.reset\_error

<span id="qiskit.providers.aer.noise.reset_error" />

`reset_error(prob0, prob1=0)`[GitHub](https://github.com/qiskit/qiskit-aer/tree/stable/0.7/qiskit/providers/aer/noise/errors/standard_errors.py "view source code")

Return a single qubit reset quantum error channel.

The error channel returned is given by the map

$$
E(ρ) = (1 - p_0 - p_1) ρ + \text{Tr}[ρ] \left(
        p_0 |0 \rangle\langle 0|
        + p_1 |1 \rangle\langle 1| \right)
$$

where the probability of no reset is given by $1 - p_0 - p_1$.

**Parameters**

*   **prob0** (*double*) – reset probability to $|0\rangle$.
*   **prob1** (*double*) – reset probability to $|1\rangle$.

**Returns**

the quantum error object.

**Return type**

[QuantumError](qiskit.providers.aer.noise.QuantumError "qiskit.providers.aer.noise.QuantumError")

**Raises**

**NoiseError** – If noise parameters are invalid.

