# Installer Testing Guide
This is a guide for installer testing, feel free to pr to add and improve it!

## Heuristic - ShodsRhuls  <TODO: Find better acronym>

- S - Security: e.g. does it give windows signing errors?
- S - Size: does it include unnecessary files?
- O - OS: test of variety of OSs
- H - High DPI: breaks them every time.
- L - Load: how does the installer perform if the system is under load?
- D - Dependencies: does it handle them gracefully, offer download or auto installs?
- S - Standards: do the files get installed to standard locations, included standard registry locations (if those are a thing)
- H - Help: does it include reasonable help content?
- U - Usability: is the installer a brick to get through?
- L - License: click-through in place? License for dlls and such included?
- R - Run: does the installed application run? Does it run from shortcuts created (if any)?
