---
title: GradientDescent
description: API reference for qiskit.algorithms.optimizers.GradientDescent
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.optimizers.GradientDescent
---

# GradientDescent

<span id="qiskit.algorithms.optimizers.GradientDescent" />

`GradientDescent(maxiter=100, learning_rate=0.01, tol=1e-07, callback=None, perturbation=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/optimizers/gradient_descent.py "view source code")

Bases: [`qiskit.algorithms.optimizers.steppable_optimizer.SteppableOptimizer`](qiskit.algorithms.optimizers.SteppableOptimizer "qiskit.algorithms.optimizers.steppable_optimizer.SteppableOptimizer")

The gradient descent minimization routine.

For a function $f$ and an initial point $\vec\theta_0$, the standard (or “vanilla”) gradient descent method is an iterative scheme to find the minimum $\vec\theta^*$ of $f$ by updating the parameters in the direction of the negative gradient of $f$

$$
\vec\theta_{n+1} = \vec\theta_{n} - \eta_n \vec\nabla f(\vec\theta_{n}),
$$

for a small learning rate $\eta_n > 0$.

You can either provide the analytic gradient $\vec\nabla f$ as `jac` in the [`minimize()`](qiskit.algorithms.optimizers.GradientDescent#minimize "qiskit.algorithms.optimizers.GradientDescent.minimize") method, or, if you do not provide it, use a finite difference approximation of the gradient. To adapt the size of the perturbation in the finite difference gradients, set the `perturbation` property in the initializer.

This optimizer supports a callback function. If provided in the initializer, the optimizer will call the callback in each iteration with the following information in this order: current number of function values, current parameters, current function value, norm of current gradient.

## Examples

A minimum example that will use finite difference gradients with a default perturbation of 0.01 and a default learning rate of 0.01.

```python
from qiskit.algorithms.optimizers import GradientDescent

def f(x):
    return (np.linalg.norm(x) - 1) ** 2

initial_point = np.array([1, 0.5, -0.2])

optimizer = GradientDescent(maxiter=100)

result = optimizer.minimize(fun=fun, x0=initial_point)

print(f"Found minimum {result.x} at a value"
    "of {result.fun} using {result.nfev} evaluations.")
```

An example where the learning rate is an iterator and we supply the analytic gradient. Note how much faster this convergences (i.e. less `nfev`) compared to the previous example.

```python
from qiskit.algorithms.optimizers import GradientDescent

def learning_rate():
    power = 0.6
    constant_coeff = 0.1
    def powerlaw():
        n = 0
        while True:
            yield constant_coeff * (n ** power)
            n += 1

    return powerlaw()

def f(x):
    return (np.linalg.norm(x) - 1) ** 2

def grad_f(x):
    return 2 * (np.linalg.norm(x) - 1) * x / np.linalg.norm(x)

initial_point = np.array([1, 0.5, -0.2])

optimizer = GradientDescent(maxiter=100, learning_rate=learning_rate)
result = optimizer.minimize(fun=fun, jac=grad_f, x0=initial_point)

