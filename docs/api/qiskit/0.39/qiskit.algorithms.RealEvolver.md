---
title: RealEvolver
description: API reference for qiskit.algorithms.RealEvolver
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.RealEvolver
---

# RealEvolver

<span id="qiskit.algorithms.RealEvolver" />

`RealEvolver`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/algorithms/evolvers/real_evolver.py "view source code")

Bases: `abc.ABC`

Pending deprecation: Interface for Quantum Real Time Evolution.

The RealEvolver interface has been superseded by the `qiskit.algorithms.time_evolvers.RealTimeEvolver` interface. This interface will be deprecated in a future release and subsequently removed after that.

## Methods

### evolve

<span id="qiskit.algorithms.RealEvolver.evolve" />

`abstract RealEvolver.evolve(evolution_problem)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.22/qiskit/algorithms/evolvers/real_evolver.py "view source code")

Perform real time evolution $\exp(-i t H)|\Psi\rangle$.

Evolves an initial state $|\Psi\rangle$ for a time $t$ under a Hamiltonian $H$, as provided in the `evolution_problem`.

**Parameters**

**evolution\_problem** ([`EvolutionProblem`](qiskit.algorithms.EvolutionProblem "qiskit.algorithms.evolvers.evolution_problem.EvolutionProblem")) – The definition of the evolution problem.

**Return type**

[`EvolutionResult`](qiskit.algorithms.EvolutionResult "qiskit.algorithms.evolvers.evolution_result.EvolutionResult")

**Returns**

Evolution result which includes an evolved quantum state.

