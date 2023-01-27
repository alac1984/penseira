27/01/2023 00:05

Tags: [[Neovim]] [[Windows]] [[Windows 10]]

To make `plug` install your scripts in Neovim, just add this to `init.vim` file:

```vimscript
call plug#begin()
    Plug 'preservim/nerdtree'
    Plug 'navarasu/onedark.nvim'
call plug#end()
```

In Neovim, just type `:PlugInstall` and all scripts will be installed.

---
# References

https://dev.to/hoo12f/setting-up-neovim-with-windows-powershell-2208