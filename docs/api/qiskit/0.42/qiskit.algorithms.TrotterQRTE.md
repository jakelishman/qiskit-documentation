---
title: TrotterQRTE
description: API reference for qiskit.algorithms.TrotterQRTE
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.TrotterQRTE
---

# TrotterQRTE

<span id="qiskit.algorithms.TrotterQRTE" />

`TrotterQRTE(product_formula=None, expectation=None, quantum_instance=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/evolvers/trotterization/trotter_qrte.py "view source code")

Bases: [`qiskit.algorithms.evolvers.real_evolver.RealEvolver`](qiskit.algorithms.RealEvolver "qiskit.algorithms.evolvers.real_evolver.RealEvolver")

Pending deprecation: Quantum Real Time Evolution using Trotterization.

The TrotterQRTE class has been superseded by the [`qiskit.algorithms.time_evolvers.trotterization.TrotterQRTE`](qiskit.algorithms.time_evolvers.trotterization.TrotterQRTE "qiskit.algorithms.time_evolvers.trotterization.TrotterQRTE") class. This class will be deprecated in a future release and subsequently removed after that.

Type of Trotterization is defined by a ProductFormula provided.

Examples:

```python
from qiskit.opflow import X, Z, Zero
from qiskit.algorithms import EvolutionProblem, TrotterQRTE
from qiskit import BasicAer
from qiskit.utils import QuantumInstance

operator = X + Z
initial_state = Zero
time = 1
evolution_problem = EvolutionProblem(operator, 1, initial_state)
# LieTrotter with 1 rep
backend = BasicAer.get_backend("statevector_simulator")
quantum_instance = QuantumInstance(backend=backend)
trotter_qrte = TrotterQRTE(quantum_instance=quantum_instance)
evolved_state = trotter_qrte.evolve(evolution_problem).evolved_state
```

**Parameters**

*   **product\_formula** (`Optional`\[[`ProductFormula`](qiskit.synthesis.ProductFormula "qiskit.synthesis.evolution.product_formula.ProductFormula")]) – A Lie-Trotter-Suzuki product formula. The default is the Lie-Trotter first order product formula with a single repetition.
*   **expectation** (`Optional`\[[`ExpectationBase`](qiskit.opflow.expectations.ExpectationBase "qiskit.opflow.expectations.expectation_base.ExpectationBase")]) – An instance of ExpectationBase which defines a method for calculating expectation values of EvolutionProblem.aux\_operators.
*   **quantum\_instance** (`Union`\[[`Backend`](qiskit.providers.Backend "qiskit.providers.backend.Backend"), [`QuantumInstance`](qiskit.utils.QuantumInstance "qiskit.utils.quantum_instance.QuantumInstance"), `None`]) – A quantum instance used for calculating expectation values of EvolutionProblem.aux\_operators.

## Methods

### evolve

<span id="qiskit.algorithms.TrotterQRTE.evolve" />

`TrotterQRTE.evolve(evolution_problem)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/evolvers/trotterization/trotter_qrte.py "view source code")

Evolves a quantum state for a given time using the Trotterization method based on a product formula provided. The result is provided in the form of a quantum circuit. If auxiliary operators are included in the `evolution_problem`, they are evaluated on an evolved state using a backend provided.

<Admonition title="Note" type="note">
  Time-dependent Hamiltonians are not yet supported.
</Admonition>

**Parameters**

**evolution\_problem** ([`EvolutionProblem`](qiskit.algorithms.EvolutionProblem "qiskit.algorithms.evolvers.evolution_problem.EvolutionProblem")) – Instance defining evolution problem. For the included Hamiltonian, `PauliOp`, `SummedOp` or `PauliSumOp` are supported by TrotterQRTE.

**Return type**

[`EvolutionResult`](qiskit.algorithms.EvolutionResult "qiskit.algorithms.evolvers.evolution_result.EvolutionResult")

**Returns**

Evolution result that includes an evolved state as a quantum circuit and, optionally, auxiliary operators evaluated for a resulting state on a backend.

**Raises**

*   **ValueError** – If `t_param` is not set to None in the EvolutionProblem (feature not currently supported).
*   **ValueError** – If the `initial_state` is not provided in the EvolutionProblem.

### supports\_aux\_operators

<span id="qiskit.algorithms.TrotterQRTE.supports_aux_operators" />

`classmethod TrotterQRTE.supports_aux_operators()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/algorithms/evolvers/trotterization/trotter_qrte.py "view source code")

Whether computing the expectation value of auxiliary operators is supported.

**Return type**

`bool`

**Returns**

**True if `aux_operators` expectations in the EvolutionProblem can be evaluated, False**

otherwise.

## Attributes

<span id="qiskit.algorithms.TrotterQRTE.expectation" />

### expectation

Returns an expectation used in the algorithm.

**Return type**

`Optional`\[[`ExpectationBase`](qiskit.opflow.expectations.ExpectationBase "qiskit.opflow.expectations.expectation_base.ExpectationBase")]

<span id="qiskit.algorithms.TrotterQRTE.product_formula" />

### product\_formula

Returns a product formula used in the algorithm.

**Return type**

[`ProductFormula`](qiskit.synthesis.ProductFormula "qiskit.synthesis.evolution.product_formula.ProductFormula")

<span id="qiskit.algorithms.TrotterQRTE.quantum_instance" />

### quantum\_instance

Returns a quantum instance used in the algorithm.

**Return type**

`Optional`\[[`QuantumInstance`](qiskit.utils.QuantumInstance "qiskit.utils.quantum_instance.QuantumInstance")]

