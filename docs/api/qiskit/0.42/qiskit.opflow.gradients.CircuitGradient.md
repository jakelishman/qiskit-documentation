---
title: CircuitGradient
description: API reference for qiskit.opflow.gradients.CircuitGradient
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.opflow.gradients.CircuitGradient
---

# CircuitGradient

<span id="qiskit.opflow.gradients.CircuitGradient" />

`CircuitGradient`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/gradients/circuit_gradients/circuit_gradient.py "view source code")

Bases: [`qiskit.opflow.converters.converter_base.ConverterBase`](qiskit.opflow.converters.ConverterBase "qiskit.opflow.converters.converter_base.ConverterBase")

Circuit to gradient operator converter.

Converter for changing parameterized circuits into operators whose evaluation yields the gradient with respect to the circuit parameters.

This is distinct from DerivativeBase converters which take gradients of composite operators and handle things like differentiating combo\_fn’s and enforcing product rules when operator coefficients are parameterized.

CircuitGradient - uses quantum techniques to get derivatives of circuits DerivativeBase - uses classical techniques to differentiate operator flow data structures

## Methods Defined Here

### convert

<span id="qiskit.opflow.gradients.CircuitGradient.convert" />

`abstract CircuitGradient.convert(operator, params=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/opflow/gradients/circuit_gradients/circuit_gradient.py "view source code")

**Parameters**

*   **operator** ([`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")) – The operator we are taking the gradient of
*   **params** (`Union`\[[`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression"), [`ParameterVector`](qiskit.circuit.ParameterVector "qiskit.circuit.parametervector.ParameterVector"), `List`\[[`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")], `Tuple`\[[`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression"), [`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")], `List`\[`Tuple`\[[`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression"), [`ParameterExpression`](qiskit.circuit.ParameterExpression "qiskit.circuit.parameterexpression.ParameterExpression")]], `None`]) – The parameters we are taking the gradient wrt: ω If a ParameterExpression, ParameterVector or List\[ParameterExpression] is given, then the 1st order derivative of the operator is calculated. If a Tuple\[ParameterExpression, ParameterExpression] or List\[Tuple\[ParameterExpression, ParameterExpression]] is given, then the 2nd order derivative of the operator is calculated.

**Return type**

[`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

**Returns**

An operator whose evaluation yields the Gradient.

**Raises**

**ValueError** – If `params` contains a parameter not present in `operator`.

