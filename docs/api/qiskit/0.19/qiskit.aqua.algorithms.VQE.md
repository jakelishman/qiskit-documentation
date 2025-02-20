---
title: VQE
description: API reference for qiskit.aqua.algorithms.VQE
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.algorithms.VQE
---

# VQE

<span id="qiskit.aqua.algorithms.VQE" />

`VQE(operator=None, var_form=None, optimizer=None, initial_point=None, expectation=None, include_custom=False, max_evals_grouped=1, aux_operators=None, callback=None, quantum_instance=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/minimum_eigen_solvers/vqe.py "view source code")

The Variational Quantum Eigensolver algorithm.

[VQE](https://arxiv.org/abs/1304.3061) is a hybrid algorithm that uses a variational technique and interleaves quantum and classical computations in order to find the minimum eigenvalue of the Hamiltonian $H$ of a given system.

An instance of VQE requires defining two algorithmic sub-components: a trial state (ansatz) from Aqua’s [`variational_forms`](qiskit.aqua.components.variational_forms#module-qiskit.aqua.components.variational_forms "qiskit.aqua.components.variational_forms"), and one of the classical [`optimizers`](qiskit.aqua.components.optimizers#module-qiskit.aqua.components.optimizers "qiskit.aqua.components.optimizers"). The ansatz is varied, via its set of parameters, by the optimizer, such that it works towards a state, as determined by the parameters applied to the variational form, that will result in the minimum expectation value being measured of the input operator (Hamiltonian).

An optional array of parameter values, via the *initial\_point*, may be provided as the starting point for the search of the minimum eigenvalue. This feature is particularly useful such as when there are reasons to believe that the solution point is close to a particular point. As an example, when building the dissociation profile of a molecule, it is likely that using the previous computed optimal solution as the starting initial point for the next interatomic distance is going to reduce the number of iterations necessary for the variational algorithm to converge. Aqua provides an [initial point tutorial](https://github.com/Qiskit/qiskit-tutorials-community/blob/master/chemistry/h2_vqe_initial_point.ipynb) detailing this use case.

The length of the *initial\_point* list value must match the number of the parameters expected by the variational form being used. If the *initial\_point* is left at the default of `None`, then VQE will look to the variational form for a preferred value, based on its given initial state. If the variational form returns `None`, then a random point will be generated within the parameter bounds set, as per above. If the variational form provides `None` as the lower bound, then VQE will default it to $-2\pi$; similarly, if the variational form returns `None` as the upper bound, the default value will be $2\pi$.

<Admonition title="Note" type="note">
  The VQE stores the parameters of `var_form` sorted by name to map the values provided by the optimizer to the circuit. This is done to ensure reproducible results, for example such that running the optimization twice with same random seeds yields the same result. Also, the `optimal_point` of the result object can be used as initial point of another VQE run by passing it as `initial_point` to the initializer.
</Admonition>

**Parameters**

*   **operator** (`Union`\[[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase"), [`LegacyBaseOperator`](qiskit.aqua.operators.legacy.LegacyBaseOperator "qiskit.aqua.operators.legacy.base_operator.LegacyBaseOperator"), `None`]) – Qubit operator of the Observable
*   **var\_form** (`Union`\[[`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit"), [`VariationalForm`](qiskit.aqua.components.variational_forms.VariationalForm "qiskit.aqua.components.variational_forms.variational_form.VariationalForm"), `None`]) – A parameterized circuit used as Ansatz for the wave function.
*   **optimizer** (`Optional`\[[`Optimizer`](qiskit.aqua.components.optimizers.Optimizer "qiskit.aqua.components.optimizers.optimizer.Optimizer")]) – A classical optimizer.
*   **initial\_point** (`Optional`\[`ndarray`]) – An optional initial point (i.e. initial parameter values) for the optimizer. If `None` then VQE will look to the variational form for a preferred point and if not will simply compute a random one.
*   **expectation** (`Optional`\[[`ExpectationBase`](qiskit.aqua.operators.expectations.ExpectationBase "qiskit.aqua.operators.expectations.expectation_base.ExpectationBase")]) – The Expectation converter for taking the average value of the Observable over the var\_form state function. When `None` (the default) an [`ExpectationFactory`](qiskit.aqua.operators.expectations.ExpectationFactory "qiskit.aqua.operators.expectations.ExpectationFactory") is used to select an appropriate expectation based on the operator and backend. When using Aer qasm\_simulator backend, with paulis, it is however much faster to leverage custom Aer function for the computation but, although VQE performs much faster with it, the outcome is ideal, with no shot noise, like using a state vector simulator. If you are just looking for the quickest performance when choosing Aer qasm\_simulator and the lack of shot noise is not an issue then set include\_custom parameter here to `True` (defaults to `False`).
*   **include\_custom** (`bool`) – When expectation parameter here is None setting this to `True` will allow the factory to include the custom Aer pauli expectation.
*   **max\_evals\_grouped** (`int`) – Max number of evaluations performed simultaneously. Signals the given optimizer that more than one set of parameters can be supplied so that potentially the expectation values can be computed in parallel. Typically this is possible when a finite difference gradient is used by the optimizer such that multiple points to compute the gradient can be passed and if computed in parallel improve overall execution time.
*   **aux\_operators** (`Optional`\[`List`\[`Union`\[[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase"), [`LegacyBaseOperator`](qiskit.aqua.operators.legacy.LegacyBaseOperator "qiskit.aqua.operators.legacy.base_operator.LegacyBaseOperator"), `None`]]]) – Optional list of auxiliary operators to be evaluated with the eigenstate of the minimum eigenvalue main result and their expectation values returned. For instance in chemistry these can be dipole operators, total particle count operators so we can get values for these at the ground state.
*   **callback** (`Optional`\[`Callable`\[\[`int`, `ndarray`, `float`, `float`], `None`]]) – a callback that can access the intermediate data during the optimization. Four parameter values are passed to the callback as follows during each evaluation by the optimizer for its current set of parameters as it works towards the minimum. These are: the evaluation count, the optimizer parameters for the variational form, the evaluated mean and the evaluated standard deviation.\`
*   **quantum\_instance** (`Union`\[[`QuantumInstance`](qiskit.aqua.QuantumInstance "qiskit.aqua.quantum_instance.QuantumInstance"), [`BaseBackend`](qiskit.providers.BaseBackend "qiskit.providers.basebackend.BaseBackend"), `None`]) – Quantum Instance or Backend

## Attributes

### aux\_operators

<span id="qiskit.aqua.algorithms.VQE.aux_operators" />

`Optional[List[Optional[qiskit.aqua.operators.operator_base.OperatorBase]]]`

Returns aux operators

**Return type**

`Optional`\[`List`\[`Optional`\[[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")]]]

### backend

<span id="qiskit.aqua.algorithms.VQE.backend" />

`qiskit.providers.basebackend.BaseBackend`

Returns backend.

**Return type**

[`BaseBackend`](qiskit.providers.BaseBackend "qiskit.providers.basebackend.BaseBackend")

### expectation

<span id="qiskit.aqua.algorithms.VQE.expectation" />

`qiskit.aqua.operators.expectations.expectation_base.ExpectationBase`

The expectation value algorithm used to construct the expectation measurement from the observable.

**Return type**

[`ExpectationBase`](qiskit.aqua.operators.expectations.ExpectationBase "qiskit.aqua.operators.expectations.expectation_base.ExpectationBase")

### initial\_point

<span id="qiskit.aqua.algorithms.VQE.initial_point" />

`Optional[numpy.ndarray]`

Returns initial point

**Return type**

`Optional`\[`ndarray`]

### operator

<span id="qiskit.aqua.algorithms.VQE.operator" />

`Optional[qiskit.aqua.operators.operator_base.OperatorBase]`

Returns operator

**Return type**

`Optional`\[[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")]

### optimal\_params

<span id="qiskit.aqua.algorithms.VQE.optimal_params" />

`List[float]`

The optimal parameters for the variational form.

**Return type**

`List`\[`float`]

### optimizer

<span id="qiskit.aqua.algorithms.VQE.optimizer" />

`Optional[qiskit.aqua.components.optimizers.optimizer.Optimizer]`

Returns optimizer

**Return type**

`Optional`\[[`Optimizer`](qiskit.aqua.components.optimizers.Optimizer "qiskit.aqua.components.optimizers.optimizer.Optimizer")]

### quantum\_instance

<span id="qiskit.aqua.algorithms.VQE.quantum_instance" />

`Union[None, qiskit.aqua.quantum_instance.QuantumInstance]`

Returns quantum instance.

**Return type**

`Optional`\[[`QuantumInstance`](qiskit.aqua.QuantumInstance "qiskit.aqua.quantum_instance.QuantumInstance")]

### random

Return a numpy random.

### setting

Prepare the setting of VQE as a string.

### var\_form

<span id="qiskit.aqua.algorithms.VQE.var_form" />

`Optional[Union[qiskit.circuit.quantumcircuit.QuantumCircuit, qiskit.aqua.components.variational_forms.variational_form.VariationalForm]]`

Returns variational form

**Return type**

`Union`\[[`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit"), [`VariationalForm`](qiskit.aqua.components.variational_forms.VariationalForm "qiskit.aqua.components.variational_forms.variational_form.VariationalForm"), `None`]

## Methods

### cleanup\_parameterized\_circuits

<span id="qiskit.aqua.algorithms.VQE.cleanup_parameterized_circuits" />

`VQE.cleanup_parameterized_circuits()`

set parameterized circuits to None

### compute\_minimum\_eigenvalue

<span id="qiskit.aqua.algorithms.VQE.compute_minimum_eigenvalue" />

`VQE.compute_minimum_eigenvalue(operator=None, aux_operators=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/minimum_eigen_solvers/vqe.py "view source code")

Computes minimum eigenvalue. Operator and aux\_operators can be supplied here and if not None will override any already set into algorithm so it can be reused with different operators. While an operator is required by algorithms, aux\_operators are optional. To ‘remove’ a previous aux\_operators array use an empty list here.

**Parameters**

*   **operator** (`Union`\[[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase"), [`LegacyBaseOperator`](qiskit.aqua.operators.legacy.LegacyBaseOperator "qiskit.aqua.operators.legacy.base_operator.LegacyBaseOperator"), `None`]) – If not None replaces operator in algorithm
*   **aux\_operators** (`Optional`\[`List`\[`Union`\[[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase"), [`LegacyBaseOperator`](qiskit.aqua.operators.legacy.LegacyBaseOperator "qiskit.aqua.operators.legacy.base_operator.LegacyBaseOperator"), `None`]]]) – If not None replaces aux\_operators in algorithm

**Return type**

[`MinimumEigensolverResult`](qiskit.aqua.algorithms.MinimumEigensolverResult "qiskit.aqua.algorithms.minimum_eigen_solvers.minimum_eigen_solver.MinimumEigensolverResult")

**Returns**

MinimumEigensolverResult

### construct\_circuit

<span id="qiskit.aqua.algorithms.VQE.construct_circuit" />

`VQE.construct_circuit(parameter)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/minimum_eigen_solvers/vqe.py "view source code")

Generate the ansatz circuit and expectation value measurement, and return their runnable composition.

**Parameters**

**parameter** (`Union`\[`List`\[`float`], `List`\[[`Parameter`](qiskit.circuit.Parameter "qiskit.circuit.parameter.Parameter")], `ndarray`]) – Parameters for the ansatz circuit.

**Return type**

[`OperatorBase`](qiskit.aqua.operators.OperatorBase "qiskit.aqua.operators.operator_base.OperatorBase")

**Returns**

The Operator equalling the measurement of the ansatz `StateFn` by the Observable’s expectation `StateFn`.

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – If no operator has been provided.

### find\_minimum

<span id="qiskit.aqua.algorithms.VQE.find_minimum" />

`VQE.find_minimum(initial_point=None, var_form=None, cost_fn=None, optimizer=None, gradient_fn=None)`

Optimize to find the minimum cost value.

**Parameters**

*   **initial\_point** (`Optional`\[`ndarray`]) – If not None will be used instead of any initial point supplied via constructor. If None and None was supplied to constructor then a random point will be used if the optimizer requires an initial point.
*   **var\_form** (`Union`\[[`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit"), [`VariationalForm`](qiskit.aqua.components.variational_forms.VariationalForm "qiskit.aqua.components.variational_forms.variational_form.VariationalForm"), `None`]) – If not None will be used instead of any variational form supplied via constructor.
*   **cost\_fn** (`Optional`\[`Callable`]) – If not None will be used instead of any cost\_fn supplied via constructor.
*   **optimizer** (`Optional`\[[`Optimizer`](qiskit.aqua.components.optimizers.Optimizer "qiskit.aqua.components.optimizers.optimizer.Optimizer")]) – If not None will be used instead of any optimizer supplied via constructor.
*   **gradient\_fn** (`Optional`\[`Callable`]) – Optional gradient function for optimizer

**Returns**

Optimized variational parameters, and corresponding minimum cost value.

**Return type**

dict

**Raises**

**ValueError** – invalid input

### get\_optimal\_circuit

<span id="qiskit.aqua.algorithms.VQE.get_optimal_circuit" />

`VQE.get_optimal_circuit()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/minimum_eigen_solvers/vqe.py "view source code")

Get the circuit with the optimal parameters.

**Return type**

[`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit")

### get\_optimal\_cost

<span id="qiskit.aqua.algorithms.VQE.get_optimal_cost" />

`VQE.get_optimal_cost()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/minimum_eigen_solvers/vqe.py "view source code")

Get the minimal cost or energy found by the VQE.

**Return type**

`float`

### get\_optimal\_vector

<span id="qiskit.aqua.algorithms.VQE.get_optimal_vector" />

`VQE.get_optimal_vector()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/minimum_eigen_solvers/vqe.py "view source code")

Get the simulation outcome of the optimal circuit.

**Return type**

`Union`\[`List`\[`float`], `Dict`\[`str`, `int`]]

### get\_prob\_vector\_for\_params

<span id="qiskit.aqua.algorithms.VQE.get_prob_vector_for_params" />

`VQE.get_prob_vector_for_params(construct_circuit_fn, params_s, quantum_instance, construct_circuit_args=None)`

Helper function to get probability vectors for a set of params

### get\_probabilities\_for\_counts

<span id="qiskit.aqua.algorithms.VQE.get_probabilities_for_counts" />

`VQE.get_probabilities_for_counts(counts)`

get probabilities for counts

### print\_settings

<span id="qiskit.aqua.algorithms.VQE.print_settings" />

`VQE.print_settings()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/minimum_eigen_solvers/vqe.py "view source code")

Preparing the setting of VQE into a string.

**Returns**

the formatted setting of VQE

**Return type**

str

### run

<span id="qiskit.aqua.algorithms.VQE.run" />

`VQE.run(quantum_instance=None, **kwargs)`

Execute the algorithm with selected backend.

**Parameters**

*   **quantum\_instance** (`Union`\[[`QuantumInstance`](qiskit.aqua.QuantumInstance "qiskit.aqua.quantum_instance.QuantumInstance"), [`BaseBackend`](qiskit.providers.BaseBackend "qiskit.providers.basebackend.BaseBackend"), `None`]) – the experimental setting.
*   **kwargs** (*dict*) – kwargs

**Returns**

results of an algorithm.

**Return type**

dict

**Raises**

[**AquaError**](qiskit.aqua.AquaError "qiskit.aqua.AquaError") – If a quantum instance or backend has not been provided

### set\_backend

<span id="qiskit.aqua.algorithms.VQE.set_backend" />

`VQE.set_backend(backend, **kwargs)`

Sets backend with configuration.

**Return type**

`None`

### supports\_aux\_operators

<span id="qiskit.aqua.algorithms.VQE.supports_aux_operators" />

`VQE.supports_aux_operators()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/aqua/algorithms/minimum_eigen_solvers/vqe.py "view source code")

Whether computing the expectation value of auxiliary operators is supported.

If the minimum eigensolver computes an eigenstate of the main operator then it can compute the expectation value of the aux\_operators for that state. Otherwise they will be ignored.

**Return type**

`bool`

**Returns**

True if aux\_operator expectations can be evaluated, False otherwise

