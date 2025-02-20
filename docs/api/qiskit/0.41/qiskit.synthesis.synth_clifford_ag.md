---
title: synth_clifford_ag
description: API reference for qiskit.synthesis.synth_clifford_ag
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.synthesis.synth_clifford_ag
---

# qiskit.synthesis.synth\_clifford\_ag

<span id="qiskit.synthesis.synth_clifford_ag" />

`synth_clifford_ag(clifford)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.23/qiskit/synthesis/clifford/clifford_decompose_ag.py "view source code")

Decompose a Clifford operator into a QuantumCircuit based on Aaronson-Gottesman method.

**Parameters**

**clifford** ([*Clifford*](qiskit.quantum_info.Clifford "qiskit.quantum_info.Clifford")) – a clifford operator.

**Returns**

a circuit implementation of the Clifford.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

## Reference:

1.  S. Aaronson, D. Gottesman, *Improved Simulation of Stabilizer Circuits*, Phys. Rev. A 70, 052328 (2004). [arXiv:quant-ph/0406196](https://arxiv.org/abs/quant-ph/0406196)

