---
title: AmplitudeEstimationResult
description: API reference for qiskit.aqua.algorithms.AmplitudeEstimationResult
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.aqua.algorithms.AmplitudeEstimationResult
---

# qiskit.aqua.algorithms.AmplitudeEstimationResult

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult" />

`AmplitudeEstimationResult(a_dict=None)`[GitHub](https://github.com/qiskit-community/qiskit-aqua/tree/stable/0.9/qiskit/aqua/algorithms/amplitude_estimators/ae.py "view source code")

AmplitudeEstimation Result.

### \_\_init\_\_

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.__init__" />

`__init__(a_dict=None)`

Initialize self. See help(type(self)) for accurate signature.

## Methods

|                                                                                                                                                    |                                                                                                                                                                                                                      |
| -------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.__init__ "qiskit.aqua.algorithms.AmplitudeEstimationResult.__init__")(\[a\_dict])   | Initialize self.                                                                                                                                                                                                     |
| [`clear`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.clear "qiskit.aqua.algorithms.AmplitudeEstimationResult.clear")()                      | **rtype**`None`                                                                                                                                                                                                      |
| [`combine`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.combine "qiskit.aqua.algorithms.AmplitudeEstimationResult.combine")(result)          | Any property from the argument that exists in the receiver is updated.                                                                                                                                               |
| `copy`()                                                                                                                                           |                                                                                                                                                                                                                      |
| [`from_dict`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.from_dict "qiskit.aqua.algorithms.AmplitudeEstimationResult.from_dict")(a\_dict)   | create new object from a dictionary                                                                                                                                                                                  |
| `fromkeys`(iterable\[, value])                                                                                                                     |                                                                                                                                                                                                                      |
| [`get`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.get "qiskit.aqua.algorithms.AmplitudeEstimationResult.get")(k\[,d])                      |                                                                                                                                                                                                                      |
| [`items`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.items "qiskit.aqua.algorithms.AmplitudeEstimationResult.items")()                      |                                                                                                                                                                                                                      |
| [`keys`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.keys "qiskit.aqua.algorithms.AmplitudeEstimationResult.keys")()                         |                                                                                                                                                                                                                      |
| [`pop`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.pop "qiskit.aqua.algorithms.AmplitudeEstimationResult.pop")(key\[, default])             | If key is not found, d is returned if given, otherwise KeyError is raised.                                                                                                                                           |
| [`popitem`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.popitem "qiskit.aqua.algorithms.AmplitudeEstimationResult.popitem")()                | as a 2-tuple; but raise KeyError if D is empty.                                                                                                                                                                      |
| [`setdefault`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.setdefault "qiskit.aqua.algorithms.AmplitudeEstimationResult.setdefault")(k\[,d]) |                                                                                                                                                                                                                      |
| [`update`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.update "qiskit.aqua.algorithms.AmplitudeEstimationResult.update")(\*args, \*\*kwargs) | If E present and has a .keys() method, does: for k in E: D\[k] = E\[k] If E present and lacks .keys() method, does: for (k, v) in E: D\[k] = v In either case, this is followed by: for k, v in F.items(): D\[k] = v |
| [`values`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.values "qiskit.aqua.algorithms.AmplitudeEstimationResult.values")()                   |                                                                                                                                                                                                                      |

## Attributes

