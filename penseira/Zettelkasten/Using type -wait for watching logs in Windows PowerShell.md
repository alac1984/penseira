12/01/2023 22:55

Status:

Tags:

If you need to watch a log in Windows, you can open PowerShell and type:

```powershell
type -wait C:\path\to\log\file.log
```

The command works exactly as Linux infamous  `tail -f`: it starts to watch change in the specified file on terminal.

---
# References

https://stackoverflow.com/questions/41722827/use-powershells-type-wait-with-select-string-to-real-time-monitor-an-applicati