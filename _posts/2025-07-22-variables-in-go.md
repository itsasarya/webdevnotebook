---
layout: post
title: Variables in Go
date: 2025-07-22 22:15 +0530
---

# `var` Keyword

- Are `explicitly` declared and used by compiler
- **`var` keyword**: Used for explicit declaration. You can declare variables with or without initializing them.
- **Shorthand `:=`**: A concise way to declare and initialize a variable in one line. Type is inferred.
- **Multiple variable declaration**: You can declare multiple variables of the same type in one statement.
- **Zero values**: Uninitialized variables are automatically set to their type's zero value (`int` is `0`, `bool` is `false`, `string` is an empty string `""`, etc.).

```go
package main

import "fmt"

func main() {
	var a int = 1       // using var keyword
	b := "b"            // using shorhand notation
	var c, d int = 3, 4 // can declare multiple variable at once
	var e int           // uninitialized variable

	fmt.Println(a)    // outputs : 1
	fmt.Println(b)    // outputs : ba
	fmt.Println(c, d) // outputs : 3 4
	fmt.Println(e)    // outputs : 0
}
```

# `const` Keyword

- Used to defined constants.
- Must be assinged value at the time of declaration.
- Can't use `Shortand syntax :=`

```go

const pi = 3.14
const name string = "Gopher"

// Grouped constant declarations
const (
    a = 1
    b             // b = 1 (same as above)
    c = "hello"
    d             // d = "hello"
)
``
```

## Iota

- Is a special identifier in Go used within `constant` declarations.
- Is reset to 0 whenever a new const block starts.
- It increments by 1 for each line inside the const block.
- You can use it for enumeration, bit masks, etc.

````go
package main

const (
    Monday = iota
    tuesday
    wednesday
)

func main() {
    fmt.Println("Days:", Monday, Tuesday, Wednesday)
}
```# `var` Keyword

- Are `explicitly` declared and used by compiler
- **`var` keyword**: Used for explicit declaration. You can declare variables with or without initializing them.
- **Shorthand `:=`**: A concise way to declare and initialize a variable in one line. Type is inferred.
- **Multiple variable declaration**: You can declare multiple variables of the same type in one statement.
- **Zero values**: Uninitialized variables are automatically set to their type's zero value (`int` is `0`, `bool` is `false`, `string` is an empty string `""`, etc.).

```go
package main

import "fmt"

func main() {
	var a int = 1       // using var keyword
	b := "b"            // using shorhand notation
	var c, d int = 3, 4 // can declare multiple variable at once
	var e int           // uninitialized variable

	fmt.Println(a)    // outputs : 1
	fmt.Println(b)    // outputs : ba
	fmt.Println(c, d) // outputs : 3 4
	fmt.Println(e)    // outputs : 0
}
````

# `const` Keyword

- Used to defined constants.
- Must be assinged value at the time of declaration.
- Can't use `Shortand syntax :=`

```go

const pi = 3.14
const name string = "Gopher"

// Grouped constant declarations
const (
    a = 1
    b             // b = 1 (same as above)
    c = "hello"
    d             // d = "hello"
)
``
```

## Iota

- Is a special identifier in Go used within `constant` declarations.
- Is reset to 0 whenever a new const block starts.
- It increments by 1 for each line inside the const block.
- You can use it for enumeration, bit masks, etc.

```go
package main

const (
    Monday = iota
    tuesday
    wednesday
)

func main() {
    fmt.Println("Days:", Monday, Tuesday, Wednesday)
}
```