print(f"Found minimum {result.x} at a value"
"of {result.fun} using {result.nfev} evaluations.")
```

An other example where the evaluation of the function has a chance of failing. The user, with specific knowledge about his function can catch this errors and handle them before passing the result to the optimizer.

> ```python
> import random
> import numpy as np
> from qiskit.algorithms.optimizers import GradientDescent
>
> def objective(x):
>     if random.choice([True, False]):
>         return None
>     else:
>         return (np.linalg.norm(x) - 1) ** 2
>
> def grad(x):
>     if random.choice([True, False]):
>         return None
>     else:
>         return 2 * (np.linalg.norm(x) - 1) * x / np.linalg.norm(x)
>
>
> initial_point = np.random.normal(0, 1, size=(100,))
>
> optimizer = GradientDescent(maxiter=20)
> optimizer.start(x0=initial_point, fun=objective, jac=grad)
>
> while optimizer.continue_condition():
>     ask_data = optimizer.ask()
>     evaluated_gradient = None
>
>     while evaluated_gradient is None:
>         evaluated_gradient = grad(ask_data.x_center)
>         optimizer.state.njev += 1
>
>     optmizer.state.nit += 1
>
>     tell_data = TellData(eval_jac=evaluated_gradient)
>     optimizer.tell(ask_data=ask_data, tell_data=tell_data)
>
> result = optimizer.create_result()
> ```

Users that aren’t dealing with complicated functions and who are more familiar with step by step optimization algorithms can use the [`step()`](qiskit.algorithms.optimizers.GradientDescent#step "qiskit.algorithms.optimizers.GradientDescent.step") method which wraps the [`ask()`](qiskit.algorithms.optimizers.GradientDescent#ask "qiskit.algorithms.optimizers.GradientDescent.ask") and [`tell()`](qiskit.algorithms.optimizers.GradientDescent#tell "qiskit.algorithms.optimizers.GradientDescent.tell") methods. In the same spirit the method [`minimize()`](qiskit.algorithms.optimizers.GradientDescent#minimize "qiskit.algorithms.optimizers.GradientDescent.minimize") will optimize the function and return the result.

To see other libraries that use this interface one can visit: [https://optuna.readthedocs.io/en/stable/tutorial/20\_recipes/009\_ask\_and\_tell.html](https://optuna.readthedocs.io/en/stable/tutorial/20_recipes/009_ask_and_tell.html)

**Parameters**

*   **maxiter** (`int`) – The maximum number of iterations.
*   **learning\_rate** (`Union`\[`float`, `List`\[`float`], `ndarray`, `Callable`\[\[], `Iterator`]]) – A constant, list, array or factory of generators yielding learning rates for the parameter updates. See the docstring for an example.
*   **tol** (`float`) – If the norm of the parameter update is smaller than this threshold, the optimizer has converged.
*   **perturbation** (`Optional`\[`float`]) – If no gradient is passed to [`minimize()`](qiskit.algorithms.optimizers.GradientDescent#minimize "qiskit.algorithms.optimizers.GradientDescent.minimize") the gradient is approximated with a forward finite difference scheme with `perturbation` perturbation in both directions (defaults to 1e-2 if required). Ignored when we have an explicit function for the gradient.

**Raises**

**ValueError** – If `learning_rate` is an array and its lenght is less than `maxiter`.

## Methods

### ask

<span id="qiskit.algorithms.optimizers.GradientDescent.ask" />

`GradientDescent.ask()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/optimizers/gradient_descent.py "view source code")

Returns an object with the data needed to evaluate the gradient.

If this object contains a gradient function the gradient can be evaluated directly. Otherwise approximate it with a finite difference scheme.

**Return type**

[`AskData`](qiskit.algorithms.optimizers.AskData "qiskit.algorithms.optimizers.steppable_optimizer.AskData")

### continue\_condition

<span id="qiskit.algorithms.optimizers.GradientDescent.continue_condition" />

`GradientDescent.continue_condition()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/optimizers/gradient_descent.py "view source code")

Condition that indicates the optimization process should come to an end.

When the stepsize is smaller than the tolerance, the optimization process is considered finished.

**Return type**

`bool`

**Returns**

`True` if the optimization process should continue, `False` otherwise.

### create\_result

<span id="qiskit.algorithms.optimizers.GradientDescent.create_result" />

`GradientDescent.create_result()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/optimizers/gradient_descent.py "view source code")

Creates a result of the optimization process.

This result contains the best point, the best function value, the number of function/gradient evaluations and the number of iterations.

**Return type**

[`OptimizerResult`](qiskit.algorithms.optimizers.OptimizerResult "qiskit.algorithms.optimizers.optimizer.OptimizerResult")

**Returns**

The result of the optimization process.

### evaluate

<span id="qiskit.algorithms.optimizers.GradientDescent.evaluate" />

`GradientDescent.evaluate(ask_data)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/optimizers/gradient_descent.py "view source code")

Evaluates the gradient.

It does so either by evaluating an analytic gradient or by approximating it with a finite difference scheme. It will either add `1` to the number of gradient evaluations or add `N+1` to the number of function evaluations (Where N is the dimension of the gradient).

**Parameters**

**ask\_data** ([`AskData`](qiskit.algorithms.optimizers.AskData "qiskit.algorithms.optimizers.steppable_optimizer.AskData")) – It contains the point where the gradient is to be evaluated and the gradient function or, in its absence, the objective function to perform a finite difference approximation.

**Return type**

[`TellData`](qiskit.algorithms.optimizers.TellData "qiskit.algorithms.optimizers.steppable_optimizer.TellData")

**Returns**

The data containing the gradient evaluation.

### get\_support\_level

<span id="qiskit.algorithms.optimizers.GradientDescent.get_support_level" />

`GradientDescent.get_support_level()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/optimizers/gradient_descent.py "view source code")

