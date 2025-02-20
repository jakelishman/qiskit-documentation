---
title: CNOTDihedralRBFitter
description: API reference for qiskit.ignis.verification.CNOTDihedralRBFitter
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.ignis.verification.CNOTDihedralRBFitter
---

# qiskit.ignis.verification.CNOTDihedralRBFitter

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter" />

`CNOTDihedralRBFitter(cnotdihedral_Z_result, cnotdihedral_X_result, elmnts_lengths, rb_pattern=None)`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.6/qiskit/ignis/verification/randomized_benchmarking/fitters.py "view source code")

Class for fitters for non-Clifford CNOT-Dihedral RB.

Derived from RBFitterBase class. Contains two RBFitter objects.

**Parameters**

*   **cnotdihedral\_Z\_result** (*qiskit.Result*) – list of results of the RB sequence that measures the ground state.
*   **cnotdihedral\_X\_result** (*qiskit.Result*) – list of results of the RB sequence that measures the $|+...+>$ state.
*   **elmnts\_lengths** (*list*) – the group elements lengths, 2D list i x j where i is the number of patterns, j is the number of elements lengths.
*   **rb\_pattern** (*list*) – the pattern for the RB sequences.

### \_\_init\_\_

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.__init__" />

`__init__(cnotdihedral_Z_result, cnotdihedral_X_result, elmnts_lengths, rb_pattern=None)`

**Parameters**

*   **cnotdihedral\_Z\_result** (*qiskit.Result*) – list of results of the RB sequence that measures the ground state.
*   **cnotdihedral\_X\_result** (*qiskit.Result*) – list of results of the RB sequence that measures the $|+...+>$ state.
*   **elmnts\_lengths** (*list*) – the group elements lengths, 2D list i x j where i is the number of patterns, j is the number of elements lengths.
*   **rb\_pattern** (*list*) – the pattern for the RB sequences.

## Methods

