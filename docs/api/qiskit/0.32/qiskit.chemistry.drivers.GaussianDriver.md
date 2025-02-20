---
title: GaussianDriver
description: API reference for qiskit.chemistry.drivers.GaussianDriver
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.chemistry.drivers.GaussianDriver
---

# GaussianDriver

<span id="qiskit.chemistry.drivers.GaussianDriver" />

`GaussianDriver(config='# rhf/sto-3g scf(conventional)\\n\\nh2 molecule\\n\\n0 1\\nH 0.0 0.0 0.0\\nH 0.0 0.0 0.735\\n\\n', molecule=None, basis='sto-3g', hf_method=<HFMethodType.RHF: 'rhf'>)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/chemistry/drivers/gaussiand/gaussiandriver.py "view source code")

Bases: `qiskit.chemistry.drivers.fermionic_driver.FermionicDriver`

Qiskit chemistry driver using the Gaussian™ 16 program.

See [http://gaussian.com/gaussian16/](http://gaussian.com/gaussian16/)

This driver uses the Gaussian open-source Gaussian 16 interfacing code in order to access integrals and other electronic structure information as computed by G16 for the given molecule. The job control file, as provided here for the molecular configuration, is augmented for our needs here such as to have it output a MatrixElement file.

**Parameters**

*   **config** (`Union`\[`str`, `List`\[`str`]]) – A molecular configuration conforming to Gaussian™ 16 format.
*   **molecule** (`Optional`\[`Molecule`]) – A driver independent Molecule definition instance may be provided. When a molecule is supplied the config parameter is ignored and the Molecule instance, along with basis and hf\_method is used to build a basic config instead. The Molecule object is read when the driver is run and converted to the driver dependent configuration for the computation. This allows, for example, the Molecule geometry to be updated to compute different points.
*   **basis** (`str`) – Basis set
*   **hf\_method** (`HFMethodType`) – Hartree-Fock Method type

**Raises**

[**QiskitChemistryError**](qiskit.chemistry.QiskitChemistryError "qiskit.chemistry.QiskitChemistryError") – Invalid Input

## Methods

### run

<span id="qiskit.chemistry.drivers.GaussianDriver.run" />

`GaussianDriver.run()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/chemistry/drivers/gaussiand/gaussiandriver.py "view source code")

Runs driver to produce a QMolecule output.

**Return type**

`QMolecule`

**Returns**

A QMolecule containing the molecular data.

## Attributes

<span id="qiskit.chemistry.drivers.GaussianDriver.basis" />

### basis

return basis

**Return type**

`str`

<span id="qiskit.chemistry.drivers.GaussianDriver.hf_method" />

### hf\_method

return Hartree-Fock method

**Return type**

`str`

<span id="qiskit.chemistry.drivers.GaussianDriver.molecule" />

### molecule

return molecule

**Return type**

`Optional`\[`Molecule`]

<span id="qiskit.chemistry.drivers.GaussianDriver.supports_molecule" />

### supports\_molecule

True for derived classes that support Molecule.

**Return type**

`bool`

**Returns**

True if Molecule is supported.