Get the support level dictionary.

### gradient\_num\_diff

<span id="qiskit.algorithms.optimizers.GradientDescent.gradient_num_diff" />

`static GradientDescent.gradient_num_diff(x_center, f, epsilon, max_evals_grouped=None)`

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

### minimize

<span id="qiskit.algorithms.optimizers.GradientDescent.minimize" />

`GradientDescent.minimize(fun, x0, jac=None, bounds=None)`

Minimizes the function.

For well behaved functions the user can call this method to minimize a function. If the user wants more control on how to evaluate the function a custom loop can be created using [`ask()`](qiskit.algorithms.optimizers.GradientDescent#ask "qiskit.algorithms.optimizers.GradientDescent.ask") and [`tell()`](qiskit.algorithms.optimizers.GradientDescent#tell "qiskit.algorithms.optimizers.GradientDescent.tell") and evaluating the function manually.

**Parameters**

*   **fun** (`Callable`\[\[`Union`\[`float`, `ndarray`]], `float`]) – Function to minimize.
*   **x0** (`Union`\[`float`, `ndarray`]) – Initial point.
*   **jac** (`Optional`\[`Callable`\[\[`Union`\[`float`, `ndarray`]], `Union`\[`float`, `ndarray`]]]) – Function to compute the gradient.
*   **bounds** (`Optional`\[`List`\[`Tuple`\[`float`, `float`]]]) – Bounds of the search space.

**Return type**

[`OptimizerResult`](qiskit.algorithms.optimizers.OptimizerResult "qiskit.algorithms.optimizers.optimizer.OptimizerResult")

**Returns**

Object containing the result of the optimization.

### print\_options

<span id="qiskit.algorithms.optimizers.GradientDescent.print_options" />

`GradientDescent.print_options()`

Print algorithm-specific options.

### set\_max\_evals\_grouped

<span id="qiskit.algorithms.optimizers.GradientDescent.set_max_evals_grouped" />

`GradientDescent.set_max_evals_grouped(limit)`

Set max evals grouped

### set\_options

<span id="qiskit.algorithms.optimizers.GradientDescent.set_options" />

`GradientDescent.set_options(**kwargs)`

Sets or updates values in the options dictionary.

The options dictionary may be used internally by a given optimizer to pass additional optional values for the underlying optimizer/optimization function used. The options dictionary may be initially populated with a set of key/values when the given optimizer is constructed.

**Parameters**

**kwargs** (*dict*) – options, given as name=value.

### start

<span id="qiskit.algorithms.optimizers.GradientDescent.start" />

`GradientDescent.start(fun, x0, jac=None, bounds=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/optimizers/gradient_descent.py "view source code")

Populates the state of the optimizer with the data provided and sets all the counters to 0.

**Parameters**

*   **fun** (`Callable`\[\[`Union`\[`float`, `ndarray`]], `float`]) – Function to minimize.
*   **x0** (`Union`\[`float`, `ndarray`]) – Initial point.
*   **jac** (`Optional`\[`Callable`\[\[`Union`\[`float`, `ndarray`]], `Union`\[`float`, `ndarray`]]]) – Function to compute the gradient.
*   **bounds** (`Optional`\[`List`\[`Tuple`\[`float`, `float`]]]) – Bounds of the search space.

**Return type**

`None`

### step

<span id="qiskit.algorithms.optimizers.GradientDescent.step" />

`GradientDescent.step()`

Performs one step in the optimization process.

This method composes [`ask()`](qiskit.algorithms.optimizers.GradientDescent#ask "qiskit.algorithms.optimizers.GradientDescent.ask"), [`evaluate()`](qiskit.algorithms.optimizers.GradientDescent#evaluate "qiskit.algorithms.optimizers.GradientDescent.evaluate"), and [`tell()`](qiskit.algorithms.optimizers.GradientDescent#tell "qiskit.algorithms.optimizers.GradientDescent.tell") to make a “step” in the optimization process.

**Return type**

`None`

### tell

<span id="qiskit.algorithms.optimizers.GradientDescent.tell" />

`GradientDescent.tell(ask_data, tell_data)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/optimizers/gradient_descent.py "view source code")

