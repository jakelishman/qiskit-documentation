---
title: Target
description: API reference for qiskit.transpiler.Target
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.transpiler.Target
---

# Target

<span id="qiskit.transpiler.Target" />

`Target(description=None, num_qubits=0, dt=None, granularity=1, min_length=1, pulse_alignment=1, aquire_alignment=1)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/transpiler/target.py "view source code")

Bases: `collections.abc.Mapping`

The intent of the `Target` object is to inform Qiskit’s compiler about the constraints of a particular backend so the compiler can compile an input circuit to something that works and is optimized for a device. It currently contains a description of instructions on a backend and their properties as well as some timing information. However, this exact interface may evolve over time as the needs of the compiler change. These changes will be done in a backwards compatible and controlled manner when they are made (either through versioning, subclassing, or mixins) to add on to the set of information exposed by a target.

As a basic example, let’s assume backend has two qubits, supports [`UGate`](qiskit.circuit.library.UGate "qiskit.circuit.library.UGate") on both qubits and [`CXGate`](qiskit.circuit.library.CXGate "qiskit.circuit.library.CXGate") in both directions. To model this you would create the target like:

```python
from qiskit.transpiler import Target, InstructionProperties
from qiskit.circuit.library import UGate, CXGate
from qiskit.circuit import Parameter

gmap = Target()
theta = Parameter('theta')
phi = Parameter('phi')
lam = Parameter('lambda')
u_props = {
    (0,): InstructionProperties(duration=5.23e-8, error=0.00038115),
    (1,): InstructionProperties(duration=4.52e-8, error=0.00032115),
}
gmap.add_instruction(UGate(theta, phi, lam), u_props)
cx_props = {
    (0,1): InstructionProperties(duration=5.23e-7, error=0.00098115),
    (1,0): InstructionProperties(duration=4.52e-7, error=0.00132115),
}
gmap.add_instruction(CXGate(), cx_props)
```

Each instruction in the Target is indexed by a unique string name that uniquely identifies that instance of an [`Instruction`](qiskit.circuit.Instruction "qiskit.circuit.Instruction") object in the Target. There is a 1:1 mapping between a name and an [`Instruction`](qiskit.circuit.Instruction "qiskit.circuit.Instruction") instance in the target and each name must be unique. By default the name is the `name` attribute of the instruction, but can be set to anything. This lets a single target have multiple instances of the same instruction class with different parameters. For example, if a backend target has two instances of an [`RXGate`](qiskit.circuit.library.RXGate "qiskit.circuit.library.RXGate") one is parameterized over any theta while the other is tuned up for a theta of pi/6 you can add these by doing something like:

```python
import math

from qiskit.transpiler import Target, InstructionProperties
from qiskit.circuit.library import RXGate
from qiskit.circuit import Parameter

target = Target()
theta = Parameter('theta')
rx_props = {
    (0,): InstructionProperties(duration=5.23e-8, error=0.00038115),
}
target.add_instruction(RXGate(theta), rx_props)
rx_30_props = {
    (0,): InstructionProperties(duration=1.74e-6, error=.00012)
}
target.add_instruction(RXGate(math.pi / 6), rx_30_props, name='rx_30')
```

Then in the `target` object accessing by `rx_30` will get the fixed angle [`RXGate`](qiskit.circuit.library.RXGate "qiskit.circuit.library.RXGate") while `rx` will get the parameterized [`RXGate`](qiskit.circuit.library.RXGate "qiskit.circuit.library.RXGate").

<Admonition title="Note" type="note">
  This class assumes that qubit indices start at 0 and are a contiguous set if you want a submapping the bits will need to be reindexed in a new\`\`Target\`\` object.
</Admonition>

<Admonition title="Note" type="note">
  This class only supports additions of gates, qargs, and qubits. If you need to remove one of these the best option is to iterate over an existing object and create a new subset (or use one of the methods to do this). The object internally caches different views and these would potentially be invalidated by removals.
</Admonition>

Create a new Target object

**Parameters**

*   **description** (*str*) – An optional string to describe the Target.
*   **num\_qubits** (*int*) – An optional int to specify the number of qubits the backend target has. If not set it will be implicitly set based on the qargs when `add_instruction()` is called. Note this must be set if the backend target is for a noiseless simulator that doesn’t have constraints on the instructions so the transpiler knows how many qubits are available.
*   **dt** (*float*) – The system time resolution of input signals in seconds
*   **granularity** (*int*) – An integer value representing minimum pulse gate resolution in units of `dt`. A user-defined pulse gate should have duration of a multiple of this granularity value.
*   **min\_length** (*int*) – An integer value representing minimum pulse gate length in units of `dt`. A user-defined pulse gate should be longer than this length.
*   **pulse\_alignment** (*int*) – An integer value representing a time resolution of gate instruction starting time. Gate instruction should start at time which is a multiple of the alignment value.
*   **acquire\_alignment** (*int*) – An integer value representing a time resolution of measure instruction starting time. Measure instruction should start at time which is a multiple of the alignment value.

## Methods

### add\_instruction

<span id="qiskit.transpiler.Target.add_instruction" />

`Target.add_instruction(instruction, properties=None, name=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/transpiler/target.py "view source code")

