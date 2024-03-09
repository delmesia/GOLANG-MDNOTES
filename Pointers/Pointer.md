# A quick introduction to Pointers
A **_pointer_** is a variable that holds the location in memory where a value is stored.

```Go
var x int32 = 5
var y  bool = true
```
Every variable is stored in one or more contigous memory location called **_addresses_**. Different types of variable take up different amount of space in memory. For example, a 32-bit integer requires four bytes to be stored, while a boolean value only requires a single byte (a Boolean value only need a bit to represent **true** or **false**)
>[!NOTE]
> The smallest amount of memory the can independently be addressed is a _byte_
```Go
// Storing two variables in memory
var x int32 = 100
var y bool = false
// pointerX will store the address of X
pointerX := &x
// pointerY will store the address of Y
pointerY := &y 
var pointerZ *string
```
## Size of a pointer type
There are different types of variable, and it can also take different numbers of memory locations depending on the variable size, however, a pointer, no matter what type it points to, is always the same number of memory locations.
>[!NOTE]
> Many modern computers use 8 bytes for a pointer.

The **zero** value for a pointer is _nil_. In Go, _nil_ is also the zero value for slices, maps, and functions since all these types are created with pointers.
>[!CAUTION]
>_nil_ value can be shadowed. Never name a variable or a function _nil_

The **&** is the address operator. It  precedes a value type and retruns the address where the value is stored:

```Go
x := "hello, world!"
pointerToX := &x // pointerToX now contain the address of x
```
The * is the indirection operator. It precedes a variable of pointer type and returns the pointed-to value. This is called dereferencing:

```Go
x := 100
fmt.Println(pointertToX) // this will print a memory address
fmt.Println(*pointerToX) // this will print the value 100
z := 10 + *pointerToX
fmt.Println(z)           //this will print the value 110
```
Before dereferencing a pointer, the pointer needs to be _non-nil_. The program will panic if _nil_ pointer has been dereferenced.

