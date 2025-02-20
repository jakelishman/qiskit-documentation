---
title: DIRECT_L_RAND
description: API reference for qiskit.algorithms.optimizers.DIRECT_L_RAND
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.optimizers.DIRECT_L_RAND
---

# qiskit.algorithms.optimizers.DIRECT\_L\_RAND

<span id="qiskit.algorithms.optimizers.DIRECT_L_RAND" />

`DIRECT_L_RAND(max_evals=1000)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.18/qiskit/algorithms/optimizers/nlopts/direct_l_rand.py "view source code")

DIviding RECTangles Locally-biased Randomized optimizer.

DIRECT-L RAND is the “locally biased” variant with some randomization in near-tie decisions. See also [`DIRECT_L`](qiskit.algorithms.optimizers.DIRECT_L "qiskit.algorithms.optimizers.DIRECT_L")

NLopt global optimizer, derivative-free. For further detail, please refer to [http://nlopt.readthedocs.io/en/latest/NLopt\_Algorithms/#direct-and-direct-l](http://nlopt.readthedocs.io/en/latest/NLopt_Algorithms/#direct-and-direct-l)

**Parameters**

**max\_evals** (`int`) – Maximum allowed number of function evaluations.

**Raises**

[**MissingOptionalLibraryError**](qiskit.aqua.MissingOptionalLibraryError "qiskit.aqua.MissingOptionalLibraryError") – NLopt library not installed.

### \_\_init\_\_

<span id="qiskit.algorithms.optimizers.DIRECT_L_RAND.__init__" />

`__init__(max_evals=1000)`

**Parameters**

**max\_evals** (`int`) – Maximum allowed number of function evaluations.

**Raises**

[**MissingOptionalLibraryError**](qiskit.aqua.MissingOptionalLibraryError "qiskit.aqua.MissingOptionalLibraryError") – NLopt library not installed.

## Methods

|                                                                                                                                                                                  |                                                                                                           |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.algorithms.optimizers.DIRECT_L_RAND.__init__ "qiskit.algorithms.optimizers.DIRECT_L_RAND.__init__")(\[max\_evals])                                          | **type max\_evals**`int`                                                                                  |
| [`get_nlopt_optimizer`](#qiskit.algorithms.optimizers.DIRECT_L_RAND.get_nlopt_optimizer "qiskit.algorithms.optimizers.DIRECT_L_RAND.get_nlopt_optimizer")()                      | Return NLopt optimizer type                                                                               |
| [`get_support_level`](#qiskit.algorithms.optimizers.DIRECT_L_RAND.get_support_level "qiskit.algorithms.optimizers.DIRECT_L_RAND.get_support_level")()                            | return support level dictionary                                                                           |
| [`gradient_num_diff`](#qiskit.algorithms.optimizers.DIRECT_L_RAND.gradient_num_diff "qiskit.algorithms.optimizers.DIRECT_L_RAND.gradient_num_diff")(x\_center, f, epsilon\[, …]) | We compute the gradient with the numeric differentiation in the parallel way, around the point x\_center. |
| [`optimize`](#qiskit.algorithms.optimizers.DIRECT_L_RAND.optimize "qiskit.algorithms.optimizers.DIRECT_L_RAND.optimize")(num\_vars, objective\_function\[, …])                   | Perform optimization.                                                                                     |
| [`print_options`](#qiskit.algorithms.optimizers.DIRECT_L_RAND.print_options "qiskit.algorithms.optimizers.DIRECT_L_RAND.print_options")()                                        | Print algorithm-specific options.                                                                         |
| [`set_max_evals_grouped`](#qiskit.algorithms.optimizers.DIRECT_L_RAND.set_max_evals_grouped "qiskit.algorithms.optimizers.DIRECT_L_RAND.set_max_evals_grouped")(limit)           | Set max evals grouped                                                                                     |
| [`set_options`](#qiskit.algorithms.optimizers.DIRECT_L_RAND.set_options "qiskit.algorithms.optimizers.DIRECT_L_RAND.set_options")(\*\*kwargs)                                    | Sets or updates values in the options dictionary.                                                         |
| [`wrap_function`](#qiskit.algorithms.optimizers.DIRECT_L_RAND.wrap_function "qiskit.algorithms.optimizers.DIRECT_L_RAND.wrap_function")(function, args)                          | Wrap the function to implicitly inject the args at the call of the function.                              |

## Attributes

|                                                                                                                                                                                   |                                                |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------- |
| [`bounds_support_level`](#qiskit.algorithms.optimizers.DIRECT_L_RAND.bounds_support_level "qiskit.algorithms.optimizers.DIRECT_L_RAND.bounds_support_level")                      | Returns bounds support level                   |
| [`gradient_support_level`](#qiskit.algorithms.optimizers.DIRECT_L_RAND.gradient_support_level "qiskit.algorithms.optimizers.DIRECT_L_RAND.gradient_support_level")                | Returns gradient support level                 |
| [`initial_point_support_level`](#qiskit.algorithms.optimizers.DIRECT_L_RAND.initial_point_support_level "qiskit.algorithms.optimizers.DIRECT_L_RAND.initial_point_support_level") | Returns initial point support level            |
| [`is_bounds_ignored`](#qiskit.algorithms.optimizers.DIRECT_L_RAND.is_bounds_ignored "qiskit.algorithms.optimizers.DIRECT_L_RAND.is_bounds_ignored")                               | Returns is bounds ignored                      |
| [`is_bounds_required`](#qiskit.algorithms.optimizers.DIRECT_L_RAND.is_bounds_required "qiskit.algorithms.optimizers.DIRECT_L_RAND.is_bounds_required")                            | Returns is bounds required                     |
| [`is_bounds_supported`](#qiskit.algorithms.optimizers.DIRECT_L_RAND.is_bounds_supported "qiskit.algorithms.optimizers.DIRECT_L_RAND.is_bounds_supported")                         | Returns is bounds supported                    |
| [`is_gradient_ignored`](#qiskit.algorithms.optimizers.DIRECT_L_RAND.is_gradient_ignored "qiskit.algorithms.optimizers.DIRECT_L_RAND.is_gradient_ignored")                         | Returns is gradient ignored                    |
| [`is_gradient_required`](#qiskit.algorithms.optimizers.DIRECT_L_RAND.is_gradient_required "qiskit.algorithms.optimizers.DIRECT_L_RAND.is_gradient_required")                      | Returns is gradient required                   |
| [`is_gradient_supported`](#qiskit.algorithms.optimizers.DIRECT_L_RAND.is_gradient_supported "qiskit.algorithms.optimizers.DIRECT_L_RAND.is_gradient_supported")                   | Returns is gradient supported                  |
| [`is_initial_point_ignored`](#qiskit.algorithms.optimizers.DIRECT_L_RAND.is_initial_point_ignored "qiskit.algorithms.optimizers.DIRECT_L_RAND.is_initial_point_ignored")          | Returns is initial point ignored               |
| [`is_initial_point_required`](#qiskit.algorithms.optimizers.DIRECT_L_RAND.is_initial_point_required "qiskit.algorithms.optimizers.DIRECT_L_RAND.is_initial_point_required")       | Returns is initial point required              |
| [`is_initial_point_supported`](#qiskit.algorithms.optimizers.DIRECT_L_RAND.is_initial_point_supported "qiskit.algorithms.optimizers.DIRECT_L_RAND.is_initial_point_supported")    | Returns is initial point supported             |
| [`setting`](#qiskit.algorithms.optimizers.DIRECT_L_RAND.setting "qiskit.algorithms.optimizers.DIRECT_L_RAND.setting")                                                             | Return setting                                 |
| [`settings`](#qiskit.algorithms.optimizers.DIRECT_L_RAND.settings "qiskit.algorithms.optimizers.DIRECT_L_RAND.settings")                                                          | The optimizer settings in a dictionary format. |

### bounds\_support\_level

<span id="qiskit.algorithms.optimizers.DIRECT_L_RAND.bounds_support_level" />

`property bounds_support_level`

Returns bounds support level

### get\_nlopt\_optimizer

<span id="qiskit.algorithms.optimizers.DIRECT_L_RAND.get_nlopt_optimizer" />

`get_nlopt_optimizer()`

Return NLopt optimizer type

**Return type**

`NLoptOptimizerType`

### get\_support\_level

<span id="qiskit.algorithms.optimizers.DIRECT_L_RAND.get_support_level" />

`get_support_level()`

return support level dictionary

### gradient\_num\_diff

<span id="qiskit.algorithms.optimizers.DIRECT_L_RAND.gradient_num_diff" />

`static gradient_num_diff(x_center, f, epsilon, max_evals_grouped=1)`

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

### gradient\_support\_level

<span id="qiskit.algorithms.optimizers.DIRECT_L_RAND.gradient_support_level" />

`property gradient_support_level`

Returns gradient support level

### initial\_point\_support\_level

<span id="qiskit.algorithms.optimizers.DIRECT_L_RAND.initial_point_support_level" />

`property initial_point_support_level`

Returns initial point support level

### is\_bounds\_ignored

<span id="qiskit.algorithms.optimizers.DIRECT_L_RAND.is_bounds_ignored" />

`property is_bounds_ignored`

Returns is bounds ignored

### is\_bounds\_required

<span id="qiskit.algorithms.optimizers.DIRECT_L_RAND.is_bounds_required" />

`property is_bounds_required`

Returns is bounds required

### is\_bounds\_supported

<span id="qiskit.algorithms.optimizers.DIRECT_L_RAND.is_bounds_supported" />

`property is_bounds_supported`

Returns is bounds supported

### is\_gradient\_ignored

<span id="qiskit.algorithms.optimizers.DIRECT_L_RAND.is_gradient_ignored" />

`property is_gradient_ignored`

Returns is gradient ignored

### is\_gradient\_required

<span id="qiskit.algorithms.optimizers.DIRECT_L_RAND.is_gradient_required" />

`property is_gradient_required`

Returns is gradient required

### is\_gradient\_supported

<span id="qiskit.algorithms.optimizers.DIRECT_L_RAND.is_gradient_supported" />

`property is_gradient_supported`

Returns is gradient supported

### is\_initial\_point\_ignored

<span id="qiskit.algorithms.optimizers.DIRECT_L_RAND.is_initial_point_ignored" />

`property is_initial_point_ignored`

Returns is initial point ignored

### is\_initial\_point\_required

<span id="qiskit.algorithms.optimizers.DIRECT_L_RAND.is_initial_point_required" />

`property is_initial_point_required`

Returns is initial point required

### is\_initial\_point\_supported

<span id="qiskit.algorithms.optimizers.DIRECT_L_RAND.is_initial_point_supported" />

`property is_initial_point_supported`

Returns is initial point supported

### optimize

<span id="qiskit.algorithms.optimizers.DIRECT_L_RAND.optimize" />

`optimize(num_vars, objective_function, gradient_function=None, variable_bounds=None, initial_point=None)`

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

<span id="qiskit.algorithms.optimizers.DIRECT_L_RAND.print_options" />

`print_options()`

Print algorithm-specific options.

### set\_max\_evals\_grouped

<span id="qiskit.algorithms.optimizers.DIRECT_L_RAND.set_max_evals_grouped" />

`set_max_evals_grouped(limit)`

Set max evals grouped

### set\_options

<span id="qiskit.algorithms.optimizers.DIRECT_L_RAND.set_options" />

`set_options(**kwargs)`

Sets or updates values in the options dictionary.

The options dictionary may be used internally by a given optimizer to pass additional optional values for the underlying optimizer/optimization function used. The options dictionary may be initially populated with a set of key/values when the given optimizer is constructed.

**Parameters**

**kwargs** (*dict*) – options, given as name=value.

### setting

<span id="qiskit.algorithms.optimizers.DIRECT_L_RAND.setting" />

`property setting`

Return setting

### settings

<span id="qiskit.algorithms.optimizers.DIRECT_L_RAND.settings" />

`property settings`

The optimizer settings in a dictionary format.

The settings can for instance be used for JSON-serialization (if all settings are serializable, which e.g. doesn’t hold per default for callables), such that the optimizer object can be reconstructed as

```python
settings = optimizer.settings
# JSON serialize and send to another server
optimizer = OptimizerClass(**settings)
```

### wrap\_function

<span id="qiskit.algorithms.optimizers.DIRECT_L_RAND.wrap_function" />

`static wrap_function(function, args)`

Wrap the function to implicitly inject the args at the call of the function.

**Parameters**

*   **function** (*func*) – the target function
*   **args** (*tuple*) – the args to be injected

**Returns**

wrapper

**Return type**

function\_wrapper

