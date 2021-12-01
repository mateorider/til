# How to Change Directories as You Navigate

tl;dr `:set autochdir`

I created a zsh alias `til` which opens this repository's root directory in vim mode so I can quickly write what I learn into an md file.

The annoying part was that once I navigated to the correct sub directory, the vim working directory will still pointing to whereever I entered
the `til` command from. That meant I would need to clumsily remember the path to the directory I wanted to create the new md file in.

The quick and easy soltuion to this is `:set autochdir`, which I put in my .vimrc. Now whenever I change directiories in while navigating in vim
the working directory will change with me, meaning I can use `:e filename` without having to recall the path.
