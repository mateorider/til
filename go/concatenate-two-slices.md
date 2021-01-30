# How to Concatenate Two Slices

Because `append` is a *variadic* function you have to add the three dots in the second argument.

```golang
append([]int{1,2}, []int{3,4}) // doesn't work. Will return "cannot use []int literal (type []int) as type int in append"

append([]int{1,2}, []int{3,4}) // Works!
```
