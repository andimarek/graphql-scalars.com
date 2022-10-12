# Built-in scalars respeced

_Note: This is part of a proposal to clarify scalar implementations, to be discussed at a GraphQL Working Group meeting_

## Int

### Literal Input

`IntValue` literal with the value being between -2<sup>31</sup> (including) and 2<sup>31</sup> (excluding).

### JSON Raw Input

JSON Numbers with `0` decimal with the value being between -2<sup>31</sup> (including) and 2<sup>31</sup> (excluding).

### JSON Result

JSON Numbers with `0` decimal with the value being between -2<sup>31</sup> (including) and 2<sup>31</sup> (excluding).

## String

### Literal Input

`StringValue` literal

### JSON Raw Input

JSON String.

### JSON Result

JSON String.

## Boolean

### Literal Input

`BooleanValue` literal.

### JSON Raw Input

JSON `true` or `false`.

### JSON Result

JSON `true` or `false`.

## ID

### Literal Input

`StringValue` or `IntValue` literal.

### JSON Raw Input

JSON String.

### JSON Result

JSON String.

## Float

### Literal Input

FloatValue literal. See [GraphQL spec](https://spec.graphql.org/draft/#sec-Float-Value)

### JSON Raw Input

The [Float](https://spec.graphql.org/draft/#sec-Float) scalar type represents signed double-precision finite values as specified by [IEEE 754](https://en.wikipedia.org/wiki/IEEE_754).

[JSON Number](https://spec.graphql.org/draft/#sec-Float.Input-Coercion), integers and floats accepted.

Excludes non-finite values such as NaN and Positive/Negative Infinity

Note: JSON Number range can be clarified

* JSON spec appears to heavily recommend IEEE 754 binary64 double precision numbers - the same as the GraphQL spec RFC 8259 - The JavaScript Object Notation (JSON) Data Interchange Format

* However it is not as prescriptive as GraphQL and allows implementations to set limits on the range and precision of numbers accepted

* Follow on point - the JSON serialization clause only specifies that a Float be serialised to a JSON Number. This should be clarified to specifically say IEEE 754 binary64.

### JSON Result

[JSON Number](https://spec.graphql.org/draft/#sec-JSON-Serialization)

Excludes non-finite values such as NaN and Positive/Negative Infinity

