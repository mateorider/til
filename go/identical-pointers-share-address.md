# Identical Pointers Will Share the Same Memory Address

If you declare two variables with identical content and print pointers to them, they will print the same memory address.

```golang
package main

import (
	"fmt"
)

type Book struct {
	Title string
}

func main() {

	a := Book{
		Title: "Red Rising",
	}
	b := Book{
		Title: "Red Rising",
	}
	fmt.Printf("%x\n", &a) // &{52656420526973696e67}
	fmt.Printf("%x\n", &b) // &{52656420526973696e67}
}
```

However, once you modify the content of one of the variable's contents, their memory addresses will differ.

```golang
package main

import (
	"fmt"
)

type Book struct {
	Title string
}

func main() {

	a := Book{
		Title: "Red Rising",
	}
	b := Book{
		Title: "Red Rising",
	}
	fmt.Printf("%x\n", &a) // &{52656420526973696e67}
	fmt.Printf("%x\n", &b) // &{52656420526973696e67}

	b.Title = "Golden Son"
	fmt.Printf("%x\n", &a) // &{52656420526973696e67}
	fmt.Printf("%x\n", &b) // &{476f6c64656e20536f6e}
}
```

