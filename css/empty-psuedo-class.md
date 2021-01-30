# The :empty Psuedo Class
# March 10, 2019

The :empty psuedo class allows youo to select elements that are empty, meaning no characters--including spaces and line breaks.

```html
<style>
  div:empty { /* css rule */ }
</style>

<!— Not empty, won’t match —>
<div> </div>

<!— Not empty, won’t match —>
<div>
</div>

<!— Empty, will match —>
<div></div>
```

This was useful when I needed to highlight an empty table cell.
