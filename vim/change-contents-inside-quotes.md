# Change the Contents Inside Quotes
## January 15, 2021

Today I copied an error check and wanted to change the error message string. 

```golang
if err != nil {
    return errors.New("need to change this string")
}
```

Go to the open quote, run `ci"` and change the string's contents :)

Helpful link: https://stackoverflow.com/questions/2147875/what-vim-commands-can-be-used-to-quote-unquote-words