Add a new instruction to the [`Target`](qiskit.transpiler.Target "qiskit.transpiler.Target")

As `Target` objects are strictly additive this is the primary method for modifying a `Target`. Typically you will use this to fully populate a `Target` before using it in [`BackendV2`](qiskit.providers.BackendV2 "qiskit.providers.BackendV2"). For example:

```python
from qiskit.circuit.library import CXGate
from qiskit.transpiler import Target, InstructionProperties

target = Target()
cx_properties = {
    (0, 1): None,
    (1, 0): None,
    (0, 2): None,
    (2, 0): None,
    (0, 3): None,
    (2, 3): None,
    (3, 0): None,
    (3, 2): None
}
target.add_instruction(CXGate(), cx_properties)
```

Will add a [`CXGate`](qiskit.circuit.library.CXGate "qiskit.circuit.library.CXGate") to the target with no properties (duration, error, etc) with the coupling edge list: `(0, 1), (1, 0), (0, 2), (2, 0), (0, 3), (2, 3), (3, 0), (3, 2)`. If there are properties available for the instruction you can replace the `None` value in the properties dictionary with an [`InstructionProperties`](qiskit.transpiler.InstructionProperties "qiskit.transpiler.InstructionProperties") object. This pattern is repeated for each [`Instruction`](qiskit.circuit.Instruction "qiskit.circuit.Instruction") the target supports.

**Parameters**

