---
title: ExchangeDataProvider
description: API reference for qiskit.finance.data_providers.ExchangeDataProvider
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.finance.data_providers.ExchangeDataProvider
---

# ExchangeDataProvider

<span id="qiskit.finance.data_providers.ExchangeDataProvider" />

`ExchangeDataProvider(token, tickers, stockmarket=StockMarket.LONDON, start=datetime.datetime(2016, 1, 1, 0, 0), end=datetime.datetime(2016, 1, 30, 0, 0))`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/finance/data_providers/exchange_data_provider.py "view source code")

Exchange data provider.

Please see: [https://github.com/Qiskit/qiskit-tutorials/blob/stable/0.14.x/qiskit/advanced/aqua/finance/data\_providers/time\_series.ipynb](https://github.com/Qiskit/qiskit-tutorials/blob/stable/0.14.x/qiskit/advanced/aqua/finance/data_providers/time_series.ipynb) for instructions on use, which involve obtaining a Quandl access token.

Initializer :type token: `str` :param token: quandl access token :type tickers: `Union`\[`str`, `List`\[`str`]] :param tickers: tickers :type stockmarket: [`StockMarket`](qiskit.finance.data_providers.StockMarket "qiskit.finance.data_providers._base_data_provider.StockMarket") :param stockmarket: LONDON, EURONEXT, or SINGAPORE :type start: \<module ‘datetime’ from ‘/usr/lib/python3.7/datetime.py’> :param start: first data point :type end: \<module ‘datetime’ from ‘/usr/lib/python3.7/datetime.py’> :param end: last data point precedes this date

**Raises**

[**QiskitFinanceError**](qiskit.finance.QiskitFinanceError "qiskit.finance.QiskitFinanceError") – provider doesn’t support stock market

## Methods

### get\_coordinates

<span id="qiskit.finance.data_providers.ExchangeDataProvider.get_coordinates" />

`ExchangeDataProvider.get_coordinates()`

Returns random coordinates for visualisation purposes.

### get\_covariance\_matrix

<span id="qiskit.finance.data_providers.ExchangeDataProvider.get_covariance_matrix" />

`ExchangeDataProvider.get_covariance_matrix()`

Returns the covariance matrix.

**Returns**

an asset-to-asset covariance matrix.

**Return type**

numpy.ndarray

**Raises**

[**QiskitFinanceError**](qiskit.finance.QiskitFinanceError "qiskit.finance.QiskitFinanceError") – no data loaded

### get\_mean\_vector

<span id="qiskit.finance.data_providers.ExchangeDataProvider.get_mean_vector" />

`ExchangeDataProvider.get_mean_vector()`

Returns a vector containing the mean value of each asset.

**Returns**

a per-asset mean vector.

**Return type**

numpy.ndarray

**Raises**

[**QiskitFinanceError**](qiskit.finance.QiskitFinanceError "qiskit.finance.QiskitFinanceError") – no data loaded

### get\_period\_return\_covariance\_matrix

<span id="qiskit.finance.data_providers.ExchangeDataProvider.get_period_return_covariance_matrix" />

`ExchangeDataProvider.get_period_return_covariance_matrix()`

Returns a vector containing the mean value of each asset.

**Returns**

a per-asset mean vector.

**Return type**

numpy.ndarray

**Raises**

[**QiskitFinanceError**](qiskit.finance.QiskitFinanceError "qiskit.finance.QiskitFinanceError") – no data loaded

### get\_period\_return\_mean\_vector

<span id="qiskit.finance.data_providers.ExchangeDataProvider.get_period_return_mean_vector" />

`ExchangeDataProvider.get_period_return_mean_vector()`

Returns a vector containing the mean value of each asset.

**Returns**

a per-asset mean vector.

**Return type**

numpy.ndarray

**Raises**

[**QiskitFinanceError**](qiskit.finance.QiskitFinanceError "qiskit.finance.QiskitFinanceError") – no data loaded

### get\_similarity\_matrix

<span id="qiskit.finance.data_providers.ExchangeDataProvider.get_similarity_matrix" />

`ExchangeDataProvider.get_similarity_matrix()`

Returns time-series similarity matrix computed using dynamic time warping.

**Returns**

an asset-to-asset similarity matrix.

**Return type**

numpy.ndarray

**Raises**

[**QiskitFinanceError**](qiskit.finance.QiskitFinanceError "qiskit.finance.QiskitFinanceError") – no data loaded

### run

<span id="qiskit.finance.data_providers.ExchangeDataProvider.run" />

`ExchangeDataProvider.run()`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.7/qiskit/finance/data_providers/exchange_data_provider.py "view source code")

Loads data, thus enabling get\_similarity\_matrix and get\_covariance\_matrix methods in the base class.

