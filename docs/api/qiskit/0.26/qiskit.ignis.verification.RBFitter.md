---
title: RBFitter
description: API reference for qiskit.ignis.verification.RBFitter
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.ignis.verification.RBFitter
---

# qiskit.ignis.verification.RBFitter

<span id="qiskit.ignis.verification.RBFitter" />

`RBFitter(backend_result, cliff_lengths, rb_pattern=None)`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.6/qiskit/ignis/verification/randomized_benchmarking/fitters.py "view source code")

Class for fitters for randomized benchmarking.

**Parameters**

*   **backend\_result** ([*Result*](qiskit.result.Result "qiskit.result.Result")) – list of results (qiskit.Result).
*   **cliff\_lengths** (*list*) – the Clifford lengths, 2D list i x j where i is the number of patterns, j is the number of cliffords lengths.
*   **rb\_pattern** (*list*) – the pattern for the RB sequences.

### \_\_init\_\_

<span id="qiskit.ignis.verification.RBFitter.__init__" />

`__init__(backend_result, cliff_lengths, rb_pattern=None)`

**Parameters**

*   **backend\_result** ([*Result*](qiskit.result.Result "qiskit.result.Result")) – list of results (qiskit.Result).
*   **cliff\_lengths** (*list*) – the Clifford lengths, 2D list i x j where i is the number of patterns, j is the number of cliffords lengths.
*   **rb\_pattern** (*list*) – the pattern for the RB sequences.

## Methods

