---
title: RandomDataProvider
description: API reference for qiskit.finance.data_providers.RandomDataProvider
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.finance.data_providers.RandomDataProvider
---

# RandomDataProvider

<span id="qiskit.finance.data_providers.RandomDataProvider" />

`RandomDataProvider(tickers=None, start=datetime.datetime(2016, 1, 1, 0, 0), end=datetime.datetime(2016, 1, 30, 0, 0), seed=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/finance/data_providers/random_data_provider.py "view source code")

Bases: `qiskit.finance.data_providers._base_data_provider.BaseDataProvider`

Pseudo-randomly generated mock stock-market data provider.

Initializer :type tickers: `Union`\[`str`, `List`\[`str`], `None`] :param tickers: tickers :type start: `datetime` :param start: first data point :type end: `datetime` :param end: last data point precedes this date :type seed: `Optional`\[`int`] :param seed: shall a seed be used?

**Raises**

[**MissingOptionalLibraryError**](qiskit.aqua.MissingOptionalLibraryError "qiskit.aqua.MissingOptionalLibraryError") – Pandas not installed

## Methods

### get\_coordinates

<span id="qiskit.finance.data_providers.RandomDataProvider.get_coordinates" />

`RandomDataProvider.get_coordinates()`

Returns random coordinates for visualisation purposes.

**Return type**

`Tuple`\[`ndarray`, `ndarray`]

### get\_covariance\_matrix

<span id="qiskit.finance.data_providers.RandomDataProvider.get_covariance_matrix" />

`RandomDataProvider.get_covariance_matrix()`

Returns the covariance matrix.

**Return type**

`ndarray`

**Returns**

an asset-to-asset covariance matrix.

**Raises**

[**QiskitFinanceError**](qiskit.finance.QiskitFinanceError "qiskit.finance.QiskitFinanceError") – no data loaded

### get\_mean\_vector

<span id="qiskit.finance.data_providers.RandomDataProvider.get_mean_vector" />

`RandomDataProvider.get_mean_vector()`

Returns a vector containing the mean value of each asset.

**Return type**

`ndarray`

**Returns**

a per-asset mean vector.

**Raises**

[**QiskitFinanceError**](qiskit.finance.QiskitFinanceError "qiskit.finance.QiskitFinanceError") – no data loaded

### get\_period\_return\_covariance\_matrix

<span id="qiskit.finance.data_providers.RandomDataProvider.get_period_return_covariance_matrix" />

`RandomDataProvider.get_period_return_covariance_matrix()`

Returns a vector containing the mean value of each asset.

**Return type**

`ndarray`

**Returns**

a per-asset mean vector.

**Raises**

[**QiskitFinanceError**](qiskit.finance.QiskitFinanceError "qiskit.finance.QiskitFinanceError") – no data loaded

### get\_period\_return\_mean\_vector

<span id="qiskit.finance.data_providers.RandomDataProvider.get_period_return_mean_vector" />

`RandomDataProvider.get_period_return_mean_vector()`

Returns a vector containing the mean value of each asset.

**Return type**

`ndarray`

**Returns**

a per-asset mean vector.

**Raises**

[**QiskitFinanceError**](qiskit.finance.QiskitFinanceError "qiskit.finance.QiskitFinanceError") – no data loaded

### get\_similarity\_matrix

<span id="qiskit.finance.data_providers.RandomDataProvider.get_similarity_matrix" />

`RandomDataProvider.get_similarity_matrix()`

Returns time-series similarity matrix computed using dynamic time warping.

**Return type**

`ndarray`

**Returns**

an asset-to-asset similarity matrix.

**Raises**

[**QiskitFinanceError**](qiskit.finance.QiskitFinanceError "qiskit.finance.QiskitFinanceError") – no data loaded

### run

<span id="qiskit.finance.data_providers.RandomDataProvider.run" />

`RandomDataProvider.run()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/finance/data_providers/random_data_provider.py "view source code")

Generates data pseudo-randomly, thus enabling get\_similarity\_matrix and get\_covariance\_matrix methods in the base class.

**Return type**

`None`

