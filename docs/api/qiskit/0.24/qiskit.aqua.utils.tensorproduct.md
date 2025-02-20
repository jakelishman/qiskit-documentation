---
title: tensorproduct
description: API reference for qiskit.aqua.utils.tensorproduct
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.aqua.utils.tensorproduct
---

<span id="qiskit-aqua-utils-tensorproduct" />

# qiskit.aqua.utils.tensorproduct

<span id="qiskit.aqua.utils.tensorproduct" />

`tensorproduct(*args)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.8/qiskit/aqua/utils/tensor_product.py "view source code")

Calculate tensor product.

m = tensorproduct(a,b,c,…) returns the kronecker product of its arguments. Each argument should either be a tensor, or a tuple containing a tensor and an integer, and tensor is put in zero-index slot. In the latter case, the integer specifies the repeat count for the tensor, e.g. tensorproduct(a,(b,3),c) = tensorproduct(a,b,b,b,c).

**Parameters**

**args** (*-*) –

**Returns**

the tensor product

**Return type**

np.ndarray