|                                                                                                                                                            |                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [`__init__`](#qiskit.ignis.verification.RBFitter.__init__ "qiskit.ignis.verification.RBFitter.__init__")(backend\_result, cliff\_lengths\[, …])            | **param backend\_result**list of results (qiskit.Result).           |
| [`add_data`](#qiskit.ignis.verification.RBFitter.add_data "qiskit.ignis.verification.RBFitter.add_data")(new\_backend\_result\[, rerun\_fit])              | Add a new result.                                                   |
| [`calc_data`](#qiskit.ignis.verification.RBFitter.calc_data "qiskit.ignis.verification.RBFitter.calc_data")()                                              | Retrieve probabilities of success from execution results.           |
| [`calc_statistics`](#qiskit.ignis.verification.RBFitter.calc_statistics "qiskit.ignis.verification.RBFitter.calc_statistics")()                            | Extract averages and std dev from the raw data (self.\_raw\_data).  |
| [`fit_data`](#qiskit.ignis.verification.RBFitter.fit_data "qiskit.ignis.verification.RBFitter.fit_data")()                                                 | Fit the RB results to an exponential curve.                         |
| [`fit_data_pattern`](#qiskit.ignis.verification.RBFitter.fit_data_pattern "qiskit.ignis.verification.RBFitter.fit_data_pattern")(patt\_ind, fit\_guess)    | Fit the RB results of a particular pattern to an exponential curve. |
| [`plot_rb_data`](#qiskit.ignis.verification.RBFitter.plot_rb_data "qiskit.ignis.verification.RBFitter.plot_rb_data")(\[pattern\_index, ax, add\_label, …]) | Plot randomized benchmarking data of a single pattern.              |

## Attributes

|                                                                                                                         |                                       |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------- |
| [`cliff_lengths`](#qiskit.ignis.verification.RBFitter.cliff_lengths "qiskit.ignis.verification.RBFitter.cliff_lengths") | Return clifford lengths.              |
| [`fit`](#qiskit.ignis.verification.RBFitter.fit "qiskit.ignis.verification.RBFitter.fit")                               | Return fit.                           |
| [`raw_data`](#qiskit.ignis.verification.RBFitter.raw_data "qiskit.ignis.verification.RBFitter.raw_data")                | Return raw data.                      |
| [`rb_fit_fun`](#qiskit.ignis.verification.RBFitter.rb_fit_fun "qiskit.ignis.verification.RBFitter.rb_fit_fun")          | Return the fit function rb\_fit\_fun. |
| [`results`](#qiskit.ignis.verification.RBFitter.results "qiskit.ignis.verification.RBFitter.results")                   | Return all the results.               |
| [`seeds`](#qiskit.ignis.verification.RBFitter.seeds "qiskit.ignis.verification.RBFitter.seeds")                         | Return the number of loaded seeds.    |
| [`ydata`](#qiskit.ignis.verification.RBFitter.ydata "qiskit.ignis.verification.RBFitter.ydata")                         | Return ydata (means and std devs).    |

### add\_data

<span id="qiskit.ignis.verification.RBFitter.add_data" />

`add_data(new_backend_result, rerun_fit=True)`

Add a new result. Re calculate the raw data, means and fit.

**Parameters**

*   **new\_backend\_result** (*list*) – list of RB results.
*   **rerun\_fit** (*bool*) – re calculate the means and fit the result.

**Additional information:**

Assumes that the executed ‘result’ is the output of circuits generated by randomized\_benchmarking\_seq.

### calc\_data

<span id="qiskit.ignis.verification.RBFitter.calc_data" />

`calc_data()`

Retrieve probabilities of success from execution results.

Outputs results into an internal variable \_raw\_data which is a 3-dimensional list, where item (i,j,k) is the probability to measure the ground state for the set of qubits in pattern “i” for seed no. j and vector length self.\_cliff\_lengths\[i]\[k].

**Additional information:**

Assumes that the executed ‘result’ is the output of circuits generated by randomized\_benchmarking\_seq.

### calc\_statistics

<span id="qiskit.ignis.verification.RBFitter.calc_statistics" />

`calc_statistics()`

Extract averages and std dev from the raw data (self.\_raw\_data).

Assumes that self.\_calc\_data has been run. Output into internal \_ydata variable. ydata is a list of dictionaries (length number of patterns). Dictionary ydata\[i]:

> *   ydata\[i]\[‘mean’] is a numpy\_array of length n; entry j of this array contains the mean probability of success over seeds, for vector length self.\_cliff\_lengths\[i]\[j].
> *   ydata\[i]\[‘std’] is a numpy\_array of length n; entry j of this array contains the std of the probability of success over seeds, for vector length self.\_cliff\_lengths\[i]\[j].

### cliff\_lengths

<span id="qiskit.ignis.verification.RBFitter.cliff_lengths" />

`property cliff_lengths`

Return clifford lengths.

### fit

<span id="qiskit.ignis.verification.RBFitter.fit" />

`property fit`

Return fit.

### fit\_data

<span id="qiskit.ignis.verification.RBFitter.fit_data" />

`fit_data()`

Fit the RB results to an exponential curve.

Fit each of the patterns. Use the data to construct guess values for the fits.

Puts the results into a list of fit dictionaries where each dictionary corresponds to a pattern and has fields:

> *   `params` - three parameters of rb\_fit\_fun. The middle one is the exponent.
> *   `err` - the error limits of the parameters.
> *   `epc` - error per Clifford.

### fit\_data\_pattern

<span id="qiskit.ignis.verification.RBFitter.fit_data_pattern" />

`fit_data_pattern(patt_ind, fit_guess)`

Fit the RB results of a particular pattern to an exponential curve.

**Parameters**

*   **patt\_ind** (*int*) – index of the data pattern to fit.
*   **fit\_guess** (*list*) – guess values for the fit.

Puts the results into a list of fit dictionaries where each dictionary corresponds to a pattern and has fields:

> *   `params` - three parameters of rb\_fit\_fun. The middle one is the exponent.
> *   `err` - the error limits of the parameters.
> *   `epc` - error per Clifford.

### plot\_rb\_data

<span id="qiskit.ignis.verification.RBFitter.plot_rb_data" />

`plot_rb_data(pattern_index=0, ax=None, add_label=True, show_plt=True)`

Plot randomized benchmarking data of a single pattern.

**Parameters**

*   **pattern\_index** (*int*) – which RB pattern to plot.
*   **ax** (*Axes*) – plot axis (if passed in).
*   **add\_label** (*bool*) – Add an EPC label.
*   **show\_plt** (*bool*) – display the plot.

**Raises**

**ImportError** – if matplotlib is not installed.

### raw\_data

<span id="qiskit.ignis.verification.RBFitter.raw_data" />

`property raw_data`

Return raw data.

### rb\_fit\_fun

<span id="qiskit.ignis.verification.RBFitter.rb_fit_fun" />

`property rb_fit_fun`

Return the fit function rb\_fit\_fun.

### results

<span id="qiskit.ignis.verification.RBFitter.results" />

`property results`

Return all the results.

### seeds

<span id="qiskit.ignis.verification.RBFitter.seeds" />

`property seeds`

Return the number of loaded seeds.

### ydata

<span id="qiskit.ignis.verification.RBFitter.ydata" />

`property ydata`

Return ydata (means and std devs).

