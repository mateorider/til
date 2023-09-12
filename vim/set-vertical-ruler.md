# Set a Vertical Ruler (kind of)

The easiest way I've found to create a pseudo vertical ruler is to use the 
`:set colorcolumn` command.

`:set colorcolumn=80` will highlight the every line's 80th position.

You can also set multiple by passing in a comma-separated list of numbers, eg:
`:set colorcolumn=80,120,160`

You can also use `cc` as the abbreviation.

Want to remove the highlighted column(s)? Run `:set cc=`

See `:help colorcolumn`
