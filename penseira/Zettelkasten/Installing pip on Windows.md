27/01/2023 00:30

Tags: [[Windows 10]] [[Windows]] [[Python]] [[Powershell]]

1. Install Python as in [[Installing Python on Windows]]
2. Add Python to PATH as in [[Adding Python and its libraries to PATH on Windows]]
3. Add `curl` on Windows as in [[Installing curl on Windows]]
4. Execute this command on Powershell:

```powershell
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
```

5. Run `get-pip.py` with the command: `python get-pip.py`
6. `pip` will be installed in `Scripts` folder as referenced in [[Adding Python and its libraries to PATH on Windows]], so this folder need to be on PATH for Powershell find `pip` command.

---
# References

https://www.geeksforgeeks.org/how-to-install-pip-on-windows/