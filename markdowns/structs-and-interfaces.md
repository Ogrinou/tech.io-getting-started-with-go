Structs and Interfaces
===

We can use **structs** to group one of more fields of logical types together. For example we could represent a
Point struct as:

```go
type Point struct {
  x int
  y int
}
```

Then in order to use it we need to initialize it. There are 3 ways to initialize a struct in Go.

```go
var c Point
```
This will create a local Point variable that is by default set to zero. 

You can also initialize using the shorthand notation:

```go
c := new(Circle) // use of new keyword
```

This allocates memory for all the fields, sets each of them to their zero value and returns a pointer. (*Circle)

If you would like to initialize the fields with a different value you can do it like that:

```go
c := Point{x: 1 , y: 2}
```

Fields and Methods
===


Interfaces
===

Go supports interfaces in a different way that other programming languages like Java do.
Like a struct an interface is created using the `type` keyword, followed by a name and the keyword `interface`:

```go
type Shape interface {
  area() float64
}
```

Now in order to "implement" this interface, a type must implement the interface methods defined. For example:

```go
type Shape interface {
  area() float64
}

type Square struct {
  x1, y1, x2, y2 float64
}

func (s *Square) area() float64 {
  l := distance(r.x1, r.y1, r.x2, r.y2) // calculate distance between 2 points
  return l * l
}
```
And we can use it like that:

```go
s := Square{0, 0, 5, 5}
fmt.Println(s.area()) // 25
```

