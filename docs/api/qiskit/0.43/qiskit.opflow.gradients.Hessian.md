---
title: Hessian
description: API reference for qiskit.opflow.gradients.Hessian
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.opflow.gradients.Hessian
---

# Hessian

<span id="qiskit.opflow.gradients.Hessian" />

`Hessian(hess_method='param_shift', **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/gradients/hessian.py "view source code")

Bases: [`HessianBase`](qiskit.opflow.gradients.HessianBase "qiskit.opflow.gradients.hessian_base.HessianBase")

Deprecated: Compute the Hessian of an expected value.

<Admonition title="Deprecated since version 0.24.0" type="danger">
  The class `qiskit.opflow.gradients.hessian.Hessian` is deprecated as of qiskit-terra 0.24.0. It will be removed no earlier than 3 months after the release date. For code migration guidelines, visit [https://qisk.it/opflow\_migration](https://qisk.it/opflow_migration).
</Admonition>

## Methods Defined Here

<span id="qiskit-opflow-gradients-hessian-convert" />

### convert

<span id="qiskit.opflow.gradients.Hessian.convert" />

`Hessian.convert(operator, params=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/gradients/hessian.py "view source code")

**Parameters**

*   **operator** ([*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")) – The operator for which we compute the Hessian
*   **params** (*Tuple\[*[*ParameterExpression*](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")*,* [*ParameterExpression*](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")*] | List\[Tuple\[*[*ParameterExpression*](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")*,* [*ParameterExpression*](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")*]] | List\[*[*ParameterExpression*](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")*] |* [*ParameterVector*](qiskit.circuit.ParameterVector "qiskit.circuit.parametervector.ParameterVector") *| None*) – The parameters we are computing the Hessian with respect to Either give directly the tuples/list of tuples for which the second order derivative is to be computed or give a list of parameters to build the full Hessian for those parameters. If not explicitly passed, the full Hessian is constructed. The parameters are then inferred from the operator and sorted by name.

**Returns**

An operator whose evaluation yields the Hessian

**Return type**

[OperatorBase](qiskit.opflow.OperatorBase "qiskit.opflow.OperatorBase")

<span id="qiskit-opflow-gradients-hessian-get-hessian" />

### get\_hessian

<span id="qiskit.opflow.gradients.Hessian.get_hessian" />

`Hessian.get_hessian(operator, params=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/opflow/gradients/hessian.py "view source code")

Get the Hessian for the given operator w\.r.t. the given parameters

**Parameters**

*   **operator** ([*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")) – Operator w\.r.t. which we take the Hessian.
*   **params** (*Tuple\[*[*ParameterExpression*](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")*,* [*ParameterExpression*](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")*] | List\[Tuple\[*[*ParameterExpression*](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")*,* [*ParameterExpression*](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")*]] | List\[*[*ParameterExpression*](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")*] |* [*ParameterVector*](qiskit.circuit.ParameterVector "qiskit.circuit.parametervector.ParameterVector") *| None*) – Parameters w\.r.t. which we compute the Hessian. If not explicitly passed, the full Hessian is constructed. The parameters are then inferred from the operator and sorted by name.

**Returns**

Operator which represents the gradient w\.r.t. the given params.

**Raises**

*   **ValueError** – If `params` contains a parameter not present in `operator`.
*   **ValueError** – If `operator` is not parameterized.
*   [**OpflowError**](qiskit.opflow.OpflowError "qiskit.opflow.OpflowError") – If the coefficient of the operator could not be reduced to 1.
*   [**OpflowError**](qiskit.opflow.OpflowError "qiskit.opflow.OpflowError") – If the differentiation of a combo\_fn requires JAX but the package is not installed.
*   **TypeError** – If the operator does not include a StateFn given by a quantum circuit
*   **TypeError** – If the parameters were given in an unsupported format.
*   **Exception** – Unintended code is reached
*   **MissingOptionalLibraryError** – jax not installed

**Return type**

[*OperatorBase*](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

## Attributes

<span id="qiskit.opflow.gradients.Hessian.hess_method" />

### hess\_method

Returns `CircuitGradient`.

**Returns**

`CircuitGradient`.

