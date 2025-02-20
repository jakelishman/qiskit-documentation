---
title: RuntimeDecoder
description: API reference for qiskit.providers.ibmq.runtime.RuntimeDecoder
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.ibmq.runtime.RuntimeDecoder
---

# qiskit.providers.ibmq.runtime.RuntimeDecoder

<span id="qiskit.providers.ibmq.runtime.RuntimeDecoder" />

`RuntimeDecoder(*args, **kwargs)`[GitHub](https://github.com/qiskit/qiskit-ibmq-provider/tree/stable/0.15/qiskit/providers/ibmq/runtime/utils.py "view source code")

JSON Decoder used by runtime service.

`object_hook`, if specified, will be called with the result of every JSON object decoded and its return value will be used in place of the given `dict`. This can be used to provide custom deserializations (e.g. to support JSON-RPC class hinting).

`object_pairs_hook`, if specified will be called with the result of every JSON object decoded with an ordered list of pairs. The return value of `object_pairs_hook` will be used instead of the `dict`. This feature can be used to implement custom decoders. If `object_hook` is also defined, the `object_pairs_hook` takes priority.

`parse_float`, if specified, will be called with the string of every JSON float to be decoded. By default this is equivalent to float(num\_str). This can be used to use another datatype or parser for JSON floats (e.g. decimal.Decimal).

`parse_int`, if specified, will be called with the string of every JSON int to be decoded. By default this is equivalent to int(num\_str). This can be used to use another datatype or parser for JSON integers (e.g. float).

`parse_constant`, if specified, will be called with one of the following strings: -Infinity, Infinity, NaN. This can be used to raise an exception if invalid JSON numbers are encountered.

If `strict` is false (true is the default), then control characters will be allowed inside strings. Control characters in this context are those with character codes in the 0-31 range, including `'\t'` (tab), `'\n'`, `'\r'` and `'\0'`.

### \_\_init\_\_

<span id="qiskit.providers.ibmq.runtime.RuntimeDecoder.__init__" />

`__init__(*args, **kwargs)`

`object_hook`, if specified, will be called with the result of every JSON object decoded and its return value will be used in place of the given `dict`. This can be used to provide custom deserializations (e.g. to support JSON-RPC class hinting).

`object_pairs_hook`, if specified will be called with the result of every JSON object decoded with an ordered list of pairs. The return value of `object_pairs_hook` will be used instead of the `dict`. This feature can be used to implement custom decoders. If `object_hook` is also defined, the `object_pairs_hook` takes priority.

`parse_float`, if specified, will be called with the string of every JSON float to be decoded. By default this is equivalent to float(num\_str). This can be used to use another datatype or parser for JSON floats (e.g. decimal.Decimal).

`parse_int`, if specified, will be called with the string of every JSON int to be decoded. By default this is equivalent to int(num\_str). This can be used to use another datatype or parser for JSON integers (e.g. float).

`parse_constant`, if specified, will be called with one of the following strings: -Infinity, Infinity, NaN. This can be used to raise an exception if invalid JSON numbers are encountered.

If `strict` is false (true is the default), then control characters will be allowed inside strings. Control characters in this context are those with character codes in the 0-31 range, including `'\t'` (tab), `'\n'`, `'\r'` and `'\0'`.

## Methods

|                                                                                                                                                  |                                                                                                                                                                           |
| ------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.providers.ibmq.runtime.RuntimeDecoder.__init__ "qiskit.providers.ibmq.runtime.RuntimeDecoder.__init__")(\*args, \*\*kwargs) | `object_hook`, if specified, will be called with the result of every JSON object decoded and its return value will be used in place of the given `dict`.                  |
| [`decode`](#qiskit.providers.ibmq.runtime.RuntimeDecoder.decode "qiskit.providers.ibmq.runtime.RuntimeDecoder.decode")(s\[, \_w])                | Return the Python representation of `s` (a `str` instance containing a JSON document).                                                                                    |
| [`object_hook`](#qiskit.providers.ibmq.runtime.RuntimeDecoder.object_hook "qiskit.providers.ibmq.runtime.RuntimeDecoder.object_hook")(obj)       | Called to decode object.                                                                                                                                                  |
| [`raw_decode`](#qiskit.providers.ibmq.runtime.RuntimeDecoder.raw_decode "qiskit.providers.ibmq.runtime.RuntimeDecoder.raw_decode")(s\[, idx])    | Decode a JSON document from `s` (a `str` beginning with a JSON document) and return a 2-tuple of the Python representation and the index in `s` where the document ended. |

### decode

<span id="qiskit.providers.ibmq.runtime.RuntimeDecoder.decode" />

`decode(s, _w=<built-in method match of re.Pattern object>)`

Return the Python representation of `s` (a `str` instance containing a JSON document).

### object\_hook

<span id="qiskit.providers.ibmq.runtime.RuntimeDecoder.object_hook" />

`object_hook(obj)`

Called to decode object.

**Return type**

`Any`

### raw\_decode

<span id="qiskit.providers.ibmq.runtime.RuntimeDecoder.raw_decode" />

`raw_decode(s, idx=0)`

Decode a JSON document from `s` (a `str` beginning with a JSON document) and return a 2-tuple of the Python representation and the index in `s` where the document ended.

This can be used to decode a JSON document from a string that may have extraneous data at the end.

