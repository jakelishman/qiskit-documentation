---
title: CircuitQFI
description: API reference for qiskit.opflow.gradients.CircuitQFI
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.opflow.gradients.CircuitQFI
---

# qiskit.opflow\.gradients.CircuitQFI

<span id="qiskit.opflow.gradients.CircuitQFI" />

`CircuitQFI`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/opflow/gradients/circuit_qfis/circuit_qfi.py "view source code")

Circuit to Quantum Fisher Information operator converter.

Converter for changing parameterized circuits into operators whose evaluation yields Quantum Fisher Information metric tensor with respect to the given circuit parameters

This is distinct from DerivativeBase converters which take gradients of composite operators and handle things like differentiating combo\_fn’s and enforcing product rules when operator coefficients are parameterized.

CircuitQFI - uses quantum techniques to get the QFI of circuits DerivativeBase - uses classical techniques to differentiate opflow data structures

### \_\_init\_\_

<span id="qiskit.opflow.gradients.CircuitQFI.__init__" />

`__init__()`

Initialize self. See help(type(self)) for accurate signature.

## Methods

|                                                                                                                         |                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------- |
| [`__init__`](#qiskit.opflow.gradients.CircuitQFI.__init__ "qiskit.opflow.gradients.CircuitQFI.__init__")()              | Initialize self.                |
| [`convert`](#qiskit.opflow.gradients.CircuitQFI.convert "qiskit.opflow.gradients.CircuitQFI.convert")(operator, params) | **type operator**`OperatorBase` |

### convert

<span id="qiskit.opflow.gradients.CircuitQFI.convert" />

`abstract convert(operator, params)`

**Parameters**

*   **operator** (`OperatorBase`) – The operator corresponding to the quantum state $|\psi(\omega)\rangle$ for which we compute the QFI.
*   **params** (`Union`\[`ParameterExpression`, `ParameterVector`, `List`\[`ParameterExpression`]]) – The parameters $\omega$ with respect to which we are computing the QFI.

**Return type**

`OperatorBase`

**Returns**

An operator whose evaluation yields the QFI metric tensor.

**Raises**

**ValueError** – If `params` contains a parameter not present in `operator`.

