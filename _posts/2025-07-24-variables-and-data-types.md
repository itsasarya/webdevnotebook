---
layout: post
title: Variables and Data Types in Golang
date: 2025-07-24 20:24 +0530
---

## Variables

Variables are named containers used to store data in a program. In Go, they are declared using the `var` and `const` keywords.

- `var`: Used to declare variables that can be reassigned to new values later in the program.

- `const`: Used to declare constants whose values cannot be changed once defined.

Variables declared using `var` can either use the keyword itself or the shorthand `:= `syntax (within functions). Constants, declared with `const`, must be initialized at declaration and cannot use shorthand syntax.

```go
package main

import "fmt"

// Global scope variables
var a int = 0           // initialized variable
var b int               // uninitialized (defaults to 0)

func main() {
    c := "shorthand syntax" // shorthand only works inside functions
    const pi = 3.14         // constant must be initialized at declaration
    fmt.Println(a, b, c, pi)
}

```

> Uninitialized variables receive their type's zero value by default (e.g., 0, "", false)

## Data Types

Go provides three primary categories of data types:

### Numeric Types

- **Integers**:  
  Signed: `int`, `int8`, `int16`, `int32`, `int64`  
  Unsigned: `uint`, `uint8`, `uint16`, `uint32`, `uint64`

- **Floating-point**: `float32`, `float64`

- **Complex numbers**: `complex64`, `complex128`

### String Type

- A string is an immutable sequence of bytes, typically UTF-8 encoded.

### Boolean Type

- Represents truth values: `true` or `false`

> Quick Notes
>
> - [Variables]({% link _go/variables.md %})
> - [Data Types]({% link _go/datatype.md %})