|                                                                                                                                                                       |                             |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------- |
| [`a_estimation`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.a_estimation "qiskit.aqua.algorithms.AmplitudeEstimationResult.a_estimation")                      | return a\_estimation        |
| [`a_samples`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.a_samples "qiskit.aqua.algorithms.AmplitudeEstimationResult.a_samples")                               | return a\_samples           |
| [`circuit_result`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.circuit_result "qiskit.aqua.algorithms.AmplitudeEstimationResult.circuit_result")                | return circuit result       |
| [`confidence_interval`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.confidence_interval "qiskit.aqua.algorithms.AmplitudeEstimationResult.confidence_interval") | return confidence\_interval |
| [`estimation`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.estimation "qiskit.aqua.algorithms.AmplitudeEstimationResult.estimation")                            | return estimation           |
| [`mapped_a_samples`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.mapped_a_samples "qiskit.aqua.algorithms.AmplitudeEstimationResult.mapped_a_samples")          | return mapped\_a\_samples   |
| [`mapped_values`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.mapped_values "qiskit.aqua.algorithms.AmplitudeEstimationResult.mapped_values")                   | return mapped\_values       |
| [`max_probability`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.max_probability "qiskit.aqua.algorithms.AmplitudeEstimationResult.max_probability")             | return max\_probability     |
| [`ml_value`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.ml_value "qiskit.aqua.algorithms.AmplitudeEstimationResult.ml_value")                                  | returns ml\_value           |
| [`mle`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.mle "qiskit.aqua.algorithms.AmplitudeEstimationResult.mle")                                                 | return mle                  |
| [`num_oracle_queries`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.num_oracle_queries "qiskit.aqua.algorithms.AmplitudeEstimationResult.num_oracle_queries")    | return num\_oracle\_queries |
| [`probabilities`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.probabilities "qiskit.aqua.algorithms.AmplitudeEstimationResult.probabilities")                   | return probabilities        |
| [`shots`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.shots "qiskit.aqua.algorithms.AmplitudeEstimationResult.shots")                                           | return shots                |
| [`y_measurements`](#qiskit.aqua.algorithms.AmplitudeEstimationResult.y_measurements "qiskit.aqua.algorithms.AmplitudeEstimationResult.y_measurements")                | return y\_measurements      |

### a\_estimation

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.a_estimation" />

`property a_estimation`

return a\_estimation

**Return type**

`float`

### a\_samples

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.a_samples" />

`property a_samples`

return a\_samples

**Return type**

`List`\[`Tuple`\[`float`, `float`]]

### circuit\_result

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.circuit_result" />

`property circuit_result`

return circuit result

**Return type**

`Union`\[`ndarray`, `Dict`\[`str`, `int`], `None`]

### clear

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.clear" />

`clear()`

**Return type**

`None`

### combine

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.combine" />

`combine(result)`

Any property from the argument that exists in the receiver is updated. :type result: `AlgorithmResult` :param result: Argument result with properties to be set.

**Raises**

**TypeError** – Argument is None

**Return type**

`None`

### confidence\_interval

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.confidence_interval" />

`property confidence_interval`

return confidence\_interval

**Return type**

`List`\[`float`]

### estimation

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.estimation" />

`property estimation`

return estimation

**Return type**

`float`

### from\_dict

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.from_dict" />

`static from_dict(a_dict)`

create new object from a dictionary

**Return type**

`AmplitudeEstimationResult`

### get

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.get" />

`get(k[, d]) → D[k] if k in D, else d. d defaults to None.`

### items

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.items" />

`items() → a set-like object providing a view on D’s items`

### keys

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.keys" />

`keys() → a set-like object providing a view on D’s keys`

### mapped\_a\_samples

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.mapped_a_samples" />

`property mapped_a_samples`

return mapped\_a\_samples

**Return type**

`List`\[`float`]

### mapped\_values

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.mapped_values" />

`property mapped_values`

return mapped\_values

**Return type**

`List`\[`float`]

### max\_probability

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.max_probability" />

`property max_probability`

return max\_probability

**Return type**

`float`

### ml\_value

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.ml_value" />

`property ml_value`

returns ml\_value

**Return type**

`float`

### mle

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.mle" />

`property mle`

return mle

**Return type**

`float`

### num\_oracle\_queries

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.num_oracle_queries" />

`property num_oracle_queries`

return num\_oracle\_queries

**Return type**

`int`

### pop

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.pop" />

`pop(key, default=None)`

If key is not found, d is returned if given, otherwise KeyError is raised.

**Return type**

`object`

### popitem

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.popitem" />

`popitem()`

as a 2-tuple; but raise KeyError if D is empty.

**Return type**

`Tuple`\[`object`, `object`]

### probabilities

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.probabilities" />

`property probabilities`

return probabilities

**Return type**

`List`\[`float`]

### setdefault

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.setdefault" />

`setdefault(k[, d]) → D.get(k,d), also set D[k]=d if k not in D`

### shots

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.shots" />

`property shots`

return shots

**Return type**

`int`

### update

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.update" />

`update(*args, **kwargs)`

If E present and has a .keys() method, does: for k in E: D\[k] = E\[k] If E present and lacks .keys() method, does: for (k, v) in E: D\[k] = v In either case, this is followed by: for k, v in F.items(): D\[k] = v

**Return type**

`None`

### values

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.values" />

`values() → an object providing a view on D’s values`

### y\_measurements

<span id="qiskit.aqua.algorithms.AmplitudeEstimationResult.y_measurements" />

`property y_measurements`

return y\_measurements

**Return type**

`List`\[`Tuple`\[`int`, `float`]]