*   **instruction** ([*qiskit.circuit.Instruction*](qiskit.circuit.Instruction "qiskit.circuit.Instruction")) – The operation object to add to the map. If it’s paramerterized any value of the parameter can be set
*   **properties** (*dict*) – A dictionary of qarg entries to an [`InstructionProperties`](qiskit.transpiler.InstructionProperties "qiskit.transpiler.InstructionProperties") object for that instruction implementation on the backend. Properties are optional for any instruction implementation, if there are no [`InstructionProperties`](qiskit.transpiler.InstructionProperties "qiskit.transpiler.InstructionProperties") available for the backend the value can be None. If there are no constraints on the instruction (as in a noisless/ideal simulation) this can be set to `{None, None}` which will indicate it runs on all qubits (or all available permutations of qubits for multi-qubit gates). The first `None` indicates it applies to all qubits and the second `None` indicates there are no [`InstructionProperties`](qiskit.transpiler.InstructionProperties "qiskit.transpiler.InstructionProperties") for the instruction. By default, if properties is not set it is equivalent to passing `{None: None}`.
*   **name** (*str*) – An optional name to use for identifying the instruction. If not specified the `name` attribute of `gate` will be used. All gates in the `Target` need unique names. Backends can differentiate between different parameterizations of a single gate by providing a unique name for each (e.g. “rx30”, “rx60”, \`”rx90”\`\` similar to the example in the documentation for the [`Target`](qiskit.transpiler.Target "qiskit.transpiler.Target") class).

**Raises**

**AttributeError** – If gate is already in map

### build\_coupling\_map

<span id="qiskit.transpiler.Target.build_coupling_map" />

`Target.build_coupling_map(two_q_gate=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/transpiler/target.py "view source code")

Get a [`CouplingMap`](qiskit.transpiler.CouplingMap "qiskit.transpiler.CouplingMap") from this target.

**Parameters**

**two\_q\_gate** (*str*) – An optional gate name for a two qubit gate in the Target to generate the coupling map for. If specified the output coupling map will only have edges between qubits where this gate is present.

**Returns**

**The [`CouplingMap`](qiskit.transpiler.CouplingMap "qiskit.transpiler.CouplingMap") object**

for this target.

**Return type**

[CouplingMap](qiskit.transpiler.CouplingMap "qiskit.transpiler.CouplingMap")

**Raises**

*   **ValueError** – If a non-two qubit gate is passed in for `two_q_gate`.
*   **IndexError** – If an Instruction not in the Target is passed in for `two_q_gate`.

### durations

<span id="qiskit.transpiler.Target.durations" />

`Target.durations()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/transpiler/target.py "view source code")

Get an InstructionDurations object from the target

**Returns**

**The instruction duration represented in the**

target

**Return type**

[InstructionDurations](qiskit.transpiler.InstructionDurations "qiskit.transpiler.InstructionDurations")

### get

<span id="qiskit.transpiler.Target.get" />

`Target.get(k[, d]) → D[k] if k in D, else d. d defaults to None.`

### get\_non\_global\_operation\_names

<span id="qiskit.transpiler.Target.get_non_global_operation_names" />

`Target.get_non_global_operation_names(strict_direction=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/transpiler/target.py "view source code")

Return the non-global operation names for the target

The non-global operations are those in the target which don’t apply on all qubits (for single qubit operations) or all multiqubit qargs (for multi-qubit operations).

**Parameters**

**strict\_direction** (*bool*) – If set to `True` the multi-qubit operations considered as non-global respect the strict direction (or order of qubits in the qargs is signifcant). For example, if `cx` is defined on `(0, 1)` and `ecr` is defined over `(1, 0)` by default neither would be considered non-global, but if `strict_direction` is set `True` both `cx` and `ecr` would be returned.

**Returns**

A list of operation names for operations that aren’t global in this target

**Return type**

List\[str]

### instruction\_properties

<span id="qiskit.transpiler.Target.instruction_properties" />

`Target.instruction_properties(index)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/transpiler/target.py "view source code")

Get the instruction properties for a specific instruction tuple

This method is to be used in conjunction with the [`instructions`](qiskit.transpiler.Target#instructions "qiskit.transpiler.Target.instructions") attribute of a [`Target`](qiskit.transpiler.Target "qiskit.transpiler.Target") object. You can use this method to quickly get the instruction properties for an element of [`instructions`](qiskit.transpiler.Target#instructions "qiskit.transpiler.Target.instructions") by using the index in that list. However, if you’re not working with [`instructions`](qiskit.transpiler.Target#instructions "qiskit.transpiler.Target.instructions") directly it is likely more efficient to access the target directly via the name and qubits to get the instruction properties. For example, if [`instructions`](qiskit.transpiler.Target#instructions "qiskit.transpiler.Target.instructions") returned:

```python
[(XGate(), (0,)), (XGate(), (1,))]
```

you could get the properties of the `XGate` on qubit 1 with:

```python
props = target.instruction_properties(1)
```

but just accessing it directly via the name would be more efficient:

```python
props = target['x'][(1,)]
```

(assuming the `XGate`’s canonical name in the target is `'x'`) This is especially true for larger targets as this will scale worse with the number of instruction tuples in a target.

**Parameters**

**index** (*int*) – The index of the instruction tuple from the [`instructions`](qiskit.transpiler.Target#instructions "qiskit.transpiler.Target.instructions") attribute. For, example if you want the properties from the third element in [`instructions`](qiskit.transpiler.Target#instructions "qiskit.transpiler.Target.instructions") you would set this to be `2`.

**Returns**

The instruction properties for the specified instruction tuple

**Return type**

[InstructionProperties](qiskit.transpiler.InstructionProperties "qiskit.transpiler.InstructionProperties")

### instruction\_schedule\_map

<span id="qiskit.transpiler.Target.instruction_schedule_map" />

`Target.instruction_schedule_map()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/transpiler/target.py "view source code")

Return an [`InstructionScheduleMap`](qiskit.pulse.InstructionScheduleMap "qiskit.pulse.InstructionScheduleMap") for the instructions in the target with a pulse schedule defined.

**Returns**

The instruction schedule map for the instructions in this target with a pulse schedule defined.

**Return type**

[InstructionScheduleMap](qiskit.pulse.InstructionScheduleMap "qiskit.pulse.InstructionScheduleMap")

### items

<span id="qiskit.transpiler.Target.items" />

`Target.items() → a set-like object providing a view on D’s items`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/transpiler/target.py "view source code")

### keys

<span id="qiskit.transpiler.Target.keys" />

`Target.keys() → a set-like object providing a view on D’s keys`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/transpiler/target.py "view source code")

### operation\_from\_name

<span id="qiskit.transpiler.Target.operation_from_name" />

`Target.operation_from_name(instruction)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/transpiler/target.py "view source code")

Get the operation class object for a given name

**Parameters**

**instruction** (*str*) – The instruction name to get the [`Instruction`](qiskit.circuit.Instruction "qiskit.circuit.Instruction") instance for

**Returns**

The Instruction instance corresponding to the name

**Return type**

[qiskit.circuit.Instruction](qiskit.circuit.Instruction "qiskit.circuit.Instruction")

### operations\_for\_qargs

<span id="qiskit.transpiler.Target.operations_for_qargs" />

`Target.operations_for_qargs(qargs)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/transpiler/target.py "view source code")

