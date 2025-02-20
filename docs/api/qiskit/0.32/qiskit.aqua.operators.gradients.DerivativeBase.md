---
title: DerivativeBase
description: API reference for qiskit.aqua.operators.gradients.DerivativeBase
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.operators.gradients.DerivativeBase
---

# DerivativeBase

<span id="qiskit.aqua.operators.gradients.DerivativeBase" />

`DerivativeBase`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/gradients/derivative_base.py "view source code")

Bases: `qiskit.aqua.operators.converters.converter_base.ConverterBase`

Base class for differentiating opflow objects.

Converter for differentiating opflow objects and handling things like properly differentiating combo\_fn’s and enforcing product rules when operator coefficients are parameterized.

This is distinct from CircuitGradient converters which use quantum techniques such as parameter shifts and linear combination of unitaries to compute derivatives of circuits.

CircuitGradient - uses quantum techniques to get derivatives of circuits DerivativeBase - uses classical techniques to differentiate opflow data structures

## Methods

### convert

<span id="qiskit.aqua.operators.gradients.DerivativeBase.convert" />

`abstract DerivativeBase.convert(operator, params=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/gradients/derivative_base.py "view source code")

**Parameters**

*   **operator** (`OperatorBase`) – The operator we are taking the gradient, Hessian or QFI of
*   **params** (`Union`\[`ParameterVector`, `ParameterExpression`, `List`\[`ParameterExpression`], `None`]) – The parameters we are taking the gradient, Hessian or QFI with respect to.

**Return type**

`OperatorBase`

**Returns**

An operator whose evaluation yields the gradient, Hessian or QFI.

**Raises**

**ValueError** – If `params` contains a parameter not present in `operator`.

### gradient\_wrapper

<span id="qiskit.aqua.operators.gradients.DerivativeBase.gradient_wrapper" />

`DerivativeBase.gradient_wrapper(operator, bind_params, grad_params=None, backend=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/gradients/derivative_base.py "view source code")

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

<span id="qiskit.aqua.operators.gradients.DerivativeBase.parameter_expression_grad" />

`static DerivativeBase.parameter_expression_grad(param_expr, param)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/operators/gradients/derivative_base.py "view source code")

Get the derivative of a parameter expression w\.r.t. the given parameter.

**Parameters**

*   **param\_expr** (`ParameterExpression`) – The Parameter Expression for which we compute the derivative
*   **param** (`ParameterExpression`) – Parameter w\.r.t. which we want to take the derivative

**Return type**

`Union`\[`ParameterExpression`, `float`]

**Returns**

ParameterExpression representing the gradient of param\_expr w\.r.t. param

