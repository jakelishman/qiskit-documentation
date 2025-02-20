---
title: extensions
description: API reference for qiskit.extensions
in_page_toc_min_heading_level: 1
python_api_type: module
python_api_name: qiskit.extensions
---

<span id="module-qiskit.extensions" />

<span id="qiskit-extensions" />

<span id="quantum-circuit-extensions-qiskit-extensions" />

# Quantum Circuit Extensions

<span id="module-qiskit.extensions" />

`qiskit.extensions`

## Unitary Extensions

|                                                                                                                                    |                       |
| ---------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| [`SingleQubitUnitary`](qiskit.extensions.SingleQubitUnitary "qiskit.extensions.SingleQubitUnitary")(unitary\_matrix\[, mode, ...]) | Single-qubit unitary. |

## Simulator Extensions

|                                                                                                                   |                                 |
| ----------------------------------------------------------------------------------------------------------------- | ------------------------------- |
| [`Snapshot`](qiskit.extensions.Snapshot "qiskit.extensions.Snapshot")(label\[, snapshot\_type, num\_qubits, ...]) | Simulator snapshot instruction. |

## Exceptions

The additional gates in this module will tend to raise a custom exception when they encounter problems.

<span id="qiskit.extensions.ExtensionError" />

`qiskit.extensions.ExtensionError(*message)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/extensions/exceptions.py "view source code")

Base class for errors raised by extensions module.

Set the error message.

<Admonition title="Deprecated since version 0.45.0_pending" type="danger">
  The class `qiskit.extensions.exceptions.ExtensionError` is pending deprecation as of qiskit 0.45.0. It will be marked deprecated in a future release, and then removed no earlier than 3 months after the release date.
</Admonition>

