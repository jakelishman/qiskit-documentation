---
title: PiecewiseChebyshev
description: API reference for qiskit.circuit.library.PiecewiseChebyshev
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.circuit.library.PiecewiseChebyshev
---

# PiecewiseChebyshev

<span id="qiskit.circuit.library.PiecewiseChebyshev" />

`PiecewiseChebyshev(f_x, degree=None, breakpoints=None, num_state_qubits=None, name='pw_cheb')`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/circuit/library/arithmetic/piecewise_chebyshev.py "view source code")

Bases: `qiskit.circuit.library.blueprintcircuit.BlueprintCircuit`

Piecewise Chebyshev approximation to an input function.

For a given function $f(x)$ and degree $d$, this class implements a piecewise polynomial Chebyshev approximation on $n$ qubits to $f(x)$ on the given intervals. All the polynomials in the approximation are of degree $d$.

The values of the parameters are calculated according to \[1] and see \[2] for a more detailed explanation of the circuit construction and how it acts on the qubits.

## Examples

```python
import numpy as np
from qiskit import QuantumCircuit
from qiskit.circuit.library.arithmetic.piecewise_chebyshev import PiecewiseChebyshev
f_x, degree, breakpoints, num_state_qubits = lambda x: np.arcsin(1 / x), 2, [2, 4], 2
pw_approximation = PiecewiseChebyshev(f_x, degree, breakpoints, num_state_qubits)
pw_approximation._build()
qc = QuantumCircuit(pw_approximation.num_qubits)
qc.h(list(range(num_state_qubits)))
qc.append(pw_approximation.to_instruction(), qc.qubits)
qc.draw(output='mpl')
```

![../\_images/qiskit-circuit-library-PiecewiseChebyshev-1.png](/images/api/qiskit/0.41/qiskit-circuit-library-PiecewiseChebyshev-1.png)

## References

**\[1]: Haener, T., Roetteler, M., & Svore, K. M. (2018).**

