26/01/2023 23:44

Tags: [[Windows]] [[Windows 10]] [[Neovim]] [[Powershell]]

1. In Powershell, install neovim with `scoop`: `scoop install neovim`
2. Create a `init.vim` folder as described in [[Neovim folders on Windows]]
3. To set up `plug`, you can use this command:

```powershell

iwr -useb https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim |` 
	ni "$(@($env:XDG_DATA_HOME, $env:LOCALAPPDATA)[$null -eq $env:XDG_DA
```

It will download `plug.vim` to `C:\Users\username\AppData\Local\nvim-data\site\autoload` . For now on, `plug` functions are loaded in Neovim when it opens.

4. You can set up `plug` as in [[Setting up plug in init.vim]]
 
---
# References

https://dev.to/hoo12f/setting-up-neovim-with-windows-powershell-2208
