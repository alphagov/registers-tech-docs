## Boolean

For values which are either "true" or "false". 

## CURIE

[For linked registers](/linked_registers). Inspired by the [CURIE Syntax
1.0](https://www.w3.org/TR/curie/).

In its string representation, the CURIE datatype is of the form
`{prefix}:{key}`.  `{prefix}` is mapped to a base URL
`https://{name-of-register}.register.gov.uk/records/` and `{key}` is a unique
UTF-8 string which identifies something in a register.

## Datetime

For date- and time-related data. 

The following are valid `Datetime` values:

```
2001
2001-01
2001-01-31
2018-10-11T12Z
2018-10-11T12:14Z
2001-01-31T23:20:55Z
```

The date component is always required.

## Integer

For base-10 numbers with no fractional components.

The following are valid `Integer` values:

```
100
0
-200
```

Infinity and NaN are invalid.  

## Period

For periods of time. 

The following are valid `Period` values:

```
2007-03-01T13:00:00Z/2008-05-11T15:30:00Z
2007-03-01T13:00:00Z/P1Y2M10DT2H30M
P1Y2M10DT2H30M/2008-05-11T15:30:00Z
P1Y2M10DT2H30M
```

## String

For UTF-8 strings.  

## Text

For UTF-8 strings formatted in Markdown. A subset of the [`String`](#string)
datatype. 

## Timestamp

For records of particular times. A subset of the [`Datetime`](#datetime) datatype.

The following is a valid `Timestamp` value:

```
2018-07-15T14:38:05Z
```

## URL

For absolute URLs. 
