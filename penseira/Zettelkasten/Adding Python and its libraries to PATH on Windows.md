27/01/2023 00:20

Tags: [[Python]] [[Windows]] [[Windows 10]]

1. Look for "environment variables" in Startup search and open "Edit System Environment Variables"
2. Click on Environment Variables button
3. Find PATH variable on the top section (user environment variables) and double click it to open
4. Click on New to add a new PATH
5. Insert this path to add `python` itself to PATH: `C:\Users\username\AppData\Local\Programs\Python\Python31x\`
6. Insert this path to add all installed libraries to PATH: `C:\Users\username\AppData\Local\Programs\Python\Python31X\Scripts\`

All binaries installed with `pip` will get to folder in 6, so adding this path guarantees that you can use them on Powershell. You can check an example on [[Installing Poetry on Windows]]

  ---
# References

[[MeDoingThingsByMyself]]