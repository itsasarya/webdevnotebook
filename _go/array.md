---
layout: page
title: Array & Slice
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

# Slice

A **slice** is a flexible, dynamically-sized view into the elements of an array.  
Unlike arrays, slices **do not have a fixed size** and can grow or shrink as needed.

> A slice does not store data itself — it’s a reference to a segment of an underlying array.

---

## Declaring a Slice

```go
var sliceName []dataType                // nil slice
sliceName := []dataType{values}         // with values
sliceName = make([]dataType, length)    // length with zero values
sliceName = make([]dataType, length, cap) // length and capacity
```

**Creating a Slice from an Array**

```go
arr := [5]int{1, 2, 3, 4, 5}
slice := arr[1:4] // from index 1 to 3 (excludes index 4)
```

**Length and Capacity**

```go
fmt.Println(len(slice)) // number of elements in slice
fmt.Println(cap(slice)) // number of elements from start index to end of underlying array
```

## Common Operation

**Append Elements**

```go
slice = append(slice, 6, 7, 8)
```

**Copy Slices**

```go
dst := make([]int, len(slice))
copy(dst, slice)
```

**Delete Element**

```go
// remove element at index i
slice = append(slice[:i], slice[i+1:]...)
```

**Insert Element**

```go
// insert value x at index i
slice = append(slice[:i], append([]T{x}, slice[i:]...)...)
```
