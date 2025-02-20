---
title: OptimizerState
description: API reference for qiskit.algorithms.optimizers.OptimizerState
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.optimizers.OptimizerState
---

# OptimizerState

<span id="qiskit.algorithms.optimizers.OptimizerState" />

`OptimizerState(x, fun, jac, nfev, njev, nit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/optimizers/steppable_optimizer.py "view source code")

Bases: `object`

Base class representing the state of the optimizer.

This class stores the current state of the optimizer, given by the current point and (optionally) information like the function value, the gradient or the number of function evaluations. This dataclass can also store any other individual variables that change during the optimization.

## Attributes

<span id="qiskit.algorithms.optimizers.OptimizerState.x" />

### x

`Union[float, numpy.ndarray]`

Current optimization parameters.

<span id="qiskit.algorithms.optimizers.OptimizerState.fun" />

### fun

`Optional[Callable[[Union[float, numpy.ndarray]], float]]`

Function being optimized.

<span id="qiskit.algorithms.optimizers.OptimizerState.jac" />

### jac

`Optional[Callable[[Union[float, numpy.ndarray]], Union[float, numpy.ndarray]]]`

Jacobian of the function being optimized.

<span id="qiskit.algorithms.optimizers.OptimizerState.nfev" />

### nfev

`Optional[int]`

Number of function evaluations so far in the optimization.

<span id="qiskit.algorithms.optimizers.OptimizerState.njev" />

### njev

`Optional[int]`

Number of jacobian evaluations so far in the opimization.

<span id="qiskit.algorithms.optimizers.OptimizerState.nit" />

### nit

`Optional[int]`

Number of optmization steps performed so far in the optimization.

