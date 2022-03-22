# Python

[PEP 8](https://peps.python.org/pep-0008/) (Python Enhancement Proposal) describes recommended conventions about writing
maintainable Python code. 

## Formatting

Formatting should follow PEP 8 Style Guide

### Imports
At the top of the file, first standard library imports, then 3rd party packages, and then your local modules.

### Miscellaneous
You should use explicit check for `None`.
```python
if my_variable is not None:  # Good
```

```python
if not my_variable:  # Bad
```

## Naming

### snake_case
Lowercase letters, words are separated by an underscore.

Usage: functions, variables, methods, names of modules (module = file with `.py` extension)

Special in Diribet - also used for package names even though the official recommendation is something like `mypackage`
instead of `my_package`.

### PascalCase
Each word is capitalized, words are not separated. 

Usage: class names

### SCREAMING_SNAKE_CASE
Use exclusively for variables that are intended to be constants. The value assigned to this variable
does not change. Python doesn't provide an easy way to "freeze" a variable, it is possible though usually, we rely on
the naming style.

## Project structure
```
.
+-- .gitignore
+-- README.md
+-- src
|   +-- main.py
+-- tests
|	+-- unit
|	|   +-- main_test.py
+-- samples
|   +-- sample_request.json
+-- requirements.txt
+-- env
```

### Project dependencies
Project dependencies (3rd party libraries) should be listed in `requirements.txt` file. 
This file can be used by any developer to install the required libraries in their environment. 
[Details here](https://pip.pypa.io/en/stable/user_guide/#requirements-files) 

You can specify version of the dependency as:
 * Specific version: `some_package==1.20.1`
 * Range: `some_package>=1.0,<=2.0`

### Virtual environment
We use virtual environments for each project to isolate their environments.
The folder containing the virtual environment is usually called `env`
[More information here](https://docs.python.org/3/library/venv.html)

### Data for analysis 
Data for analysis must not be pushed to Git. They should be stored on Google Drive.
Data that represent a sample (typically s sample of a JSON request for web servers) or data for tests
should be included in the repository. 
