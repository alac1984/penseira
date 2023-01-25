05/01/2023 00:18

Tags: [[VSCode]] [[Vim]]

1. Hit CTRL + SHIFT + P and type `settings.json`
2. Choose the Workspace file and open it
3. Insert the code below somewhere:

```json
{
	"vim.handleKeys": {
		"<C-b>": false,
		"<C-d>": false,
	}
}
```

Every insertion with `false` will remove that combination from Vim extension handling.

---
# References

https://stackoverflow.com/questions/65698293/vim-for-vscode-how-to-disable-key-ctrl-and-ctrl-in-vim-key