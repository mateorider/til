# Struct vs. Embedded Field Interface Implementation

After reading Bill Kennedy's [article](https://www.ardanlabs.com/blog/2014/05/methods-interfaces-and-embedded-types.html)
on the subject, I learned how the go compiler reacts when it encounters a struct that implements the
same interface that one of its embedded fields also implements. 

The linked article above asks two questions: 1) would the compiler throw an error due to having two
implementations of the interface? and 2) how does the compiler determine which implementation to use
for the interface calls?

Answer to question 1:  *No*. It is perfectly valid go to have a struct and an embedded field on that
struct have methods that implement the same interface.

Answer to question 2: As long as the outer type satisfies the interface, *the compiler will use the
outer struct's implementation over the embedded field's*. 


On a separate note, if the the outer type's method set does not satisfy an interface but it has an
embedded field that does, the implementation of the embedded field can still be accessed via the 
outer type.

See the spec for the exact rules on [method sets](https://golang.org/ref/spec#Method_sets) and
[embedded fields/method set promotion](https://golang.org/ref/spec#Struct_types).

