## Boolean

A datatype which can have one of two states, `True` and `False`. 

## CURIE

Inspired by the [CURIE Syntax 1.0](https://www.w3.org/TR/curie/), the `CURIE`
(compact URL) datatype provides a mechanism [to link
registers](/linked_registers).

CURIEs are of the form `{prefix}:{key}`, where `{prefix}` is mapped to a base
URL `https://{name-of-register}.register.gov.uk/records/`.

## Datetime

A datatype for date- and time-related data which conforms to a subset of
[ISO8601](https://www.iso.org/standard/40874.html). 

The date component is always required.

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

A datatype for base-10 numbers with no fractional components.

The following are valid `Integer` values:

```
100
0
-200
```

Infinity and NaN are invalid.  

## Period

A datatype for periods of time. Conforms to a subset of
[ISO8601](https://www.iso.org/standard/40874.html).

The following are valid `Period` values:

```
2007-03-01T13:00:00Z/2008-05-11T15:30:00Z
2007-03-01T13:00:00Z/P1Y2M10DT2H30M
P1Y2M10DT2H30M/2008-05-11T15:30:00Z
P1Y2M10DT2H30M
```

## String

A datatype for sequences of one or more Unicode characters.

Must be encoded in UTF-8.

Empty strings are invalid.

## Text

A subset of the [`String`](#string) datatype. For sequences of Unicode
characters formatted in Markdown.

## Timestamp

A subset of the [`Datetime`](#datetime) datatype.

The following is a valid `Timestamp` value:

```
2018-07-15T14:38:05Z
```

## URL

A datatype to contain an absolute URL. 
