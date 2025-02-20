---
title: ProbDistribution
description: API reference for qiskit.result.ProbDistribution
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.result.ProbDistribution
---

# ProbDistribution

<span id="qiskit.result.ProbDistribution" />

`ProbDistribution(data, shots=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/result/distributions/probability.py "view source code")

Bases: `dict`

A generic dict-like class for probability distributions.

Builds a probability distribution object.

**Parameters**

*   **data** (*dict*) –

    Input probability data. Where the keys represent a measured classical value and the value is a float for the probability of that result. The keys can be one of several formats:

    > *   A hexadecimal string of the form `"0x4a"`
    > *   A bit string e.g. `'0b1011'` or `"01011"`
    > *   An integer

*   **shots** (*int*) – Number of shots the distribution was derived from.

**Raises**

*   **TypeError** – If the input keys are not a string or int
*   **ValueError** – If the string format of the keys is incorrect

## Methods

### binary\_probabilities

<span id="qiskit.result.ProbDistribution.binary_probabilities" />

`ProbDistribution.binary_probabilities(num_bits=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/result/distributions/probability.py "view source code")

Build a probabilities dictionary with binary string keys

**Parameters**

**num\_bits** (*int*) – number of bits in the binary bitstrings (leading zeros will be padded). If None, the length will be derived from the largest key present.

**Returns**

**A dictionary where the keys are binary strings in the format**

`"0110"`

**Return type**

dict

### clear

<span id="qiskit.result.ProbDistribution.clear" />

`ProbDistribution.clear() → None. Remove all items from D.`

### copy

<span id="qiskit.result.ProbDistribution.copy" />

`ProbDistribution.copy() → a shallow copy of D`

### fromkeys

<span id="qiskit.result.ProbDistribution.fromkeys" />

`ProbDistribution.fromkeys(value=None, /)`

Create a new dictionary with keys from iterable and values set to value.

### get

<span id="qiskit.result.ProbDistribution.get" />

`ProbDistribution.get(key, default=None, /)`

Return the value for key if key is in the dictionary, else default.

### hex\_probabilities

<span id="qiskit.result.ProbDistribution.hex_probabilities" />

`ProbDistribution.hex_probabilities()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.19/qiskit/result/distributions/probability.py "view source code")

Build a probabilities dictionary with hexadecimal string keys

**Returns**

**A dictionary where the keys are hexadecimal strings in the**

format `"0x1a"`

**Return type**

dict

### items

<span id="qiskit.result.ProbDistribution.items" />

`ProbDistribution.items() → a set-like object providing a view on D’s items`

### keys

<span id="qiskit.result.ProbDistribution.keys" />

`ProbDistribution.keys() → a set-like object providing a view on D’s keys`

### pop

<span id="qiskit.result.ProbDistribution.pop" />

`ProbDistribution.pop(k[, d]) → v, remove specified key and return the corresponding value.`

If key is not found, d is returned if given, otherwise KeyError is raised

### popitem

<span id="qiskit.result.ProbDistribution.popitem" />

`ProbDistribution.popitem() → (k, v), remove and return some (key, value) pair as a`

2-tuple; but raise KeyError if D is empty.

### setdefault

<span id="qiskit.result.ProbDistribution.setdefault" />

`ProbDistribution.setdefault(key, default=None, /)`

Insert key with a value of default if key is not in the dictionary.

Return the value for key if key is in the dictionary, else default.

### update

<span id="qiskit.result.ProbDistribution.update" />

`ProbDistribution.update([E, ]**F) → None. Update D from dict/iterable E and F.`

If E is present and has a .keys() method, then does: for k in E: D\[k] = E\[k] If E is present and lacks a .keys() method, then does: for k, v in E: D\[k] = v In either case, this is followed by: for k in F: D\[k] = F\[k]

### values

<span id="qiskit.result.ProbDistribution.values" />

`ProbDistribution.values() → an object providing a view on D’s values`

