---
title: optimize_svm
description: API reference for qiskit.aqua.utils.optimize_svm
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.aqua.utils.optimize_svm
---

# optimize\_svm

<span id="qiskit.aqua.utils.optimize_svm" />

`optimize_svm(kernel_matrix, y, scaling=None, max_iters=500, show_progress=False)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/utils/qp_solver.py "view source code")

Solving quadratic programming problem for SVM; thus, some constraints are fixed.

**Parameters**

*   **kernel\_matrix** (`ndarray`) – NxN array
*   **y** (`ndarray`) – Nx1 array
*   **scaling** (`Optional`\[`float`]) – the scaling factor to renormalize the y, if it is None, use L2-norm of y for normalization
*   **max\_iters** (`int`) – number of iterations for QP solver
*   **show\_progress** (`bool`) – showing the progress of QP solver

**Returns**

Sx1 array, where S is the number of supports np.ndarray: Sx1 array, where S is the number of supports np.ndarray: Sx1 array, where S is the number of supports

**Return type**

np.ndarray

**Raises**

**NameError** – If cvxpy is not installed

