---
title: L_BFGS_B
description: API reference for qiskit.algorithms.optimizers.L_BFGS_B
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.optimizers.L_BFGS_B
---

<span id="l-bfgs-b" />

# L\_BFGS\_B

<span id="qiskit.algorithms.optimizers.L_BFGS_B" />

`L_BFGS_B(maxfun=15000, maxiter=15000, ftol=2.220446049250313e-15, iprint=-1, eps=1e-08, options=None, max_evals_grouped=1, **kwargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/algorithms/optimizers/l_bfgs_b.py "view source code")

Bases: [`SciPyOptimizer`](qiskit.algorithms.optimizers.SciPyOptimizer "qiskit.algorithms.optimizers.scipy_optimizer.SciPyOptimizer")

Limited-memory BFGS Bound optimizer.

The target goal of Limited-memory Broyden-Fletcher-Goldfarb-Shanno Bound (L-BFGS-B) is to minimize the value of a differentiable scalar function $f$. This optimizer is a quasi-Newton method, meaning that, in contrast to Newtons’s method, it does not require $f$’s Hessian (the matrix of $f$’s second derivatives) when attempting to compute $f$’s minimum value.

Like BFGS, L-BFGS is an iterative method for solving unconstrained, non-linear optimization problems, but approximates BFGS using a limited amount of computer memory. L-BFGS starts with an initial estimate of the optimal value, and proceeds iteratively to refine that estimate with a sequence of better estimates.

The derivatives of $f$ are used to identify the direction of steepest descent, and also to form an estimate of the Hessian matrix (second derivative) of $f$. L-BFGS-B extends L-BFGS to handle simple, per-variable bound constraints.

Uses `scipy.optimize.fmin_l_bfgs_b`. For further detail, please refer to [https://docs.scipy.org/doc/scipy/reference/optimize.minimize-lbfgsb.html](https://docs.scipy.org/doc/scipy/reference/optimize.minimize-lbfgsb.html)

**Parameters**

*   **maxfun** (*int*) – Maximum number of function evaluations.
*   **maxiter** (*int*) – Maximum number of iterations.
*   **ftol** (*SupportsFloat*) – The iteration stops when $(f^k - f^{k+1}) / \max\{|f^k|, |f^{k+1}|,1\} \leq \text{ftol}$.
*   **iprint** (*int*) – Controls the frequency of output. `iprint < 0` means no output; `iprint = 0` print only one line at the last iteration; `0 < iprint < 99` print also $f$ and $|\text{proj} g|$ every iprint iterations; `iprint = 99` print details of every iteration except n-vectors; `iprint = 100` print also the changes of active set and final $x$; `iprint > 100` print details of every iteration including $x$ and $g$.
*   **eps** (*float*) – If jac is approximated, use this value for the step size.
*   **options** (*dict | None*) – A dictionary of solver options.
*   **max\_evals\_grouped** (*int*) – Max number of default gradient evaluations performed simultaneously.
*   **kwargs** – additional kwargs for `scipy.optimize.minimize`.

## Methods

<span id="qiskit-algorithms-optimizers-l-bfgs-b-get-support-level" />

### get\_support\_level

<span id="qiskit.algorithms.optimizers.L_BFGS_B.get_support_level" />

`L_BFGS_B.get_support_level()`

Return support level dictionary

<span id="qiskit-algorithms-optimizers-l-bfgs-b-gradient-num-diff" />

### gradient\_num\_diff

<span id="qiskit.algorithms.optimizers.L_BFGS_B.gradient_num_diff" />

`static L_BFGS_B.gradient_num_diff(x_center, f, epsilon, max_evals_grouped=None)`

We compute the gradient with the numeric differentiation in the parallel way, around the point x\_center.

**Parameters**

*   **x\_center** (*ndarray*) – point around which we compute the gradient
*   **f** (*func*) – the function of which the gradient is to be computed.
*   **epsilon** (*float*) – the epsilon used in the numeric differentiation.
*   **max\_evals\_grouped** (*int*) – max evals grouped, defaults to 1 (i.e. no batching).

**Returns**

the gradient computed

**Return type**

grad

<span id="qiskit-algorithms-optimizers-l-bfgs-b-minimize" />

### minimize

<span id="qiskit.algorithms.optimizers.L_BFGS_B.minimize" />

`L_BFGS_B.minimize(fun, x0, jac=None, bounds=None)`

Minimize the scalar function.

**Parameters**

*   **fun** (*Callable\[\[POINT], float]*) – The scalar function to minimize.
*   **x0** (*POINT*) – The initial point for the minimization.
*   **jac** (*Callable\[\[POINT], POINT] | None*) – The gradient of the scalar function `fun`.
*   **bounds** (*list\[tuple\[float, float]] | None*) – Bounds for the variables of `fun`. This argument might be ignored if the optimizer does not support bounds.

**Returns**

The result of the optimization, containing e.g. the result as attribute `x`.

**Return type**

[OptimizerResult](qiskit.algorithms.optimizers.OptimizerResult "qiskit.algorithms.optimizers.OptimizerResult")

<span id="qiskit-algorithms-optimizers-l-bfgs-b-print-options" />

### print\_options

<span id="qiskit.algorithms.optimizers.L_BFGS_B.print_options" />

`L_BFGS_B.print_options()`

Print algorithm-specific options.

<span id="qiskit-algorithms-optimizers-l-bfgs-b-set-max-evals-grouped" />

### set\_max\_evals\_grouped

<span id="qiskit.algorithms.optimizers.L_BFGS_B.set_max_evals_grouped" />

`L_BFGS_B.set_max_evals_grouped(limit)`

Set max evals grouped

<span id="qiskit-algorithms-optimizers-l-bfgs-b-set-options" />

### set\_options

<span id="qiskit.algorithms.optimizers.L_BFGS_B.set_options" />

`L_BFGS_B.set_options(**kwargs)`

Sets or updates values in the options dictionary.

The options dictionary may be used internally by a given optimizer to pass additional optional values for the underlying optimizer/optimization function used. The options dictionary may be initially populated with a set of key/values when the given optimizer is constructed.

**Parameters**

**kwargs** (*dict*) – options, given as name=value.

<span id="qiskit-algorithms-optimizers-l-bfgs-b-wrap-function" />

### wrap\_function

<span id="qiskit.algorithms.optimizers.L_BFGS_B.wrap_function" />

`static L_BFGS_B.wrap_function(function, args)`

Wrap the function to implicitly inject the args at the call of the function.

**Parameters**

*   **function** (*func*) – the target function
*   **args** (*tuple*) – the args to be injected

**Returns**

wrapper

**Return type**

function\_wrapper

## Attributes

<span id="qiskit.algorithms.optimizers.L_BFGS_B.bounds_support_level" />

### bounds\_support\_level

Returns bounds support level

<span id="qiskit.algorithms.optimizers.L_BFGS_B.gradient_support_level" />

### gradient\_support\_level

Returns gradient support level

<span id="qiskit.algorithms.optimizers.L_BFGS_B.initial_point_support_level" />

### initial\_point\_support\_level

Returns initial point support level

<span id="qiskit.algorithms.optimizers.L_BFGS_B.is_bounds_ignored" />

### is\_bounds\_ignored

Returns is bounds ignored

<span id="qiskit.algorithms.optimizers.L_BFGS_B.is_bounds_required" />

### is\_bounds\_required

Returns is bounds required

<span id="qiskit.algorithms.optimizers.L_BFGS_B.is_bounds_supported" />

### is\_bounds\_supported

Returns is bounds supported

<span id="qiskit.algorithms.optimizers.L_BFGS_B.is_gradient_ignored" />

### is\_gradient\_ignored

Returns is gradient ignored

<span id="qiskit.algorithms.optimizers.L_BFGS_B.is_gradient_required" />

### is\_gradient\_required

Returns is gradient required

<span id="qiskit.algorithms.optimizers.L_BFGS_B.is_gradient_supported" />

### is\_gradient\_supported

Returns is gradient supported

<span id="qiskit.algorithms.optimizers.L_BFGS_B.is_initial_point_ignored" />

### is\_initial\_point\_ignored

Returns is initial point ignored

<span id="qiskit.algorithms.optimizers.L_BFGS_B.is_initial_point_required" />

### is\_initial\_point\_required

Returns is initial point required

<span id="qiskit.algorithms.optimizers.L_BFGS_B.is_initial_point_supported" />

### is\_initial\_point\_supported

Returns is initial point supported

<span id="qiskit.algorithms.optimizers.L_BFGS_B.setting" />

### setting

Return setting

<span id="qiskit.algorithms.optimizers.L_BFGS_B.settings" />

### settings

