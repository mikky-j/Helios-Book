# Structs and Enums

## Structs

Structs in Helios are a named grouping of types.
They are also known as *product types*.
They are similar to structs in other languages like Rust.

```rust, noplaypen
// Rational (fractional type)
struct Rational {
    top: Int,
    bottom: Int,
}

// Instantiating a struct
x: Rational = Rational { top: 1, bottom: 3 }
```

## Enums

Enums are used to represent types that have multiple variants.
Enums are also known as `sum types`.
They're useful for datums and redeemers with differing content.

```go, noplaypen
enum FanSetting {
    On{ speed: Int },
    Off{}
}
```

### The `switch` expression 

The `switch` expression is used to pattern-match on enum variants.

```rust, noplaypen
enum Datum {
    Submission{...}, // content of Submission has the same syntax as a regular struct-type
    Queue{...},
    Post{...}
}

switch (expr) {
    case (x: Datum::Submission) { // double-colon to reference the sub-type
        ... // expression must use x
    },
    case Datum::Queue {
        ... // x not used, so can't be declared
    },
    default { // default must come last if all sub-types of Datum aren't handled explicitely
        true
    }
}

```
