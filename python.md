# Python

PEP - Python Enhancement Proposal<br>
Documents written by community of python language developers describing recommended conventions about writing
maintainable python code. 
[Source here](https://peps.python.org/pep-0008/)

1. [Installing Python](#installing-python) 
2. [Using `pip`](#using-pip) - installing 3rd party packages
3. [Python project setup](#project-setup)
    - repository structure
    - virtual environments & dependencies
4. Jupyter notebooks 
5. [Naming style](#naming-style) 


## Installing Python
[Official downloads page](https://www.python.org/downloads/)

Custom installation
- pip
- python test suite
- create shortcuts for applications
- debugging symbols and debug binaries
- ! customize install location
  choose something simple like C:\python, C:\python310, C:\pythons\py37, C:\pythons\py310

If you install python into a folder at `C:\python`, you will have to put this path into the Path environment variable.
Path is just a list of paths to executable files you want to run easily without having to specify the full path to
the executable that actually starts your application. For example, you can open up the command prompt and type 
`notepad.exe` to run the notepad program because by default `notepad.exe` (stored at `C:\Windows` for example)
which is included in the Path environment variable. Notepad.exe runs a GUI program, python.exe runs a CLI program, that 
executes your python scripts (`.py` files).

The python installer offers to modify the Path variable for you. If you want to use multiple versions of python,
you can rename the installation directory and the `.exe` file to some appropriate name e.g. `python310.exe`,
`python38.exe`.

Note: Everytime the environment variables are changed, you need to open a new cmd prompt to see the changes.

## Using pip
pip = package installer for python.
Example usage:
- install latest version of numpy package: `python -m pip install numpy`
- check that numpy is installed, show information about it: `python -m pip show numpy`
- remove numpy: `python -m pip uninstall numpy`

`-m` flag = run standard library module as a script. This syntax may seem more verbose, but it's clearly visible which python
interpreter is used. So if I had a folder `C:\python310` (added to Path) containing `python310.exe`,
I could call `python310 -m pip [...]`.

## Project setup

### Repository structure
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

`requirements.txt` file contains information about 3rd party libraries and their versions used in the project.
Specific version: `some_package==1.20.1`
Range: `some_package>=1.0,<=2.0`

### Virtual environment
Part of the python standard library is a package called `venv`: [docs](https://docs.python.org/3/library/venv.html)
<br>
To create a virtual environment:
```
python -m venv my_environment
```
This creates a new directory structure with the root folder called `my_environment`. The goal is to create a lightweight
isolated environment where you can install packages that won't conflict with the globally installed packages.
Three key components:
1. copy of the python executable
   <br> (this is NOT 'the whole python' it's just a copy of the `.exe`
   file that runs the whole python program)
2. `pyenv.cfg` file <br>
   Config file for this environment. <br>
   Simple key = value definitions:
    ```
    home = C:\python310
    include-system-site-packages = false
    version = 3.10.4
    ```
   The `home` settings point to the base python interpreter used in this environment. The standard library modules are
   taken from there.
3. `site-packages` directory <br> The packages specific to this environment.

To activate the environment called `my_environment`, open cmd in the folder where it's located and:
```
call my_environment/scripts/activate.bat
```

Among other things, the activation means that it puts whatever `.exe` is in the `scripts` folder to the beginning of Path.
So if you used `python310.exe` to create this environment, and the `pyenv.cfq` file contains path to this file, you can
rename the `scripts/python310.exe` to `scripts/python.exe` for convenience because what matters is the path under `home`
in `pyenv.cfg`.

Note: To see what is in Path in cmd: `echo %PATH%`.

#### Note on IntelliJ
File -> Project Structure -> Project Settings
This is where you configure the SDK (general term meaning Software Development Kit) this is either a virtual environment 
or the global interpreter. 

## Naming style

### snake_case
Lowercase letters, words are separated by underscore.
Usage: functions, variables, methods, names of modules (module = file with `.py` extension)
Special in Diribet - also used for package names even though official recommendation is something like `mypackage`
instead of `my_package`.

### PascalCase
Each word is capitalized, words are not separated. Use when naming classes.

### SCREAMING_SNAKE_CASE
Use exclusively for variables that are intended to be constants. The value assigned to this variable
does not change. Python doesn't provide an easy way to "freeze" a variable, it is possible though usually we rely on
the naming style. Constants are usually declared in a specific file named 'constants'.


## Miscellaneous
**Imports** <br>
At the top of the file, first standard library imports, then 3rd party packages, and then your local modules.

**Data for analysis** <br>
Shared on Google drive. Data that represent a sample (typically sample of a json request for web servers) or data for testing the software
are included in the repository.

**None as a falsy value**<br>
Explicit check for `None` for variables that are not boolean.
`if my_variable is not None:` vs `if not my_variable`







			







