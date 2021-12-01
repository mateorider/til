# Syntax for bash sub functions

Usually, bash functions are defined using `{}` to wrap the body, like so:
```bash
function_name() {
  # code
}
```

If you use `()` to wrap the function body instead, the function will execute __within a subshell__.

Variables in the function are lexically-scoped (basically how you would expect function-local variables to work in other languages)

Source: [Bash functions are better than I thought](https://cuddly-octo-palm-tree.com/posts/2021-10-31-better-bash-functions/?utm_source=Pointer&utm_campaign=4580adccb4-ISSUE_265&utm_medium=email&utm_term=0_6ba2b83261-4580adccb4-608318342)
