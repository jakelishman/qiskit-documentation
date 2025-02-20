---
title: COBYLA
description: API reference for qiskit.aqua.components.optimizers.COBYLA
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.components.optimizers.COBYLA
---

# COBYLA

<span id="qiskit.aqua.components.optimizers.COBYLA" />

`COBYLA(maxiter=1000, disp=False, rhobeg=1.0, tol=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/components/optimizers/cobyla.py "view source code")

Bases: `qiskit.aqua.components.optimizers.optimizer.Optimizer`

Constrained Optimization By Linear Approximation optimizer.

COBYLA is a numerical optimization method for constrained problems where the derivative of the objective function is not known.

Uses scipy.optimize.minimize COBYLA. For further detail, please refer to [https://docs.scipy.org/doc/scipy/reference/generated/scipy.optimize.minimize.html](https://docs.scipy.org/doc/scipy/reference/generated/scipy.optimize.minimize.html)

**Parameters**

*   **maxiter** (`int`) – Maximum number of function evaluations.
*   **disp** (`bool`) – Set to True to print convergence messages.
*   **rhobeg** (`float`) – Reasonable initial changes to the variables.
*   **tol** (`Optional`\[`float`]) – Final accuracy in the optimization (not precisely guaranteed). This is a lower bound on the size of the trust region.

## Methods

### get\_support\_level

<span id="qiskit.aqua.components.optimizers.COBYLA.get_support_level" />

`COBYLA.get_support_level()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/components/optimizers/cobyla.py "view source code")

Return support level dictionary

### gradient\_num\_diff

<span id="qiskit.aqua.components.optimizers.COBYLA.gradient_num_diff" />

`static COBYLA.gradient_num_diff(x_center, f, epsilon, max_evals_grouped=1)`

We compute the gradient with the numeric differentiation in the parallel way, around the point x\_center.

**Parameters**

*   **x\_center** (*ndarray*) – point around which we compute the gradient
*   **f** (*func*) – the function of which the gradient is to be computed.
*   **epsilon** (*float*) – the epsilon used in the numeric differentiation.
*   **max\_evals\_grouped** (*int*) – max evals grouped

**Returns**

the gradient computed

**Return type**

grad

### optimize

<span id="qiskit.aqua.components.optimizers.COBYLA.optimize" />

`COBYLA.optimize(num_vars, objective_function, gradient_function=None, variable_bounds=None, initial_point=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/components/optimizers/cobyla.py "view source code")

Perform optimization.

**Parameters**

*   **num\_vars** (*int*) – Number of parameters to be optimized.
*   **objective\_function** (*callable*) – A function that computes the objective function.
*   **gradient\_function** (*callable*) – A function that computes the gradient of the objective function, or None if not available.
*   **variable\_bounds** (*list\[(float, float)]*) – List of variable bounds, given as pairs (lower, upper). None means unbounded.
*   **initial\_point** (*numpy.ndarray\[float]*) – Initial point.

**Returns**

**point, value, nfev**

point: is a 1D numpy.ndarray\[float] containing the solution value: is a float with the objective function value nfev: number of objective function calls made if available or None

**Raises**

**ValueError** – invalid input

### print\_options

<span id="qiskit.aqua.components.optimizers.COBYLA.print_options" />

`COBYLA.print_options()`

Print algorithm-specific options.

### set\_max\_evals\_grouped

<span id="qiskit.aqua.components.optimizers.COBYLA.set_max_evals_grouped" />

`COBYLA.set_max_evals_grouped(limit)`

Set max evals grouped

### set\_options

<span id="qiskit.aqua.components.optimizers.COBYLA.set_options" />

`COBYLA.set_options(**kwargs)`

Sets or updates values in the options dictionary.

The options dictionary may be used internally by a given optimizer to pass additional optional values for the underlying optimizer/optimization function used. The options dictionary may be initially populated with a set of key/values when the given optimizer is constructed.

**Parameters**

**kwargs** (*dict*) – options, given as name=value.

### wrap\_function

<span id="qiskit.aqua.components.optimizers.COBYLA.wrap_function" />

`static COBYLA.wrap_function(function, args)`

Wrap the function to implicitly inject the args at the call of the function.

**Parameters**

*   **function** (*func*) – the target function
*   **args** (*tuple*) – the args to be injected

**Returns**

wrapper

**Return type**

function\_wrapper

## Attributes

<span id="qiskit.aqua.components.optimizers.COBYLA.bounds_support_level" />

### bounds\_support\_level

Returns bounds support level

<span id="qiskit.aqua.components.optimizers.COBYLA.gradient_support_level" />

### gradient\_support\_level

Returns gradient support level

<span id="qiskit.aqua.components.optimizers.COBYLA.initial_point_support_level" />

### initial\_point\_support\_level

Returns initial point support level

<span id="qiskit.aqua.components.optimizers.COBYLA.is_bounds_ignored" />

### is\_bounds\_ignored

Returns is bounds ignored

<span id="qiskit.aqua.components.optimizers.COBYLA.is_bounds_required" />

### is\_bounds\_required

Returns is bounds required

<span id="qiskit.aqua.components.optimizers.COBYLA.is_bounds_supported" />

### is\_bounds\_supported

Returns is bounds supported

<span id="qiskit.aqua.components.optimizers.COBYLA.is_gradient_ignored" />

### is\_gradient\_ignored

Returns is gradient ignored

<span id="qiskit.aqua.components.optimizers.COBYLA.is_gradient_required" />

### is\_gradient\_required

Returns is gradient required

<span id="qiskit.aqua.components.optimizers.COBYLA.is_gradient_supported" />

### is\_gradient\_supported

Returns is gradient supported

<span id="qiskit.aqua.components.optimizers.COBYLA.is_initial_point_ignored" />

### is\_initial\_point\_ignored

Returns is initial point ignored

<span id="qiskit.aqua.components.optimizers.COBYLA.is_initial_point_required" />

### is\_initial\_point\_required

Returns is initial point required

<span id="qiskit.aqua.components.optimizers.COBYLA.is_initial_point_supported" />

### is\_initial\_point\_supported

Returns is initial point supported

<span id="qiskit.aqua.components.optimizers.COBYLA.setting" />

### setting

Return setting

