---
title: GSLS
description: API reference for qiskit.algorithms.optimizers.GSLS
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.optimizers.GSLS
---

# GSLS

<span id="qiskit.algorithms.optimizers.GSLS" />

`qiskit.algorithms.optimizers.GSLS(maxiter=10000, max_eval=10000, disp=False, sampling_radius=1e-06, sample_size_factor=1, initial_step_size=0.01, min_step_size=1e-10, step_size_multiplier=0.4, armijo_parameter=0.1, min_gradient_norm=1e-08, max_failed_rejection_sampling=50)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.45/qiskit/algorithms/optimizers/gsls.py "view source code")

Bases: [`Optimizer`](qiskit.algorithms.optimizers.Optimizer "qiskit.algorithms.optimizers.optimizer.Optimizer")

Gaussian-smoothed Line Search.

An implementation of the line search algorithm described in [https://arxiv.org/pdf/1905.01332.pdf](https://arxiv.org/pdf/1905.01332.pdf), using gradient approximation based on Gaussian-smoothed samples on a sphere.

<Admonition title="Note" type="note">
  This component has some function that is normally random. If you want to reproduce behavior then you should set the random number generator seed in the algorithm\_globals (`qiskit.utils.algorithm_globals.random_seed = seed`).
</Admonition>

**Parameters**

*   **maxiter** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – Maximum number of iterations.
*   **max\_eval** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – Maximum number of evaluations.
*   **disp** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – Set to True to display convergence messages.
*   **sampling\_radius** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")) – Sampling radius to determine gradient estimate.
*   **sample\_size\_factor** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – The size of the sample set at each iteration is this number multiplied by the dimension of the problem, rounded to the nearest integer.
*   **initial\_step\_size** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")) – Initial step size for the descent algorithm.
*   **min\_step\_size** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")) – Minimum step size for the descent algorithm.
*   **step\_size\_multiplier** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")) – Step size reduction after unsuccessful steps, in the interval (0, 1).
*   **armijo\_parameter** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")) – Armijo parameter for sufficient decrease criterion, in the interval (0, 1).
*   **min\_gradient\_norm** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")) – If the gradient norm is below this threshold, the algorithm stops.
*   **max\_failed\_rejection\_sampling** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – Maximum number of attempts to sample points within bounds.

## Attributes

<span id="qiskit.algorithms.optimizers.GSLS.bounds_support_level" />

### bounds\_support\_level

Returns bounds support level

<span id="qiskit.algorithms.optimizers.GSLS.gradient_support_level" />

### gradient\_support\_level

Returns gradient support level

<span id="qiskit.algorithms.optimizers.GSLS.initial_point_support_level" />

### initial\_point\_support\_level

Returns initial point support level

<span id="qiskit.algorithms.optimizers.GSLS.is_bounds_ignored" />

### is\_bounds\_ignored

Returns is bounds ignored

<span id="qiskit.algorithms.optimizers.GSLS.is_bounds_required" />

### is\_bounds\_required

Returns is bounds required

<span id="qiskit.algorithms.optimizers.GSLS.is_bounds_supported" />

### is\_bounds\_supported

Returns is bounds supported

<span id="qiskit.algorithms.optimizers.GSLS.is_gradient_ignored" />

### is\_gradient\_ignored

Returns is gradient ignored

<span id="qiskit.algorithms.optimizers.GSLS.is_gradient_required" />

### is\_gradient\_required

Returns is gradient required

<span id="qiskit.algorithms.optimizers.GSLS.is_gradient_supported" />

### is\_gradient\_supported

Returns is gradient supported

<span id="qiskit.algorithms.optimizers.GSLS.is_initial_point_ignored" />

### is\_initial\_point\_ignored

Returns is initial point ignored

<span id="qiskit.algorithms.optimizers.GSLS.is_initial_point_required" />

### is\_initial\_point\_required

Returns is initial point required

<span id="qiskit.algorithms.optimizers.GSLS.is_initial_point_supported" />

### is\_initial\_point\_supported

Returns is initial point supported

<span id="qiskit.algorithms.optimizers.GSLS.setting" />

### setting

Return setting

<span id="qiskit.algorithms.optimizers.GSLS.settings" />

### settings

## Methods

### get\_support\_level

<span id="qiskit.algorithms.optimizers.GSLS.get_support_level" />

`get_support_level()`

Return support level dictionary.

**Returns**

A dictionary containing the support levels for different options.

**Return type**

[dict](https://docs.python.org/3/library/stdtypes.html#dict "(in Python v3.12)")\[[str](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)"), [int](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")]

### gradient\_approximation

<span id="qiskit.algorithms.optimizers.GSLS.gradient_approximation" />

`gradient_approximation(n, x, x_value, directions, sample_set_x, sample_set_y)`

Construct gradient approximation from given sample.

**Parameters**

*   **n** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – Dimension of the problem.
*   **x** ([*ndarray*](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.26)")) – Point around which the sample set was constructed.
*   **x\_value** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")) – Objective function value at x.
*   **directions** ([*ndarray*](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.26)")) – Directions of the sample points wrt the central point x, as a 2D array.
*   **sample\_set\_x** ([*ndarray*](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.26)")) – x-coordinates of the sample set, one point per row, as a 2D array.
*   **sample\_set\_y** ([*ndarray*](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.26)")) – Objective function values of the points in sample\_set\_x, as a 1D array.

**Returns**

Gradient approximation at x, as a 1D array.

**Return type**

[*ndarray*](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.26)")

### gradient\_num\_diff

<span id="qiskit.algorithms.optimizers.GSLS.gradient_num_diff" />

`static gradient_num_diff(x_center, f, epsilon, max_evals_grouped=None)`

We compute the gradient with the numeric differentiation in the parallel way, around the point x\_center.

**Parameters**

*   **x\_center** (*ndarray*) – point around which we compute the gradient
*   **f** (*func*) – the function of which the gradient is to be computed.
*   **epsilon** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")) – the epsilon used in the numeric differentiation.
*   **max\_evals\_grouped** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – max evals grouped, defaults to 1 (i.e. no batching).

**Returns**

the gradient computed

**Return type**

grad

### ls\_optimize

<span id="qiskit.algorithms.optimizers.GSLS.ls_optimize" />

`ls_optimize(n, obj_fun, initial_point, var_lb, var_ub)`

Run the line search optimization.

**Parameters**

*   **n** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – Dimension of the problem.
*   **obj\_fun** ([*Callable*](https://docs.python.org/3/library/collections.abc.html#collections.abc.Callable "(in Python v3.12)")*\[\[*[*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")  *|*[*ndarray*](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.26)")*],* [*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")*]*) – Objective function.
*   **initial\_point** ([*ndarray*](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.26)")) – Initial point.
*   **var\_lb** ([*ndarray*](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.26)")) – Vector of lower bounds on the decision variables. Vector elements can be -np.inf if the corresponding variable is unbounded from below.
*   **var\_ub** ([*ndarray*](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.26)")) – Vector of upper bounds on the decision variables. Vector elements can be np.inf if the corresponding variable is unbounded from below.

**Returns**

Final iterate as a vector, corresponding objective function value, number of evaluations, and norm of the gradient estimate.

**Raises**

[**ValueError**](https://docs.python.org/3/library/exceptions.html#ValueError "(in Python v3.12)") – If the number of dimensions mismatches the size of the initial point or the length of the lower or upper bound.

**Return type**

[tuple](https://docs.python.org/3/library/stdtypes.html#tuple "(in Python v3.12)")\[[numpy.ndarray](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.26)"), [float](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)"), [int](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)"), [float](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")]

### minimize

<span id="qiskit.algorithms.optimizers.GSLS.minimize" />

`minimize(fun, x0, jac=None, bounds=None)`

Minimize the scalar function.

**Parameters**

*   **fun** (*Callable\[\[POINT],* [*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")*]*) – The scalar function to minimize.
*   **x0** (*POINT*) – The initial point for the minimization.
*   **jac** (*Callable\[\[POINT], POINT] | None*) – The gradient of the scalar function `fun`.
*   **bounds** ([*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")*\[*[*tuple*](https://docs.python.org/3/library/stdtypes.html#tuple "(in Python v3.12)")*\[*[*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")*,* [*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")*]] | None*) – Bounds for the variables of `fun`. This argument might be ignored if the optimizer does not support bounds.

**Returns**

The result of the optimization, containing e.g. the result as attribute `x`.

**Return type**

[OptimizerResult](qiskit.algorithms.optimizers.OptimizerResult "qiskit.algorithms.optimizers.OptimizerResult")

### print\_options

<span id="qiskit.algorithms.optimizers.GSLS.print_options" />

`print_options()`

Print algorithm-specific options.

### sample\_points

<span id="qiskit.algorithms.optimizers.GSLS.sample_points" />

`sample_points(n, x, num_points)`

Sample `num_points` points around `x` on the `n`-sphere of specified radius.

The radius of the sphere is `self._options['sampling_radius']`.

**Parameters**

*   **n** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – Dimension of the problem.
*   **x** ([*ndarray*](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.26)")) – Point around which the sample set is constructed.
*   **num\_points** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – Number of points in the sample set.

**Returns**

A tuple containing the sampling points and the directions.

**Return type**

[tuple](https://docs.python.org/3/library/stdtypes.html#tuple "(in Python v3.12)")\[[numpy.ndarray](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.26)"), [numpy.ndarray](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.26)")]

### sample\_set

<span id="qiskit.algorithms.optimizers.GSLS.sample_set" />

`sample_set(n, x, var_lb, var_ub, num_points)`

Construct sample set of given size.

**Parameters**

*   **n** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – Dimension of the problem.
*   **x** ([*ndarray*](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.26)")) – Point around which the sample set is constructed.
*   **var\_lb** ([*ndarray*](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.26)")) – Vector of lower bounds on the decision variables. Vector elements can be -np.inf if the corresponding variable is unbounded from below.
*   **var\_ub** ([*ndarray*](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.26)")) – Vector of lower bounds on the decision variables. Vector elements can be np.inf if the corresponding variable is unbounded from above.
*   **num\_points** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – Number of points in the sample set.

**Returns**

Matrices of (unit-norm) sample directions and sample points, one per row. Both matrices are 2D arrays of floats.

**Raises**

[**RuntimeError**](https://docs.python.org/3/library/exceptions.html#RuntimeError "(in Python v3.12)") – If not enough samples could be generated within the bounds.

**Return type**

[tuple](https://docs.python.org/3/library/stdtypes.html#tuple "(in Python v3.12)")\[[numpy.ndarray](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.26)"), [numpy.ndarray](https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html#numpy.ndarray "(in NumPy v1.26)")]

### set\_max\_evals\_grouped

<span id="qiskit.algorithms.optimizers.GSLS.set_max_evals_grouped" />

`set_max_evals_grouped(limit)`

Set max evals grouped

### set\_options

<span id="qiskit.algorithms.optimizers.GSLS.set_options" />

`set_options(**kwargs)`

Sets or updates values in the options dictionary.

The options dictionary may be used internally by a given optimizer to pass additional optional values for the underlying optimizer/optimization function used. The options dictionary may be initially populated with a set of key/values when the given optimizer is constructed.

**Parameters**

**kwargs** ([*dict*](https://docs.python.org/3/library/stdtypes.html#dict "(in Python v3.12)")) – options, given as name=value.

### wrap\_function

<span id="qiskit.algorithms.optimizers.GSLS.wrap_function" />

`static wrap_function(function, args)`

Wrap the function to implicitly inject the args at the call of the function.

**Parameters**

*   **function** (*func*) – the target function
*   **args** ([*tuple*](https://docs.python.org/3/library/stdtypes.html#tuple "(in Python v3.12)")) – the args to be injected

**Returns**

wrapper

**Return type**

function\_wrapper

