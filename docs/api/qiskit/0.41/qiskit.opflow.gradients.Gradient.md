---
title: Gradient
description: API reference for qiskit.opflow.gradients.Gradient
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.opflow.gradients.Gradient
---

# Gradient

<span id="qiskit.opflow.gradients.Gradient" />

`Gradient(grad_method='param_shift', **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/gradients/gradient.py "view source code")

Bases: [`qiskit.opflow.gradients.gradient_base.GradientBase`](qiskit.opflow.gradients.GradientBase "qiskit.opflow.gradients.gradient_base.GradientBase")

Convert an operator expression to the first-order gradient.

**Parameters**

*   **grad\_method** (`Union`\[`str`, [`CircuitGradient`](qiskit.opflow.gradients.CircuitGradient "qiskit.opflow.gradients.circuit_gradients.circuit_gradient.CircuitGradient")]) – The method used to compute the state/probability gradient. Can be either `'param_shift'` or `'lin_comb'` or `'fin_diff'`. Ignored for gradients w\.r.t observable parameters.
*   **kwargs** (*dict*) – Optional parameters for a CircuitGradient

**Raises**

**ValueError** – If method != `fin_diff` and `epsilon` is not None.

## Methods Defined Here

### convert

<span id="qiskit.opflow.gradients.Gradient.convert" />

`Gradient.convert(operator, params=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/gradients/gradient.py "view source code")

**Parameters**

*   **operator** ([`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")) – The operator we are taking the gradient of.
*   **params** (`Union`\[[`ParameterVector`](qiskit.circuit.ParameterVector "qiskit.circuit.parametervector.ParameterVector"), [`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression"), `List`\[[`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")], `None`]) – The parameters we are taking the gradient with respect to. If not explicitly passed, they are inferred from the operator and sorted by name.

**Return type**

[`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

**Returns**

An operator whose evaluation yields the Gradient.

**Raises**

*   **ValueError** – If `params` contains a parameter not present in `operator`.
*   **ValueError** – If `operator` is not parameterized.

### get\_gradient

<span id="qiskit.opflow.gradients.Gradient.get_gradient" />

`Gradient.get_gradient(operator, params)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/gradients/gradient.py "view source code")

Get the gradient for the given operator w\.r.t. the given parameters

**Parameters**

*   **operator** ([`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")) – Operator w\.r.t. which we take the gradient.
*   **params** (`Union`\[[`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression"), [`ParameterVector`](qiskit.circuit.ParameterVector "qiskit.circuit.parametervector.ParameterVector"), `List`\[[`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")]]) – Parameters w\.r.t. which we compute the gradient.

**Return type**

[`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

**Returns**

Operator which represents the gradient w\.r.t. the given params.

**Raises**

*   **ValueError** – If `params` contains a parameter not present in `operator`.
*   [**OpflowError**](qiskit.opflow.OpflowError "qiskit.opflow.OpflowError") – If the coefficient of the operator could not be reduced to 1.
*   [**OpflowError**](qiskit.opflow.OpflowError "qiskit.opflow.OpflowError") – If the differentiation of a combo\_fn requires JAX but the package is not installed.
*   **TypeError** – If the operator does not include a StateFn given by a quantum circuit
*   **Exception** – Unintended code is reached
*   **MissingOptionalLibraryError** – jax not installed

## Attributes

<span id="qiskit.opflow.gradients.Gradient.grad_method" />

### grad\_method

Returns `CircuitGradient`.

**Return type**

[`CircuitGradient`](qiskit.opflow.gradients.CircuitGradient "qiskit.opflow.gradients.circuit_gradients.circuit_gradient.CircuitGradient")

**Returns**

`CircuitGradient`.

