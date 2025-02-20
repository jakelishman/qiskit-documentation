---
title: EnergySurfaceBase
description: API reference for qiskit.chemistry.algorithms.pes_samplers.EnergySurfaceBase
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.chemistry.algorithms.pes_samplers.EnergySurfaceBase
---

<span id="qiskit-chemistry-algorithms-pes-samplers-energysurfacebase" />

# qiskit.chemistry.algorithms.pes\_samplers.EnergySurfaceBase

<span id="qiskit.chemistry.algorithms.pes_samplers.EnergySurfaceBase" />

`EnergySurfaceBase`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.8/qiskit/chemistry/algorithms/pes_samplers/potentials/potential_base.py "view source code")

Class to hold a potential energy surface

### \_\_init\_\_

<span id="qiskit.chemistry.algorithms.pes_samplers.EnergySurfaceBase.__init__" />

`__init__()`

Initialize self. See help(type(self)) for accurate signature.

## Methods

|                                                                                                                                                                                                                      |                                                                              |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| [`__init__`](#qiskit.chemistry.algorithms.pes_samplers.EnergySurfaceBase.__init__ "qiskit.chemistry.algorithms.pes_samplers.EnergySurfaceBase.__init__")()                                                           | Initialize self.                                                             |
| [`eval`](#qiskit.chemistry.algorithms.pes_samplers.EnergySurfaceBase.eval "qiskit.chemistry.algorithms.pes_samplers.EnergySurfaceBase.eval")(x)                                                                      | After fitting the data to the fit function, predict the energy at a point x. |
| [`fit`](#qiskit.chemistry.algorithms.pes_samplers.EnergySurfaceBase.fit "qiskit.chemistry.algorithms.pes_samplers.EnergySurfaceBase.fit")(xdata, ydata\[, initial\_vals, bounds\_list])                              | Fits surface to data                                                         |
| [`get_equilibrium_geometry`](#qiskit.chemistry.algorithms.pes_samplers.EnergySurfaceBase.get_equilibrium_geometry "qiskit.chemistry.algorithms.pes_samplers.EnergySurfaceBase.get_equilibrium_geometry")(\[scaling]) | Get the equilibrium energy.                                                  |
| [`get_minimal_energy`](#qiskit.chemistry.algorithms.pes_samplers.EnergySurfaceBase.get_minimal_energy "qiskit.chemistry.algorithms.pes_samplers.EnergySurfaceBase.get_minimal_energy")(\[scaling])                   | Get the minimal energy.                                                      |
| [`get_trust_region`](#qiskit.chemistry.algorithms.pes_samplers.EnergySurfaceBase.get_trust_region "qiskit.chemistry.algorithms.pes_samplers.EnergySurfaceBase.get_trust_region")()                                   | Get the trust region.                                                        |

### eval

<span id="qiskit.chemistry.algorithms.pes_samplers.EnergySurfaceBase.eval" />

`abstract eval(x)`

After fitting the data to the fit function, predict the energy at a point x.

**Parameters**

**x** (`float`) – value to evaluate surface in

**Return type**

`float`

**Returns**

value of surface in point x

### fit

<span id="qiskit.chemistry.algorithms.pes_samplers.EnergySurfaceBase.fit" />

`abstract fit(xdata, ydata, initial_vals=None, bounds_list=None)`

Fits surface to data

**Parameters**

*   **xdata** (`List`\[`float`]) – x data to be fitted
*   **ydata** (`List`\[`float`]) – y data to be fitted
*   **initial\_vals** (`Optional`\[`List`\[`float`]]) – Initial values for fit parameters. None for default. Order of parameters is d\_e, alpha, r\_0 and m\_shift (see fit\_function implementation)
*   **bounds\_list** (`Optional`\[`Tuple`\[`List`\[`float`], `List`\[`float`]]]) – Bounds for the fit parameters. None for default. Order of parameters is d\_e, alpha, r\_0 and m\_shift (see fit\_function implementation)

**Return type**

`None`

### get\_equilibrium\_geometry

<span id="qiskit.chemistry.algorithms.pes_samplers.EnergySurfaceBase.get_equilibrium_geometry" />

`abstract get_equilibrium_geometry(scaling=1.0)`

Get the equilibrium energy.

Returns the geometry for the minimal energy (scaled by ‘scaling’) Default units (scaling=1.0) are Angstroms. Scale by 1E-10 to get meters.

**Parameters**

**scaling** (`float`) – scaling factor

**Return type**

`float`

**Returns**

equilibrium geometry

### get\_minimal\_energy

<span id="qiskit.chemistry.algorithms.pes_samplers.EnergySurfaceBase.get_minimal_energy" />

`abstract get_minimal_energy(scaling=1.0)`

Get the minimal energy.

Returns the value of the minimal energy (scaled by ‘scaling’) Default units (scaling=1.0) are J/mol. Scale appropriately for Hartrees.

**Parameters**

**scaling** (`float`) – scaling factor

**Return type**

`float`

**Returns**

minimum energy

### get\_trust\_region

<span id="qiskit.chemistry.algorithms.pes_samplers.EnergySurfaceBase.get_trust_region" />

`abstract get_trust_region()`

Get the trust region.

Returns the bounds of the region (in space) where the energy surface implementation can be trusted. When doing spline interpolation, for example, that would be the region where data is interpolated (vs. extrapolated) from the arguments of fit().

**Return type**

`Tuple`\[`float`, `float`]

**Returns**

the trust region between bounds

