# How to get the current week number

I google this every single week before I start my writeups. I really should just
use a script that executes the following when I need to create a new doc.

```bash
date +%V
```

Also, for reference:

```go
year, week := time.Now().ISOWeek()
```
