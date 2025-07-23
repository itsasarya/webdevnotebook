---
layout: page
title: Data Types
---

There three basic types `numeric` `boolean` `string`

## Numeric

- `int`: stores whole numbers without decimals. Can be `+ve` or `-ve`
  - have `5 keywords/ types` of signed integers: **`int`, `int8`, `int16`, `int32`, `int64`**.
- `uint`:unsigned integers store only `+ve` value.
  - have `5 keywords/ types` of unsigned integers: **`uint`, `uint8`, `uint16`, `uint32`, `uint64`.**
- `float`: stores -ve or +ve decimal point numbers.
  - have `two keywords`: `float32`, `float64`

```go
package main

import "fmt"

func main() {
var x int = 10 // Signed integer
var y uint = 5 // Unsigned integer
var z float32 = 3.14 // Float with decimal

    fmt.Println(x)         // outputs: 10
    fmt.Println(y)         // outputs: 5
    fmt.Println(z)         // outputs: 3.14

}
```

---

## Boolean

Represents `bool` value its either `true` or `false`

```go
package main

import "fmt"

func main() {
	a := true
	b := false
	fmt.Println(a) // outputs: True
	fmt.Println(b) // outputs: false
}
```

---

## String

Used to stores `text` value and must enclosed within double qoutes `"`.

```go
package main

import "fmt"

func main() {
	a := "data types"
	b := "Hello"
	fmt.Println(a) // outputs: data types
	fmt.Println(b) // outputs: Hello
}
```