Optimizing Quantum Circuits for Arithmetic. [arXiv:1805.12445](http://arxiv.org/abs/1805.12445)

**\[2]: Carrera Vazquez, A., Hiptmair, H., & Woerner, S. (2022).**

Enhancing the Quantum Linear Systems Algorithm Using Richardson Extrapolation. [ACM Transactions on Quantum Computing 3, 1, Article 2](https://doi.org/10.1145/3490631)

**Parameters**

*   **f\_x** (`Union`\[`float`, `Callable`\[\[`int`], `float`]]) – the function to be approximated. Constant functions should be specified as f\_x = constant.
*   **degree** (`Optional`\[`int`]) – the degree of the polynomials. Defaults to `1`.
*   **breakpoints** (`Optional`\[`List`\[`int`]]) – the breakpoints to define the piecewise-linear function. Defaults to the full interval.
*   **num\_state\_qubits** (`Optional`\[`int`]) – number of qubits representing the state.
*   **name** (`str`) – The name of the circuit object.

## Attributes

<span id="qiskit.circuit.library.PiecewiseChebyshev.ancillas" />

### ancillas

Returns a list of ancilla bits in the order that the registers were added.

**Return type**

`List`\[[`AncillaQubit`](qiskit.circuit.AncillaQubit "qiskit.circuit.quantumregister.AncillaQubit")]

<span id="qiskit.circuit.library.PiecewiseChebyshev.breakpoints" />

### breakpoints

The breakpoints for the piecewise approximation.

**Return type**

`List`\[`int`]

**Returns**

The breakpoints for the piecewise approximation.

<span id="qiskit.circuit.library.PiecewiseChebyshev.calibrations" />

### calibrations

Return calibration dictionary.

The custom pulse definition of a given gate is of the form `{'gate_name': {(qubits, params): schedule}}`

**Return type**

`dict`

<span id="qiskit.circuit.library.PiecewiseChebyshev.clbits" />

### clbits

Returns a list of classical bits in the order that the registers were added.

**Return type**

`List`\[[`Clbit`](qiskit.circuit.Clbit "qiskit.circuit.classicalregister.Clbit")]

<span id="qiskit.circuit.library.PiecewiseChebyshev.data" />

### data

<span id="qiskit.circuit.library.PiecewiseChebyshev.degree" />

### degree

The degree of the polynomials.

**Return type**

`int`

**Returns**

The degree of the polynomials.

<span id="qiskit.circuit.library.PiecewiseChebyshev.extension_lib" />

### extension\_lib

`= 'include "qelib1.inc";'`

<span id="qiskit.circuit.library.PiecewiseChebyshev.f_x" />

### f\_x

The function to be approximated.

**Return type**

`Union`\[`float`, `Callable`\[\[`int`], `float`]]

**Returns**

The function to be approximated.

<span id="qiskit.circuit.library.PiecewiseChebyshev.global_phase" />

### global\_phase

Return the global phase of the circuit in radians.

**Return type**

`Union`\[[`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression"), `float`]

<span id="qiskit.circuit.library.PiecewiseChebyshev.header" />

### header

`= 'OPENQASM 2.0;'`

<span id="qiskit.circuit.library.PiecewiseChebyshev.instances" />

### instances

`= 2242`

<span id="qiskit.circuit.library.PiecewiseChebyshev.metadata" />

### metadata

The user provided metadata associated with the circuit

The metadata for the circuit is a user provided `dict` of metadata for the circuit. It will not be used to influence the execution or operation of the circuit, but it is expected to be passed between all transforms of the circuit (ie transpilation) and that providers will associate any circuit metadata with the results it returns from execution of that circuit.

**Return type**

`dict`

<span id="qiskit.circuit.library.PiecewiseChebyshev.num_ancillas" />

### num\_ancillas

Return the number of ancilla qubits.

**Return type**

`int`

<span id="qiskit.circuit.library.PiecewiseChebyshev.num_clbits" />

### num\_clbits

Return number of classical bits.

**Return type**

`int`

<span id="qiskit.circuit.library.PiecewiseChebyshev.num_parameters" />

### num\_parameters

**Return type**

`int`

<span id="qiskit.circuit.library.PiecewiseChebyshev.num_qubits" />

### num\_qubits

Return number of qubits.

**Return type**

`int`

<span id="qiskit.circuit.library.PiecewiseChebyshev.num_state_qubits" />

### num\_state\_qubits

The number of state qubits representing the state $|x\rangle$.

**Return type**

`int`

**Returns**

The number of state qubits.

<span id="qiskit.circuit.library.PiecewiseChebyshev.op_start_times" />

### op\_start\_times

Return a list of operation start times.

This attribute is enabled once one of scheduling analysis passes runs on the quantum circuit.

**Return type**

`List`\[`int`]

**Returns**

List of integers representing instruction start times. The index corresponds to the index of instruction in `QuantumCircuit.data`.

**Raises**

**AttributeError** – When circuit is not scheduled.

<span id="qiskit.circuit.library.PiecewiseChebyshev.parameters" />

### parameters

**Return type**

`ParameterView`

<span id="qiskit.circuit.library.PiecewiseChebyshev.polynomials" />

### polynomials

The polynomials for the piecewise approximation.

**Return type**

`List`\[`List`\[`float`]]

**Returns**

The polynomials for the piecewise approximation.

**Raises**

**TypeError** – If the input function is not in the correct format.

<span id="qiskit.circuit.library.PiecewiseChebyshev.prefix" />

### prefix

`= 'circuit'`

<span id="qiskit.circuit.library.PiecewiseChebyshev.qregs" />

### qregs

A list of the quantum registers associated with the circuit.

<span id="qiskit.circuit.library.PiecewiseChebyshev.qubits" />

### qubits

Returns a list of quantum bits in the order that the registers were added.

**Return type**

`List`\[[`Qubit`](qiskit.circuit.Qubit "qiskit.circuit.quantumregister.Qubit")]