|                                                                                                                                                                                       |                                                                                   |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.ignis.verification.CNOTDihedralRBFitter.__init__ "qiskit.ignis.verification.CNOTDihedralRBFitter.__init__")(cnotdihedral\_Z\_result, …\[, …])                    | **param cnotdihedral\_Z\_result**list of results of the                           |
| [`add_data`](#qiskit.ignis.verification.CNOTDihedralRBFitter.add_data "qiskit.ignis.verification.CNOTDihedralRBFitter.add_data")(new\_cnotdihedral\_Z\_result, …\[, …])               | Add a new result.                                                                 |
| [`calc_data`](#qiskit.ignis.verification.CNOTDihedralRBFitter.calc_data "qiskit.ignis.verification.CNOTDihedralRBFitter.calc_data")()                                                 | Retrieve probabilities of success from execution results.                         |
| [`calc_statistics`](#qiskit.ignis.verification.CNOTDihedralRBFitter.calc_statistics "qiskit.ignis.verification.CNOTDihedralRBFitter.calc_statistics")()                               | Extract averages and std dev.                                                     |
| [`fit_data`](#qiskit.ignis.verification.CNOTDihedralRBFitter.fit_data "qiskit.ignis.verification.CNOTDihedralRBFitter.fit_data")()                                                    | Fit the non-Clifford cnot-dihedral RB results.                                    |
| [`fit_data_pattern`](#qiskit.ignis.verification.CNOTDihedralRBFitter.fit_data_pattern "qiskit.ignis.verification.CNOTDihedralRBFitter.fit_data_pattern")(patt\_ind, fit\_guess\[, …]) | Fit the RB results of a particular pattern to an exponential curve.               |
| [`plot_rb_data`](#qiskit.ignis.verification.CNOTDihedralRBFitter.plot_rb_data "qiskit.ignis.verification.CNOTDihedralRBFitter.plot_rb_data")(\[pattern\_index, ax, add\_label, …])    | Plot non-Clifford cnot-dihedral randomized benchmarking data of a single pattern. |

## Attributes

|                                                                                                                                                          |                                                        |
| -------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------ |
| [`cliff_lengths`](#qiskit.ignis.verification.CNOTDihedralRBFitter.cliff_lengths "qiskit.ignis.verification.CNOTDihedralRBFitter.cliff_lengths")          | Return group elements lengths.                         |
| [`fit`](#qiskit.ignis.verification.CNOTDihedralRBFitter.fit "qiskit.ignis.verification.CNOTDihedralRBFitter.fit")                                        | Return fit as a 2 element list.                        |
| [`fit_cnotdihedral`](#qiskit.ignis.verification.CNOTDihedralRBFitter.fit_cnotdihedral "qiskit.ignis.verification.CNOTDihedralRBFitter.fit_cnotdihedral") | Return cnotdihedral fit parameters.                    |
| [`raw_data`](#qiskit.ignis.verification.CNOTDihedralRBFitter.raw_data "qiskit.ignis.verification.CNOTDihedralRBFitter.raw_data")                         | Return raw\_data as 2 element list.                    |
| [`rb_fit_fun`](#qiskit.ignis.verification.CNOTDihedralRBFitter.rb_fit_fun "qiskit.ignis.verification.CNOTDihedralRBFitter.rb_fit_fun")                   | Return the fit function rb\_fit\_fun.                  |
| [`rbfit_X`](#qiskit.ignis.verification.CNOTDihedralRBFitter.rbfit_X "qiskit.ignis.verification.CNOTDihedralRBFitter.rbfit_X")                            | Return the cnotdihedral X fitter.                      |
| [`rbfit_Z`](#qiskit.ignis.verification.CNOTDihedralRBFitter.rbfit_Z "qiskit.ignis.verification.CNOTDihedralRBFitter.rbfit_Z")                            | Return the cnotdihedral Z fitter.                      |
| [`results`](#qiskit.ignis.verification.CNOTDihedralRBFitter.results "qiskit.ignis.verification.CNOTDihedralRBFitter.results")                            | Return all the results as a 2 element list.            |
| [`seeds`](#qiskit.ignis.verification.CNOTDihedralRBFitter.seeds "qiskit.ignis.verification.CNOTDihedralRBFitter.seeds")                                  | Return the number of loaded seeds as a 2 element list. |
| [`ydata`](#qiskit.ignis.verification.CNOTDihedralRBFitter.ydata "qiskit.ignis.verification.CNOTDihedralRBFitter.ydata")                                  | Return ydata (means and std devs) as a 2 element list. |

### add\_data

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.add_data" />

`add_data(new_cnotdihedral_Z_result, new_cnotdihedral_X_result, rerun_fit=True)`

Add a new result.

**Parameters**

*   **new\_cnotdihedral\_Z\_result** (*list*) – list of rb results of the cnot-dihedral Z circuits.
*   **new\_cnotdihedral\_X\_result** (*list*) – list of rb results of the cnot-dihedral X circuits.
*   **rerun\_fit** (*bool*) – re-calculate the means and fit the result.

**Additional information:**

Assumes that the executed ‘result’ is the output of circuits generated by randomized\_benchmarking\_seq.

### calc\_data

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.calc_data" />

`calc_data()`

Retrieve probabilities of success from execution results. Outputs results into an internal variable: \_raw\_data .

### calc\_statistics

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.calc_statistics" />

`calc_statistics()`

Extract averages and std dev. Outputs results into an internal variable: \_ydata .

### cliff\_lengths

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.cliff_lengths" />

`property cliff_lengths`

Return group elements lengths.

### fit

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.fit" />

`property fit`

Return fit as a 2 element list.

### fit\_cnotdihedral

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.fit_cnotdihedral" />

`property fit_cnotdihedral`

Return cnotdihedral fit parameters.

### fit\_data

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.fit_data" />

`fit_data()`

Fit the non-Clifford cnot-dihedral RB results.

Fit each of the patterns. According to the paper:

[Scalable randomized benchmarking of non-Clifford gates](https://www.nature.com/articles/npjqi201612)

**Returns**

A list of dictionaries where each dictionary corresponds to a pattern and has fields:

> *   `alpha` - alpha parameter of the non-Clifford cnot-dihedral RB.
> *   `'alpha_err` - the error of the alpha parameter of the non-Clifford cnot-dihedral RB.
> *   `epg_est` - the estimated error per a CNOT-dihedral element.
> *   `epg_est_error` - the estimated error derived from the params\_err.

**Return type**

list

### fit\_data\_pattern

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.fit_data_pattern" />

`fit_data_pattern(patt_ind, fit_guess, fit_index=0)`

Fit the RB results of a particular pattern to an exponential curve.

**Parameters**

*   **patt\_ind** (*int*) – index of the data pattern to fit.
*   **fit\_guess** (*list*) – guess values for the fit.
*   **fit\_index** (*int*) – 0 fit the standard data, 1 fit the interleaved data.

### plot\_rb\_data

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.plot_rb_data" />

`plot_rb_data(pattern_index=0, ax=None, add_label=True, show_plt=True)`

Plot non-Clifford cnot-dihedral randomized benchmarking data of a single pattern.

**Parameters**

*   **pattern\_index** (*int*) – which RB pattern to plot.
*   **ax** (*Axes*) – plot axis (if passed in).
*   **add\_label** (*bool*) – Add an EPG label.
*   **show\_plt** (*bool*) – display the plot.

**Raises**

**ImportError** – if matplotlib is not installed.

### raw\_data

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.raw_data" />

`property raw_data`

Return raw\_data as 2 element list.

### rb\_fit\_fun

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.rb_fit_fun" />

`property rb_fit_fun`

Return the fit function rb\_fit\_fun.

### rbfit\_X

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.rbfit_X" />

`property rbfit_X`

Return the cnotdihedral X fitter.

### rbfit\_Z

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.rbfit_Z" />

`property rbfit_Z`

Return the cnotdihedral Z fitter.

### results

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.results" />

`property results`

Return all the results as a 2 element list.

### seeds

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.seeds" />

`property seeds`

Return the number of loaded seeds as a 2 element list.

### ydata

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.ydata" />

`property ydata`

Return ydata (means and std devs) as a 2 element list.

