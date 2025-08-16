---
layout: page
title: Maps in Go
---

A **map** in Go is an unordered collection of key–value pairs.  
It is similar to a `dict` in Python.

---

## Declaring Maps

```go
// Declare without init (nil map, unusable until initialized)
var m map[string]int

// Declare and init with make
m = make(map[string]int)

// Shorthand (inside functions)
m := make(map[string]int)

// With literal values
m := map[string]int{
    "route": 66,
    "speed": 120,
}
```

## Adding and Updating Values
```go
m := make(map[string]int)

m["route"] = 66       // add new key
m["route"] = 100      // update existing key
m["speed"] = 120      // add another
fmt.Println(m)
// map[route:100 speed:120]
```

## Checking if Key Exists
```go
value, ok := m["route"]
if ok {
    fmt.Println("Found:", value)
} else {
    fmt.Println("Key not found")
}
```
## Deleting Keys

```go
delete(m, "route")
```

## Passing Maps to functions

```go
func addData(m map[string]int, key string, value int) {
    m[key] = value // modifies original map (reference type)
}

func main() {
    m := make(map[string]int)
    addData(m, "Route", 89)
    addData(m, "Highway", 24)
    fmt.Println(m)
    // map[Route:89 Highway:24]
}
```

**Key Points**
- Maps are reference types → passing to functions updates the original.
- Keys must be of a comparable type (string, int, bool, structs without slices/maps/functions).
- Maps are unordered → iteration order is random.
- A nil map can be compared, but not written to.