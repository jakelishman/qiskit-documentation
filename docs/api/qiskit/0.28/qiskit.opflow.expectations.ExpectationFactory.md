---
title: ExpectationFactory
description: API reference for qiskit.opflow.expectations.ExpectationFactory
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.opflow.expectations.ExpectationFactory
---

# qiskit.opflow\.expectations.ExpectationFactory

<span id="qiskit.opflow.expectations.ExpectationFactory" />

`ExpectationFactory`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/opflow/expectations/expectation_factory.py "view source code")

A factory class for convenient automatic selection of an Expectation based on the Operator to be converted and backend used to sample the expectation value.

### \_\_init\_\_

<span id="qiskit.opflow.expectations.ExpectationFactory.__init__" />

`__init__()`

Initialize self. See help(type(self)) for accurate signature.

## Methods

|                                                                                                                                                              |                                                                                                                                                               |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.opflow.expectations.ExpectationFactory.__init__ "qiskit.opflow.expectations.ExpectationFactory.__init__")()                             | Initialize self.                                                                                                                                              |
| [`build`](#qiskit.opflow.expectations.ExpectationFactory.build "qiskit.opflow.expectations.ExpectationFactory.build")(operator\[, backend, include\_custom]) | A factory method for convenient automatic selection of an Expectation based on the Operator to be converted and backend used to sample the expectation value. |

### build

<span id="qiskit.opflow.expectations.ExpectationFactory.build" />

`static build(operator, backend=None, include_custom=True)`

A factory method for convenient automatic selection of an Expectation based on the Operator to be converted and backend used to sample the expectation value.

**Parameters**

*   **operator** (`OperatorBase`) – The Operator whose expectation value will be taken.
*   **backend** (`Union`\[`Backend`, `BaseBackend`, `QuantumInstance`, `None`]) – The backend which will be used to sample the expectation value.
*   **include\_custom** (`bool`) – Whether the factory will include the (Aer) specific custom expectations if their behavior against the backend might not be as expected. For instance when using Aer qasm\_simulator with paulis the Aer snapshot can be used but the outcome lacks shot noise and hence does not intuitively behave overall as people might expect when choosing a qasm\_simulator. It is however fast as long as the more state vector like behavior is acceptable.

**Return type**

`ExpectationBase`

**Returns**

The expectation algorithm which best fits the Operator and backend.

**Raises**

**ValueError** – If operator is not of a composition for which we know the best Expectation method.

