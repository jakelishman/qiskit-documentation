---
title: Counts
description: API reference for qiskit.result.Counts
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.result.Counts
---

# qiskit.result.Counts

<span id="qiskit.result.Counts" />

`Counts(data, time_taken=None, creg_sizes=None, memory_slots=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.17/qiskit/result/counts.py "view source code")

A class to store a counts result from a circuit execution.

Build a counts object

**Parameters**

*   **data** (*dict*) –

    The dictionary input for the counts. Where the keys represent a measured classical value and the value is an integer the number of shots with that result. The keys can be one of several formats:

    > *   A hexadecimal string of the form `"0x4a"`
    > *   A bit string prefixed with `0b` for example `'0b1011'`
    > *   A bit string formatted across register and memory slots. For example, `'00 10'`.
    > *   A dit string, for example `'02'`. Note for objects created with dit strings the `creg_sizes``and ``memory_slots` kwargs don’t work and [`hex_outcomes()`](#qiskit.result.Counts.hex_outcomes "qiskit.result.Counts.hex_outcomes") and [`int_outcomes()`](#qiskit.result.Counts.int_outcomes "qiskit.result.Counts.int_outcomes") also do not work.

*   **time\_taken** (*float*) – The duration of the experiment that generated the counts

*   **creg\_sizes** (*list*) – a nested list where the inner element is a list of tuples containing both the classical register name and classical register size. For example, `[('c_reg', 2), ('my_creg', 4)]`.

*   **memory\_slots** (*int*) – The number of total `memory_slots` in the experiment.

**Raises**

*   **TypeError** – If the input key type is not an int or string
*   **QiskitError** – If a dit string key is input with creg\_sizes and/or memory\_slots

### \_\_init\_\_

<span id="qiskit.result.Counts.__init__" />

`__init__(data, time_taken=None, creg_sizes=None, memory_slots=None)`

Build a counts object

**Parameters**

*   **data** (*dict*) –

    The dictionary input for the counts. Where the keys represent a measured classical value and the value is an integer the number of shots with that result. The keys can be one of several formats:

    > *   A hexadecimal string of the form `"0x4a"`
    > *   A bit string prefixed with `0b` for example `'0b1011'`
    > *   A bit string formatted across register and memory slots. For example, `'00 10'`.
    > *   A dit string, for example `'02'`. Note for objects created with dit strings the `creg_sizes``and ``memory_slots` kwargs don’t work and [`hex_outcomes()`](#qiskit.result.Counts.hex_outcomes "qiskit.result.Counts.hex_outcomes") and [`int_outcomes()`](#qiskit.result.Counts.int_outcomes "qiskit.result.Counts.int_outcomes") also do not work.

*   **time\_taken** (*float*) – The duration of the experiment that generated the counts

*   **creg\_sizes** (*list*) – a nested list where the inner element is a list of tuples containing both the classical register name and classical register size. For example, `[('c_reg', 2), ('my_creg', 4)]`.

*   **memory\_slots** (*int*) – The number of total `memory_slots` in the experiment.

**Raises**

*   **TypeError** – If the input key type is not an int or string
*   **QiskitError** – If a dit string key is input with creg\_sizes and/or memory\_slots

## Methods

|                                                                                                                    |                                                                                                                                                                                                                               |
| ------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.result.Counts.__init__ "qiskit.result.Counts.__init__")(data\[, time\_taken, creg\_sizes, …]) | Build a counts object                                                                                                                                                                                                         |
| [`clear`](#qiskit.result.Counts.clear "qiskit.result.Counts.clear")()                                              |                                                                                                                                                                                                                               |
| [`copy`](#qiskit.result.Counts.copy "qiskit.result.Counts.copy")()                                                 |                                                                                                                                                                                                                               |
| [`fromkeys`](#qiskit.result.Counts.fromkeys "qiskit.result.Counts.fromkeys")(\[value])                             | Create a new dictionary with keys from iterable and values set to value.                                                                                                                                                      |
| [`get`](#qiskit.result.Counts.get "qiskit.result.Counts.get")(key\[, default])                                     | Return the value for key if key is in the dictionary, else default.                                                                                                                                                           |
| [`hex_outcomes`](#qiskit.result.Counts.hex_outcomes "qiskit.result.Counts.hex_outcomes")()                         | Return a counts dictionary with hexadecimal string keys                                                                                                                                                                       |
| [`int_outcomes`](#qiskit.result.Counts.int_outcomes "qiskit.result.Counts.int_outcomes")()                         | Build a counts dictionary with integer keys instead of count strings                                                                                                                                                          |
| [`items`](#qiskit.result.Counts.items "qiskit.result.Counts.items")()                                              |                                                                                                                                                                                                                               |
| [`keys`](#qiskit.result.Counts.keys "qiskit.result.Counts.keys")()                                                 |                                                                                                                                                                                                                               |
| [`most_frequent`](#qiskit.result.Counts.most_frequent "qiskit.result.Counts.most_frequent")()                      | Return the most frequent count                                                                                                                                                                                                |
| [`pop`](#qiskit.result.Counts.pop "qiskit.result.Counts.pop")(k\[,d])                                              | If key is not found, d is returned if given, otherwise KeyError is raised                                                                                                                                                     |
| [`popitem`](#qiskit.result.Counts.popitem "qiskit.result.Counts.popitem")()                                        | 2-tuple; but raise KeyError if D is empty.                                                                                                                                                                                    |
| [`setdefault`](#qiskit.result.Counts.setdefault "qiskit.result.Counts.setdefault")(key\[, default])                | Insert key with a value of default if key is not in the dictionary.                                                                                                                                                           |
| [`update`](#qiskit.result.Counts.update "qiskit.result.Counts.update")(\[E, ]\*\*F)                                | If E is present and has a .keys() method, then does: for k in E: D\[k] = E\[k] If E is present and lacks a .keys() method, then does: for k, v in E: D\[k] = v In either case, this is followed by: for k in F: D\[k] = F\[k] |
| [`values`](#qiskit.result.Counts.values "qiskit.result.Counts.values")()                                           |                                                                                                                                                                                                                               |

## Attributes

|                   |   |
| ----------------- | - |
| `bitstring_regex` |   |

### clear

<span id="qiskit.result.Counts.clear" />

`clear() → None. Remove all items from D.`

### copy

<span id="qiskit.result.Counts.copy" />

`copy() → a shallow copy of D`

### fromkeys

<span id="qiskit.result.Counts.fromkeys" />

`fromkeys(value=None, /)`

Create a new dictionary with keys from iterable and values set to value.

### get

<span id="qiskit.result.Counts.get" />

`get(key, default=None, /)`

Return the value for key if key is in the dictionary, else default.

### hex\_outcomes

<span id="qiskit.result.Counts.hex_outcomes" />

`hex_outcomes()`

Return a counts dictionary with hexadecimal string keys

**Returns**

**A dictionary with the keys as hexadecimal strings instead of**

bitstrings

**Return type**

dict

**Raises**

**QiskitError** – If the Counts object contains counts for dit strings

### int\_outcomes

<span id="qiskit.result.Counts.int_outcomes" />

`int_outcomes()`

Build a counts dictionary with integer keys instead of count strings

**Returns**

A dictionary with the keys as integers instead of bitstrings

**Return type**

dict

**Raises**

**QiskitError** – If the Counts object contains counts for dit strings

### items

<span id="qiskit.result.Counts.items" />

`items() → a set-like object providing a view on D’s items`

### keys

<span id="qiskit.result.Counts.keys" />

`keys() → a set-like object providing a view on D’s keys`

### most\_frequent

<span id="qiskit.result.Counts.most_frequent" />

`most_frequent()`

Return the most frequent count

**Returns**

The bit string for the most frequent result

**Return type**

str

**Raises**

**QiskitError** – when there is >1 count with the same max counts, or an empty object.

### pop

<span id="qiskit.result.Counts.pop" />

`pop(k[, d]) → v, remove specified key and return the corresponding value.`

If key is not found, d is returned if given, otherwise KeyError is raised

### popitem

<span id="qiskit.result.Counts.popitem" />

`popitem() → (k, v), remove and return some (key, value) pair as a`

2-tuple; but raise KeyError if D is empty.

### setdefault

<span id="qiskit.result.Counts.setdefault" />

`setdefault(key, default=None, /)`

Insert key with a value of default if key is not in the dictionary.

Return the value for key if key is in the dictionary, else default.

### update

<span id="qiskit.result.Counts.update" />

`update([E, ]**F) → None. Update D from dict/iterable E and F.`

If E is present and has a .keys() method, then does: for k in E: D\[k] = E\[k] If E is present and lacks a .keys() method, then does: for k, v in E: D\[k] = v In either case, this is followed by: for k in F: D\[k] = F\[k]

### values

<span id="qiskit.result.Counts.values" />

`values() → an object providing a view on D’s values`

