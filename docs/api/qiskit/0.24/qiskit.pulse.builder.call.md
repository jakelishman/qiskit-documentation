---
title: call
description: API reference for qiskit.pulse.builder.call
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.pulse.builder.call
---

<span id="qiskit-pulse-builder-call" />

# qiskit.pulse.builder.call

<span id="qiskit.pulse.builder.call" />

`call(target)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.16/qiskit/pulse/builder.py "view source code")

Call the `target` within the currently active builder context.

Examples:

```python
from qiskit import circuit, pulse, schedule, transpile
from qiskit.test.mock import FakeOpenPulse2Q

backend = FakeOpenPulse2Q()

qc = circuit.QuantumCircuit(2)
qc.cx(0, 1)
qc_transpiled = transpile(qc, optimization_level=3)
sched = schedule(qc_transpiled, backend)

with pulse.build(backend) as pulse_prog:
        pulse.call(sched)
        pulse.call(qc)
```

**Parameters**

**target** (`Union`\[`QuantumCircuit`, `Schedule`]) – Target circuit or pulse schedule to call.

**Raises**

**exceptions.PulseError** – If the input `target` type is not supported.

