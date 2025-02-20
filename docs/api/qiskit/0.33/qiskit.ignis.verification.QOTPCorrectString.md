---
title: QOTPCorrectString
description: API reference for qiskit.ignis.verification.QOTPCorrectString
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.ignis.verification.QOTPCorrectString
---

# qiskit.ignis.verification.QOTPCorrectString

<span id="qiskit.ignis.verification.QOTPCorrectString" />

`QOTPCorrectString(qotp_string, qotp_postp)`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.7/qiskit/ignis/verification/accreditation/qotp.py "view source code")

Corrects a measurement string, shifting the qotp

**Parameters**

*   **qotp\_string** (*str*) – a measurement output string
*   **qotp\_postp** (*list*) – a binary list denoting the one time pad

**Returns**

the corrected counts dict

**Return type**

dict

