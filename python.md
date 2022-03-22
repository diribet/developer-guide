# Python

PEP - Python Enhancement Proposal
Documents written by community of python language developers describing recommended conventions about writing
maintainable python code. 
[Source here](https://peps.python.org/pep-0008/)

## Naming style

### snake_case
Lowercase letters, words are separated by underscore.
Usage: functions, variables, methods, names of modules (module = file with `.py` extension)
Special in Diribet - also used for package names even though official recommendation is something like `mypackage`
instead of `my_package`.

### PascalCase
Each word is capitalized, words are not separated. Use when naming classes.

### SCREAMING_SNAKE_CASE
Use exclusively for variables that you intend to use as constants. That is value assigned to this variable
does not change. Python doesn't provide an easy way to "freeze" a variable, it is possible though, usually we rely on
the naming style. Constants are usually declared in a specific file named 'constants'.

## Repository structure
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

`requirements.txt` file contains information about 3rd party libraries ans their versions used in the project.
Specific version: `some_package==1.20.1`
Range: `some_package>=1.0,<=2.0`

We use virtual environments for each project and they're often just called `env`
[More information here](https://docs.python.org/3/library/venv.html)

Data for analysis is shared on Google drive.
Data that represent a sample (typically sample of a json request for web servers) or data for testing the software
are included in the repository. 


## Imports
At the top of the file, first standard library imports, then 3rd party packages and then your local modules.

## Miscellaneous 
Explicit check for `None` for variables that are not boolean.
`if my_variable is not None:` vs `if not my_variable`







			







