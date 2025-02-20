---
title: QFIBase
description: API reference for qiskit.opflow.gradients.QFIBase
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.opflow.gradients.QFIBase
---

# QFIBase

<span id="qiskit.opflow.gradients.QFIBase" />

`qiskit.opflow.gradients.QFIBase(qfi_method='lin_comb_full')`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.25/qiskit/opflow/gradients/qfi_base.py "view source code")

Bases: [`DerivativeBase`](qiskit.opflow.gradients.DerivativeBase "qiskit.opflow.gradients.derivative_base.DerivativeBase")

Deprecated: Base class for Quantum Fisher Information (QFI).

Compute the Quantum Fisher Information (QFI) given a pure, parameterized quantum state.

The QFI is:

> \[QFI]kl= Re\[〈∂kψ|∂lψ〉−〈∂kψ|ψ〉〈ψ|∂lψ〉] \* 4.

<Admonition title="Deprecated since version 0.24.0" type="danger">
  The class `qiskit.opflow.gradients.qfi_base.QFIBase` is deprecated as of qiskit-terra 0.24.0. It will be removed no earlier than 3 months after the release date. For code migration guidelines, visit [https://qisk.it/opflow\_migration](https://qisk.it/opflow_migration).
</Admonition>

**Parameters**

**qfi\_method** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")  *|*[*CircuitQFI*](qiskit.opflow.gradients.CircuitQFI "qiskit.opflow.gradients.circuit_qfis.circuit_qfi.CircuitQFI")) – The method used to compute the state/probability gradient. Can be either a [`CircuitQFI`](qiskit.opflow.gradients.CircuitQFI "qiskit.opflow.gradients.CircuitQFI") instance or one of the following pre-defined strings `'lin_comb_full'`, `` 'overlap_diag'` `` or `` 'overlap_block_diag'` ``.

**Raises**

[**ValueError**](https://docs.python.org/3/library/exceptions.html#ValueError "(in Python v3.12)") – if `qfi_method` is neither a `CircuitQFI` object nor one of the predefined strings.

## Attributes

<span id="qiskit.opflow.gradients.QFIBase.qfi_method" />

### qfi\_method

Returns `CircuitQFI`.

**Returns**

`CircuitQFI`.

