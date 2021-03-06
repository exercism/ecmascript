# `typeof`

The `typeof` operator returns a [`string`][type-string] indicating the type of the unevaluated _operand_.

Because JavaScript is a [prototype-based][info-prototype-inheritance] language, the `typeof` operator **can not** be used to determine if an object "inherits" from a certain "class", like the [`is`][csharp-operator-is] operator in [C#][language-csharp], or the [`.is_a?`][ruby-method-is] in [Ruby][language-ruby]. A similar operator exists in JavaScript: [`instanceof`][keyword-instanceof].

## Table with types and results

| `operand` type                               | `typeof` result            |
| -------------------------------------------- | -------------------------- |
| [Undefined][type-undefined]                  | `"undefined"`              |
| [Null][type-null]                            | `"object"` (see below)     |
| [Boolean][type-boolean]                      | `"boolean"`                |
| [Number][type-number]                        | `"number"`                 |
| [BigInt][type-bigint]                        | `"bigint"`                 |
| [String][type-string]                        | `"string"`                 |
| [Symbol][type-symbol]                        | `"symbol"`                 |
| Host object (provided by the JS environment) | _Implementation-dependent_ |
| [Function][type-function] object             | `"function"`               |
| Any other object                             | `"object"`                 |

## Why `null` is `"object"`

```javascript
typeof null;
// => 'object'
```

In the first implementation of JavaScript, JavaScript values were represented
as a type tag and a value. The type tag for objects was 0. [`null`][type-null]
was represented as the NULL [pointer][type-pointer] (`0x00` in most
platforms). Consequently, `null` had 0 as type tag, hence the `"object"`
`typeof` return value. [Read more][ref-null-pointer-typeof].

[info-prototype-inheritance]: ../info/prototype_inheritance.md
[keyword-instanceof]: ./instanceof.md
[language-csharp]: https://github.com/exercism/v3/blob/main/csharp/README.md
[language-ruby]: https://github.com/exercism/v3/blob/main/ruby/README.md
[type-array]: https://github.com/exercism/v3/blob/main/reference/types/array.md
[type-bigint]: https://github.com/exercism/v3/blob/main/reference/types/big_integer.md
[type-boolean]: https://github.com/exercism/v3/blob/main/reference/types/boolean.md
[type-function]: https://github.com/exercism/v3/blob/main/reference/types/function.md
[type-null]: https://github.com/exercism/v3/blob/main/reference/types/null.md
[type-number]: https://github.com/exercism/v3/blob/main/reference/types/number.md
[type-object]: https://github.com/exercism/v3/blob/main/reference/types/object.md
[type-pointer]: https://github.com/exercism/v3/blob/main/reference/types/pointer.md
[type-string]: https://github.com/exercism/v3/blob/main/reference/types/string.md
[type-symbol]: https://github.com/exercism/v3/blob/main/reference/types/symbol.md
[type-undefined]: https://github.com/exercism/v3/blob/main/reference/concepts/undefined.md
[ref-null-pointer-typeof]: https://2ality.com/2013/10/typeof-null.html
[csharp-operator-is]: https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/is
[ruby-method-is]: https://ruby-doc.org/core/Object.html#method-i-is_a-3F
