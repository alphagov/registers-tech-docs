## CURIE

Inspired by the [CURIE Syntax 1.0](https://www.w3.org/TR/curie/), the CURIE
(compact URL) datatype provides a mechanism [to link
registers](/linked_registers).

CURIEs are of the form `{prefix}:{key}`, where `{prefix}` is mapped to a base
URL `https://{name-of-register}.register.gov.uk/records/`.

## Datetime

A datatype for date- and time-related data which conforms to a subset of
[ISO8601](https://www.iso.org/standard/40874.html). The date component is always required.

The following are valid `Datetime` values:

```
2001
2001-01
2001-01-31
2018-10-11T12Z
2018-10-11T12:14Z
2001-01-31T23:20:55Z
```

## Integer

A base 10 number with no fractional component.

integer = "0" / (["-"] non-zero *digit)
digit =  "0" / positive-digit
non-zero =  "1" / "2" / "3" / "4" / "5" / "6" / "7" / "8" / "9"
Leading zeros are not allowed, except for the integer 0, which is represented as the string 0. Negative values are marked with a leading “-” character (UNICODE 0x2D HYPHEN-MINUS).

Numeric values such as Infinity and NaN are not permitted.

