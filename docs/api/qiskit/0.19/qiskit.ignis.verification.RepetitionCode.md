---
title: RepetitionCode
description: API reference for qiskit.ignis.verification.RepetitionCode
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.ignis.verification.RepetitionCode
---

# RepetitionCode

<span id="qiskit.ignis.verification.RepetitionCode" />

`RepetitionCode(d, T=0)`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.3/qiskit/ignis/verification/topological_codes/circuits.py "view source code")

Implementation of a distance d repetition code, implemented over T syndrome measurement rounds.

Creates the circuits corresponding to a logical 0 and 1 encoded using a repetition code.

**Parameters**

*   **d** (*int*) – Number of code qubits (and hence repetitions) used.
*   **T** (*int*) – Number of rounds of ancilla-assisted syndrome measurement.

**Additional information:**

No measurements are added to the circuit if T=0. Otherwise T rounds are added, followed by measurement of the code qubits (corresponding to a logical measurement and final syndrome measurement round).

## Methods

### get\_circuit\_list

<span id="qiskit.ignis.verification.RepetitionCode.get_circuit_list" />

`RepetitionCode.get_circuit_list()`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.3/qiskit/ignis/verification/topological_codes/circuits.py "view source code")

**Returns**

self.circuit as a list, with circuit\_list\[0] = circuit\[‘0’] circuit\_list\[1] = circuit\[‘1’]

**Return type**

circuit\_list

### process\_results

<span id="qiskit.ignis.verification.RepetitionCode.process_results" />

`RepetitionCode.process_results(raw_results)`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.3/qiskit/ignis/verification/topological_codes/circuits.py "view source code")

**Parameters**

**raw\_results** (*dict*) – A dictionary whose keys are logical values, and whose values are standard counts dictionaries, (as obtained from the get\_counts method of a `qiskit.Result` object).

**Returns**

**Dictionary with the same structure as the input, but with**

the bit strings used as keys in the counts dictionaries converted to the form required by the decoder.

**Return type**

results

#### Additional information:

The circuits must be executed outside of this class, so that their is full freedom to compile, choose a backend, use a noise model, etc. The results from these executions should then be used to create the input for this method.

### readout

<span id="qiskit.ignis.verification.RepetitionCode.readout" />

`RepetitionCode.readout()`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.3/qiskit/ignis/verification/topological_codes/circuits.py "view source code")

Readout of all code qubits, which corresponds to a logical measurement as well as allowing for a measurement of the syndrome to be inferred.

### syndrome\_measurement

<span id="qiskit.ignis.verification.RepetitionCode.syndrome_measurement" />

`RepetitionCode.syndrome_measurement(reset=True, barrier=False)`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.3/qiskit/ignis/verification/topological_codes/circuits.py "view source code")

Application of a syndrome measurement round.

**Parameters**

*   **reset** (*bool*) – If set to true add a boolean at the end of each round
*   **barrier** (*bool*) – Boolean denoting whether to include a barrier at the end.

### x

<span id="qiskit.ignis.verification.RepetitionCode.x" />

`RepetitionCode.x(logs=('0', '1'), barrier=False)`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.3/qiskit/ignis/verification/topological_codes/circuits.py "view source code")

Applies a logical x to the circuits for the given logical values.

**Parameters**

*   **logs** (*list or tuple*) – List or tuple of logical values expressed as strings.
*   **barrier** (*bool*) – Boolean denoting whether to include a barrier at the end.