Get the operation class object for a specified qarg

**Parameters**

**qargs** (*tuple*) – A qargs tuple of the qubits to get the gates that apply to it. For example, `(0,)` will return the set of all instructions that apply to qubit 0.

**Returns**

The list of [`Instruction`](qiskit.circuit.Instruction "qiskit.circuit.Instruction") instances that apply to the specified qarg.

**Return type**

list

**Raises**

**KeyError** – If qargs is not in target

### qargs\_for\_operation\_name

<span id="qiskit.transpiler.Target.qargs_for_operation_name" />

`Target.qargs_for_operation_name(operation)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/transpiler/target.py "view source code")

Get the qargs for a given operation name

**Parameters**

**operation** (*str*) – The operation name to get qargs for

**Returns**

The set of qargs the gate instance applies to.

**Return type**

set

### timing\_constraints

<span id="qiskit.transpiler.Target.timing_constraints" />

`Target.timing_constraints()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/transpiler/target.py "view source code")

Get an `TimingConstraints` object from the target

**Returns**

The timing constraints represented in the Target

**Return type**

TimingConstraints

### update\_from\_instruction\_schedule\_map

<span id="qiskit.transpiler.Target.update_from_instruction_schedule_map" />

`Target.update_from_instruction_schedule_map(inst_map, inst_name_map=None, error_dict=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/transpiler/target.py "view source code")

Update the target from an instruction schedule map.

If the input instruction schedule map contains new instructions not in the target they will be added. However if it contains additional qargs for an existing instruction in the target it will error.

**Parameters**

*   **inst\_map** ([*InstructionScheduleMap*](qiskit.pulse.InstructionScheduleMap "qiskit.pulse.InstructionScheduleMap")) – The instruction

*   **inst\_name\_map** (*dict*) – An optional dictionary that maps any instruction name in `inst_map` to an instruction object

*   **error\_dict** (*dict*) –

    A dictionary of errors of the form:

    ```python
    {gate_name: {qarg: error}}
    ```

*   **example::** (*for*) – \{‘rx’: \{(0, ): 1.4e-4, (1, ): 1.2e-4}}

*   **each entry in the inst\_map if error\_dict is defined** (*For*) –

*   **when updating the Target the error value will be pulled from** (*a*) –

*   **dictionary. If one is not found in error\_dict then** (*this*) –

*   **will be used.** (*None*) –

**Raises**

*   **ValueError** – If `inst_map` contains new instructions and `inst_name_map` isn’t specified
*   **KeyError** – If a `inst_map` contains a qarg for an instruction that’s not in the target

### update\_instruction\_properties

<span id="qiskit.transpiler.Target.update_instruction_properties" />

`Target.update_instruction_properties(instruction, qargs, properties)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/transpiler/target.py "view source code")

Update the property object for an instruction qarg pair already in the Target

**Parameters**

*   **instruction** (*str*) – The instruction name to update
*   **qargs** (*tuple*) – The qargs to update the properties of
*   **properties** ([*InstructionProperties*](qiskit.transpiler.InstructionProperties "qiskit.transpiler.InstructionProperties")) – The properties to set for this nstruction

**Raises**

**KeyError** – If `instruction` or `qarg` are not in the target

### values

<span id="qiskit.transpiler.Target.values" />

`Target.values() → an object providing a view on D’s values`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/transpiler/target.py "view source code")

## Attributes

<span id="qiskit.transpiler.Target.aquire_alignment" />

### aquire\_alignment

<span id="qiskit.transpiler.Target.description" />

### description

<span id="qiskit.transpiler.Target.dt" />

### dt

<span id="qiskit.transpiler.Target.granularity" />

### granularity

<span id="qiskit.transpiler.Target.instructions" />

### instructions

Get the list of tuples ``(:class:`~qiskit.circuit.Instruction`, (qargs))`` for the target

<span id="qiskit.transpiler.Target.min_length" />

### min\_length

<span id="qiskit.transpiler.Target.num_qubits" />

### num\_qubits

<span id="qiskit.transpiler.Target.operation_names" />

### operation\_names

Get the operation names in the target.

<span id="qiskit.transpiler.Target.operations" />

### operations

Get the operation class objects in the target.

<span id="qiskit.transpiler.Target.physical_qubits" />

### physical\_qubits

Returns a sorted list of physical\_qubits

<span id="qiskit.transpiler.Target.pulse_alignment" />

### pulse\_alignment

<span id="qiskit.transpiler.Target.qargs" />

### qargs

The set of qargs in the target.

