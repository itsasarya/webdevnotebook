---
layout: page
title: Variables
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
	fmt.Println(b)    // outputs : b
	fmt.Println(c, d) // outputs : 3 4
	fmt.Println(e)    // outputs : 0
}
```

# `const` Keyword

- Is used to define constants.
- Must be assigned value at the time of declaration.
- Can't use `Shorthand syntax :=`

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
    Tuesday
    Wednesday
)

func main() {
    fmt.Println("Days:", Monday, Tuesday, Wednesday)
}
```

# Scope and Shadowing

Variable scope in Go determines where a variable is accessible and for how long it exists in memory. Go defines three types of variable scope: block scope, package scope, and global scope.

#### 1. Block Scope

- Variables declared within a function, loop (like `for` loops), or conditional statement (like `if` statements) are said to have block scope.
- These variables are only accessible within the specific block (and any blocks nested within it) where they are declared.

```go
package main

import "fmt"

func main() {
    x := 10 // x is local to main()

    if true {
        y := 20 // y is local to the if block
        fmt.Println(y) // Accessible here
    }

    // fmt.Println(y) // ERROR: y is out of scope here
    fmt.Println(x) // Accessible here
}
```

#### Package Scope

- Variable which are accessible in every part of the package.
- Can't use shorthand declaration in package scope

```go
package main

import "fmt"

var num = 10

func main() {
	fmt.Println(num)
}

```

#### Global Scope

- These are package variables which can span there reach out of the package.
- To export a variable you have to capitalize it

```go
package main

import "fmt"

var SomeVar string = "hello" //global variable

func main(){
    fmt.Println("%d, world", SomeVar)
}
```
