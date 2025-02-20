---
title: WikipediaDataProvider
description: API reference for qiskit.finance.data_providers.WikipediaDataProvider
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.finance.data_providers.WikipediaDataProvider
---

# WikipediaDataProvider

<span id="qiskit.finance.data_providers.WikipediaDataProvider" />

`WikipediaDataProvider(token=None, tickers=None, start=datetime.datetime(2016, 1, 1, 0, 0), end=datetime.datetime(2016, 1, 30, 0, 0))`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/finance/data_providers/wikipedia_data_provider.py "view source code")

Bases: `qiskit.finance.data_providers._base_data_provider.BaseDataProvider`

Wikipedia data provider.

Please see: [https://github.com/Qiskit/qiskit-tutorials/blob/master/tutorials/finance/11\_time\_series.ipynb](https://github.com/Qiskit/qiskit-tutorials/blob/master/tutorials/finance/11_time_series.ipynb) for instructions on use.

Initializer :type token: `Optional`\[`str`] :param token: quandl access token, which is not needed, strictly speaking :type tickers: `Union`\[`str`, `List`\[`str`], `None`] :param tickers: tickers :type start: `datetime` :param start: start time :type end: `datetime` :param end: end time

> **Raises:**
>
> MissingOptionalLibraryError: Quandl not installed

## Methods

### get\_coordinates

<span id="qiskit.finance.data_providers.WikipediaDataProvider.get_coordinates" />

`WikipediaDataProvider.get_coordinates()`

Returns random coordinates for visualisation purposes.

**Return type**

`Tuple`\[`ndarray`, `ndarray`]

### get\_covariance\_matrix

<span id="qiskit.finance.data_providers.WikipediaDataProvider.get_covariance_matrix" />

`WikipediaDataProvider.get_covariance_matrix()`

Returns the covariance matrix.

**Return type**

`ndarray`

**Returns**

an asset-to-asset covariance matrix.

**Raises**

[**QiskitFinanceError**](qiskit.finance.QiskitFinanceError "qiskit.finance.QiskitFinanceError") – no data loaded

### get\_mean\_vector

<span id="qiskit.finance.data_providers.WikipediaDataProvider.get_mean_vector" />

`WikipediaDataProvider.get_mean_vector()`

Returns a vector containing the mean value of each asset.

**Return type**

`ndarray`

**Returns**

a per-asset mean vector.

**Raises**

[**QiskitFinanceError**](qiskit.finance.QiskitFinanceError "qiskit.finance.QiskitFinanceError") – no data loaded

### get\_period\_return\_covariance\_matrix

<span id="qiskit.finance.data_providers.WikipediaDataProvider.get_period_return_covariance_matrix" />

`WikipediaDataProvider.get_period_return_covariance_matrix()`

Returns a vector containing the mean value of each asset.

**Return type**

`ndarray`

**Returns**

a per-asset mean vector.

**Raises**

[**QiskitFinanceError**](qiskit.finance.QiskitFinanceError "qiskit.finance.QiskitFinanceError") – no data loaded

### get\_period\_return\_mean\_vector

<span id="qiskit.finance.data_providers.WikipediaDataProvider.get_period_return_mean_vector" />

`WikipediaDataProvider.get_period_return_mean_vector()`

Returns a vector containing the mean value of each asset.

**Return type**

`ndarray`

**Returns**

a per-asset mean vector.

**Raises**

[**QiskitFinanceError**](qiskit.finance.QiskitFinanceError "qiskit.finance.QiskitFinanceError") – no data loaded

### get\_similarity\_matrix

<span id="qiskit.finance.data_providers.WikipediaDataProvider.get_similarity_matrix" />

`WikipediaDataProvider.get_similarity_matrix()`

Returns time-series similarity matrix computed using dynamic time warping.

**Return type**

`ndarray`

**Returns**

an asset-to-asset similarity matrix.

**Raises**

[**QiskitFinanceError**](qiskit.finance.QiskitFinanceError "qiskit.finance.QiskitFinanceError") – no data loaded

### run

<span id="qiskit.finance.data_providers.WikipediaDataProvider.run" />

`WikipediaDataProvider.run()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/finance/data_providers/wikipedia_data_provider.py "view source code")

Loads data, thus enabling get\_similarity\_matrix and get\_covariance\_matrix methods in the base class.

**Return type**

`None`

