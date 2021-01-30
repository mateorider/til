# Calculate the Sum from 0..n Without a Loop
## June 4, 2019

Instead of looping, adding each iteration to the sum, you can do it by simply multiplying n by n+1 then dividing that result by 2.

```golang
func sum0to(n int) int {
	return n * (n+1) / 2
}

sum0to(3) // 3 * (3+1) / 2 = 6
sum0to(10) // 10 * (10+1) / 2 = 55
```
