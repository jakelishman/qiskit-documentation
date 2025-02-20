---
title: synth_clifford_depth_lnn
description: API reference for qiskit.synthesis.synth_clifford_depth_lnn
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.synthesis.synth_clifford_depth_lnn
---

<span id="qiskit-synthesis-synth-clifford-depth-lnn" />

# qiskit.synthesis.synth\_clifford\_depth\_lnn

<span id="qiskit.synthesis.synth_clifford_depth_lnn" />

`synth_clifford_depth_lnn(cliff)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.24/qiskit/synthesis/clifford/clifford_decompose_layers.py "view source code")

Synthesis of a Clifford into layers for linear-nearest neighbour connectivity.

The depth of the synthesized n-qubit circuit is bounded by 9\*n+4, which is not optimal. It should be replaced by a better algorithm that provides depth bounded by 7\*n-4 \[3].

**Parameters**

**cliff** ([*Clifford*](qiskit.quantum_info.Clifford "qiskit.quantum_info.Clifford")) – a clifford operator.

**Returns**

a circuit implementation of the Clifford.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

## Reference:

1.  S. Bravyi, D. Maslov, *Hadamard-free circuits expose the structure of the Clifford group*, [arXiv:2003.09412 \[quant-ph\]](https://arxiv.org/abs/2003.09412)
2.  Dmitri Maslov, Martin Roetteler, *Shorter stabilizer circuits via Bruhat decomposition and quantum circuit transformations*, [arXiv:1705.09176](https://arxiv.org/abs/1705.09176).
3.  Dmitri Maslov, Willers Yang, *CNOT circuits need little help to implement arbitrary Hadamard-free Clifford transformations they generate*, [arXiv:2210.16195](https://arxiv.org/abs/2210.16195).