Updates `x` by an ammount proportional to the learning rate and value of the gradient at that point.

**Parameters**

*   **ask\_data** ([`AskData`](qiskit.algorithms.optimizers.AskData "qiskit.algorithms.optimizers.steppable_optimizer.AskData")) – The data used to evaluate the function.
*   **tell\_data** ([`TellData`](qiskit.algorithms.optimizers.TellData "qiskit.algorithms.optimizers.steppable_optimizer.TellData")) – The data from the function evaluation.

**Raises**

**ValueError** – If the gradient passed doesn’t have the right dimension.

**Return type**

`None`

### wrap\_function

<span id="qiskit.algorithms.optimizers.GradientDescent.wrap_function" />

`static GradientDescent.wrap_function(function, args)`

Wrap the function to implicitly inject the args at the call of the function.

**Parameters**

*   **function** (*func*) – the target function
*   **args** (*tuple*) – the args to be injected

**Returns**

wrapper

**Return type**

function\_wrapper

## Attributes

<span id="qiskit.algorithms.optimizers.GradientDescent.bounds_support_level" />

### bounds\_support\_level

Returns bounds support level

<span id="qiskit.algorithms.optimizers.GradientDescent.gradient_support_level" />

### gradient\_support\_level

Returns gradient support level

<span id="qiskit.algorithms.optimizers.GradientDescent.initial_point_support_level" />

### initial\_point\_support\_level

Returns initial point support level

<span id="qiskit.algorithms.optimizers.GradientDescent.is_bounds_ignored" />

### is\_bounds\_ignored

Returns is bounds ignored

<span id="qiskit.algorithms.optimizers.GradientDescent.is_bounds_required" />

### is\_bounds\_required

Returns is bounds required

<span id="qiskit.algorithms.optimizers.GradientDescent.is_bounds_supported" />

### is\_bounds\_supported

Returns is bounds supported

<span id="qiskit.algorithms.optimizers.GradientDescent.is_gradient_ignored" />

### is\_gradient\_ignored

Returns is gradient ignored

<span id="qiskit.algorithms.optimizers.GradientDescent.is_gradient_required" />

### is\_gradient\_required

Returns is gradient required

<span id="qiskit.algorithms.optimizers.GradientDescent.is_gradient_supported" />

### is\_gradient\_supported

Returns is gradient supported

<span id="qiskit.algorithms.optimizers.GradientDescent.is_initial_point_ignored" />

### is\_initial\_point\_ignored

Returns is initial point ignored

<span id="qiskit.algorithms.optimizers.GradientDescent.is_initial_point_required" />

### is\_initial\_point\_required

Returns is initial point required

<span id="qiskit.algorithms.optimizers.GradientDescent.is_initial_point_supported" />

### is\_initial\_point\_supported

Returns is initial point supported

<span id="qiskit.algorithms.optimizers.GradientDescent.perturbation" />

### perturbation

Returns the perturbation.

This is the perturbation used in the finite difference gradient approximation.

**Return type**

`Optional`\[`float`]

<span id="qiskit.algorithms.optimizers.GradientDescent.setting" />

### setting

Return setting

<span id="qiskit.algorithms.optimizers.GradientDescent.settings" />

### settings

**Return type**

`Dict`\[`str`, `Any`]

<span id="qiskit.algorithms.optimizers.GradientDescent.state" />

### state

Return the current state of the optimizer.

**Return type**

[`GradientDescentState`](qiskit.algorithms.optimizers.GradientDescentState "qiskit.algorithms.optimizers.gradient_descent.GradientDescentState")

<span id="qiskit.algorithms.optimizers.GradientDescent.tol" />

### tol

Returns the tolerance of the optimizer.

Any step with smaller stepsize than this value will stop the optimization.

**Return type**

`float`

