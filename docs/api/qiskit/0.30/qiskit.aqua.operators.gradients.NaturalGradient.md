---
title: NaturalGradient
description: API reference for qiskit.aqua.operators.gradients.NaturalGradient
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.operators.gradients.NaturalGradient
---

# NaturalGradient

<span id="qiskit.aqua.operators.gradients.NaturalGradient" />

`NaturalGradient(grad_method='lin_comb', qfi_method='lin_comb_full', regularization=None, **kwargs)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/gradients/natural_gradient.py "view source code")

Bases: `qiskit.aqua.operators.gradients.gradient_base.GradientBase`

Convert an operator expression to the first-order gradient.

Given an ill-posed inverse problem

> x = arg min\{||Ax-C||^2} (1)

one can use regularization schemes can be used to stabilize the system and find a numerical solution

> x\_lambda = arg min\{||Ax-C||^2 + lambda\*R(x)} (2)

where R(x) represents the penalization term.

**Parameters**

*   **grad\_method** (`Union`\[`str`, `CircuitGradient`]) – The method used to compute the state gradient. Can be either `'param_shift'` or `'lin_comb'` or `'fin_diff'`.
*   **qfi\_method** (`Union`\[`str`, `CircuitQFI`]) – The method used to compute the QFI. Can be either `'lin_comb_full'` or `'overlap_block_diag'` or `'overlap_diag'`.
*   **regularization** (`Optional`\[`str`]) – Use the following regularization with a least square method to solve the underlying system of linear equations Can be either None or `'ridge'` or `'lasso'` or `'perturb_diag'` `'ridge'` and `'lasso'` use an automatic optimal parameter search If regularization is None but the metric is ill-conditioned or singular then a least square solver is used without regularization
*   **kwargs** (*dict*) – Optional parameters for a CircuitGradient

## Methods

### convert

<span id="qiskit.aqua.operators.gradients.NaturalGradient.convert" />

`NaturalGradient.convert(operator, params=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/gradients/natural_gradient.py "view source code")

**Parameters**

*   **operator** (`OperatorBase`) – The operator we are taking the gradient of.
*   **params** (`Union`\[`ParameterVector`, `ParameterExpression`, `List`\[`ParameterExpression`], `None`]) – The parameters we are taking the gradient with respect to.

**Return type**

`OperatorBase`

**Returns**

An operator whose evaluation yields the NaturalGradient.

**Raises**

*   **TypeError** – If `operator` does not represent an expectation value or the quantum state is not `CircuitStateFn`.
*   **ValueError** – If `params` contains a parameter not present in `operator`.

### gradient\_wrapper

<span id="qiskit.aqua.operators.gradients.NaturalGradient.gradient_wrapper" />

`NaturalGradient.gradient_wrapper(operator, bind_params, grad_params=None, backend=None)`

Get a callable function which provides the respective gradient, Hessian or QFI for given parameter values. This callable can be used as gradient function for optimizers.

**Parameters**

*   **operator** (`OperatorBase`) – The operator for which we want to get the gradient, Hessian or QFI.
*   **bind\_params** (`Union`\[`ParameterExpression`, `ParameterVector`, `List`\[`ParameterExpression`]]) – The operator parameters to which the parameter values are assigned.
*   **grad\_params** (`Union`\[`ParameterExpression`, `ParameterVector`, `List`\[`ParameterExpression`], `Tuple`\[`ParameterExpression`, `ParameterExpression`], `List`\[`Tuple`\[`ParameterExpression`, `ParameterExpression`]], `None`]) – The parameters with respect to which we are taking the gradient, Hessian or QFI. If grad\_params = None, then grad\_params = bind\_params
*   **backend** (`Union`\[`BaseBackend`, `QuantumInstance`, `None`]) – The quantum backend or QuantumInstance to use to evaluate the gradient, Hessian or QFI.

**Returns**

Function to compute a gradient, Hessian or QFI. The function takes an iterable as argument which holds the parameter values.

**Return type**

callable(param\_values)

### parameter\_expression\_grad

<span id="qiskit.aqua.operators.gradients.NaturalGradient.parameter_expression_grad" />

`static NaturalGradient.parameter_expression_grad(param_expr, param)`

Get the derivative of a parameter expression w\.r.t. the given parameter.

**Parameters**

*   **param\_expr** (`ParameterExpression`) – The Parameter Expression for which we compute the derivative
*   **param** (`ParameterExpression`) – Parameter w\.r.t. which we want to take the derivative

**Return type**

`Union`\[`ParameterExpression`, `float`]

**Returns**

ParameterExpression representing the gradient of param\_expr w\.r.t. param

## Attributes

<span id="qiskit.aqua.operators.gradients.NaturalGradient.grad_method" />

### grad\_method

Returns `CircuitGradient`.

**Return type**

`CircuitGradient`

**Returns**

`CircuitGradient`.

<span id="qiskit.aqua.operators.gradients.NaturalGradient.qfi_method" />

### qfi\_method

Returns `CircuitQFI`.

Returns: `CircuitQFI`

**Return type**

`CircuitQFI`

<span id="qiskit.aqua.operators.gradients.NaturalGradient.regularization" />

### regularization

Returns the regularization option.

Returns: the regularization option.

**Return type**

`Optional`\[`str`]

