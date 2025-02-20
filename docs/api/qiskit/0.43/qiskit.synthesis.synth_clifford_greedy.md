---
title: synth_clifford_greedy
description: API reference for qiskit.synthesis.synth_clifford_greedy
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.synthesis.synth_clifford_greedy
---

<span id="qiskit-synthesis-synth-clifford-greedy" />

# qiskit.synthesis.synth\_clifford\_greedy

<span id="qiskit.synthesis.synth_clifford_greedy" />

`synth_clifford_greedy(clifford)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/synthesis/clifford/clifford_decompose_greedy.py "view source code")

Decompose a Clifford operator into a QuantumCircuit based on the greedy Clifford compiler that is described in Appendix A of Bravyi, Hu, Maslov and Shaydulin.

This method typically yields better CX cost compared to the Aaronson-Gottesma method.

**Parameters**

**clifford** ([*Clifford*](qiskit.quantum_info.Clifford "qiskit.quantum_info.Clifford")) – a clifford operator.

**Returns**

a circuit implementation of the Clifford.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

**Raises**

**QiskitError** – if symplectic Gaussian elimination fails.

## Reference:

1.  Sergey Bravyi, Shaohan Hu, Dmitri Maslov, Ruslan Shaydulin, *Clifford Circuit Optimization with Templates and Symbolic Pauli Gates*, [arXiv:2105.02291 \[quant-ph\]](https://arxiv.org/abs/2105.02291)

