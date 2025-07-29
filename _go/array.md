---
layout: page
title: Array
---

A collection of elements of the same type with a fixed size stored in contiguous memory locations.
The `[n]T` is an array of `n` values of type `T`.

# Declare an Array

- with `var` keyword

```go
var arrayName = [length]dataType{values} // length is defined
var arrayName = [...]dataType{values} // length is inferred
```

- with `:=` sign

```go
arrayName := [length]dataType{values} // length is defined
arrayName := [...]dataType{values} // length is inferred
```

# Accessing Element

To access an element in an array `arrayName[index]`.

```go
package main

import "fmt"

func main() {
	var arr = [5]int{1, 2, 3, 4, 5}
    fmt.Println(arr[0]) // outputs: 1
}
```

# Changing Element

To change an element in an array `arrayName[index] = newValue`.

```go
package main

import "fmt"

func main() {
	var arr = [5]int{1, 2, 3, 4, 5}
    arr[0] = 10
    fmt.Println(arr[0]) // outputs: 10
}
```

# Array Length

To get the length of an array `len(arrayName)`.

```go
package main

import "fmt"

func main() {
	var arr = [5]int{1, 2, 3, 4, 5}
    var arr2 = [...]int{1, 2, 3, 4, 5,6,7,8,9}

    println(len(arr)) // outputs: 5
    println(len(arr2)) // outputs: 9
}
```
