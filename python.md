# Python

PEP - Python Enhancement Proposal
Dokumenty vydávan0 a udržvan0 komunitou vývojářů jazyka, které poisují nějaké doporučované
konvence a postupy o tom, jak psát udržitelný kód v pythonu.
[Najdete zde](https://peps.python.org/pep-0008/)

## Styl pojmenování

### snake_case
Malá písmena, slova oddělujeme podtržítkem.
Použití:
funkce, proměnné, metody u třídy, názvy tzv. module (module = jeden soubor s příponou .py)
V Diribetu také používáme pro názvy package, které by podle oficálních doporučení neměly slova oddělovat.


### PascalCase
Každé slovo začíná velkým písmenem, slova se neoddělují. Pužíváme pro názvy tříd.

### SCREAMING_SNAKE_CASE
Používáme výhradně pro proměnné, které zamýšlíme používat jako konstanty - tj. hodnota přiřazená této proměnné se nemění.
Python nám nedává k dispozici jednoduchý způsob jak "zmrazit" proměnnou, tak abychom ji nemohli podruhé přiřadit hodnotu,
i když toho lze dosáhnout, mnohem častěji se jednoduše používá pojmenování velkými písmeny, aby bylo jasné,
že MY_CONSTANT se nebude měnit. Konstanty jsou většinou definovány pro celý package či nějakou scope, kde dávají smysl v
samostatném souboru.

## Struktura repozitáře
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

Soubor requirements.txt obsahuje informace o použitých externích knihovnách a jejich verzích.
Specifická verze `some_package==1.20.1`
`some_package>=1.0,<=2.0`

Používáme virtual environment a tyhle složky pojmenujeme často `env`
[Více info zde](https://docs.python.org/3/library/venv.html)

Data k datovým analýzám dáváme na Google drive. Data typu "vzor" nebo data pro testy softwaru naopak do gitu patří. 


## Importy
To první, co v souboru je. Nejdřív importy standardních knihoven, pak instalované knihovny třetí strany,
pak lokální moduly a package.



## Různé
Explicitni check pro `None`, u proměnných, co nejsou boolean.
`if my_variable is not None:` vs `if not my_variable`







			







