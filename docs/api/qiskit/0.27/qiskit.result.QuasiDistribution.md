---
title: QuasiDistribution
description: API reference for qiskit.result.QuasiDistribution
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.result.QuasiDistribution
---

# qiskit.result.QuasiDistribution

<span id="qiskit.result.QuasiDistribution" />

`QuasiDistribution(data, shots=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.17/qiskit/result/distributions/quasi.py "view source code")

A dict-like class for representing qasi-probabilities.

<Admonition title="Warning" type="caution">
  This is an unsupported class in the current 0.17.x release series. It is present for compatibility with the qiskit-ibmq-provider’s beta qiskit runtime support, but this interface isn’t guaranteed to be stable when moving to >=0.18.0 and likely will change.
</Admonition>

Builds a quasiprobability distribution object.

**Parameters**

*   **data** (*dict*) – Input quasiprobability data.
*   **shots** (*int*) – Number of shots the distribution was derived from.

### \_\_init\_\_

<span id="qiskit.result.QuasiDistribution.__init__" />

`__init__(data, shots=None)`

Builds a quasiprobability distribution object.

**Parameters**

*   **data** (*dict*) – Input quasiprobability data.
*   **shots** (*int*) – Number of shots the distribution was derived from.

## Methods

|                                                                                                                                                                                  |                                                                                                                                                                                                                               |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.result.QuasiDistribution.__init__ "qiskit.result.QuasiDistribution.__init__")(data\[, shots])                                                               | Builds a quasiprobability distribution object.                                                                                                                                                                                |
| [`clear`](#qiskit.result.QuasiDistribution.clear "qiskit.result.QuasiDistribution.clear")()                                                                                      |                                                                                                                                                                                                                               |
| [`copy`](#qiskit.result.QuasiDistribution.copy "qiskit.result.QuasiDistribution.copy")()                                                                                         |                                                                                                                                                                                                                               |
| [`fromkeys`](#qiskit.result.QuasiDistribution.fromkeys "qiskit.result.QuasiDistribution.fromkeys")(\[value])                                                                     | Create a new dictionary with keys from iterable and values set to value.                                                                                                                                                      |
| [`get`](#qiskit.result.QuasiDistribution.get "qiskit.result.QuasiDistribution.get")(key\[, default])                                                                             | Return the value for key if key is in the dictionary, else default.                                                                                                                                                           |
| [`items`](#qiskit.result.QuasiDistribution.items "qiskit.result.QuasiDistribution.items")()                                                                                      |                                                                                                                                                                                                                               |
| [`keys`](#qiskit.result.QuasiDistribution.keys "qiskit.result.QuasiDistribution.keys")()                                                                                         |                                                                                                                                                                                                                               |
| [`nearest_probability_distribution`](#qiskit.result.QuasiDistribution.nearest_probability_distribution "qiskit.result.QuasiDistribution.nearest_probability_distribution")(\[…]) | Takes a quasiprobability distribution and maps it to the closest probability distribution as defined by the L2-norm.                                                                                                          |
| [`pop`](#qiskit.result.QuasiDistribution.pop "qiskit.result.QuasiDistribution.pop")(k\[,d])                                                                                      | If key is not found, d is returned if given, otherwise KeyError is raised                                                                                                                                                     |
| [`popitem`](#qiskit.result.QuasiDistribution.popitem "qiskit.result.QuasiDistribution.popitem")()                                                                                | 2-tuple; but raise KeyError if D is empty.                                                                                                                                                                                    |
| [`setdefault`](#qiskit.result.QuasiDistribution.setdefault "qiskit.result.QuasiDistribution.setdefault")(key\[, default])                                                        | Insert key with a value of default if key is not in the dictionary.                                                                                                                                                           |
| [`update`](#qiskit.result.QuasiDistribution.update "qiskit.result.QuasiDistribution.update")(\[E, ]\*\*F)                                                                        | If E is present and has a .keys() method, then does: for k in E: D\[k] = E\[k] If E is present and lacks a .keys() method, then does: for k, v in E: D\[k] = v In either case, this is followed by: for k in F: D\[k] = F\[k] |
| [`values`](#qiskit.result.QuasiDistribution.values "qiskit.result.QuasiDistribution.values")()                                                                                   |                                                                                                                                                                                                                               |

### clear

<span id="qiskit.result.QuasiDistribution.clear" />

`clear() → None. Remove all items from D.`

### copy

<span id="qiskit.result.QuasiDistribution.copy" />

`copy() → a shallow copy of D`

### fromkeys

<span id="qiskit.result.QuasiDistribution.fromkeys" />

`fromkeys(value=None, /)`

Create a new dictionary with keys from iterable and values set to value.

### get

<span id="qiskit.result.QuasiDistribution.get" />

`get(key, default=None, /)`

Return the value for key if key is in the dictionary, else default.

### items

<span id="qiskit.result.QuasiDistribution.items" />

`items() → a set-like object providing a view on D’s items`

### keys

<span id="qiskit.result.QuasiDistribution.keys" />

`keys() → a set-like object providing a view on D’s keys`

### nearest\_probability\_distribution

<span id="qiskit.result.QuasiDistribution.nearest_probability_distribution" />

`nearest_probability_distribution(return_distance=False)`

Takes a quasiprobability distribution and maps it to the closest probability distribution as defined by the L2-norm.

**Parameters**

**return\_distance** (*bool*) – Return the L2 distance between distributions.

**Returns**

Nearest probability distribution. float: Euclidean (L2) distance of distributions.

**Return type**

[ProbDistribution](qiskit.result.ProbDistribution "qiskit.result.ProbDistribution")

## Notes

Method from Smolin et al., Phys. Rev. Lett. 108, 070502 (2012).

### pop

<span id="qiskit.result.QuasiDistribution.pop" />

`pop(k[, d]) → v, remove specified key and return the corresponding value.`

If key is not found, d is returned if given, otherwise KeyError is raised

### popitem

<span id="qiskit.result.QuasiDistribution.popitem" />

`popitem() → (k, v), remove and return some (key, value) pair as a`

2-tuple; but raise KeyError if D is empty.

### setdefault

<span id="qiskit.result.QuasiDistribution.setdefault" />

`setdefault(key, default=None, /)`

Insert key with a value of default if key is not in the dictionary.

Return the value for key if key is in the dictionary, else default.

### update

<span id="qiskit.result.QuasiDistribution.update" />

`update([E, ]**F) → None. Update D from dict/iterable E and F.`

If E is present and has a .keys() method, then does: for k in E: D\[k] = E\[k] If E is present and lacks a .keys() method, then does: for k, v in E: D\[k] = v In either case, this is followed by: for k in F: D\[k] = F\[k]

### values

<span id="qiskit.result.QuasiDistribution.values" />

`values() → an object providing a view on D’s values`

